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

# 5. Demostrar que cualquier tautología proposicional que esté escrita usando los conectivos ¬, ∨, ∧, → contiene alguna ocurrencia ya sea del símbolo ¬ o del símbolo →.

Se intentará demostrar por inducción que cualquier fórmula que sólo contenga los conectores ∨ y ∧ puede tomar el valor F. Para esto se tomará como ejemplo una fórmula $A$.

Hipótesis inductiva: para toda fórmula A que sólo contenga los conectores ∨ y ∧, con hasta N conectivos, se cumple al menos un caso en el que sea falsa.

Caso base ($N = 0$):
* $A$ es una fórmula unaria.
* Por lo tanto, el valor de $A$ dependerá del valor de su única variable.
* Si $p = F$, entonces $A = F$.

Caso $N + 1$:
* Una fórmula puede tener alguno de estos dos formatos (siendo B y C términos con menos de N conectivos):
    1. $A = B ∨ C$
    2. $A = B ∧ C$
* Al tratarse de operaciones de conjunción y disyunción, existe al menos un caso en el que su resultado sea falso.

Se pudo probar que cualquier fórmula que sólo contenga los conectores ∨ y ∧ puede tomar el valor F. Por lo tanto, estos conectores por sí solos no son suficientes para escribir una tautología, sino que debe haber al menos una ocurrencia de ¬ o →.

# 6.¿Es cierto que en el Cálculo de Enunciados pueden escribirse dos fbfs que tengan diferentes letras de proposición y aún así ambas fbfs sean lógicamente equivalentes?. Fundar.

Dos fbf $A$ y $B$ son lógicamente equivalentes sí y sólo si tienen el mismo valor de verdad para todas sus interpretaciones posibles. Dicho de otra manera, son lógicamente equivalentes si la forma $A ↔ B$ es una tautología.

Por lo tanto, la equivalencia entre dos fórmulas no depende de sus letras de proposición, sino de los resultados finales. Para que esto sea posible, puede establecerse una correspondencia entre las variables.

Un ejemplo de fórmulas lógicamente equivalentes independientemente de sus variables son las tautologías, ya que todas sus interpretaciones posibles son verdaderas. Un ejemplo con letras distintas:
* (p ∨ ¬p): todas sus interpretaciones son verdaderas independientemente del valor de $p$.
* (q → q): es un condicional trivial, en el que al igual que el caso anterior, sus interpretaciones son siempre verdaderas independientemente del valor de $q$.

Para estas dos fórmulas se cumple que $(p ∨ ¬p) ↔ (q → q)$, por lo que son lógicamente equivalentes.

# 7. Para las tablas dadas a continuación, encontrar al menos dos fbf del Cálculo de Enunciados que las tenga por tablas de verdad.

**Ayuda: alcanza con usar p, q, ¬, ∧, ∨.**

## a. 
| p | q | f |
| - | - | - |
| V | V | V |
| V | F | V |
| F | V | V |
| F | F | V |

1. (p ∨ ¬p)
2. (q ∨ ¬q)

## b.
| p | q | f |
| - | - | - |
| V | V | V |
| V | F | F |
| F | V | V |
| F | F | F |

1. q
2. (p ∧ ¬p) ∨ q

## c.
| p | q | f |
| - | - | - |
| V | V | V |
| V | F | V |
| F | V | F |
| F | F | F |

1. p
2. (q ∧ ¬q) ∨ p

# 8. Determinar cuáles de las siguientes fbfs son lógicamente implicadas por la fbf (A ∧ B). Fundamentar.

Una fórmula $X$ implica lógicamente a otra fórmula $Y$ si la forma $X → Y$ es una tautología.

Se intentará demostrar que (A ∧ B) implica lógicamente a las siguientes fórmulas:

## i. A

| A | B | A ∧ B | (A ∧ B) → A |
| - | - | ----- | ----------- |
| V | V |   V   | V |
| V | F |   F   | V |
| F | V |   F   | V |
| F | F |   F   | V |

(A ∧ B) → A es una tautología, por lo que se cumple (A ∧ B) ⇒ A.

## ii. B

| A | B | A ∧ B | (A ∧ B) → B |
| - | - | ----- | ----------- |
| V | V |   V   | V |
| V | F |   F   | V |
| F | V |   F   | V |
| F | F |   F   | V |

(A ∧ B) → B es una tautología, por lo que se cumple (A ∧ B) ⇒ B.

## iii. A ∨ B

| A | B | A ∧ B | A ∨ B | (A ∧ B) → (A ∨ B) |
| - | - | ----- | ----- | ----------------- |
| V | V |   V   | V | V |
| V | F |   F   | V | V |
| F | V |   F   | V | V |
| F | F |   F   | F | V |

(A ∧ B) → (A ∨ B) es una tautología, por lo que se cumple (A ∧ B) ⇒ A ∨ B.

## iv. ¬A ∨ B

| A | B | A ∧ B | ¬A ∨ B | (A ∧ B) → (¬A ∨ B) |
| - | - | ----- | ----- | ------------------- |
| V | V |   V   | V | V |
| V | F |   F   | F | V |
| F | V |   F   | V | V |
| F | F |   F   | V | V |

