---
layout: post
title: Teoría de Conjuntos Básica
tags:
  - Español
  - Set Theory
---

>## Índice
>* Table of Contents
>{:toc}


## &sect;1	Conceptos Fundamentales

### Notación básica

Comunmente usaremos letras mayúsculas $$A, B, \dots$$  para denotar conjuntos y minúsculas $$a,b,\dots$$ para denotar sus **objetos** o **elementos**. Denotamos que un objeto pertenece a $$A$$ como:

$$
a\in A
$$

Si el elemento no pertenece a $$A$$ lo denotaremos como:

$$
a\notin A
$$

Si escribimos $$a=b$$ nos referimos a **igualdad lógica** es decir, $$a$$ y $$b$$ son símbolos para el mismo elemento. De manera similar, podemos escribir $$A=B$$ cuando dos conjuntos son iguales.

Decimos que $$A$$ es un **subconjunto** de $$B$$ si cada elemento de $$A$$ es también un elemento de $$B$$, denotaremos esto como:

$$
A\subset B
$$

Decimos que $$A$$ es un **subconjunto propio** de $$B$$ si no son iguales, y se escribe:

$$
A \subsetneq B
$$

Los conjuntos se pueden especificar como una colección de elementos discretos o como elementos de otro conjunto que comparten una propiedad. Por ejemplo:

$$
A = \lbrace a,b,c \rbrace
$$

$$
B = \left\lbrace x \mid x \text{ es un entero par } \right\rbrace
$$

### Unión de conjuntos y "o" lógico 

Dados dos conjuntos $$A$$ y $$B$$, podemos generar un conjunto que consista de todos los elementos de $$A$$ y los de $$B$$. Llamaremos a este conjunto la **unión** de $$A$$ y $$B$$, denotado como $$A \cup B$$. Formalmente lo definiremos como:

$$
A\cup B = \left\lbrace x\mid x\in A \text{ ó }x\in B \right\rbrace
$$

En matemáticas, como no se puede tolerar la ambigüedad, cuando decimos "ó" queremos decir "$$P$$, $$Q$$ o ambos".

### Intersección de conjuntos, el Conjunto Vacío y el significado de "*si... entonces*"

Dados los conjuntos $$A$$ y $$B$$, otra forma de construir otro conjunto es tomando las partes comunes de $$A$$ y $$B$$. Este conjunto se llama la **intersección** de $$A$$ y $$B$$ y se denota como $$A\cap B$$. Formalmente la definimos como:

$$
A\cap B = \left\lbrace x\mid x\in A \text{ and }x\in B \right\rbrace
$$

¿Qué pasa cuando no tienen elementos en común? Para encargarnos de esta eventualidad, introducimos el concepto del **conjunto vacío**, denotado $$\emptyset$$, del cual podemos pensar como "un conjunto sin elementos".

Usando este convenio, podemos expresar el caso en el que $$A$$ y $$B$$ no tienen elementos en común:

$$
A\cap B=\emptyset
$$

También podemos expresar esto diciendo que $$A$$ y $$B$$ son **disjuntos**.

Como el concepto de $$\emptyset$$ es un convenio, se han de clarificar algunos aspectos. Es claro por la definición de el conjunto vacío que $$\forall x, x\notin \emptyset$$. De manera similar, por las definiciones de unión e intersección tendremos:

$$
A\cup \emptyset = A\qquad \text{and}\qquad A\cap \emptyset =\emptyset
$$

La relación de inclusión tiene un poco más de truco. Dado un conjunto $$A$$, ¿debemos decir que $$\emptyset \subset A$$? Esa expresión significa "Todo elemento que pertenece al conjunto vacío pertenece a $$A$$", o de otro modo, "Para todo objeto $$x$$, si $$x$$ pertenece al conjunto vacío, entonces también pertenece a $$A$$".

¿Es esta afirmación correcta o no? La frase de la forma *si x entonces y* tiene ambigüedad en el lenguaje cotidiano, esta duda es inadmisible en matemáticas, por eso *si $$P$$ entonces $$Q$$* significa que, si $$P$$ es cierto, $$Q$$ también lo es, pero que si $$P$$ no es cierto, no podemos discernir nada sobre la veracidad de $$Q$$.

Para visualizar el ejemplo sobre el conjunto vacío, tomemos un ejemplo más simple sobre los números reales:

$$
\text{Si }x^2 <0\text{, then }x=23
$$

Podemos decir que esta afirmación es correcta, ya que nunca tendremos el caso en el que $$x^2 <0$$, en este caso, podemos decir que la afirmación es **vacuamente cierta**. De este modo, podemos decir que el que $$\emptyset \subset A$$ es vacuamente cierto.

### Contrapositivo y converso

La discusión sobre el significado de "si,... entonces", nos lleva a considerar otro tema en lógica elemental que a veces causa dificultades, la relación entre una *afirmación*, su *contrapositiva*, y su *conversa*.

Dada una afirmación de la forma "*Si $$P$$, entonces $$Q$$*", su **contrapositiva** se define como la afirmación "*Si $$Q$$ no es cierto, entonces $$P$$ no es cierto*". Si tenemos una afirmación de la forma:

$$
P\Rightarrow Q
$$

que se lee $$P$$ implica $$Q$$ se sigue que:

$$
(¬\ Q)\Rightarrow(¬\ P)
$$

Hay otra afirmación que se puede formar desde la afirmación $$P\Rightarrow Q$$, y es 

$$
Q\Rightarrow P
$$

