---
layout: post
title: "La máquina Enigma en Python"
tags:
  - Spanish
  - Algebra
  - Python
---

Vamos a simular la máquina Enigma usando Python. Para empezar, vamos a simplificar la máquina como una serie de permutaciones que nos envían letras del alfabeto a otras letras. Vamos a escribirlas usando la notación usual donde, por ejemplo, la permutación que nos lleva una letra a la siguiente será:

$$
\begin{pmatrix}
  abcdefghijklmnopqrstuvwxyz \\
  bcdefghijklmnopqrstuvwxyza
\end{pmatrix}
$$

Y, en Python, esto lo representaremos solo como la segunda fila, por tanto, necesitaremos alguna función auxiliar para llevar esto:

```py
def letra_a_num(a):
  return ord(a.upper())-ord("A")
def num_a_letra(a):
  return "ABCDEFGHIJKLMNOPQRSTUVWXYZ"[a]
```

Esto lo usaremos para pasar letras a números, y así poder buscarlas en nuestras cadenas que usaremos para representar las permutaciones.

## Configuración de los rotores

La máquina que estamos emulando es el modelo E-Eins, o sea, la primera de uso militar. Esta máquina tiene tres rotores, a elegir entre cinco. Estos rotores se sitúan entre los contactos de entrada/salida y el llamado reflector (que en esta máquina es uno entre dos).

Cuando pulsamos una tecla del teclado de la máquina, el rotor de la derecha gira una posición, y después se cierra un circuito que pasa por cada disco, luego vuelve por el reflector (que es otra permutación) para luego volver por los rotores y llegar a una bombilla asignada a una letra, que será la letra cifrada.

Por tanto, necesitamos una manera de simular el giro de los rotores, aquí es donde entrará la siguiente función, la cual cicla las letras de la permutación y luego les asigna la letra anterior:

```py
def cicla_permuta(perm, n=1):
  for _ in range(0,n):
    perm = perm[1:]+str(perm[0])
    perm = "".join([num_a_letra((letra_a_num(i)-1)%26) for i in perm])
  return perm
```
Así como una función que nos de la imagen de una letra por una permutación:

```py
def permuta(perm, direc, a):
    if direc == 1:
        return perm[letra_a_num(a)]
    else:
        return num_a_letra(perm.index(a))
```

Esto nos permite tomar la imagen tanto de la permutación como de su inversa.

Por último, cada rotor tiene dos configuraciones, la llamada configuración interna (Ringstellung), que es un desfase del disco indicador del rotor con respecto al cableado interno y la configuración externa (Grundstellung) que es el desfase del rotor una vez introducido. A su vez, cada rotor tiene un punto llamado el turnover, cuando un disco gira pasado su punto de turnover, girará el siguiente. Para modelizarlo en Python, usaremos la siguiente clase:

```py
class Rotor:
    def __init__(self, to, perm):
        self.rs = 0 # Ringstellung
        self.gs = 0 # Grundstellung
        self.perm_init = perm
        self.to = to # Donde se hace el turnover
        self.perm = perm # Permutación del anillo
        self.isTurnover = False # Si se tiene o no que hacer turnover
    def set_rs(self, rs):
        self.rs = rs
        self.perm = cicla_permuta(self.perm, -rs%26)
    def set_gs(self, gs):
        self.gs = gs
        self.perm = cicla_permuta(self.perm_init, gs)
    def permuta_ida(self, a):
        return permuta(self.perm, 1, a)
    def permuta_vuelta(self, a):
        return permuta(self.perm, 0, a)
    def turn(self):
        self.gs = (self.gs + 1) % 26
        self.perm = cicla_permuta(self.perm)#, 25)
        if (self.gs)%26 == self.to:
            self.isTurnover = True
    def turnover(self):
        if self.isTurnover:
            self.isTurnover = False
            return True
        else:
            return False
```

También se pueden combinar el Grundstellung y el Ringstellung en una sola configuración total que sería la resta de ambos, pero aquí estoy intentando hacer una reproducción fiel de su uso.

## El clavijero

El clavijero era una fase extra de seguridad que permutaba una letra por otra a la entrada y salida. Lo modelizamos usando un diccionario de Python, siendo `None` el clavijero vacío. Por tanto, usaremos la siguiente función para pasar el clavijero:

```py
def pasa_clavijero(pares, a):
    if pares == None:
        return a
    elif not (a in pares.keys() or a in pares.values()):
        return a
    else:
        for k, v in pares.items():
            if k == a:
                return v
            elif v == a:
                return k
```

## La máquina

