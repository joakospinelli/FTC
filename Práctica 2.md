# 1. Responder breve y claramente los siguientes incisos:
## a. ¿En qué difieren entre sí los lenguajes recursivos, los lenguajes recursivamente numerables no recursivos, y los lenguajes no recursivamente numerables?

* Un lenguaje es **recursivo (R)** si existe una MT que lo acepte y se detenga en todos los casos. Son un subconjunto de los **recursivamente numerables**.
* Un lenguaje es **recursivamente enumerable (RE)** si existe una MT que lo acepte, pero no siempre se detenga.
* Los lenguajes **recursivamente enumerables no recursivos** son aquellos que forman parte del conjunto `R - RE`. Estos lenguajes tienen uma MT que los acepte, pero hay casos en los que no se detiene. Son un subconjunto directo de Ł (todos los lenguajes).
* Los lenguajes **no recursivamente numerables (CO-RE)** son aquellos que forman parte del conjunto RE<sup>C</sup> (o Ł - RE). Estos lenguajes pueden no tener una MT que los acepte.

## b. Probar que R ∈ RE ∈ Ł.

Siguiendo las definiciones:
* Todo lenguaje L ∈ R debe cumplir:
    1. Si la entrada ∈ L, entonces la MT siempre se detendrá en el estado `qA`.
    2. Si la entrada ∉ L, entonces la MT siempre se detendrá en el estado `qR`.
* Todo lenguaje L ∈ RE debe cumplir:
    1. Si la entrada ∈ L, entonces la MT siempre se detendrá en el estado `qA`.
    2. Si la entrada ∉ L, entonces pueden darse dos casos:
        1. La MT se detendrá en el estado `qR`.
        2. La MT entrará en bucle.

Los lenguajes que pertenecen a R son un subconjunto de RE formado por aquellos L que cumplan las propiedades `1` y `2.a`, por lo tanto R ∈ RE.

Por último, en Ł se encuentran todos los lenguajes posibles, independientemente del estado final de sus MT o si entran en bucle o no; por lo tanto, RE es un subconjunto de Ł formado por aquellos lenguajes que que sus MT siempre terminan si su entrada es aceptada, pero podrían no terminar cuando su entrada no pertenece al lenguaje.

## c. ¿Qué lenguajes de la clase CO-RE tienen MT que los aceptan? ¿También los deciden?

1. El conjunto CO-RE está formado por los lenguajes resultantes de la operación RE<sup>C</sup> (o RE - Ł).
2. El conjunto R está formado por los lenguajes resultantes de la operación RE ⋂ CO-RE.
3. Por definición, los L ∈ R **siempre** tienen una MT que los acepte.

Por lo tanto, los lenguajes de CO-RE que tienen una MT que los acepte son aquellos pertenecientes a R.

## d. Justificar por qué los lenguajes universal Ʃ* y vacío ∅ son recursivos.

Ʃ* es recursivo porque, al incluir todas las cadenas posibles, su MT siempre va a aceptar cualquier entrada.

∅ es recursivo porque, al no tener ninguna cadena, su MT va a rechazar cualquier entrada sin entrar en bucle.

## e. Justificar por qué un lenguaje finito es recursivo.

Al tratarse de un lenguaje finito, la MT que lo genera no lo hará de manera indefinida, sino que eventualmente terminará con un número determinado de cadenas.

Por definición, una MT debe aceptar aquellas cadenas que pertenezcan al lenguaje. Como se sabe exactamente cuáles son las cadenas pertenecen a este y cuáles no, M siempre finalizará, ya sea como `qA` o `qR`.

Dado que la MT siempre finaliza, se trata de un lenguaje recursivo.

## f. Justificar por qué si L1 ∈ CO-RE y L2 ∈ CO-RE, entonces (L1 ⋂ L2) ∈ CO-RE.

