# 1. Responder breve y claramente los siguientes incisos:

## a. ¿En qué se diferencia un problema de búsqueda de un problema de decisión?

Los problemas que resuelve una Máquina de Turing pueden ser de decisión o de búsqueda.
* Los problemas de decisión intentar obtener una respuesta cuyo valor sea "sí" o "no".
* Los problemas de búsqueda intentan obtener un resultado exacto a partir de los valores de entrada.

Siguiendo el ejemplo de un grafo, en el que se busca obtener el camino desde el nodo 1 hasta el nodo N, un problema de decisión respondería si existe un camino o no, mientras que un problema de búsqueda respondería con el camino completo.

## b. ¿Por qué en el caso de los problemas de decisión, podemos referirnos indistintamente a problemas y lenguajes?

Se pueden usar como sinónimos ya que, en un problema de decisión, una MT acepta el lenguaje que cumpla con las condiciones propuestas por el problema.

## c. En clase se presentó el problema de satisfactibilidad de las fórmulas booleanas, en su forma de decisión: "Dada una fórmula φ, ¿existe una asignación A de valores de verdad que la hace verdadera?" Enunciar el problema de búsqueda asociado.

*"Dada una fórmula φ, ¿qué asignación de valores A la vuelve verdadera?"*

En este caso, lo que se está buscando obtener es la secuencia de valores booleanos que hagan que el valor de φ sea verdadero.

## d. Además de la visión de MT que reconoce lenguajes (visión reconocedora), está la visión de MT que los genera (visión generadora). En el caso del problema del inciso anterior, ¿qué lenguaje generaría la MT de visión generadora que resuelve el problema?

La MT generadora crearía un lenguaje con todas las combinaciones booleanas posibles que vuelvan a la fórmula φ verdadera.

## e. ¿Qué postula la Tesis de Church-Turing?

*Todo lo computable puede ser computado por una Máquina de Turing*.

Esto significa que, a partir del esquema de la Máquina de Turing, se puede resolver cualquier problema que pueda ser resuelto computacionalmente; por el contrario, un problema que no pueda resolverse con una MT no puede resolverse mediante la computación.

## f. ¿Cuándo dos MT son equivalentes? ¿Y cuándo dos modelos de MT son equivalentes?

Dos MT son equivalentes si estas aceptan el mismo lenguaje. Por otro lado, dos modelos de MT son equivalentes si para cada MT de un modelo existe una equivalente en el otro.

# 2. Dado el alfabeto Ʃ = {0, 1}:

## a. Obtener el conjunto Ʃ* y el lenguaje incluido en Ʃ* con cadenas de a lo sumo 2 símbolos.

Ʃ* = { λ, 0, 1, 01, 10, 00, 11, 000, 111, 1100, ... }

L = { λ, 0, 1, 01, 10, 00, 11 }

## b. Dado el lenguaje L = {0<sup>n</sup> 1<sup>n</sup> | n ≥ 0}, calcular Ʃ* ⋂ L, Ʃ* ⋃ L y L<sup>C</sup> con respecto a Ʃ*.

* Ʃ* ⋂ L: L
* Ʃ* ⋃ L: Ʃ*
* L<sup>C</sup>: Ʃ* - L

# 3. En clase se mostró una MT no determinística (MTN) para aceptar las cadenas de la forma ha<sup>n</sup> o hb<sup>n</sup>, con n ≥ 0. Construir una MT determinística (MTD) equivalente.

M = { Q, Ʃ, δ, q0, qA, qR }

Q = { q0, qh, qa, qb, qA, qR }
* q0: estado inicial.
* qh: encontró el símbolo "h" inicial.
* qa: busca un símbolo "a".
* qb: busca un símbolo "b".

Ʃ = { h, a, b, B }

|    | h | a | b | B |
| -- | - | - | - | - |
| q0 | qh, h, R | - | - | - |
| qh | - | qa, a, R | qb, b, R | - |
| qa | - | qa, a, R | - | qA, a, S |
| qb | - | - | qb, b, R | qA, b, S |

*// Considerando que si ya encontró un símbolo "a" no puede tener un símbolo "b".*

# 4. Describir una MT con varias cintas (la idea general), que acepte de la manera más eficiente posible el lenguaje L = {a<sup>n</sup>b<sup>n</sup>c<sup>n</sup> | n ≥ 0}.

Idea general:
1. Copia todos los símbolos "a" en una segunda cinta, hasta que encuentra un símbolo "b". El cabezal termina al final de la cinta 2 y en el primer símbolo "b" de la cinta 1.
1. Desplazarse hacia la derecha en la cinta 1 y hacia la izquierda en la cinta 2. Reemplaza las "a" de la cinta 2 mientras haya una "b" en la cinta 1. El cabezal termina al inicio de la cinta 2 y en el primer símbolo "c" de la cinta 1.
    1. Si encuentra un espacio en blanco o una "c" en la cinta 1, rechaza la entrada.
    1. Si encuentra un espacio en blanco en la cinta 2 cuando tiene que reemplazar un símbolo "a" por uno "b", rechaza la entrada.
