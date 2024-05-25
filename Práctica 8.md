# 1. Traduzca al lenguaje simbólico los siguientes enunciados:

## a. Juan necesita un matemático o un informático.

* p: *"Juan necesita un matemático"*.
* q: *"Juan necesita un informático"*.

p ∨ q

## b. Si Juan necesita un informático entonces necesita un matemático.

* p: *"Juan necesita un matemático"*.
* q: *"Juan necesita un informático"*.

q → p

## c. Si Juan no necesita un matemático entonces necesita un informático.

* p: *"Juan necesita un matemático"*.
* q: *"Juan necesita un informático"*.

¬p → q

## d. Si Juan contrata un informático entonces el proyecto tendrá éxito.

* p: *"Juan contrata un informático"*.
* q: *"El proyecto tendrá éxito"*.

p → q

## e. Si el proyecto no tiene éxito entonces Juan no ha contratado un informático.

* p: *"Juan contrata un informático"*.
* q: *"El proyecto tendrá éxito"*.

¬q → ¬p

## f. El proyecto tendrá éxito si y sólo si Juan contrata un informático.

* p: *"Juan contrata un informático"*.
* q: *"El proyecto tendrá éxito"*.

q ↔ p

## g. Para aprobar Lógica, el alumno debe asistir a clase, desarrollar un cuaderno de prácticas aceptable y demostrar que dicho cuaderno ha sido desarrollado por él; o desarrollar un cuaderno de prácticas aceptable y aprobar el examen final.

* p: *"El alumno aprueba Lógica"*.
* q: *"El alumno asiste a clase"*.
* r: *"El alumno desarrolla un cuaderno de prácticas"*.
* s: *"El alumno demuestra que el cuaderno de prácticas es suyo"*.
* t: *"El alumno aprueba el exámen final"*.

((q ^ r ^ s) ∨ (r ^ t)) → p

## h. El alumno puede asistir a clase u optar por un examen libre.

* p: *"El alumno asiste a clase"*.
* q: *"El alumno rinde el examen libre"*.

p ∨ q

## i. Si x es un número racional e y es un entero, entonces z no es real.

* p: *"x es un número racional"*.
* q: *"y es un número entero"*.
* r: *"z es un número real"*.

(p ^ q) → ¬r

## j. La suma de dos números es par si y sólo si los dos números son pares o los dos números son impares

* p: *"La suma dos números es par"*.
* q: *"Los dos números son pares"*.
* r: *"Los dos números son impares"*.

p ↔ (q ∨ r)

# 2. Dada la siguiente información: Si el unicornio es mítico, entonces es inmortal, pero si no es mítico, entonces es un mamífero mortal. Si el unicornio es o inmortal o un mamífero, entonces tiene un cuerno. El unicornio es mágico si tiene un cuerno.

* p: *"El unicornio es mítico"*.
* q: *"El unicornio es inmortal"*.
* r: *"El unicornio es mamífero"*.
* s: *"El unicornio tiene un cuerno"*.
* t: *"E unicornio es mágico"*.

Premisas:
1. p → q
2. ¬p → (r ^ ¬q)
3. (q ∨ r) → s
4. s → t

## a. El unicornio es mítico?. Fundamentar.

A partir del enunciado se toma la conclusión $A = p$. Se busca encontrar un caso en el que la argumentación sea inválida. Para esto se asumirá $p = F$ y se buscará encontrar una premisa que sea falsa.

$A2$ (¬p → (r ^ ¬q)):
* p es F.
* $A2$ es verdadero con $r = V$ y $q = F$.

$A1$ (p → q):
* p es F.
* q es F.
* $A1$ es verdadero.

$A3$ ((q ∨ r) → s):
* q es F.
* r es V.
* $A3$ es verdadero con $s = V$.

$A4$ (s → t):
* s es V.
* $A4$ es verdadero con $t = V$.

Se encontró un caso en el que todas las premisas son verdaderas, a pesar de que la conclusión sea falsa. Por lo tanto, la argumentación es inválida.

## b. El unicornio no es mítico?. Fundamentar.

A partir del enunciado se toma la conclusión $A = ¬p$. Se busca encontrar un caso en el que la argumentación sea inválida. Para esto se asumirá $p = V$ y se buscará encontrar una premisa que sea falsa.

$A1$ (p → q):
* p es V.
* $A1$ es verdadero con $q = V$.

$A2$ (¬p → (r ^ ¬q)):
* p es V.
* q es V.
* Al tratarse de un condicional, si el primer término es falso el resultado es verdadero independientemente del valor del segundo término.
* $A2$ es verdadero.

$A3$ ((q ∨ r) → s):
* q es V.
* Al tratarse de una operación de disyunción, el valor de r no importa.
* $A3$ es verdadero con $s = V$.

$A4$ (s → t):
* s es V.
* $A4$ es verdadero con $t = V$.

Se encontró un caso en el que todas las premisas son verdaderas, a pesar de que la conclusión sea falsa. Por lo tanto, la argumentación es inválida.

## c. El unicornio es mágico?. Fundamentar.