La cual es la **conversa** de $$P\Rightarrow Q$$. Debemos tener cuidado entre la conversa y la contrapositiva de una afirmación. Mientras que una afirmación y su contrapositiva son lógicamente equivalentes, una afirmación y su conversa no dicen nada la una sobre la otra. 

Si tenemos un caso en el que tanto una afirmación como su conversa son ciertas, lo expresaremos:

$$
P\Leftrightarrow Q
$$

Lo que se lee como "*$$P$$ es cierto si y solo si $$Q$$ es cierto*".

### Diferencia de dos conjuntos

La última operación útil entre conjuntos será la **diferencia** de dos conjuntos, denotada $$A-B$$, y definida como el conjunto que contiene todos los elementos de $$A$$ que no están en $$B$$, formalmente:

$$
A-B= \left\lbrace x\mid x\in A \text{ and }x\notin B \right\rbrace
$$

### Reglas de la teoría de conjuntos

Dados varios conjuntos, se pueden formar nuevos conjuntos aplicando las operaciones vistas a ellos, como en álgebra, usaremos paréntesis para indicar el orden de operaciones, tenemos varias propiedades para estas operaciones:

- *Primera distributiva:* $$A\cap (B\cup C)=(A\cap B)\cup (A\cap C)$$

- *Segunda distributiva:* $$A\cup(B\cap C)=(A\cup B)\cap(A\cup C)$$

- *Primera ley de DeMorgan:* $$A-(B\cup C)=(A-B)\cap(A-C)$$

  Ó, "*El complementario de la unión es la intersección de complementarios*"

- *Segunda ley de DeMorgan:* $$A-(B\cap C)=(A-B)\cup(A-C)$$ 

  Ó, "*El complementario de la intersección es la unión de complementarios*

### Familias de Conjuntos

Podemos considerar conjuntos cuyos elementos sean de cualquier naturaleza, incluso conjuntos de *conjuntos*. En particular, es útil considerar el *conjunto de todos los posibles subconjuntos de $$A$$*, denotaremos este conjunto $$\mathcal{P}(A)$$ y lo llamaremos **conjunto potencia** o **partes de** $$A$$.

Cuando tenemos un conjunto cuyos elementos son conjuntos, solemos llamarlo **familia** y lo denotamos con tipografía caligráfica como $$\mathcal{A}$$, o $$\mathcal{B}$$, aquí necesitamos tener cuidado con la tipografía, ya que tenemos que distinguir entre $$a$$ como *elemento*, del conjunto $$A$$, y el conjunto de un elemento $$\lbrace a \rbrace$$ que es un *subconjunto* de $$A$$. Para ilustrar, sea $$A=\lbrace a,b,c\rbrace$$, entonces:

$$
a\in A,\qquad 
\lbrace a\rbrace \subset A,\text{ and } \qquad
\lbrace a \rbrace \in \mathcal{P}(A)
$$

### Uniones e intersecciones arbitrarias

Dada una familia $$\mathcal{A}$$, la **unión** de los elementos de $$\mathcal{A}$$ se define como:

$$
\bigcup_{A\in \mathcal{A}} A=\left\lbrace x\mid x\in A \text{ para al menos un }A\in \mathcal{A} \right\rbrace
$$

Y la **intersección** de elementos de $$\mathcal{A}$$ se define como:

$$
\bigcap_{A\in \mathcal{A}} A=\left\lbrace x\mid x\in A\ \forall A\in\mathcal{A}
\right\rbrace
$$

Para evitar confusiones, *no definimos la intersección cuando $$\mathcal{A}$$ sea vacío*.

### Producto cartesiano

Dados dos conjuntos $$A$$ y $$B$$, definimos su **producto cartesiano** como:

$$
A \times B=\left\lbrace \left(a,b\right) 
\mid a\in A, b\in B
\right\rbrace
$$

También podemos denotar $$(a,b)$$ como $$a\times b$$ ó $$\lbrace a\rbrace \times \lbrace b\rbrace$$ para evitar confusiones con los intervalos abiertos en $$\mathbb{R}$$.

## &sect;2	Funciones

**Definición.** *Una **regla de asignación** es un subconjunto $$r$$ del producto cartesiano $$C\times D$$ de dos conjuntos, con la propiedad de que cada elemento de $$C$$ aparece en la primera coordenada de **como mucho una** pareja ordenada que pertenezca a $$r$$*

En otras palabras, un subconjunto $$r$$ de $$C\times D$$ es una regla de asignación si:

$$
\left[
(c,d)\in r \text{ y } (c,d^\prime)\in r
\right] \Rightarrow
[d=d^\prime]
$$

Dada una regla de asignación $$r$$, su **dominio** es el subconjunto $$C$$ que contiene todas las primeras coordenadas de los elementos de $$r$$, y la **imagen** de $$r$$ será el conjunto $$D$$ que tiene todas lass segundas coordenadas. Formalmente:

$$
\text{dominio }r= \left\lbrace 
 c\mid \exists d\in D \text{ tq } (c,d)\in r
\right\rbrace
\\
\text{imagen }r= \left\lbrace 
 d\mid \exists c\in C \text{ tq } (c,d)\in r
\right\rbrace
$$

Dada una regla de asignación, su dominio e imagen están completamente definidas. Ahora podemos ver lo que es una función:

**Definición:** *Una **función** $$f$$ es una regla de asignación $$r$$, junto a un conjunto $$B$$ que contiene la imagen de $$r$$. El dominio $$A$$ de la regla $$r$$ también se llama el **dominio** de $$f$$; el conjunto imagen de $$r$$ también se llamará la **imagen** de $$f$$; y $$B$$ será el **rango** de $$f$$*