* Por definición de intersección, los elementos del conjunto L1 ⋂ L2 forma parte de L1 o de L2.
* Tanto L1 como L2 ∈ CO-RE, por lo tanto cada uno de sus elementos ∈ CO-RE.
* Como todos los elementos de L1 y L2 ∈ CO-RE, y los elementos de L1 ⋂ L2 son parte de alguno de estos dos conjuntos, todos los elementos de la intersección ∈ CO-RE.
* Por lo tanto, L1 ⋂ L2 ∈ CO-RE.

*// CONSULTAR: quedó medio básica esta rta, no sé si había que hacerlo con teoría de conjuntos ☝🤓*

# 2. Considerando el Lema 2 estudiado en la Clase 2:
## a. ¿Cómo implementaría copiar la entrada w en la cinta 2 de la MT M?

**Lema 2: si L1 y L2 ∈ R, entonces L1 ⋂ L2 ∈ R**.

Para resolverlo usa dos MT (M1 y M2) dentro de M, las cuales aceptan los lenguajes de L1 y L2 respectivamente. M2 recibe como entrada las cadenas aceptadas por M1 (es decir, que pertenecían a L1); por lo tanto, si M2 acepta esta entrada quiere decir que formaba parte tanto de L1 como de L2, por lo tanto L1 ⋂ L2. 

M = { Q ,Ʃ, δ, q0, qA, qB }

Ʃ = L1 ∪ B

Q = { q0, qe, qn, qA, qB }
* q0: estado inicial.
* qe: escribiendo en cinta 2.
* qn: continúa con la próxima MT *(según el ejemplo de la clase, se ejecutaban secuencialmente)*

*// suponiendo "x" como cualquier símbolo ∈ Ʃ y "z" como cualquier símbolo ∉ Ʃ*

Función de transición:
* `δ(q0, (B,B))`: qe, (B,R), (B,S)
* `δ(qe, (x,B))`: qe, (x,R), (x,R)
* `δ(qe, (z,B))`: qR, (B,S), (B,S)
* `δ(qe, (B,B))`: qn, (B,S), (B,S)

## b. ¿Cómo implementaría borrar el contenido de la cinta 2 de la MT M?

M = { Q ,Ʃ, δ, q0, qA, qR }

Ʃ = L2 ∪ B

Q = { q0, qb, qA, qR }
* q0: estado inicial.
* qb: borrando contenido.

*// suponiendo "x" como cualquier símbolo ∈ Ʃ y "z" como cualquier símbolo ∉ Ʃ*