A partir del enunciado se toma la conclusión $A = t$. Se busca encontrar un caso en el que la argumentación sea inválida. Para esto se asumirá $t = F$ y se buscará encontrar una premisa que sea falsa.

$A4$ (s → t):
* t es F.
* $A4$ es verdadero con $s = F$.

$A3$ ((q ∨ r) → s):
* s es F.
* $A3$ es verdadero con $q = F$ y $r = F$.

$A2$ (¬p → (r ^ ¬q)):
* r es F.
* q es F.
* $A2$ es verdadero con $p = V$.

$A1$ (p → q):
* p es V.
* q es F.
* $A1$ es falso.

No se encontró el caso en el que todas las premisas sean verdaderas, incluso considerando la conclusión como falsa. Por lo tanto, la argumentación es válida.

# 3. La página web tiene un error o el examen de álgebra no es el 2 de julio. Si el examen de álgebra es el 2 de julio entonces la página web tiene un error. El examen de álgebra es el 14 de julio si y sólo si la página web tiene un error y el período de exámenes no termina el 10 de julio. Teniendo en cuenta que el período de exámenes termina el 10 de julio y que la página web tiene un error, deducir la verdad o falsedad de los siguientes enunciados:

* p: *"La página web tiene un error"*.
* q: *"El examen de álgebra es el 2 de julio"*.
* r: *"El examen de álgebra es el 14 de julio"*.
* s: *"El período de exámenes termina el 10 de julio"*.

Premisas:
1. p ∨ ¬q
2. q → p
3. r ↔ (p ^ ¬s)

A partir del enunciado se sabe que $p = V$, $s = V$. Reemplazando estos valores las premisas quedan de la siguiente manera:
1. V ∨ ¬q = V
2. q → V = V
3. r ↔ (V ^ ¬V) = r ↔ F = ¬r

## a. El examen de álgebra es el 2 de julio.

A partir del enunciado se toma la conclusión $A = q$. Se busca encontrar un caso en el que la argumentación sea inválida. Para esto se asumirá $q = F$ y se buscará encontrar una premisa que sea falsa.

$A1$ y $A2$ siempre son verdaderas.

$A3$ es verdadera con $r = F$.

Se encontró un caso en el que todas las premisas son verdaderas, a pesar de que la conclusión sea falsa. Por lo tanto, la argumentación es inválida.

## b. Si la página web no tiene un error entonces el examen de álgebra es el 14 de julio.

A partir del enunciado se toma la conclusión $A = ¬p → r$. Se busca encontrar un caso en el que la argumentación sea inválida. Para esto se asumirá $A = F$ y se buscará encontrar una premisa que sea falsa.

Para que se cumpla $A = F$, debe elegirse una asignación de valores para ¬p → r que su resultado sea falso.
* Como se garantiza que $p$ es verdadero, su valor no puede modificarse.
* Al tratarse de un condicional, como el primer término es falso no puede obtenerse un resultado falso.

A partir de esto, se concluye que la conclusión siempre será verdadera, por lo que la argumentación es válida.

# 4. Se tienen las siguientes premisas:

* p: *"Juan tiene suerte"*.
* q: *"Llueve"*.
* r: *"Juan estudia"*.
* s: *"Juan aprueba"*.

1. Si Juan tiene suerte y llueve entonces estudia: (p ^ q) → r
2. Juan aprobará si y sólo si estudia o tiene suerte: s ↔ (r ∨ p)
3. Si Juan no tiene suerte entonces no llueve: ¬p → ¬q

Se sabe que llueve ($q = V$). Por lo que las premisas quedarían de la siguiente manera:

1. (p ^ V) → r = p → r
2. s ↔ (r ∨ p)
3. ¬p → ¬V = ¬p → F = p

## a. ¿Aprobará Juan?

A partir del enunciado se toma la conclusión $A = s$. Se busca encontrar un caso en el que la argumentación sea inválida. Para esto se asumirá $s = F$ y se buscará encontrar una premisa que sea falsa.

$A3$ es verdadero con $p = V$.

$A1$ es verdadero con $r = V$.

$A2$ s ↔ (r ∨ p):
* s es F.
* p es V.
* r es V.
* (r ∨ p) es V.
* Al tratarse de un bicondicional, $A2$ es falso.

No se encontró el caso en el que todas las premisas sean verdaderas, incluso considerando a la conclusión como falsa. Por lo tanto, la argumentación es válida.

## b. ¿Tendrá suerte Juan?

A partir del enunciado se toma la conclusión $A = p$. Se busca encontrar un caso en el que la argumentación sea inválida. Para esto se asumirá $p = F$ y se buscará encontrar una premisa que sea falsa.

*// SIEMPRE ES NECESARIO HACER TODAS LAS PREMISAS AUNQUE ENCUENTRES UNA FALSA A LA PRIMERA???*

$A3$ es falso.

$A1$ es verdadero independientemente del valor de $r$.

$A2$ es verdadero con $s = V$.

No se encontró el caso en el que todas las premisas sean verdaderas, incluso considerando a la conclusión como falsa. Por lo tanto, la argumentación es válida.