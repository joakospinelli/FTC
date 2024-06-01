# 1. Retome el Ejercicio 1 de la Práctica 1:
## a. Seleccione un par de enunciados que sean lógicamente equivalentes (que tengan el mismo significado). Demuéstrelo mediante tablas de verdad.

d. Si Juan contrata un informático entonces el proyecto tendrá éxito.
* p: "Juan contrata un informático".
* q: "El proyecto tendrá éxito".

$A_1$: p → q

e. Si el proyecto no tiene éxito entonces Juan no ha contratado un informático.
* p: "Juan contrata un informático".
* q: "El proyecto tendrá éxito".

$A_2$: ¬q → ¬p

| p | q | $A_1$ | $A_2$ |
| - | - | ----- | ----- |
| V | V |   V   |   V   |
| V | F |   F   |   F   |
| F | V |   V   |   V   |
| F | F |   V   |   V   |

## b. Para cada item construya un enunciado que sea lógicamente equivalente.

### a. Juan necesita un matemático o un informático.
* p: "Juan necesita un matemático".
* q: "Juan necesita un informático".

p ∨ q

Equivalencia lógica (usando ley conmutativa de disyunción):

q ∨ p (*Juan necesita un informático o un matemático*).

### b. Si Juan necesita un informático entonces necesita un matemático.
* p: "Juan necesita un matemático".
* q: "Juan necesita un informático".

q → p

Equivalencia lógica (usando el conjunto de conectivas {$ ¬, ∨ $}):

¬q ∨ p (*Juan no necesita un informático o necesita un matemático*).

### c. Si Juan no necesita un matemático entonces necesita un informático.
* p: "Juan necesita un matemático".
* q: "Juan necesita un informático".

¬p → q

Equivalencia lógica (implicando $A → B = ¬B → ¬A$):

¬q → p (*Si Juan no necesita un informático, entonces necesita un matemático*).

### d. Si Juan contrata un informático entonces el proyecto tendrá éxito.
* p: "Juan contrata un informático".
* q: "El proyecto tendrá éxito".

p → q

Equivalencia lógica (usando el conjunto de conectivas {$ ¬, ∨ $}):

¬p ∨ q (*Juan no contrata un informático o el proyecto tendrá éxito*).

### e. Si el proyecto no tiene éxito entonces Juan no ha contratado un informático.
* p: "Juan contrata un informático".
* q: "El proyecto tendrá éxito".

¬q → ¬p

Equivalencia lógica (implicando $A → B = ¬B → ¬A$):

p → q (*Si Juan contrata a un informático, entonces el proyecto tendrá éxito*).

### f. El proyecto tendrá éxito si y sólo si Juan contrata un informático.
* p: "Juan contrata un informático".
* q: "El proyecto tendrá éxito".

q ↔ p

Equivalencia lógica (implicando la negación del bicondicional):

¬q ↔ ¬p (*El proyecto no tendrá éxito si y sólo si Juan no contrata un informático*).

### g. Para aprobar Lógica, el alumno debe asistir a clase, desarrollar un cuaderno de prácticas aceptable y demostrar que dicho cuaderno ha sido desarrollado por él; o desarrollar un cuaderno de prácticas aceptable y aprobar el examen final.
* p: "El alumno aprueba Lógica".
* q: "El alumno asiste a clase".
* r: "El alumno desarrolla un cuaderno de prácticas".
* s: "El alumno demuestra que el cuaderno de prácticas es suyo".
* t: "El alumno aprueba el exámen final".

((q ^ r ^ s) ∨ (r ^ t)) → p

Equivalencia lógica (usando el conjunto de conectivas {$ ¬, ∨ $}):

¬((q ^ r ^ s) ∨ (r ^ t)) ∨ p

Aplicando la ley de De Morgan en el primer término:

(¬(q ^ r ^ s) ^ ¬(r ^ t)) ∨ p (*El alumno no asiste a clases, ni desarrolla el cuaderno de prácticas ni demuestra que es suyo y además no desarrolla el cuaderno de prácticas ni aprueba el final, o aprueba la cursada*).

### h. El alumno puede asistir a clase u optar por un examen libre.
* p: "El alumno asiste a clase".
* q: "El alumno rinde el examen libre".

p ∨ q

Equivalencia lógica (usando ley conmutativa de disyunción):

q ∨ p (*El alumno puede optar por un examen libre o asistir a clase*).

### i. Si x es un número racional e y es un entero, entonces z no es real.
* p: "x es un número racional".
* q: "y es un número entero".
* r: "z es un número real".

(p ^ q) → ¬r