Función de transición:
* `δ(q0, (B,B))`: qb, (B,S), (B,L)
* `δ(qb, (B,x))`: qb, (B,S), (#,L)
* `δ(qb, (B,y))`: qR, (B,S), (y,S)
* `δ(qb, (B,B))`: qA, (B,S), (B,S)

*// CONSULTAR: esto lo hice como si estuviese modelando la M1 y M2. Lo tendría que haber hecho modelando la M directamente? en ese caso habría que cambiar los estados nomás*

# 3. Probar:
## a. La clase R es cerrada con respecto a la operación de unión.

Demostrar que L1 ∪ L2 ∈ R. Se suponen dos MT M1 y M2 que aceptan L1 y L2 respectivamente, dentro de una MT M que las ejecuta secuencialmente.

Al tratarse de una unión, con que sólo una de M1 o M2 acepte la entrada ya podemos suponer que forma parte del lenguaje L1 ∪ L2 (no es necesaria la verificación en ambas como en la intersección). Como ambos conjuntos ∈ R, por definición se sabe que su unión también.

Idea general:
1. Copiar la entrada en una segunda cinta.
2. La M1 itera sobre los elementos de la cinta.
    1. Si todos los símbolos ∈ L1, pasa al estado `qA1`.
    2. Si encuentra un elemento que no, pasa al estado `qR1`.
3. Una vez que terminó la ejecución de M1, pueden ocurrir dos casos según el estado con el que finalice:
    1. Si aceptó la entrada, se puede confirmar que la entrada pertenece a L1 ∪ L2.
    2. Si rechazó la entrada, se debe ejecutar M2 para saber si la entrada ∈ L2.
4. Al terminar de ejecutar M1 y M2, si al menos una de las 2 MT aceptó la entrada, se puede concluir que L1 ∪ L2 ∈ R.

M = { Q<sub>M</sub>, Ʃ<sub>M</sub>, δ<sub>M</sub>, q0, qA<sub>M</sub>, qR<sub>M</sub> }

M1 = { Q<sub>M1</sub>, Ʃ<sub>M1</sub>, δ<sub>M1</sub>, q0, qA<sub>M1</sub>, qR<sub>M1</sub> }

M2 = { Q<sub>M2</sub>, Ʃ<sub>M2</sub>, δ<sub>M2</sub>, q0, qA<sub>M2</sub>, qR<sub>M2</sub> }

Ʃ<sub>M</sub> = Ʃ<sub>M1</sub> ∪ Ʃ<sub>M2</sub>

Q<sub>M</sub> = Q<sub>M1</sub> ∪ Q<sub>M2</sub> ∪ { q0, qc, qr, qa<sub>Mi</sub>, qw, qA, qR }
* q0: estado inicial
* qc: copiando en cinta 2.
* qr: vuelve al inicio de la fila.
* qa<sub>Mi</sub>: la MT Mi revisa la cinta.

Funciones de transición:
* q0(x,B): qc(x,S), (B,S)
* qc(x,B): qc(x,R), (x,R)
* qc(B,B): q0<sub>M1</sub> (B,R), (B,R)
* q0<sub>M1</sub>(x,x): qa<sub>M1</sub>(x,R), (x,R) *// para todo "x" ∈ Ʃ<sub>M1</sub>*
* qa<sub>M1</sub>(B,B): qA<sub>M1</sub>(B,S), (B,S)
* qA<sub>M1</sub>(B,B): qA(B,S), (B,S)
* qR<sub>M1</sub>(B,B): q0<sub>M2</sub>(B,S), (B,S)
* qA<sub>M2</sub>(B,B): qA(B,S), (B,S)
* qR<sub>M2</sub>(B,B): qR (B,S), (B,S)

## b. La clase RE es cerrada con respecto a la operación de intersección. 

Demostrar que L1 ⋂ L2 ∈ RE. Se suponen dos MT M1 y M2 que aceptan L1 y L2 respectivamente, dentro de una MT M que las ejecuta secuencialmente.

A diferencia del conjunto recursivo, con los lenguajes ∈ RE no se puede garantizar que las MT que los aceptan finalicen correctamente; con que una de las dos permanezca en bucle, M también lo hará.

Además, al tratarse de una intersección, la entrada debe pasar por las dos MT para poder ser aceptada. 

# 4. Sean L1 y L2 dos lenguajes recursivamente numerables de números naturales codificados en unario (por ejemplo, el número 5 se representa con 11111). Probar que también es recursivamente numerable el lenguaje L = {x | x es un número natural codificado en unario, y existen y, z, tales que y + z = x, con y ∈ L1, z ∈ L2}

* L1 ∈ RE
* L2 ∈ RE
* L(M1) = L1
* L(M2) = L2
* L = L1 * L2
* Demostrar que L ∈ RE

Como L1 y L2 son números escritos en lenguaje unario, la suma de dos números sería lo mismo que la concatenación de símbolos 1. Se busca construir una máquina M que compruebe que L ∈ RE.

Al tratarse de lenguajes de RE, no se puede garantizar la finalización de L1 o L2; por lo tanto, tampoco se puede confirmar para L. Debido a esto la comprobación debe realizarse ejecutando M1 y M2 concurrentemente.

# 5. Dada una MT M1 con alfabeto Ʃ = {0, 1}:
## a. Construir una MT M2 que determine si L(M1) tiene al menos una cadena.

## b. ¿Se puede construir además una MT M3 para determinar si L(M1) tiene a lo sumo una cadena? Justificar.