Usaremos una clase que toma como campos los tres rotores (ordenados de derecha a izquierda), el reflector y el clavijero, y aplica las permutaciones dadas antes. Notar que los rotores giran **antes** de que se cifre cada letra:

```py
class Maschine:
    def __init__(self, r1, r2, r3, ukw, kl):
        self.r1, self.r2, self.r3 = r1, r2, r3
        self.ukw = ukw
        self.kl = kl
        
    def settings(self, gss, rss):
        self.r1.set_gs(gss[2])
        self.r2.set_gs(gss[1])
        self.r3.set_gs(gss[0])
        
        self.r1.set_rs(rss[2])
        self.r2.set_rs(rss[1])
        self.r3.set_rs(rss[0])
    def cifrar_letra(self, a):
        self.r1.turn()
        if self.r1.turnover():
            self.r2.turn()
            if self.r2.turnover():
                self.r3.turn()
        ret = pasa_clavijero(self.kl, a)
        ret = self.r1.permuta_ida(ret)
        ret = self.r2.permuta_ida(ret)
        ret = self.r3.permuta_ida(ret)
        ret = permuta(self.ukw,1,ret)
        ret = self.r3.permuta_vuelta(ret)
        ret = self.r2.permuta_vuelta(ret)
        ret = self.r1.permuta_vuelta(ret)
        ret = pasa_clavijero(self.kl, ret)
        return ret
    def cifrar_mensaje(self,X):
        return "".join([self.cifrar_letra(i) for i in X])
    def __repr__(self):
        return "("+num_a_letra(M.r3.gs) + ", "+ num_a_letra(M.r2.gs)+", "+num_a_letra(M.r1.gs)+")"
```

Aquí, usamos el método mágico `__repr__` para ver los Grundstellung de los rotores como se verían en las ventanillas de la máquina al usar la función `print` con un objeto de esta clase.

## Cableados y ejemplo

Los cableados que se usaban durante la guerra (con la notación que estamos usando) eran:

```py
permR1 = "EKMFLGDQVZNTOWYHXUSPAIBRCJ"
permR2 = "AJDKSIRUXBLHWTMCQGZNPYFVOE"
permR3 = "BDFHJLCPRTXVZNYEIWGAKMUSQO"
permR4 = "ESOVPZJAYQUIRHXLNFTGKDCMWB"
permR5 = "VZBRGITYUPSDNHLXAWMJQOFECK"
UKW_C  = "FVPJIAOYEDRZXWGCTKUQSBNMHL"
UKW_B  = "YRUHQSLDPXNGOKMIEBFZCWVJAT"
```

Con esas permutaciones podemos generar los rotores:

```py
R1 = Rotor(letra_a_num("Q")+1, permR1)
R2 = Rotor(letra_a_num("E")+1, permR2)
R3 = Rotor(letra_a_num("V")+1, permR3)
R4 = Rotor(letra_a_num("J")+1, permR3)
R5 = Rotor(letra_a_num("Z")+1, permR3)
```

Aquí estamos poniendo el punto de turnover que tenían los rotores de la época, usamos `+1` porque el turnover pasa en la letra de después del punto de turnover.

Ahora, si tomamos un clavijero `AK HL`, rotores `I-II-III` configuración externa `DIE` y configuración interna `GOV`, configuramos la máquina usando:

```py
KL = {"A":"K","H":"L"}
M = Maschine(R3,R2,R1,UKW_B,KL) # recordar que los rotores van de dcha a izda
GS = ["D","I","E"]
RS = ["G","O","V"]
M.settings(list(map(letra_a_num, GS)), list(map(letra_a_num, RS)))
```

Podemos ahora cifrar un mensaje, por ejemplo: *Máquina enigma programada en Python*. Primero, quitamos las tildes y cambiamos los espacios por `X`, obteniendo `MAQUINAXENIGMAXPROGRAMADAXENXPYTHON`, y lo ciframos así:

```py
M.cifrar_mensaje("MAQUINAXENIGMAXPROGRAMADAXENXPYTHON")
```

Obteniendo (yo esto lo tengo en un cuaderno de ipython, así que la salida me sale inmediatamente debajo):

```
'NRPILCIMQVCLXYWBBJZDETHXUZXBTVONEYB'
```

Después, si reseteamos la máquina y volvemos a pasar el mensaje, lo desciframos:

```py
M.settings(list(map(letra_a_num, GS)), list(map(letra_a_num, RS)))
M.cifrar_mensaje(mensaje_cifrado)
```

```
'MAQUINAXENIGMAXPROGRAMADAXENXPYTHON'
```