Podremos expresar que $$f$$ es una función de dominio $$A$$ (o con soporte en $$A$$) y rango $$B$$ de la siguiente forma:

$$
f:A\longrightarrow B
$$

**Definición:** *Sea $$f:A\to B$$ un a función y sea $$A_0$$ un subconjunto de $$A$$, definimos la **restricción** de $$f$$ a $$A_0$$ como la función que asigna $$A_0$$ a $$B$$ con regla:*

$$
\left\lbrace
 \left(a,f(a)\right) \mid a \in A_0
\right\rbrace
$$

*y se denota como $$f\mid _{A_0}$$*

**Definición:** *Dadas dos funciones $$f:A\to B$$ y $$g:B\to C$$, definimos la **composición** $$g\circ f$$ de $$f$$ y $$g$$ como la función $$g\circ f:A\to C$$ definida como $$(g\circ f)(a)=g(f(a))$$.*

Podemos clasificar funciones de acuerdo con tres categorías:

- **Inyectiva:** $$f(a)=f(a^\prime)\Longrightarrow a=a^\prime$$
- **Sobre ó supreyectiva:** $$\forall b\in B\ \exists a\in A$$ tq $$b=f(a)$$ 
- **Biyectiva:** si es tanto Inyectiva como Sobre.

La inyectividad depende de la regla, mientras que la suprayectividad depende del rango. Se sigue facilmente que la composición de dos aplicaciones biyectivas será biyectiva.

Sea $$f$$ biyectiva, eso quiere decir que existe una función de $$B$$ a $$A$$ llamada la **inversa** de $$f$$. Se denota como $$f^{-1}$$ y se define haciendo que $$f^{-1}(b)$$ sea el único elemento $$a$$ de $$A$$ para el cual $$f(a)=b$$. Dado $$b\in B$$, al ser la función sobre, existe tal elemento $$a\in A$$; el hecho de que sea inyectiva quiere decir que existe *solo uno*. Es fácil ver que, siendo $$f$$ biyectiva, $$f^{-1}$$ también lo será.

**Lema:** *Sea $$f:A\to B$$. Si existen dos funciones $$g:B\to A$$ y $$h:B \to A$$ tales que $$g(f(a))=a\ \forall a \in A$$ y $$f(h(b))=b\ \forall b\in B$$, entonces $$f$$ es biyectiva y $$h=g=f^{-1}$$.*

**Definición:** *Sea $$f:A\to B$$. Sea $$A_0 \subset A$$, denotamos $$f(A_0)$$ al conjunto de todas las imagenes de puntos en $$A_0$$ bajo $$f$$; llamaremos a este conjunto la **imagen** de $$A_0$$ bajo $$f$$. Formalmente:*

$$
f(A_0)=\left\lbrace
 b\mid b=f(a)\text{ para al menos un }a\in A_0
\right\rbrace
$$

*Por otro lado, si $$B_0$$ es un subconjunto de $$B$$, denotamos como $$f^{-1}(B_0)$$ al conjunto de elementos de $$A$$ cuyas imágenes bajo $$f$$ yacen en $$B_0$$; lo llamamos la **antiimagen** de $$B_0$$ bajo $$f$$. Formalmente:*

$$
f^{-1}(B_0)=\left\lbrace
 a\mid f(a)\in B_0
\right\rbrace
$$

Debemos notar aquí que la inversa de una función tiene mejor comportamiento que la función en si. La inversa conserva inclusión, unión e intersección, mientras que la función solo conserva unión e inclusión. También cabe mencionar lo siguiente:

$$
A_0 \subset f^{-1}(f(A_0))
 \qquad\text{y}\qquad
 f(f^{-1}(B_0))\subset B_0
$$

**Pero no son igualdades**. La primera inclusión será una igualdad si $$f$$ es inyectiva, y la segunda si es sobre.

## &sect;3	Relaciones

**Definición:** Una **relación** sobre un conjunto $$A$$ es un subconjunto $$C$$ del producto cartesiano $$A\times A$$.

Usamos la notación $$xCy$$ para referirnos a lo mismo que $$(x,y)\in C$$, el que "*$$x$$ e $$y$$ están relacionados por $$C$$*".

### Relaciones de equivalencia y particiones

Una **relación de equivalencia** sobre $$A$$ es una relación $$C$$ en $$A$$ que cumple las siguientes tres propiedades:

1. **Reflexividad:** $$xCx\ \ \forall x\in A$$ 
2. **Simetría: **$$xCy\Rightarrow yCx$$
3. **Transitividad: **$$xCy,yCz\Rightarrow xCz$$ 

Frecuentemente se usa el símbolo $$\sim$$ para denotar una relación de equivalencia (pero para JL, mejor $$\mathfrak{R}$$)

Dada una relación de equivalencia $$\sim$$ en un conjunto $$A$$ y un elemento $$x\in A$$, definimos un cierto subconjunto $$E\subset A$$, llamado la **clase de equivalencia** de $$x$$, como:

$$
E=\lbrace y\mid y\sim x\rbrace
$$

**Lema:** *Dos clases de equivalencia $$E$$ y $$E^\prime$$ son o bien disjuntas o iguales*

Dada una relación de equivalencia sobre $$A$$, denotamos por $$\mathscr{E}$$ la familia de todas las clases de equivalencia determinadas por esta relación

