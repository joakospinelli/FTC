# 1. Señalar las ocurrencias libres o ligadas de x1, x2, x3 en la siguiente FBF escrita en un lenguaje de primer orden, donde C = { c }, F = { f,g } y P = { A<sup>2</sup><sub>1</sub> }, con g de aridad 1; f de aridad 2; A<sup>2</sup><sub>1</sub> de aridad 2.

1. $∀x_1 (∃x_2 A^2_1 (x_1, f(x_2, x_3)) → ∀x_3 A^2_1 (g(c), x_1) ∨ A^2_1(x_1, x_3))$
    * $x_1$ está ligada para toda la FBF.
    * $x_2$ está ligada en el antecedente de la implicación.
    * $x_3$ está libre.

2. $∀x_1 (∃x_2 A^2_1 (x_1, f(x_2, x_3))) → ∀x_3 A^2_1 (g(c), x_1) ∨ A^2_1(x_1, x_3)$
    * $x_1$ está ligada sólo en el antecedente de la implicación, y está libre en la conclusión.
    * $x_2$ está ligada en el antecedente de la implicación.
    * $x_3$ está libre.

# 2. Sean A y F FBFs escritas en un lenguaje de primer orden, analizar si son lógicamente equivalentes los siguientes pares de FBF (usar i-equivalencia o contraejemplos según corresponda):

## a. (∀x) A | ∃x A

Se demostrará por contraejemplo.

* U = N (conjunto de números naturales)
* I(A) = { (x): x es par }

∀x A es falso para I(A).

∃x A es verdadero para I(A).

Por lo tanto, no son lógicamente equivalentes.

## b. ∃x∃y A | ∃y∃x A

Se demostrará por i-equivalencia.

1. $|=_I,_v(∃x (∃y (A)))$ si y sólo si existe una valoración i-equivalente $w$ en la que $|=_I,_w (∃y (A))$.
2. $|=_I,_w (∃y A)$ si y sólo si existe una valoración $a$ i-equivalente en la que $|=_I,_a (A)$.
3. Dadas unas valoraciones para $x$ e $y$ que satisfacen $|=_I,_v(∃x (∃y (A)))$, con estas mismas valoraciones se satisface $|=_I,_v(∃y (∃x (A)))$.
4. En el caso de que no existan valoraciones, ambas FBFs son falsas.

Por lo tanto, ambas fórmulas son lógicamente equivalentes.

## c. ∃x∀y A | ∀y∃x A

Se demostrará por i-equivalencia.

1. $|=_I,_v((∃x)(∀y (A)))$ si y sólo si existe una valoración i-equivalente $w$ en la que $|=_I,_w((∀y (A)))$.
2. $|=_I,_w((∀y (A)))$ si y sólo si existe una valoración i-equivalente $a$ en la que $|=_I,_a(A)$.
3. Dadas unas valoraciones para $x$ e $y$ que satisfacen $|=_I,_v((∃x)(∀y (A)))$, con esas mismas valoraciones se satisface $|=_I,_v((∀x)(∃y (A)))$.
4. En el caso de que no existan valoraciones, ambas FBFs son falsas.

Por lo tanto, ambas fórmulas son lógicamente equivalentes.

## d. ∃x(A ∧ B) | ∃xA ∧ ∃xB

Se demostrará por i-equivalencia.

1. $|=_I,_v((∃x)(A ∧ B))$ si y sólo si existe una valoración i-equivalente $w$ en la que $|=_I,_w((∃x)(A))$ y $|=_I,_w((∃x)(B))$.
2. Si existe una valoración $x$ que satisface $|=_I,_x((∃x)(A))$ y $|=_I,_x((∃x)(B))$ a la vez, entonces también satisface a $|=_I,_x((∃x)(A) ∧ (∃x)(B))$.
3. En el caso de que no existan valoraciones, todas las FBFs son falsas.

Por lo tanto, ambas fórmulas son lógicamente equivalentes.

## e. ∃x(A ∨ B) | ∃xA ∨ ∃xB

Se demostrará por i-equivalencia.