(A ∧ B) → (¬A ∨ B) es una tautología, por lo que se cumple (A ∧ B) ⇒ ¬A ∨ B.

## v. ¬B → A

| A | B | A ∧ B | ¬B → A | (A ∧ B) → (¬B → A) |
| - | - | ----- | ----- | ------------------- |
| V | V |   V   | V | V |
| V | F |   F   | V | V |
| F | V |   F   | V | V |
| F | F |   F   | F | V |

(A ∧ B) → (¬B → A) es una tautología, por lo que se cumple (A ∧ B) ⇒ ¬B → A.

## vi. A ↔ B

| A | B | A ∧ B | A ↔ B | (A ∧ B) → (A ↔ B) |
| - | - | ----- | ----- | ----------------- |
| V | V |   V   | V | V |
| V | F |   F   | F | V |
| F | V |   F   | F | V |
| F | F |   F   | V | V |

(A ∧ B) → (A ↔ B) es una tautología, por lo que se cumple (A ∧ B) ⇒ A ↔ B.

## vii. A → B

| A | B | A ∧ B | A → B | (A ∧ B) → (A → B) |
| - | - | ----- | ----- | ----------------- |
| V | V |   V   | V | V |
| V | F |   F   | F | V |
| F | V |   F   | V | V |
| F | F |   F   | V | V |

(A ∧ B) → (A → B) es una tautología, por lo que se cumple (A ∧ B) ⇒ A → B.

## viii. ¬B → ¬A

| A | B | A ∧ B | ¬B → ¬A | (A ∧ B) → (¬B → ¬A) |
| - | - | ----- | ----- | ----------------- |
| V | V |   V   | V | V |
| V | F |   F   | F | V |
| F | V |   F   | V | V |
| F | F |   F   | V | V |

(A ∧ B) → (¬B → ¬A) es una tautología, por lo que se cumple (A ∧ B) ⇒ ¬B → ¬A.

# ix. B → ¬A

| A | B | A ∧ B | B → ¬A | (A ∧ B) → (B → ¬A) |
| - | - | ----- | ----- | ----------------- |
| V | V |   V   | F | F |
| V | F |   F   | V | V |
| F | V |   F   | V | V |
| F | F |   F   | V | V |

(A ∧ B) → (B → ¬A) no es una tautología, ya que no se encontró una asignación de valores en la que no es verdadera. Por lo tanto, no se cumple (A ∧ B) ⇒ B → ¬A.

# 9. Sea la relación ≤ tal que dadas fbfs A , B se cumple que A ≤ B si y sólo si A → B es una tautología. Dadas las fbfs: p, p → q, ¬p, p ∧ ¬p, r ∨ ¬r organizarlas bajo la relación ≤. Representar gráficamente.

*// no termino de entender cómo organizar las relaciones así que lo voy a dejar*
## p

### p → q

### ¬p

### p ∧ ¬p

### r ∨ ¬r


## p → q

### p

### ¬p

### p ∧ ¬p

### r ∨ ¬r


## p ∧ ¬p

### p

### p → q

### ¬p

### r ∨ ¬r


## r ∨ ¬r

### p

### p → q

### ¬p

### p ∧ ¬p

# 10. Sea A una fbf donde aparecen sólo los conectivos ∧, ¬. Sea A' la fbf que se obtiene a partir de A reemplazando cada ∧ por ∨ y cada letra de proposición por su negación (o sea, cada p por ¬p, cada q por ¬q, etc.). ¿Es cierto que A' es lógicamente equivalente a ¬A ? Fundamentar.

A partir de una fbf $A$, formada sólo por los conectivos { ∧, ¬ }, se obtiene otra fbf $A'$ que es igual a $A$, pero reemplazando ∧ por ∨ y negando cada preposición.

Se busca demostrar que $A'$ y $¬A$ son lógicamente equivalentes.

Desde la hipótesis podemos sacar algunas conclusiones:
* $¬A$ se obtiene negando los resultados de $A$.
* $A'$ se obtiene a partir de $A$ realizando los siguientes cambios:
    * Los conectivos ∧ se reemplazan por ∨
    * Cada preposición $p$ se reemplaza por $¬p$.

Podemos encontrar ciertas similitudes entre las definiciones de $¬A$ y $A'$ con las leyes de De Morgan, la cual implica que el resultado de la negación de una fbf es igual a esa misma fbf, pero intercambiando sus conectivos ∧ por ∨ (y viceversa) y negando todas las preposiciones. Formalmente se define como:
* ¬(p ∨ q) = ¬p ∧ ¬q
* ¬(p ∧ q) = ¬p ∨ ¬q

A partir de esto podemos considerar que $A'$ se obtiene aplicando las leyes de De Morgan en $A$, por lo que $¬A$ y $A'$ son lógicamente equivalentes.

## b. Ejemplificar con algunos ejemplos concretos escritos en lenguaje natural.

* p: *"mañana llueve"*.
* q: *"mañana hay sol"*.
* $A$: (p ∧ ¬q): *"Mañana llueve y no hay sol"*.
* $A'$: (¬p ∨ q): *"Mañana no llueve o hay sol"*.

