# 1. Responder:
## a. ¿Por qué sólo tiene sentido tratar la complejidad temporal dentro de la clase R?

Porque los lenguajes que estén fuera de dicha clase no pueden garantizar su finalización, por lo tanto no son temporalmente medibles.

## b. Probar que $n^3 = O(2^n)$.

Una función $T_1(n)$ es del orden de una función $T_2(n)$, es decir: $T_1(n) = O(T_2)n$ si para todo $n$ se cumple que $T_1(n) <= c * T_2(n)$, con un $c > 0$.

Por lo tanto, $n^3$ sería de orden $2^n$ si existiese una constante $c$ a partir de la cual se cumpla $n^3 <= c* 2^n$ para toda $n$.

Para probar esto se calculará el límite $lim(n → ∞) n^3/2^n$ (suponiendo $c = 1$).

Esto se trata de una función $f(x)/g(x)$, en la cual $f(x)$ es una función cuadrática y $g(x)$ es exponencial; como el crecimiento de una exponencial siempre es mayor al de una cuadrática, el límite tiende a 0.

Por lo tanto, $n^3 <= 2^n$ para todo $n$, y $n^3$ es de orden $2^n$.

## c. Probar que si $T_1(n)$ = $O(T_2(n))$, entonces TIME($T_1(n)$) ⊆ TIME($T_2(n)$).

Un lenguaje L ∈ $TIME(T(n))$ si existe una MT M que lo decide en tiempo O($T(n)$).

A partir de la definición anterior asumimos que existe una MT que resuelva el lenguaje L en un tiempo $T_1(n)$.

Siguiendo la definición de orden temporal, para que $T_1(n) = O(T_2(n))$ se debe cumplir que $T_1(n) <= c * T_2(n)$, con un $c > 0$; por lo tanto, $T_1(n)$ es menor que $T_2(n)$.

Dado a que $T_1(n)$ es menor que $T_2(n)$, es seguro asumir que todos los lenguajes L ∈ $TIME(T_1(n))$ también van a pertenecer a L ∈ $TIME(T_2(n))$, por lo tanto $TIME(T_1(n)) ⊆ TIME(T_2(n))$.

## d. ¿Por qué es indistinta la cantidad de cintas de las MT que utilizamos para analizar los lenguajes, en el marco de la jerarquía temporal que definimos?



## e. Probar que si L está en P, también lo está su complemento $L^C$.

La clase $P$ está formada por todos los lenguajes aceptados por una MT en tiempo $O(n^k)$; es decir, en tiempo polinomial.

Se supone que un lenguaje $L^C$ es aceptado por una máquina MT M' que invierte los resultados de la MT M que acepta el lenguaje $L$. Por lo tanto, el tiempo de ejecución de la MT M que resuelve $L$ será el mismo que el de M'.

Por lo tanto, como ambos lenguajes tienen el mismo tiempo de ejecución, si $L ∈ P$, su complemento también lo hará.

# 2. Sea el lenguaje SMALL-SAT = {φ | φ es una fórmula booleana sin cuantificadores en la forma normal conjuntiva (o FNC), y existe una asignación de valores de verdad que la satisface en la que hay a lo sumo 3 variables con valor de verdad verdadero}. Probar que SMALL-SAT ∈ P.
**Comentario: φ está en la forma FNC si es una conjunción de disyunciones de variables o variables negadas, como p.ej. (x1  x2)  x4  (x3  x5  x6).**

# 3. Considerando los dos lenguajes siguientes, (1) justificar por qué no estarían en P,
(2) probar que están en NP, (3) justificar por qué sus complementos no estarían en NP:
a) El problema del conjunto dominante de un grafo consiste en determinar si un grafo no
dirigido tiene un conjunto dominante de vértices. Un subconjunto D de vértices de un grafo
G es un conjunto dominante de G, si todo vértice de G fuera de D es adyacente a algún
vértice de D. El lenguaje que representa el problema es:
DOM-SET = {(G, K) | G es un grafo no dirigido y tiene un conjunto dominante de K
vértices}.
b) El problema de los grafos isomorfos consiste en determinar si dos grafos son isomorfos.
Dos grafos son isomorfos si son idénticos salvo por la denominación de sus arcos. P.ej. el
grafo G1 = ({1, 2, 3, 4}, {(1,2), (2,3), (3,4), (4,1)}) es isomorfo al grafo G2 = ({1, 2, 3, 4},
{(1,2), (2,4), (4,3). (3,1)}). El lenguaje que representa el problema es:
ISO = {(G1, G2) | G1 y G2 son grafos isomorfos}. 