1. $|=_I,_v((∃x)(A ∨ B))$ si y sólo si existe una valoración i-equivalente $w$ en la que $|=_I,_w((∃x)(A))$ o $|=_I,_b((∃x)(B))$
2. Si existe una valoración $x$ que satisface a cualquiera de $|=_I,_x((∃x)(A))$ o $|=_I,_b((∃x)(B))$, entonces también satisface $|=_I,_x((∃x)(A) ∨ (∃x)(B))$.
3. En el caso de que no existan valoraciones, ambas FBFs son falsas.

Por lo tanto, ambas fórmulas son lógicamente equivalentes.

## f. ∀x(A ∨ B) | ∀xA ∨ ∀xB

Se demostrará por contraejemplo.

* Universo U = N (conjunto de números naturales)
* I(A) = { (x): x es par }
* I(B) = { (x): x es impar }

∀x(A ∨ B) es verdadero. Se puede leer como *todo "x" es un número par o impar*.

∀xA ∨ ∀xB es falso. Se puede leer como *todos los números "x" son pares o todos los números "x" son impares*.

Por lo tanto, las fórmulas no son lógicamente equivalentes.

# 3. Dado un lenguaje de primer orden con las siguientes características:

* Constantes: { c,u }
* Funciones: ⊘
* Predicados: P = $A^2_1$, con $A^2_1$ de aridad 2.

Sea I la interpretación para ese lenguaje sobre el dominio de los números naturales:
* I(c) = 0
* I(u) = 1
* I($A^2_1(x,y)$) = { (x,y) ∈ N * N; x ≤ y }

## a. Verificar si las siguientes afirmaciones son o no correctas:

*// una fórmula es satisfactible si existe una valoración y una interpretación para la cual la fórmula es verdadera.*

*// una fórmula es verdadera si existe una interpretación I para la que es satisfactible en todas sus valoraciones.*

*// una fórmula es lógicamente válida si es verdadera para todas sus interpretaciones.*

*// una fórmula es contradictoria si es falsa para todas sus interpretaciones.*

### i. $A^2_1(c,x)$ es satisfactible en I.

Sea "x" un número natural cualquiera, la fórmula $A^2_1(c,x)$ siempre será verdadera ya que x siempre será ≤ a 0.

Por lo tanto, $A^2_1(c,x)$ es satisfactible en I.

### ii. $A^2_1(u,x)$ es satisfactible en I.

Sea "x" un número natural cualquiera, la fórmula $A^2_1(u,x)$ será verdadera para los casos en los que x sea mayor o igual a 1.

Por lo tanto, como existe una valoración en la que $|=_I, _v A^2_1(u,x)$, se dice que $A^2_1(u,x)$ es satisfactible en I.

### iii. $∀x A^2_1(c,x)$ es satisfactible en I.

Sea "x" un número natural, la fórmula $A^2_1(u,x)$ será verdadera para todos los números naturales.

Por lo tanto, $∀x A^2_1(c,x)$ es satisfactible en I.

### iv. $∀x A^2_1(u,x)$ es satisfactible en I.

Sea "x" un número natural, la fórmula $A^2_1(u,x)$ no se cumple para todos los números naturales. Por contraejemplo, sea $x = 0$ no se cumple $A^2_1$.

Por lo tanto, $∀x A^2_1(u,x)$ es satisfactible en I.

### v. $A^2_1(c,x)$ es verdadera en I.

Sea "x" un número natural cualquiera, la fórmula $A^2_1(c,x)$ se cumple para todos los valores posibles de "x".

Por lo tanto, se cumple $A^2_1(c,x)$ para todas las asignaciones de I, por lo que es verdadera.

### vi. $∀xA^2_1(c,x)$ es lógicamente válida.

Suponiendo otra interpretación J, en la que:
* Universo U = Z
* J(c) = 0

$∀xA^2_1(c,x)$ no es verdadera para la interpretación J, ya que los números negativos son menores a 0.

Por lo tanto, $∀xA^2_1(c,x)$ no es lógicamente válida.

### vii. $A^2_1(u,c) ∧ ¬A^2_1(u,c)$ es contradictoria.

$A^2_1(u,c) ∧ ¬A^2_1(u,c)$ es contradictoria, ya que sigue la forma básica de la contradicción $p ∧ ¬p$.

# 4. Ofrecer una interpretación para los siguientes lenguajes de primer orden donde las fórmulas sean verdaderas y otra donde sean falsas. Traducir en cada caso las fórmulas dadas a oraciones apropiadas en el lenguaje natural.

## a.

$C = F = ⊘$.