| p | q | ¬p | ¬q | p ∧ ¬q | ¬A: ¬(p ∧ ¬q) | A': (¬p ∨ q) | ¬A ↔ A' |
| - | - | -- | -- | ------ | ------------- | ------------ | ------- |
| V | V | F | F | F | V | V | V |
| V | F | F | V | V | F | F | V | 
| F | V | V | F | F | V | V | V |
| F | F | V | V | F | V | V | V |

Como podemos ver, se cumple $¬A ↔ A'$ para todos sus valores de verdad, por lo que son lógicamente equivalentes.

# 11. Sea # el operador binario definido como p#q = def (p ∧ ¬q) ∨ (¬p ∧ q). 

## a. Probar que # es asociativo, es decir, x#(y#z) es lógicamente equivalente a (x#y)#z.

Se quiere demostrar que x#(y#z) ↔ (x#y)#z es una tautología.



| x | y | z | (y#z) | (x#y) | x#(y#z) | (x#y)#z | x#(y#z) ↔ (x#y)#z |
| - | - | - | ----- | ----- | ------- | ------- | ----------------- |
| V | V | V | F | F | V | V | V |
| V | V | F | V | F | F | F | V |
| V | F | V | V | V | F | F | V |
| V | F | F | F | V | V | V | V |
| F | V | V | F | V | F | F | V |
| F | V | F | V | V | V | V | V |
| F | F | V | V | F | V | V | V |
| F | F | F | F | F | F | F | V |

Se cumple x#(y#z) ↔ (x#y)#z para todos sus valores de verdad, por lo que ambas fbf son lógicamente equivalentes. Debido a esto, la operación # es asociativa.

## b. Probar que # es conmutativo, es decir, y#z es lógicamente equivalente a z#y.

| y | z | y#z | z#y | z#y ↔ y#z |
| - | - | --- | --- | --------- |
| V | V | F | F | V |
| V | F | V | V | V |
| F | V | V | V | V |
| F | F | F | F | V |

Se cumple z#y ↔ y#z para todos sus valores de verdad, por lo que ambas fbf son lógicamente equivalentes. Debido a esto, la operación # es conmutativa.

# 12. Demostrar que las siguientes fórmulas son lógicamente equivalentes.

## a. (p → q) es lógicamente equivalente a (¬p ∨ q)

| p | q | ¬p | p → q | ¬p ∨ q | (p → q) ↔ (¬p ∨ q) |
| - | - | -- | ----- | ------ | ---------------- |
| V | V | F | V | V | V |
| V | F | F | F | F | V |
| F | V | V | V | V | V |
| F | F | V | V | V | V |

Como $(p → q) ↔ (¬p ∨ q)$ es una tautología, se cumple que $(p → q)$ y $(¬p ∨ q)$ sean lógicamente equivalentes.

## b. (p ↔ q) es lógicamente equivalente a ((p → q) ∧ (q → p))

| p | q | p ↔ q | p → q | q → p | (p → q) ∧ (q → p) | (p ↔ q) ↔ ((p → q) ∧ (q → p))
| - | - | ----- | ----- | ----- | ----------------- | - | 
| V | V | V | V | V | V | V |
| V | F | F | F | V | F | V |
| F | V | F | V | F | F | V |
| F | F | V | V | V | V | V |

Como $(p ↔ q) ↔ ((p → q) ∧ (q → p))$ es una tautología, se cumple que $(p ↔ q)$ y $((p → q) ∧ (q → p))$ sean lógicamente equivalentes.

## c. (¬(p ∧ q)) es lógicamente equivalente a (¬p ∨ ¬q)

| p | q | p ∧ q | ¬(p ∧ q) | ¬p | ¬q | (¬p ∨ ¬q) | (¬(p ∧ q)) ↔ (¬p ∨ ¬q) |
| - | - | ----- | -------- | -- | -- | --------- | ----------------------- |
| V | V | V | F | F | F | F | V |
| V | F | F | V | F | V | V | V |
| F | V | F | V | V | F | V | V |
| F | F | F | V | V | V | V | V |

Como $(¬(p ∧ q)) ↔ (¬p ∨ ¬q)$ es una tautología, se cumple que $(¬(p ∧ q))$ y $(¬p ∨ ¬q)$ sean lógicamente equivalentes.

## d. (¬(p ∨ q)) es lógicamente equivalente a (¬p ∧ ¬q)

| p | q | p ∨ q | ¬(p ∨ q) | ¬p | ¬q | ¬p ∧ ¬q | (¬(p ∨ q)) ↔ (¬p ∧ ¬q) |
| - | - | ----- | -------- | -- | -- | ------- | ---------------------- |
| V | V | V | F | F | F | F | V |
| V | F | V | F | F | V | F | V |
| F | V | V | F | V | F | F | V |
| F | F | F | V | V | V | V | V |

Como $(¬(p ∨ q)) ↔ (¬p ∧ ¬q)$ es una tautología, se cumple que $(¬(p ∨ q))$ y $(¬p ∧ ¬q)$ sean lógicamente equivalentes.