**Definición:** Una **partición** de $$A$$ es una familia de subconjuntos no vacíos y disjuntos de $$A$$, cuya unión es todo $$A$$.

Dada una partición $$\mathcal{D}$$ de $$A$$ hay **exactamente una** relación de equivalencia definida en $$A$$ que genera tal partición.

### Relaciones de orden

Una relación $$C$$ en un conjunto $$A$$ se dice **de orden**, si es:

1. **Comparable:** $$\forall x,y\in A$$ tq $$x\neq y$$ entonces, o bien $$xCy$$ o $$yCx$$
2. **No reflexiva:** $$\nexists x\in A$$ tq $$xCx$$
3. **Transitiva:** Si $$xCy$$ y $$yCz$$, entonces $$xCz$$

Notar que las tres propiedades *juntas* implican que para ninguna pareja $$x,y\in A$$ se pueden cumplir $$xCy$$ y $$yCx$$ simultáneamente.

Se usa el símbolo $$<$$ para las relaciones de orden.

**Definición:** Sea $$X$$ un conjunto y $$<$$ una relación de orden en $$X$$, si $$a<b$$, podemos usar la notación $$(a,b)$$ para denotar el conjunto:

$$
\left\lbrace
 x\mid a<x<b
\right\rbrace
$$

que se llamará un **intervalo abierto** en $$X$$. Si el conjunto es vacío, $$a$$ se dirá el **predecesor inmediato** de $$b$$, y $$b$$ será el **sucesor inmediato** de $$a$$.

**Definición:** Supongamos que $$A, B$$ son conjuntos con relaciones de orden $$<_A , <_B$$. Decimos que $$A$$ y $$B$$ tienen el mismo **tipo de orden** si existe una biyección entre ellos que preserve el orden, es decir $$\exists f:A\to B$$ tq:

$$
a_1 <_A a_2 \Rightarrow f(a_1)<_B f(a_2)
$$

**Definición:** Sean $$A,B$$ dos conjuntos con relaciones de orden $$<_A , <_B$$ respectivamente. Definimos una relación de orden en $$A\times B$$ definiendo:

$$
a_1 \times b_1 < a_2 \times b_2
$$

si $$a_1 <_A a_2$$, o si $$a_1 = a_2$$ y $$b_1 <_B b_2$$. Se llama **Relación de orden de diccionario**.

Sea $$A$$ un conjunto con una relación de orden $$<$$. Sea $$A_0 \subset A$$. Decimos que un elemento $$b\in A_0$$ es el **mayor elemento (máximo)** de $$A_0$$ si $$b\in A_0$$ y $$x \le b\ \ \forall x\in A_0$$. Definimos de manera análoga el **menor elemento (mínimo)** de $$A_0$$.

Decimos que el subconjunto $$A_0 \subset A$$ está **acotado por arriba** si $$\exists b\in A$$ tq $$x\le b\ \ \forall x\in A_0$$, llamaremos a $$b$$ una **cota superior** de $$A_0$$. Si el conjunto de todas las cotas superiores de $$A_0$$ tiene un mínimo, ese elemento se llamará la **menor cota superior** o **supremo** de $$A_0$$ ($$\sup A_0$$).

Similarmente, diremos que el subconjunto $$A_0 \subset A$$ está **acotado por abajo** si $$\exists b\in A$$ tq $$x\ge b\ \ \forall x\in A_0$$, llamaremos a $$b$$ una **cota inferior** de $$A_0$$. Si el conjunto de todas las cotas superiores de $$A_0$$ tiene un máximo, ese elemento se llamará la **mayor cota inferior** o **ínfimo** de $$A_0$$ ($$\inf A_0$$).

El supremo e ínfimo de un conjunto *pueden no estar* dentro del propio conjunto, en el caso de que estén, coincidirán siempre con el mínimo y máximo.

**Definición:** Un conjunto ordenado $$A$$ se dice tiene la **propiedad de mínima cota superior** si todo subconjunto $$\emptyset \neq A_0 \subset A$$ acotado por arriba tiene al menos una cota superior. De forma análoga, diremos que tiene la propiedad de **máxima cota inferior** si todo subconjunto no vacío acotado por abajo tiene al menos una cota inferior.

$$A$$ tiene la propiedad de mínima cota superior $$\iff$$ tiene la propiedad de máxima cota inferior.

## &sect;4	Los enteros y los reales

### Los reales

Asumimos que existe un conjunto $$\mathbb{R}$$, llamado **los números reales**, con dos operaciones binarias $$+$$ y $$\cdot$$ sobre $$\mathbb{R}$$ llamadas adición y producto, y una relación de orden $$<$$ en $$\mathbb{R}$$, tal que se cumplen las siguientes propiedades:

- *Propiedades algebraicas:*
  
  1. $$(x+y)+z=x+(y+z) \\ (x\cdot y)\cdot z=x\cdot (y\cdot z), \forall x,y,z\in\mathbb{R}$$
  
  2. $$x+y=y+x \\ x\cdot y=y\cdot x, \forall x,y\in \mathbb{R}$$
  
  3. Existe un único elemento en $$\mathbb{R}$$ llamado **cero**, denotado 0, tal que $$x+0=x,\forall x\in\mathbb{R}$$
  
     Existe un único elemento en $$\mathbb{R}$$ llamado **uno**, distinto de 0 y denotado 1, tal que $$x\cdot 1=x,\forall x\in \mathbb{R}$$
  
  4.  Para cada $$x\in\mathbb{R}$$ existe un único $$y$$ tal que $$x+y=0$$
  
      Para cada $$x\in\mathbb{R}$$ existe un único $$y$$ tal que $$x\cdot y=1$$
  
  5.  $$x\cdot (y+z)=(x\cdot y)+(x\cdot z),\forall x,y,z\in\mathbb{R}$$
  