$P = { A^2_1 }$, con $A^2_1$ de aridad 2.

1. $∀x ∀y(A^2_1(x,y) → A^2_1(y,x))$
2. $∀x(A^2_1(x,x))$
3. $∀x ∀y ∀z((A^2_1(x,y) ∧ A^2_1(y,z)) → A^2_1(x,z))$

### Verdaderas

* U = N (conjunto de números naturales)
* I($A^2_1$) = { (x,y) : "x" es igual a "y" }

1. Para todo $x$ y para todo $y$, si $x$ es igual a $y$ entonces $y$ es igual a $x$.
2. Para todo $x$, $x$ es igual a sí mismo.
3. Para todo $x$, $y$ e $z$, si $x$ es igual a $y$ e $y$ es igual a $z$, entonces $x$ y $z$ son iguales.

### Falsas

* U = N (conjunto de materias)
* I($A^2_1$) = { (x,y) : "x" es mayor correlativa de "y" }

1. Para todo $x$ e $y$ no se cumple que, si $x$ es correlativa de $y$ entonces $y$ sea correlativa de $x$.
2. Para todo $x$, no se cumple que $x$ sea correlativa de sí misma.
3. Para todo $x$, $y$ e $z$, no se cumple que si $x$ es correlativa de $y$, e $y$ es correlativa de $z$, entonces $x$ también sea correlativa de $z$.

## b.

$C = { c }$

$F = { f }$, con $f$ de aridad 2.

$P = { A^2_1 }$, con $A^2_1$ de aridad 2.

1. $∀x(A^2_1(x,c) → A^2_1(x, f(y)))$
2. $∀x(¬A^2_1(x,x))$
3. $¬∀x∀y(A^2_1(x,y))$

### Verdaderas

* U = Z (conjunto de números enteros)
* I($c$) = 0
* I($f(x)$) = retorna $x$ multiplicado por 0.
* I($P^2_1$) = { (x,y) : "x" es mayor estricto a "y". }

1. Para todo número $x$, se cumple que si $x$ es mayor a 0, entonces será mayor a cualquier número multiplicado por $0$.
2. Para todo número $x$, se cumple que nunca será mayor a sí mismo.
3. No para todo $x$ y para todo $y$, se cumple que $x$ sea mayor a $y$.

### Falsas

No puede llegarse a un caso en el que sean falsas, ya que las FBF 1 y 3 son contradictorias entre sí.

# 5. Determinar si las siguientes FBFs escritas en algún lenguaje de primer orden son contradictorias, satisfactibles en alguna interpretación, verdaderas en alguna intepretación o lógicamente válidas. Fundamentar

## a. (∃x)(¬A(x)) ∨ (∀x)(A(x) ∨ B(x))

Se buscará demostrar que $(∃x)(¬A(x)) ∨ (∀x)(A(x) ∨ B(x))$ es lógicamente válida. Para esto se analizarán los términos por separado:

$(∃x)(¬A(x))$ implica que existe al menos un $x$ en el que $A(x)$ sea falsa.

$(∀x)(A(x) ∨ B(x))$ implica que (A(x) ∨ B(x)) se cumple para todos los $x$.

1. Si $(∃x)(¬A(x))$ es falso, implica que $(∀x)(A(x))$ es verdadero.
2. Por lo tanto, el segundo término será verdadero.
3. en el caso contrario, el primer término será verdadero y el segundo será falso.
4. Por lo tanto, la disyunción será siempre verdadera.

Por lo tanto, $(∃x)(¬A(x)) ∨ (∀x)(A(x) ∨ B(x))$ es lógicamente válida independientemente de la interpretación.

## b. ∃y∃x P(x,y) → ∃x∃y P(x,y)

Es lógicamente válido ya que el orden de los cuantificadores no afecta el resultado de la fórmula, la cual tiene un formato de $p → p$ que siempre es verdadero.

# 6.

## a. Si la FBF A(x) es satisfactible, entonces la FBF ∃x A(x) es lógicamente válida? Fundamentar.

Que $A(x)$ sea satisfactible implica que es verdadera para una interpretación $I$ y una validación $v$. Sin embargo, no se puede garantizar que se cumpla para todas las interpretaciones y valoraciones posibles.

Por lo tanto, no se puede concluir que $∃x A(x)$ sea lógicamente válida.

