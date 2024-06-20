# 1.
## a. Expresar en lenguaje de predicados de primer orden las siguientes afirmaciones:

### i. Algunas aves no vuelan

*"Existen animales "x" que son aves y no vuelan"*.

* $A(x)$: x es un ave.
* $V(x)$: x vuela.

$(∃x) (A(x) ∧ ¬V(x))$

*// tendría que consultar si está bien escribir los predicados así o si tengo que respetar el $P^1_1(x)$*

### ii. No todas las aves vuelan

*"No es el caso que, para todo animal "x", se cumpla que si son aves entonces vuelen"*.

* $A(x)$: x es un ave.
* $V(x)$: x vuela.

$¬(∀x) (A(x) → V(x))$

## b. Analizar la relación entre ambas. Mostrar cómo se puede transformar una expresión en otra.

*// es literal el ejemplo de la teoría*

Tenemos dos afirmaciones en lenguaje de predicados con las mismas premisas:
1. $(∃x) (A(x) ∧ ¬V(x))$
2. $¬(∀x) (A(x) → V(x))$

Como vemos, la 1 usa el cuantificador existencial y la 2 usa el cuantificador universal (negado).

Para facilitar la comparación, se transformará la fórmula 2 siguiendo algunas propiedades booleanas:
* $¬(∀x) (A(x) → V(x))$
* $¬(∀x) (¬A(x) ∨ V(x))$
* $¬(∀x) ¬(A(x) ∧ V(x))$

De esta manera, obtenemos dos fórmulas similares, aunque con cuantificadores distintos:
1. $(∃x) (A(x) ∧ ¬V(x))$
2. $¬(∀x) ¬(A(x) ∧ ¬V(x))$

Al comparar estas fórmulas finales, podemos concluir que los enunciados con cunatificadores existenciales son equivalentes a aquellas con el cuantificador universal negado y que además nieguen las propiedades.

Intuitivamente, podemos concluir que estas dos frases son iguales:
* No es el caso que, para todo X, no tengan la propiedad P.
* Existe algún X con la propiedad P.

# 2. Escribir las siguientes proposiciones usando un lenguaje de predicados de primer orden:

## a. El cero es el menor natural.

*"Para todo objeto "x" se cumple que, si es un número natural distinto a 0, entonces 0 es menor que él"*.

Predicados:
* $N(x)$: x es un número natural.
* $D(x,y)$: x es distinto a y.
* $M(x,y)$: x es menor a y.

Constantes:
* 0: representa al número cero.

Variables:
* x: representa un número cualquiera.

$(∀x)((N(x) ∧ D(x,0) → M(0,x)))$

## b. El conjunto vacío está incluido en cualquier conjunto.

*"Para todo objeto "x" se cumple que, si es un conjunto, el conjunto vacío está incluído en él"*.

Predicados:
* $C(x)$: x es un conjunto.
* $I(x,y)$: el conjunto x incluye al conjunto y.

Constantes:
* ⊘: representa al conjunto vacío.

Variables:
* x: representa un número cualquiera.

$(∀x) (C(x) → I(x,⊘))$

## c. Si se prueba una propiedad para el cero y luego se prueba que esa misma propiedad vale para el número n+1 , si vale para n entonces se ha probado que la propiedad vale para cualquier número natural.

*"Para todo objeto "x" se cumple que, si es una propiedad que se probó para el 0 y vale para el número n+1, entonces vale para cualquier número natural"*.

Predicados:
* P(x): x es una propiedad en los números naturales.
* C(x,y): x es una propiedad válida sobre el número y.
* N(x): x es un número natural.

Constantes:
* 0: representa al número 0.

Variables:
* 0: representa al número 0.
* x,n: representan a un número natural cualquiera.
* p: representa una propiedad cualquiera.

Funciones:
* $f(x)$: función para obtener al sucesor del número x.

$(∀p) (((P(p) ∧ C(p,0) ∧ C(p,f(n))) → C(p,n)) → (∀x) (N(x) → C(p,x)))$

Voy a escribir con palabras lo de arriba porque sino no lo entiendo:

*Si "p" es una propiedad que se cumple en 0 y en n+1, y entonces se cumple en n, para todo "x" se cumple que, si "x" es un número natural, entonces "p" se cumple en "x".*

## d. Si hay un número natural que cumple cierta propiedad, entonces hay un mínimo natural que cumple esa propiedad.

*// un mínimo natural sería un número menor a x?*

