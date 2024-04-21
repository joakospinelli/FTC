# 1. Mostrar que las reducciones polinomiales son reflexivas y transitivas. 
**Ayuda: basarse en lo que vimos con las reducciones generales, y considerar adicionalmente que deben ser computables en tiempo polinomial.**

Las reducciones polinomiales son reflexivas ya que la función identidad (que copia un *String* de entrada en la salida) puede realizarse en tiempo polinomial.

Son transitivas porque, dada una reducción L1≤p L2, se puede generar una función de reducción L2 ≤p L3 que también se realizará en tiempo polinomial, y por lo tanto puede probarse que L1 ≤p L3.

# 2. ¿Qué significa concretamente que si L1 ≤p L2, entonces L2 es tan o más difícil que L1, en el marco de la complejidad temporal?

Un lenguaje sólo puede reducirse a otro de su misma clase o de una mayor.

Que L1 ≤p L2 indica que L2 será a lo sumo polinomial (de clase P), o de alguna de mayor categoría, como NP.

# 3. Mostramos que existe una reducción polinomial del lenguaje CH (correspondiente al problema del circuito hamiltoniano) al lenguaje TSP (correspondiente al problema del viajante de comercio). En base a esto, justificar:
## a. Como TSP es NP-completo, entonces CH ∈ NP.

**Verdadero:** una de las propiedades de la clase NPC es que todos los lenguajes de NP reducen a él, por lo tanto si TSP es NPC, CH debe pertenecer a NP.

## b. Como CH es NP-completo, entonces TSP es NP-difícil.

*Un lenguaje NP-difícil es aquel que todos los lenguajes de NP pueden reducirse a él.*

**Falso:** a partir de la reducción de CH a TSP no se puede demostrar la prtenencia de TSP, ya que éste podría ser más difícil que CH.

# 4. ¿Por qué si un lenguaje es NP-completo, en la práctica se considera que no pertenece a la clase P?

Porque si existiese un lenguaje NPC que perteneciese a P, todos los lenguajes de NP podrían reducirse a él, por lo tanto P sería igual a NP.

# 5. Justificar por qué si L1 ∈ NPC y L2 ∈ NPC, entonces se cumple L1 ≤p L2 y L2 ≤p L1.

Al pertenecer a NPC, se sabe por definición que L1 y L2 también ∈ NP.

Siguiendo la otra definición de NPC, todos los lenguajes ∈ NP pueden reducirse a un lenguaje ∈ NPC.

Siguiendo estas propiedades, como tanto L1 y L2 ∈ NPC, pueden reducirse entre sí.

# 6. Probar que si se cumple L1 ≤p L2, L2 ≤p L1, y L1 ∈ NPC, entonces L2 ∈ NPC.

A partir de L2 ≤p L1 con L1 ∈ NPC, podemos saber que L2 ∈ NP.

Como L1 ∈ NPC, sabemos que pertenece a NP.

A partir de L1 ≤p L2, podemos saber que los lenguajes NP pueden reducirse a L2.

Podemos demostrar que L2 ∈ NP y todos los lenguajes de NP pueden reducirse a L2, por lo tanto L2 ∈ NPc.

# 7. Explicar cómo agregaría un lenguaje a la clase NPC a partir del lenguaje CLIQUE, que se sabe está en la clase NPC.

Supongamos que queremos crear un lenguaje L1 ∈ NPC.

Primero este debe ∈ NP, es decir, debe verificarse en tiempo polinomial; para esto debe crearse una MT que pueda hacerlo.

Luego de esto debe demostrarse que todos los lenguajes de NP pueden reducirse a L1; para esto podemos usar a CLIQUE.

Dada una reducción de CLIQUE ≤p L1 sabemos que:
* CLIQUE ∈ NPC, por lo tanto todos los lenguajes NP reducen a él.
* Como CLIQUE puede reducirse a L1, todos los lenguajes que se reducen a CLIQUE también se reducirán a L1 (*transitividad*).

Como L1 ∈ NP y es NP-difícil, L1 ∈ NPC.

# 8. Sean los lenguajes A y B, tales que A ≠ ⊘, A ≠ Ʃ*, y B ∈ P. Probar: (A ⋂ B) ≤p A.

# 9. Sea el lenguaje SH-s-t = {(G, s, t) | G es un grafo que tiene un camino (o sendero) de Hamilton del vértice s al vértice t}. Un grafo G = (V, E) tiene un camino de Hamilton del vértice s al vértice t si G tiene un camino entre s y t que recorre todos los vértices restantes una sola vez. Probar que SH-s-t es NP-completo. **Ayuda: se sabe que CH (el lenguaje correspondiente al problema del circuito hamiltoniano) es NP-completo.**