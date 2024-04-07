# 1. Considerando la reducción de HP a LU descripta en clase, responder:

## a. Explicar por qué la función identidad, es decir la función que a toda cadena le asigna la misma cadena, no es una reducción de HP a L<sub>U</sub>.

La función identidad se define como $f(x) = x$. Para que una función de reducción sea válida de HP a L<sub>U</sub> se deben cumplir las siguientes propiedades:
1. Para toda entrada $w$ ∈ HP, su $f(x)$ ∈ L<sub>U</sub>.
2. Para toda entrada $w$ ∉ HP, su $f(x)$ ∉ L<sub>U</sub>.
3. La función $f$ debe ser computable.

El problema de la reducción de HP a L<sub>U</sub> es que HP está contenido en L<sub>U</sub>, por lo tanto existen entradas $w$ que pertenecen al conjunto (L<sub>U</sub> - HP), en las cuales $w$ ∉ HP pero $f(x)$ ∈ L<sub>U</sub>.

Por lo tanto, la función identidad no es una reducción de HP a L<sub>U</sub>.

## b. Explicar por qué las MT M' generadas en los pares de salida (< M' >, w), o bien paran aceptando, o bien loopean.

Suponiendo una MT M que ejecuta M' para garantizar que ésta termina o no, independientemente de que acepte o rechace la entrada se considera que la MT terminó, por lo que finalizará con estado `qA`. Por otro lado, al entrar en bucle no hay manera de retornar un estado final, aunque este sea `qR`; por lo tanto, la máquina quedará en bucle.

## c. Explicar por qué la función utilizada para reducir HP a L<sub>U</sub> también sirve para reducir HP<sup>C</sup> a L<sub>U</sub><sup>C</sup>.

Porque la reducción cumple la propiedad de complementos en la que:
* Si L<sub>1</sub> <= L<sub>2</sub>
* Entonces L<sub>1</sub><sup>C</sup> <= L<sub>2</sub><sup>C</sup> con la misma función de reducción.

## d. Explicar por qué la función utilizada para reducir HP a L<sub>U</sub> no sirve para reducir L<sub>U</sub> a HP.

Porque la reducción no garantiza la simetría de las funciones.

HP <= L<sub>U</sub> no garantiza L<sub>U</sub> <= HP con la misma función.

## e. Explicar por qué la siguiente MT M<sub>f</sub> no computa una reducción de HP a L<sub>U</sub>: dada una cadena válida (< M >, w), M<sub>f</sub> ejecuta M sobre w, si M acepta entonces genera la salida (< M >, w), y si M rechaza entonces genera la cadena 1.

No es una reducción porque la función representada por M<sub>f</sub> no es total computable, ya que no puede garantizar la finalización correcta de las entradas $w$ en HP.

# 2. Justificar por qué una reducción de L<sub>U</sub> a L<sub>Ʃ*</sub> no sirve para probar que L<sub>Ʃ*</sub> ∉ RE.

Supongamos una función de reducción $f(x) = < M_Ʃ* >$, suponiendo una MT a partir de la cual se puede producir el lenguaje.

$f$ es una función computable, puesto que la MT puede producirse sin entrar en bucle. Esto se debe a que todo lenguaje tiene una MT que lo produce.

Sin embargo, pueden darse casos en los que haya una entrada $w$ ∉ L<sub>U</sub>, sin embargo $f(x)$ sí pertenezca a L<sub>Ʃ*</sub>. Por lo tanto, la función de reducción no es válida.

Como no puede realizarse la reducción, no puede usarse el teorema para demostrar que L<sub>1</sub> ∈ RE-> L<sub>2</sub> ∈ RE ni su contrarrecíproco. Sin embargo, como L<sub>Ʃ*</sub> es más complejo que L<sub>U</sub>, no pueden realizarse suposiciones sobre él.

# 3. Existe una reducción de L<sub>U</sub><sup>C</sup> a L<sub>⊘</sub>. ¿A qué clase de la jerarquía de la computabilidad, entonces, no pertenece L<sub>⊘</sub>?

Si existe una reducción válida de L<sub>U</sub><sup>C</sup> a L<sub>⊘</sub>, se puede usar el teorema:

L<sub>U</sub><sup>C</sup> <= L<sub>⊘</sub> entonces L<sub>U</sub><sup>C</sup> ∉ RE -> L<sub>⊘</sub> ∉ RE.

Por lo tanto, como L<sub>U</sub><sup>C</sup> ∉ RE entonces L<sub>⊘</sub> ∉ RE.


# 4. Sea el lenguaje D<sub>HP</sub> = {w<sub>i</sub> | M<sub>i</sub> para desde w<sub>i</sub>, según el orden canónico}. Encontrar una reducción de D<sub>HP</sub> a HP.

HP está formado por los pares ( < M >, w) en los que M para sobre la entrada $w$.

D<sub>HP</sub> está formado por los pares (< M<sub>i</sub> >, w) generadas en orden canónico, en los que M para sobre la entrada $w$ generada en su mismo orden $i$.

Dado esto, se busca encontrar una función que reduzca D<sub>HP</sub> a HP. 

Supongamos una $f((<M_i>, w_i)) = (<M>, w)$:
* Si M<sub>i</sub> para sobre $w_i$, entonces ∈ D<sub>HP</sub> y $f(x)$ produce un par (< M >, w) que ∈ HP.
* Si M<sub>i</sub> no para sobre $w_i$, entonces ∉ D<sub>HP</sub> y $f(x)$ produce un par (< M >, w) que ∉ HP.

Por lo tanto, $f((<M_i>, w_i)) = (<M>, w)$ reduce D<sub>HP</sub> a HP.

*// igual no sé si es computable*

# 5. Construir un autómata finito que reconozca el lenguaje de todas las cadenas con 0 y 1, incluso la cadena vacía, tales que a todo 0 le siga un 1.

M = { Q, Ʃ, δ, q0, qA, qR }

Q = {q0, qA, qR, q1 }
* q0: estado inicial.
* q1: buscando un símbolo "1".
* qa: buscando un símbolo "0".

Función de transición:
* δ(q0, B): (qA, B, S)
* δ(q0, 0): (q1, 0, R)
* δ(q0, 1): (q0, 1, R)
* δ(q1, 1): (q0, 1, R)
* δ(q1, 0): (qR, 0, S)

# 6. Un autómata linealmente acotado (ALA) es una MT con una sola cinta, con la restricción de que su cabezal sólo puede moverse a lo largo de las celdas ocupadas por la cadena de entrada. Probar que el lenguaje aceptado por un ALA es recursivo.

**Ayuda: ¿en cuántos pasos se puede detectar que el ALA entra en loop?**

Dada una cadena de entrada con $w$ caracteres, se puede saber la cantidad de pasos que va a tomar una MT ALA antes de entrar en bucle.

Suponiendo que tiene Q estados y Ʃ símbolos, la MT puede realizar $|Q| * |Ʃ|^w$ pasos antes de entrar en bucle.

*// A partir de esto cómo se prueba que es recursivo?*

# 7. Construir una MT que genere todos los índices i tales que (< Mi >, wi) ∈ HP, según el orden canónico.