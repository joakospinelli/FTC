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

Ʃ = L1 ∪ B

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

## b. La clase RE es cerrada con respecto a la operación de intersección. 

# 4. Sean L1 y L2 dos lenguajes recursivamente numerables de números naturales codificados en unario (por ejemplo, el número 5 se representa con 11111). Probar que también es recursivamente numerable el lenguaje L = {x | x es un número natural codificado en unario, y existen y, z, tales que y + z = x, con y ∈ L1, z ∈ L2}. Ayuda: la prueba es similar a la vista en clase, de la propiedad de clausura de la clase RE con respecto a la operación de concatenación.


# 5. Dada una MT M1 con alfabeto Ʃ = {0, 1}:
## a. Construir una MT M2 que determine si L(M1) tiene al menos una cadena.

## b. ¿Se puede construir además una MT M3 para determinar si L(M1) tiene a lo sumo una cadena? Justificar.