- *Propiedades mixtas algebraicas y de orden:*

  6. Si $$x>y$$, entonces $$x+z>y+z$$

     Si $$x>y,z>0$$, entonces $$x\cdot z>y\cdot z$$

- *Propiedades de orden:*

  7. La relación de orden $$<$$ tiene la propiedad de mínima cota superior.
  8. Si $$x<y$$, existe un elemento $$z$$ tal que $$x<z$$ y $$z<y$$

Las propiedades (1) a (5) definen en álgebra un **campo**, añadiendo la propiedad (6) tenemos un **campo ordenado**.

Las propiedades (7) y (8) definen en topología un **continuo lineal**. En general las propiedades (1) a (7) se toman como axiomas, mientras que la propiedad (8) se ve como un teorema, ya que es consecuencia de las otras.

### Los enteros

S pueden definir usando las propiedades (1) a (6).

**Definición:** Un subconjunto $$A$$ de los reales se dice **inductivo** si contiene al número 1 y, para cada $$x\in A$$, el número $$x+1$$ también está en $$A$$. Sea $$\mathcal{A}$$ una familia de todos los subconjuntos de $$\mathbb{R}$$. Entonces el conjunto $$\mathbb{Z}_+$$ de los **enteros positivos** se define como:

$$
\mathbb{Z}_+ = \bigcap_{A\in\mathcal{A}} A
$$

El conjunto de los enteros positivos tiene dos propiedades que se infieren de la definición:

1. $$\mathbb{Z}_+$$ es inductivo
2. (*Principio de inducción*). Si $$A$$ es un conjunto inductivo de enteros positivos, entonces $$A=\mathbb{Z}_+$$

$$\mathbb{Z}$$ se definirá como el conjunto de los enteros positivos junto con el 0 y todos los recíprocos aditivos de los positivos. Así mismo, los **racionales** ($$\mathbb{Q}$$) se definirán como cocientes de enteros.

Se puede demostrar que, dado un entero $$n$$, no existe un entero $$a$$, tq $$n<a<n+1$$.

Sea $$n$$ un entero positivo, usamos el símbolo $$S_n$$ para denotar el conjunto de todos los enteros positivos menores que $$n$$; llamaremos a esto una **sección<a name="seccion"></a>** de los enteros positivos. El conjunto $$S_1$$ es vacío.

**Teorema 4.1: (Principio del buen orden).** *Todo subconjunto de $$\mathbb{Z}_+$$ tiene un elemento mínimo*