## b. La FBF abierta ∀y P(x,y) → ∀y∀x P(x,y) es lógicamente válida? Fundamentar.

No es lógicamente válida ya que su resultado depende de la interpretación que se realice sobre $P(x,y)$.

## c. Sea un lenguaje de primer orden de constante 'c' y las letras de predicado P y Q, ambas de aridad 1. Sea la FBF (P(c) ∧ ∀x(P(x) → Q(x))) → Q(c), es lógicamenta válida? Fundamentar.

Se buscará demostrar que $(P(c) ∧ ∀x(P(x) → Q(x))) → Q(c)$ es lógicamente válida. Para esto se analizarán los términos por separado:

Si $(P(c) ∧ ∀x(P(x) → Q(x)))$ es falso, la fórmula será verdadera debido a la tabla de verdad de la implicación.

Si $(P(c) ∧ ∀x(P(x) → Q(x)))$ es verdadero:
1. Deben cumplirse tanto $P(c) = V$ como $∀x(P(x) → Q(x)) = V$.
2. Como $P(c)$ es verdadero y $c$ pertenece al mismo universo que $x$, entonces $∀x(P(x) → Q(x))$ será verdadero con $P(x) = V$ y $Q(x) = V$.
3. Como se sabe que $Q(x) = V$ para todo $x$, entonces $Q(c) = V$.

Por lo tanto, la FBF es lógicamente válida.

## d. Sean A y B dos FBF escritas en un lenguaje de primer orden. La FBF ∀x (A(x) ∨ B(x)) → ((∀xA(x)) ∨ (∀xB(x))) es lógicamente válida? Fundamentar.

Se buscará de mostrar que $∀x (A(x) ∨ B(x)) → ((∀xA(x)) ∨ (∀xB(x)))$ es lógicamente válida.

Para esto se buscará un contraejemplo. Dada una interpretación I en la que:
* U: Universo de los números naturales.
* I(A): $x$ es un número par.
* I(B): $x$ es un número impar.

1. El término $∀x (A(x) ∨ B(x))$ es válido. Podría leerse como "Todos los números naturales son pares o impares".
2. El término $((∀xA(x)) ∨ (∀xB(x)))$ no es válido. Podría leerse como "Todos los números naturales son pares o todos son impares".
3. Al ser una implicación, el resultado queda V → F que en la tabla de verdad es falso.

Se encontró una interpretación en la que la FBF es falsa, por lo que no es lógicamente válida.

# 7. Sea A una FBF de un lenguaje de primer orden e I una interpretación para tal lenguaje, demostrar que A es verdadera en I si y sólo si ¬A es falsa en I.

Dada una FBF $A = P^1_1(x)$ de un lenguaje, se quiere demostrar que $A = V$ si y sólo si cuando $¬A = F$ para una interpretación $I$ de dicho lenguaje.

Dada una interpretación $I$, en el caso de que $¬A$ sea falsa:
1. $⊧_I,_v (¬A)$ no se cumple para ninguna valoración $v$.
2. A partir de esto, $⊧_I,_v (¬(¬A))$ se cumple con la misma valoración $v$.
3. $⊧_I,_v (¬(¬A)) = ⊧_I,_v (A)$ (propiedad de doble negación).
4. Por lo tanto, siempre que $⊧_I,_v (A)$ se cumpla en una valoración $v$, $⊧_I,_v (¬A)$ no se cumplirá.

# 8. Sea A una FBF que no contiene cuantificadores escrita en algún lenguaje de primer orden. Sea I una interpretación para tal lenguaje, es posible decidir acerca del valor de A en I? Fundamentar.

El resultado de A depende de la interpretación que se realice sobre sus predicados.

Si A tuviese cuantificadores, se podría evaluar su valor de verdad final independientemente de la valoración de sus variables.

Sin embargo, como el enunciado aclara que A no tiene cuantificadores, para decidir su valor en $I$ no alcanza con saber la interpretación, sino que también debe conocerse la valoración sobre la que se está trabajando.

# 9. Retomar la práctica anterior y para cada item del ejercicio 4, encontrar alguna interpretación donde todas las sentencias sean verdaderas, y además:

## a. Pipo es un dragón que vive en un zoológico.

## b. Sebastián es bueno y malo al mismo tiempo.

## c. Pedro es un peluquero.