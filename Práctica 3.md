# 1. Probar que los lenguajes L<sub>U</sub> = {(< M >, w) | M acepta w} y HP = {(< M >, w) | M para a partir de w} pertenecen a la clase RE.

## a.

L<sub>U</sub> = { (< M >, w) | M acepta w }

Demostrar que L<sub>U</sub> ∈ RE.

Para probar esto se crea una MT U encargada de correr < M > a partir de la entrada `w`.

Como < M > se ejecutará sobre MT U, se puede garantizar que siempre que la entrada ∈ L<sub>U</sub> finalizará con el estado `qA`. Sin embargo, no se puede garantizar el resultado en el caso de que las cadenas no pertenezcan al lenguaje.

Al ejecutar < M > sobre MT U produce los siguientes resultados:
* Si `w` ∈ RE, < M > termina en qA<sub>< M ></sub>, por lo que MT U termina en `qA`.
* Si `w` ∉ RE, < M > termina en qR<sub>< M ></sub>, por lo que MT U termina en `qR`.
* Si < M > termina en bucle, MT U también lo hará.

## b.

HP = { (< M >, w) | M para a partir de w }

Demostrar que L<sub>HP</sub> ∈ RE.

Para probar esto se crea una MT U encargada de correr < M > a partir de la entrada `w`.

Como < M > se ejecutará sobre MT U, se puede garantizar que siempre que la entrada ∈ L<sub>HP</sub> finalizará con el estado `qA`. Sin embargo, no se puede garantizar el resultado en el caso de que las cadenas no pertenezcan al lenguaje.

El lenguaje busca probar que la MT < M > pare con la entrada `w`, independientemente de que la acepte o no; por lo tanto, MT U debería finalizar en el estado `qA` ya sea que < M > acepte o rechace. *// CONSULTAR ESTO*

Al ejecutar < M > sobre MT U produce los siguientes resultados:
* Si `w` ∈ RE, < M > termina en qA<sub>< M ></sub>, por lo que MT U termina en `qA`.
* Si `w` ∉ RE, < M > termina en qR<sub>< M ></sub>, igualmente MT U termina en `qA`.
* Si < M > termina en bucle, MT U también lo hará.

# 2. Responder cada uno de los incisos.
## a. ¿Se puede decidir si una MT M con una cinta, a partir de la cadena vacía λ, escribe alguna vez un símbolo no blanco?

## b. ¿Se puede decidir si a partir de una cadena w, una MT M que sólo se mueve a la derecha para?

La MT M siempre va a parar si la cadena `w` ∈ R.

## c. ¿Se puede decidir si dada una MT M, existe una cadena w a partir de la cual M para en a lo sumo 10 pasos?

Si L(M) ∈ R, entonces se garantiza que M va a finalizar.

Para decidir si finalizará en 10 pasos o menos, podría ejecutarse < M > en una MT U con espacio limitado a 10 celdas.
* Si < M > finaliza, MT U finaliza en `qA`. *// CONSULTAR ESTO (misma duda que ej 1)*
* Si no, finaliza en `qR`.

## d. ¿Se puede decidir si dada una MT M, existe una cadena w de a lo sumo 10 símbolos a partir de la cual M para?

No se puede garantizar su finalización, ya que no se puede asegurar que la MT pare después de leer toda la cadena `w`.

# 3. Explicar cómo enumeraría los números naturales pares, los números enteros, los números racionales (o fraccionarios) y las cadenas de Ʃ* siendo Ʃ = {0, 1}.

Para enumerarlos usaría la notación unaria.

Pares:
1. Iniciar con 2 cintas en blanco
3. Marcar el inicio de un nro. en la cinta 2
4. Escribir "1" en la cinta 2 por cada "1" en la cinta 1
5. Agregar dos "1" en la cinta 1 y volver al primer símbolo
6. Vuelve al paso 2

Enteros:
1. Iniciar con 3 cintas en blanco
3. Marcar el inicio de un nro. en la cinta 2
4. Escribir "1" en la cinta 2 por cada "1" en la cinta 1
4. Escribir un "0" en la cinta 3 (indicando que es un nro. negativo) y luego un  "1" en la cinta 3 por cada "1" en la cinta 1 *// CONSULTAR ESTO (porque quedaría un -0)*
5. Agregar un "1" en la cinta 1 y volver al primer símbolo
6. Vuelve al paso 2

Racionales:

Ʃ*:
1. Iniciar con 2 cintas en blanco
2. Marcar el inicio de una cadena en la cinta 2
3. Copiar los símbolos de la cinta 1 en la cinta 2
4. Si había un "0" en la cinta 1, escribir un "1" y volver al primer símbolo.
    * Si había un "1" o un espacio en blanco, escribir un "0".
5. Volver al paso 2

# 4. Una función f : A ⟶ B se dice que es total computable, si existe una MT M<sub>f</sub> que computa f para todo elemento a ∈ A. Sea la función fHP: Ʃ* ⟶ {0, 1}, tal que:
### fHP (x) = 1, si x = (< M >, w) y M para a partir de w.
### fHP (x) = 0, si x = (< M >, w) y M no para a partir de w, o bien x ≠ (< M >, w).

## Probar que la función fHP no es total computable.

fHP supone una MT<sub>f</sub> que siempre finaliza, por lo que podemos suponer que L(fHP) ∈ R.

Por definición, fHP debe retornar un valor "0" (qR) en el caso de que la MT < M > rechace la entrada `w` o no finalice a partir de ella.

Dado esto, encontramos una inconsistencia en la que fHP debe retornar un resultado, incluso en el caso de que no finalice. Por lo tanto, MT<sub>f</sub> entraría en un bucle.

Por lo tanto, como no podemos asegurar la finalización de MT<sub>f</sub> para todas sus entradas, concluimos que L(fHP) ∈ RE y entonces fHP no es total comptable.

*// acá está explicado con la definición de HP, pero me parecía mejor tener la otra rta para entenderlo mejor*

Dada la función fHP, al suponerla total computable se puede generar una MT<sub>f</sub>, la cual ∈ R.

Dicha MT<sub>f</sub> aceptaría las cadenas en las que fHP(x) = 1, que por definición es: *"(< M >, w) y M para a partir de w"*.

Ese resultado de la función corresponde al lenguaje del Halting Problem (HP), el cual ∈ RE. Por lo tanto, se genera una falla lógica ya que M<sub>f</sub> no podría pertenecer a R al no poder garantizar la finalización de su ejecución en este caso.

Por lo tanto, MT<sub>f</sub> pertenecería a RE y fHP no sería total computable.

# 5. Responder cada uno de los incisos.
## a. Si L1 ∈ RE y L2 ∈ RE, ¿L1 – L2 ∈ RE?
## b. Si L1 ⋂ L2 ∈ RE, ¿L1 o L2 ∈ RE?
## c. Si L1 ⋃ L2 ∈ RE, ¿L1 o L2 ∈ RE?
# 6. Explicar (informal pero claramente) cómo sería una MT que genera la n-ésima fórmula booleana satisfactible, cuya sintaxis contiene variables de la forma x<sub>i</sub>, los operadores lógicos del conjunto {¬, , }, y paréntesis. 