1. Desplazarse hacia la derecha en la cinta 1 y hacia la izquierda en la cinta 2. Reemplaza las "b" de la cinta 2 mientras hata una "c" en la cinta 1.
    1. Si encuentra un espacio en blanco en cualquiera de las 2 cintas mientras hay un símbolo en la otra, rechaza la entrada.
1. Si ambos cabezales terminaron en un espacio en blanco, se acepta la entrada.

Definición formal:

M = { Q, Ʃ, δ, q0, qA, qR }

Ʃ = { a, b, c, B }

Q = { q0, qa, qb, qc, qA, qR }
* q0: estado inicial.
* qa: copiando símbolos "a".
* qb: copiando símbolos "b".
* qc: copiando símbolos "c".


1. `δ(q0, (a,B)): qa, (a,R), (a,R)`: si valida que haya una "a" en la primera posición, comienza a escribir en la cinta 2.
2. `δ(qa, (a,B)): qa, (a,R), (a,R)`: mientras haya "a" en la cinta 1 y espacios en blanco en la cinta 2, continúa escribiendo.
3. `δ(qa, (b,B)): qb, (b,R), (B,L)`: una vez que encuentra una "b" en la cinta 1 y se asegura que no haya "a" en la cinta 2, apunta el cabezal en la primer "b" de la cinta 1 y se desplaza a la izquierda en la cinta 2 para comenzar a sobrescribir las "a".
4. `δ(qb, (b,a)): qb, (b,R), (b,L)`: mientras haya "b" en la cinta 1 y "a" en la cinta 2, continúa sobrescribiéndolas.
5. `δ(qb, (c,B)): qc, (c,R), (B,R)`: una vez que encuentra una "c" en la cinta 1 y se asegura que no haya "b" en la cinta 2, apunta el cabezal en la primer "c" de la cinta 1 y se desplaza a la derecha en la cinta 2 para comenzar a sobrescribir las "b".
6. `δ(qc, (c,b)): qc(c,R), (c,R)`: mientras haya "c" en la cinta 1 y "b" en la cinta 2, continúa sobrescribiéndolas.
7. `δ(qc, (B,B)): qA(B,S), (B,S)`: si luego de terminar de copiar las "c" ambas cintas están en su espacio en blanco, significa que había tanta cantidad de "a" como de "b" y "c".

*// CONSULTAR: cuando encuentro el siguiente símbolo en la cinta 1 (como en los puntos 3 o 5) debería desplazarme en la cinta 1 o dejarla en S? CREO que si me muevo queda en una posición más que la cinta 2*

# 5. Describir cómo simular una MT (la idea general) por otra que no tenga el movimiento S (es decir el no movimiento).

Idea general:

Crear una MT que, al llegar a cierto símbolo, simule detenerse moviéndose entre las mismas 2 celdas indefinidamente.

1. La MT en estado *qa* encuentra un símbolo *a* en la posición *k*, indicando que debe detenerse.
2. Cambia al estado *qs* y se desplaza hacia la derecha sin modificar el símbolo.
3. Una vez en la posición *k + 1*, cambia al estado *qb* y se desplaza a la izquierda.

Definición formal:

MT = { Q, Ʃ, δ, q0, qA, qR }

Ʃ = { a, b, B }

Q = { q0, qa, qb, qs, qA, qR }
* q0: estado inicial.
* qa: buscando un símbolo "a".
* qb: buscando un símbolo "b".
* qs: no desplazarse.

Funciones de transición:
1. `δ(q0, a)`: (qa, a, R)
2. `δ(qa, a)`: (qs, a, R)
3. `δ(qs, b)`: (qb, b, L)
3. `δ(qs, B)`: (qb, B, L)

*// CONSULTAR: hacer esto hace que se detenga sólo una vez, pero si cambio el resultado de la FT 3 por (qa, b, L) se terminaría deteniendo indefinidamente. No sé si hay alguna manera de detenerla por ciertos movimientos.*

# 6. En clase se construyó una MT con 2 cintas para aceptar L = {w | w ∈ {a, b}* y w es un palíndromo o "capicúa"}. Construir una MT con una cinta para aceptar L (la solución que vimos para aceptar el lenguaje de las cadenas a<sup>n</sup>b<sup>n</sup>, con n ≥ 1, puede ser un buen punto de partida).

Idea general:

Crear una MT con una cinta que acepte las cadenas en las que, dado un símbolo "a", del otro lado de la cadena haya otro igual.

1. Marca el primer símbolo de la cadena y cambia a un estado para buscar uno igual del otro lado.
2. Va a buscar el último símbolo de la cadena y lo compara con el primero.
    1. Si son iguales, lo marca y vuelve al principio para comparar el segundo símbolo.
    2. Si son distintos, rechaza la entrada.
3. Si volvió al inicio de la cadena, vuelve a realizar este ciclo con el resto de caracteres.
4. Acepta la entrada si todos los caracteres están marcados.

Definición formal:

MT = { Q, Ʃ, δ, q0, qA, qR }

Ʃ = { a, b, a', b', B }

Q = { q0, qa, qb, qr, qn, qA, qR }
* q0: estado inicial.
* qa: desplazándose hacia el final de la cadena buscando el último símbolo "a".
* qb: desplazándose hacia el final de la cadena buscando el último símbolo "b".
* qra: volviendo desde el final para marcar el último símbolo "a".
* qrb: volviendo desde el final para marcar el último símbolo "b".
* qr: volviendo a buscar el primer símbolo sin marcar de la cadena.
* qt: debe obtener el primer símbolo sin marcar.


|    | a | b | a' | b' | B |
| -- | - | - | -- | -- | - |
| q0 | qa, a', R | qb, b', R |
| qa | qa, a, R | qa, b, R | qra, a', L | qra, b', L | qra, B, L |
| qb | qb, a, R | qb, b, R | qrb, a', L | qrb, b', L | qrb, B, L |
| qra | qr, a', L | qR, b, S | qA, a', S | qA, b', S |
| qrb | qR, a, S | qr, b', L | qA, a', S | qA, b', S |
| qr | qr, a, L | qr, b, L | qt, a', R | qt, b', R |
| qt | qa, a', R | qb, b', R | qA, a', S | qB, b', S | qA, B, S |

# 7. Construir una MT que calcule la resta de dos números (se puede considerar la idea de solución propuesta en clase).

Idea general:

Suponiendo los números en sistema unario, copiar el primer término en una segunda cinta e ir eliminando los símbolos del segundo término para obtener el resultado de la resta.

1. Copiar los símbolos en una segunda cinta hasta llegar al caracter de resta.
2. Cambiar los símbolos de la cinta 2 por espacios en blanco hasta que no haya símbolos en la cinta 1.

M = { Q, Ʃ, δ, q0, qA, qR }

Ʃ = { 0, 1, B }

Q = { q0, qe, qr, qA, qR }

* q0: estado inicial
* qe: copiando los símbolos del primer término en la cinta 2.
* qr: eliminando símbolos de la cinta 2 para obtener el resultado.

Funciones de transición:
* `δ(q0(1,B))`: qe(1,1), (R,R)
* `δ(qe(1,B))`: qe(1,1), (R,R)
* `δ(qe(0,B))`: qr(0,B), (R,L)
* `δ(qr(1,1))`: qr(1,B), (R,L)
* `δ(qr(B,1))`: qA(B,1), (S,S)
* `δ(qr(B,B))`: qA(B,B), (S,S)

El resultado quedaría en la cinta 2.

*// CONSULTAR: esto sólo acepta restas positivas y en las que el término 1 >= término 2*

# 8. Construir una MT que genere todas las cadenas de la forma a<sup>n</sup>b<sup>n</sup>, con n ≥ 1 (se puede considerar la idea de solución propuesta en clase).

Para este enunciado habría que construir una MT generadora, la cual no tendría fin: estaría en un bucle generando cadenas en una cinta, separando cada una por un delimitador.

Idea general:
1. Usar una cinta como contador: escribir un símbolo especial en cada vuelta.
2. Escribir los n símbolos "a" en otra cinta hasta que la cinta 1 llegue al espacio en blanco del extremo derecho
3. Escribir los n símbolos "b" en otra cinta hasta que la cinta 1 llegua al espacio en blanco del extremo izquierdo.
4. Aumentar el contador de la cinta contadora y poner un delimitador en la cinta escritora.

Definición formal:

M = { Q, Ʃ, δ, q0, qA, qR }

Ʃ = { a, b, B, #, 1 }

Q = { q0, qa, qb, qA, qR }
* q0: estado inicial.
* qa: escribiendo símbolos "a".
* qb: escribiendo símbolos "b".

Funciones de transición:
* `δ(q0, (B,B))`: qa (B,S), (1,S)
* `δ(qa, (B,1))`: qa (a,R), (1,R)
* `δ(qa, (B,B))`: qb(B,S), (B,L)
* `δ(qb, (B,1))`: qb(b,R), (1,L)
* `δ(qb, (B,B))`: qa(#,R), (1,S)