Equivalencia lógica (implicando $A → B = ¬B → ¬A$):

r → ¬(p ^ q)

Aplicando la ley de De Morgan en el segundo término:

r → (¬p ∨ ¬q) (*Si "z" es un número real, entonces "x" no es un número racional o "y" no es un número entero*).


### j. La suma de dos números es par si y sólo si los dos números son pares o los dos números son impares
* p: "La suma dos números es par".
* q: "Los dos números son pares".
* r: "Los dos números son impares".

p ↔ (q ∨ r)

Equivalencia lógica (usando ley conmutativa del bicondicional):

(q ∨ r) ↔ p (*Dos números son pares o impares si y sólo si la suma de los dos es par*).

# 2. Sean A, B fórmulas bien formadas que cumplen que (¬A ∨ B) es tautología. Sea C una fbf cualquiera. Determinar, si es posible, cuáles de las siguientes fbfs son tautologías y cuáles contradicciones. Justificar las respuestas.

## a. ((¬(A → B)) → C)

Se quiere demostrar que la fórmula es verdadera para todos los valores posibles de sus variables.

* Se sabe que $(¬A ∨ B) = V$.
* Usando equivalencias lógicas, se puede demostrar que $(¬A ∨ B) = A → B$.
* Por lo tanto, $A → B = V$.
* A partir de esto, sabemos que el primer término de la fórmula siempre va a ser falso.
* Al tratarse de una fórmula condicional, si el primer término es falso, su valor final siempre será verdadero independientemente del valor del segundo término.
* Por lo tanto, $((¬(A → B)) → C)$ es una tautología.


## b. (C → ((¬A) ∨ B))

Se quiere demostrar que la fórmula es verdadera para todos los valores posibles de sus variables.

* Se sabe que $(¬A ∨ B) = V$.
* Por lo tanto, el segundo término de la fórmula siempre será verdadero.
* Al tratarse de una fórmula condicional, si el segundo término es verdadero, su valor final siempre será verdadero independientemente del valor del primer término.
* Por lo tanto, $(C → ((¬A) ∨ B))$ es una tautología.

## c. ((¬A) → B)

Se quiere demostrar que la fórmula es verdadera para todos los valores posibles de sus variables.

* Se sabe que $(¬A ∨ B) = V$.
* A partir de esta tautología no puede encontrarse una equivalencia útil para resolver la fórmula.
* Por lo tanto, no se puede demostrar que $((¬A) → B)$ sea una tautología ni una contradicción.

# 3. ¿Es cierto que dadas A y B fbfs cualesquiera, siempre ocurre que si A y A → B son tautologías entonces B también lo es? Fundamentar. Ejemplificar con algunos ejemplos concretos escritos en lenguaje natural.

Se quiere demostrar que $B$ es una tautología.

Se tienen las siguientes hipótesis:
* $A$ es una tautología.
* $(A → B)$ es una tautología.

A partir de esto, $(A → B)$ puede escribirse como $(V → B) = V$.

Considerando que la fbf es un condicional, se cumple $(V → B) = V$ si y sólo si $B = V$. Por lo tanto, a partir de las hipótesis propuestas, se puede demostrar que $B$ es una tautología.

Ejemplo con lenguaje natural:
* *"Si hay nubes, entonces llueve."*
* p: "*Hay nubes*".
* q: "*Llueve*".
* p → q
* Si el enunciado es correcto y se sabe que hay nubes, entonces necesariamente debe llover.

# 4. Sea A una fbf donde aparecen sólo los conectivos ∧, ∨, ¬ . Sea A' la fbf que se obtiene a partir de A reemplazando cada ∧ por ∨ y cada ∨ por ∧. ¿Si A es una tautología, A' también lo es? Justificar. Ejemplificar con algunos ejemplos escritos en lenguaje natural.

Hipótesis:
* Se tienen dos fórmulas bien formadas $A$ y $A'$.
* $A'$ se obtiene a partir de $A$, reemplazando los conectores ∧ por ∨ respectivamente.

Se buscará demostrar que esta propiedad es inválida a partir de un contra-ejemplo:

* Para el contra-ejemplo se supondrá $A = p ∨ ¬p$.
* $A$ es una tautología.
* A' = p ^ ¬p, invirtiendo los conectores de $A$.
* La tabla de verdad de $A'$ sería:
    | p | ¬p | p ^ ¬p |
    | - | -- | ------ |
    | V | F  | F      |
* Por lo tanto, $A'$ no es una tautología (*de hecho es una contradicción ☝🤓*).

*// esto estaría bueno demostrarlo también x inducción y absurdo para practicar*