**Teorema 4.2: (Principio de inducción fuerte.** *Sea $$A$$ un conjunto de enteros positivos. Supongamos que para cada entero positivo $$n$$, la afirmación $$S_n \subset A$$ implica $$n\in A$$. Entonces $$A=\mathbb{Z}_+$$*.

Hasta ahora nos bastaba con los axiomas (1) a (6) de los reales, pero necesitamos el (7) para una cosa:

**Axioma de ordenación de Arquímedes: ** El conjunto de los enteros positivos no tiene cota superior en los reales.

## &sect;5 Productos Cartesianos

**Definición:** Sea $$\mathcal{A}$$ una familia no vacía de conjuntos. Una **función índice** de $$\mathcal{A}$$ es una función sobre $$f$$ sobre un conjunto $$J$$, llamado el **conjunto índice** de $$\mathcal{A}$$. La familia $$\mathcal{A}$$ junto con la función índice $$f$$ se llama **familia indexada**. Dado $$\alpha\in J$$, denotaremos el conjunto $$f(\alpha)$$ como $$A_\alpha$$. Y denotaremos la familia indexada como:

$$
\left\lbrace
 A_\alpha
\right\rbrace_{\alpha\in J}
$$

Cabe notar que la función no tiene que ser *inyectiva*, por lo cual puede darse el caso de que $$A_\alpha = A_\beta$$ si $$\alpha\neq\beta$$.

**Definición:** Sea $$m$$ un entero positivo. Dado un conjunto $$X$$, definimos una $$m$$**-tupla** de elementos de $$X$$ como una función:

$$
\bar{x}:\lbrace 1,\dots,m \rbrace \to X
$$

Si $$\bar{x}$$ es una $$m$$-tupla, solemos denotar el valor de $$\bar{x}$$ en $$i$$ como $$x_i$$ en vez de $$\bar{x}(i)$$, y llamaremos a este valor la $$i$$-ésima **coordenada** de $$\bar{x}$$. También solemos representar la función misma con el símbolo:

$$
\left(
 x_1,x_2,\dots,x_m
\right)
$$

Sea ahora la familia $$\left\lbrace A_1 ,\cdots,A_m \right\rbrace$$ de conjuntos indexada por el conjunto $$\lbrace 1,\cdots, m\rbrace$$. Sea $$X=A_1 \cup \cdots\cup A_m$$. Definimos el **producto cartesiano** de esta familia indexada, denotado por:

$$
\prod_{i=1}^m A_i 
\qquad\text{ó}\qquad
 A_1 \times\cdots\times A_m
$$

Será el conjunto de todas las $$m$$-tuplas $$(x_1 ,\dots,x_m)$$ de elementos de $$X$$ tales que $$x_i \in A_i$$ para cada $$i$$.

**Definición:** Dado un conjunto $$X$$ definimos una $$\omega$$**-tupla** de elementos de $$X$$ como una función:

$$
\bar{x}:\mathbb{Z}_+ \to X
$$

También decimos que esta función es una **secuencia** o una **secuencia infinita** de elementos de $$X$$.

Ahora, sea $$\lbrace A_1, A_2,\dots\rbrace$$ una familia de conjuntos, indexada por los enteros positivos; sea $$X$$ la unión de todos los conjuntos de esta familia. El **producto cartesiano** de esta familia indexada, denotado por:

$$
\prod_{i\in \mathbb{Z}_+}A_i \quad\text{ó}\quad A_1 \times A_2 \times\cdots 
$$

se define como el conjunto de todas las $$\omega$$-tuplas $$(x_1 , x_2 ,\cdots)$$ de elementos de $$X$$ tales que $$x_i \in A_i$$ para cada $$i$$.

Si todos los $$A_i$$'s son iguales e iguales a $$X$$, el producto cartesiano $$X\times\overbrace{\cdots}^{m}\times X$$ se denotará $$X^m$$ mientras que el producto cartesiano $$X\times X\times\cdots$$ se denotará $$X^\omega$$. 

## &sect;6 Conjuntos Finitos

Usaremos los conjuntos definidos antes como [sección](#seccion) como prototipo de conjunto finito.

**Definición:** Diremos que un conjunto es **finito** si hay una correspondencia biyectiva entre $$A$$ y una sección de los enteros positivos. Es decir, $$A$$ es finito si es vacío o existe una biyección:

$$
f:A\to \lbrace 1,\dots,n\rbrace
$$

para algún entero positivo $$n$$. En el caso de $$A=\emptyset$$ diremos que $$A$$ tiene **cardinalidad** 0 ($$\vert  A\vert  =0$$) en el otro caso, diremos que tiene **cardinalidad** $$n$$ ($$\vert  A\vert  =n$$).

**Lema 6.1:** *Sea $$n$$ un entero positivo. Sea $$A$$ un conjunto; sea $$a_0$$ un elemento de $$A$$. Entonces existe una correspondencia biyectiva $$f$$ entre el conjunto $$A$$ y $$\lbrace 1, \dots n+1\rbrace$$ si y solo si existe una correspondencia biyectiva $$g$$ del conjunto $$A-\lbrace a_0\rbrace$$ con el conjunto $$\lbrace 1,\dots,n\rbrace$$.*

**Teorema 6.2:** *Sea $$A$$ un conjunto; suponemos que existe una biyección $$f:A\to\lbrace 1,\dots,n\rbrace$$ para algún $$n\in\mathbb{Z}_+$$. Sea $$S$$ un subconjunto propio ($$\subsetneq$$) de $$A$$. Entonces no existe una biyección $$g:B\to \lbrace 1,\dots,n\rbrace$$; pero (asumiendo $$B\neq\emptyset$$) existe una biyección $$g:B\to\lbrace 1,\dots,m\rbrace$$ para algún $$m<n$$.*

**Corolario 6.3:** *Si $$A$$ es finito, no existe biyección entre $$A$$ y un subconjunto propio suyo.*

**Corolario 6.4:** *$$\mathbb{Z}_+$$ no es finito.*

​	**Dem:** La función $$f:\mathbb{Z}_+\to\mathbb{Z}_+ -\lbrace 1\rbrace$$ dada por $$f(n)=n+1$$ es una biyección entre $$\mathbb{Z}_+$$ y él mismo.

$$
\hspace{20cm}\blacksquare
$$

**Corolario 6.5:** *La cardinalidad de un conjunto finito $$A$$ está únicamente determinada por $$A$$.*

**Corolario 6.6:** *Si $$B$$ es un subconjunto del conjunto finito $$A$$, entonces $$B$$ es infinito. Si $$B$$ es un subconjunto propio de $$A$$, entonces la cardinalidad de $$B$$ es menor que la cardinalidad de $$A$$.*

**Corolario 6.7:** *Sea $$B$$ un conjunto no vacío. Entonces las afirmaciones siguientes son equivalentes:*

1. *$$B$$ es finito*
2. *Hay una función sobre de una sección de los enteros positivos a $$B$$*
3. *Hay una función inyectiva de $$B$$ a una sección de los enteros positivos*

**Corolario 6.8:** *Las uniones finitas y productos cartesianos finitos de conjuntos finitos son finitas.*

## &sect;7 Conjuntos contables e incontables

**Definición:** un conjunto se dice **infinito** si no es finito. Se dice **contablemente infinito** si existe una correspondencia biyectiva:

$$
f:A\to\mathbb{Z}_+
$$

**Definición:** un conjunto se dice **contable** si es finito o contablemente infinito. Un conjunto que no es contable se dice **incontable**.

Solemos expresar contable como $$\vert  A\vert  \le\aleph_0$$, e incontable como $$\vert  A\vert  >\aleph_0$$. $$\aleph_0$$ se toma para representar la cardinalidad de los enteros positivos. 

Existe un sencillo criterio para discernir si un conjunto es contable:

**Teorema 7.1:** *Sea $$B$$ un conjunto no vacío. Entonces las siguientes afirmaciones son equivalentes:*

1. *$$B$$ es contable*
2. *Hay una función sobre $$f:\mathbb{Z}_+\to B$$*
3. *Hay una función inyectiva $$g:B\to \mathbb{Z}_+$$

**Lema 7.2:** *Si $$C$$ es un subconjunto infinito de $$\mathbb{Z}_0$$, entonces $$C$$ es contablemente finito*

A veces, para demostrar algo (como el lema de arriba[^nota dems]), necesitamos "definir algo por inducción", es decir, definir algo recursivamente, para esto necesitamos el **principio de definición recursiva**.

[^nota dems]: No demuestro las cosas en este primer apartado

Dado el subconjunto infinito $$C$$ de $$\mathbb{Z}_+$$, hay una única función $$h:\mathbb{Z}_+\to C$$ satisfaciendo la formula:

$$
(*)\qquad\begin{eqnarray}
h(1)&=&\text{ elemento más pequeño de }C\\
h(i)&=&\text{ elemento más pequeño de }[C-h(\lbrace 1,\dots,i-1\rbrace)]\ \forall i>1
\end{eqnarray}
$$

La fórmula ($$*$$) se llama **fórmula de recursión** de $$h$$; define la función $$h$$, *con respecto a si misma*. Una definición dada de esta manera se llamará **definición recursiva**. Las definiciones recursivas pueden llevarnos a problemas:

> *Dado que el barbero de Sevilla afeita a todo hombre que no se afeite a si mismo.*
>
> *¿Quién afeitará al barbero de Sevilla?*

Algunas fórmulas recursivas tienen sentido. En concreto, se tiene el siguiente principio:

**Principio de definición recursiva:** *Sea $$A$$ un conjunto. Dada una fórmula que define $$h(1)$$ como un único elemento de $$A$$, y para todo $$i>1$$, define $$i$$ de manera única como elemento de $$A$$ en términos de valores de $$h$$ para enteros positivos menores que $$i$$, esta fórmula determina una única función $$h:\mathbb{Z}_+\to A$$.*

**Corolario 7.3:** *Un subconjunto de un conjunto contable es contable.*

**Corolario 7.4:** *El conjunto $$\mathbb{Z}_+ \times \mathbb{Z_+}$$ es contablemente infinito*

Por este corolario podemos ver que $$\mathbb{Q}_+$$ es contablemente infinito, ya que podemos definir la suprayección:

$$
\begin{eqnarray}
g:\mathbb{Z}_+\times\mathbb{Z}_+&\to&\mathbb{Q}\\
(n,m)&\mapsto& m/n
\end{eqnarray}
$$


**Teorema 7.5:** *La unión contable de conjuntos contables es contable.*

**Teorema 7.6:** *El producto contable de conjuntos contables es contable.*

**Teorema 7.8:** *Sea $$X=\lbrace 0,1\rbrace$$. Entonces el conjunto $$X^\omega$$ es incontable.*

El producto cartesiano $$\lbrace 0,1\rbrace^\omega$$ es un ejemplo de conjunto incontable, otro ejemplo será $$\mathcal{P}(\mathbb{Z}_+)$$:

**Teorema 7.9:** *Sea $$A$$ un conjunto. No existe aplicación inyectiva $$f:\mathcal{P}(A)\to A$$, y tampoco existe aplicación sobre $$g:A\to\mathcal{P}(A)$$.*

## &sect;8 El Principio de Definición Recursiva

(En el libro de Munkres esto va mucho más gradual, yo voy a la versión general)

**Teorema (Principio de definición recursiva):** *Sea $$A$$ un conjunto; sea $$a_0$$ un elemento de $$A$$. Suponemos que $$\rho$$ es una función que asigna, a cada función $$f$$ que aplica una sección no vacía de los enteros positivos a $$A$$, un elemento de $$A$$. Entonces existe una única función*

$$
h:\mathbb{Z}_+\to A
$$

*tal que*

$$
(*)\qquad\begin{eqnarray*}
h(1)&=&a_0,\\
h(i)&=&\rho(h\mid\lbrace 1,\dots,i-1\rbrace)\quad\text{para }i>1
\end{eqnarray*}
$$

La fórmula ($$*$$) se llamará **fórmula de recursión** para $$h$$. Especifica $$h(1)$$, y expresa el valor de $$h$$ en $$i>1$$ en función de los valores de $$h$$ para enteros positivos menores de $$i$$.

## &sect;9 Conjuntos Infinitos y el Axioma de Elección

**Teorema 9.1:** *Sea $$A$$ un conjunto. Las siguientes afirmaciones son equivalentes:*

1. *Existe una función inyectiva $$f:\mathbb{Z}_+\to A$$*
2. *Existe una biyección de $$A$$ con un subconjunto propio de $$A$$*
3. *$$A$$ es infinito*

Al intentar demostrar este teorema[^nota dems], nos topamos con un problema similar al que nos llevó a las definiciones recursivas, ahora, lo que intentamos definir es:

$$
\begin{eqnarray}
f(1) &=& a_1\\
f(i) &=& \text{elemento arbitrario de }A-f(\lbrace 1,\dots,i-1\rbrace)\quad\text{para }i>1
\end{eqnarray}
$$

Lo cual no es una definición por recursión aceptable, ya que no define de forma única $$f(i)$$ en función a $$f\mid\lbrace 1,\dots, i-1\rbrace$$. Esto quiere decir que necesitamos una nueva manera de afirmar la existencia de un conjunto:

**El axioma de Elección:** *Dada una familia $$\mathcal{A}$$ de conjuntos no vacíos y disjuntos, existe un conjunto $$C$$ que consiste exactamente de un elemento de cada miembro de $$\mathcal{A}$$; esto quiere decir, un conjunto $$C$$ contenido en la unión de los elementos de $$\mathcal{A}$$ y, para cada $$A\in\mathcal{A}$$, el conjunto $$C\cap A$$ contiene un solo elemento.*

Podemos considerar por tanto que el conjunto $$C$$ está formado "eligiendo" un elemento de cada uno de los conjuntos en $$\mathcal{A}$$.

**Lema 9.2 (Existencia de una función de elección):** *Dada una familia $$\mathcal{B}$$ de conjuntos no vacíos (no necesariamente disjuntos), existe una función:*

$$
c:\mathcal{B}\to\bigcup_{B\in\mathcal{B}}B
$$

*tal que $$c(B)$$ es un elemento de $$B$$, para cada $$B\in\mathcal{B}$$.*

Esta función $$c$$ se llamará **función de elección** para la familia $$\mathcal{B}$$. La diferencia entre este lema y el axioma de elección es que en este lema no necesitamos que los conjuntos sean disjuntos.

## &sect;10 Conjuntos Bien Ordenados

**Definición:** Un conjunto $$A$$ con una relación de orden $$<$$ se dice **bien ordenado** si todo subconjunto no vacío tiene un elemento mínimo.

Hay varias maneras de construir elementos bien ordenados, dos son las siguientes:

1. Si $$A$$ es un conjunto bien ordenado, entonces todo subconjunto de $$A$$ está bien ordenado con la restricción de la relación de orden.
2. Si $$A,B$$ son conjuntos bien ordenados, entonces $$A\times B$$ está bien ordenado con el orden de diccionario.

Dado un conjunto sin relación de orden $$A$$, podemos preguntarnos si puede admitir alguna relación que lo haga bien ordenado:

**Teorema 10.1:** *Todo conjunto finito, no vacío y ordenado tiene el tipo de orden de una sección $$\lbrace1,\dots,n\rbrace$$ de $$\mathbb{Z}_+$$ y por tanto está bien ordenado.*

**Teorema (Teorema del buen orden):** *Sea $$A$$ un conjunto, existe una relación de orden en $$A$$ que lo hace bien ordenado.*

**Corolario:** *Existe un conjunto bien ordenado incontable.*

**Definición:** Sea $$X$$ un conjunto bien ordenado. Dado $$\alpha\in X$$, sea $$S_\alpha$$ el conjunto:

$$
S_\alpha = \lbrace
 x\mid x\in X\text{ and }x<\alpha
 \rbrace
$$

al cual llamaremos **sección** de $$X$$ por $$\alpha$$.

**Lema 10.2:** *Existe un conjunto bien ordenado $$A$$ que tiene un elemento máximo $$\Omega$$, tal que la sección $$S_\Omega$$ de $$A$$ por $$\Omega$$ es incontable, pero todas las demás secciones de $$A$$ son contables.*

Notamos que $$S_\Omega$$ es un conjunto bien ordenado del cual todas las secciones son finitas. Su tipo de orden está determinado únicamente por este hecho. Lo llamaremos **primer conjunto bien ordenado incontable**. También denotaremos el conjunto bien ordenado $$A=S_\Omega \cup \lbrace\Omega\rbrace$$ como $$\bar{S} _\Omega$$.

La propiedad más útil de este conjunto es:

**Teorema 10.3:** *Sea $$A$$ un subconjunto contable d $$S_\Omega$$, entonces $$A$$ tiene una cota superior en $$S_\Omega$$.*

## &sect;11 Principio Maximal (de Hausdorff)

Dado un conjunto $$A$$, una relación $$\prec$$ se llamá **orden parcial estricto** en $$A$$ si cumple las siguientes propiedades:

1. (*No-reflexividad*) La relación $$a\prec a$$ nunca se cumple.
2. (*Transitividad*) Si $$a\prec b$$ y $$b\prec c$$, entonces $$a\prec c$$.

Siendo $$\prec$$ un orden parcial estricto sobre $$A$$, puede darse el caso de que algún subconjunto $$B$$ de $$A$$ esté simplemente ordenado por la relación; lo único que hace falta es que cualquier pareja de elementos sean comparables bajo $$\prec$$.

**Teorema (Principio Maximal de Hausdorff):** *Sea $$A$$ un conjunto; sea $$\prec$$ un orden parcial estricto sobre $$A$$, entonces existe un subconjunto de $$A$$ simplemente ordenado.*

**Definición:** Sea $$A$$ un conjunto y sea $$\prec$$ un orden parcial estricto. Si $$B$$ es un subconjunto de $$A$$, una **cota superior** de $$B$$ es un elemento $$c\in A$$ tal que $$\forall b \in B$$, o bien $$b=c$$ ó $$b\prec c$$. Un **elemento maximal** de $$A$$ es un elemento $$m\in A$$ tal que no existe ningún elemento de $$A$$ para el cual se cumpla $$m\prec a$$.

**Lema de Zorn:** *Sea $$A$$ un conjunto estrictamente parcialmente ordenado. Si cada subconjunto simplemente ordenado de $$A$$ tiene una cota superior en $$A$$, entonces $$A$$ tiene un elemento maximal*

A veces se usa el concepto de **orden parcial** (no estricto). Esto se refiere a una relación $$a\preceq b$$ si $$a=b$$ ó $$a\prec b$$.

Fuente: [*Topology Second Edition*, James R. Munkres](https://www.allbookstores.com/Topologh-2nd-Edition-James-Munkres/9780131816299)