*"Para todo objeto "p" se cumple que, si existe al menos un número natural "x" sobre el cual se aplique la propiedad "p", entonces hay otro número natural menor a "x" sobre el cual también se aplica"*.

Predicados:
* $P(x)$: x es una propiedad.
* $N(x)$: x es un número natural.
* $C(x,y)$: x es una propiedad válida sobre el número y.
* $M(x,y)$: el número x es menor al número y.

Variables:
* x,y: representan un número cualquiera.
* p: representa una propiedad cualquiera.

$(∀p) ((P(p) → (∃x) (N(x) ∧ C(p,y))) → (∃y) ((N(y) ∧ M(y,x)) → (C(p,y))))$

# 3. Expresar en lenguaje de predicados de primer orden el conocimiento asociado a las siguientes situaciones:

## a. Todos los alumnos de LeIA, cuyo documento es par y han aprobado el parcial con nota mayor a 7 están inscriptos en la mesa de finales de agosto.

*"Para todo objeto "x" se cumple que, si "x" es un alumno de LeIA con documento par y aprobó el parcial con más de 7, entonces "x" está inscripto a la mesa de finales de agosto"*.

Predicados:
* $A(x,y)$: "x" es alumno de la materia "y".
* $D(x)$: el número "x" es par.
* $P(x,y)$: "x" aprobó el parcial de la matería "y".
* M(x,y): el número "x" es mayor al número "y".
* $F(x, y)$: "x" está inscripto en la mesa de finales del mes "y".

*// podría hacerse alguna suposición como que si aprobó el parcial con más de 7 es porque es alumno y ya aprobó, pero supongo que no es la idea del ejercicio*

Constantes:
* L: representa a la materia LeIA.
* 7: representa la nota numérica 7.
* AG: representa al mes de agosto.

Variables:
* x: representa un alumno cualquiera.

Funciones:
* $f_1(x)$: función para obtener el DNI de "x".
* $f_2(x)$: función para obtener el resultado de "x" en el parcial de la materia "y".

$(∀x) ((A(x,L) ∧ D(f_1(x)) ∧ P(x,L) ∧ M(f_2(x,L),7)) → F(x,AG))$

## b. Algunos alumnos de informática mayores de 18 años han sido vacunados con la vacuna Sputnik V.

*"Existe al menos un objeto "x" que es alumno de informática, mayor de 18 años y está vacunado con Sputnik V"*.

Predicados:
* $E(x,y)$: "x" es alumno de la facultad "y".
* $M(x,y)$: el número "x" es mayor que el número "y".
* $V(x,y)$: "x" fue vacunado con la vacuna "y".

Constantes:
* INFO: representa a la Facultad de Informática.
* 18: representa al número 18, refiriéndose a la edad.
* SPV: representa a la vacuna Sputnik V.

Variables:
* x: representa a un alumno.

Funciones:
* $f_1(x)$: función para obtener la edad de "x".

$(∃x) (E(x,INFO) ∧ M(f_1(x), 18) ∧ V(x,SPV))$

## c. Todos los jugadores de la selección argentina que viven en Europa, excepto los de Inglaterra, participarán en el mundial.

*"Para todos los objetos "x" se cumple que, si son jugadores de la selección argentina y viven en Europa (menos Inglaterra), entonces participarán en el mundial"*.

Predicados:
* $J(x,y)$: "x" juega en la selección "y".
* $V(x,y)$: "x" vive en la región "y".
* $M(x)$: "x" participará en el mundial.

Constantes:
* ARG: representa a Argentina.
* EUR: representa a Europa.
* ENG: representa a Inglaterra.

Variables:
* x: representa a un jugador cualquiera.

$(∀x) ((J(x,ARG) ∧ V(x,EUR) ∧ ¬V(x,ENG)) → M(x))$

# 4. Expresar en lenguaje de predicados de primer orden el conocimiento asociado a las siguientes situaciones:

## a. Ningún dragón que viva en un zoológico es feliz. Cualquier animal que encuentre gente amable es feliz. Las personas que visitan los zoológicos son amables. Los animales que viven en zoológicos encuentran personas que visitan zoológicos.

## b. Todo peluquero afeita a todo aquel que no se afeita a sí mismo. Ningún peluquero afeita a alguien que se afeite a sí mismo.

## c. Si alguien hace algo bueno, ese alguien es bueno; del mismo modo, si alguien hace algo malo, es malo. Sebastián ayuda a su madre y también miente algunas veces. Mentir es malo y ayudar es bueno.