# 1. Analizar si la siguiente secuencia de FBFs de L se tratan de una demostración en L de la forma Γ |-<sub>L</sub> A para algún conjunto Γ de FBFs y alguna FBF A.

1. $((¬p) → (¬(q → r))) → ((q → r) → p)$
2. $((¬p) → (¬(q → r)))$
3. $((q → r) → p)$

## a. Describir al conjunto Γ y a la FBF A y explicar cada paso de la secuencia (es decir, axiomas y reglas de inferencia).

1. $((¬p) → (¬(q → r))) → ((q → r) → p)$ (instancia de L3)
2. $((¬p) → (¬(q → r)))$ (hipótesis)
3. $((q → r) → p)$ (aplicación de MP entre 1 y 2)

Se pudo llegar a $A$ a partir del conjunto de premisas $Γ$, por lo que L es válida.

$Γ$ = { $(¬p) → (¬(q → r))$ }

$A = ((q → r) → p)$

*// en gamma sólo van las HIPÓTESIS (no cuentan los pasos de axiomas o MP)*

## b. Decir si A es un teorema de L

Puede demostrarse si A es o no teorema de L mediante la propiedad de completitud, verificando si A es una tautología.

| p | q | r | q → r | (q → r) → p |
| - | - | - | ----- | ----------- |
| V | V | V | V | V |
| V | V | F | F | V |
| V | F | V | V | V |
| V | F | F | V | V |
| F | V | V | V | F |
| F | V | F | F | V |
| F | F | V | V | F |
| F | F | F | V | F |

Se encontró una asignación de valores en la que A no es verdadera, por lo tanto no es una tautología.

De acuerdo a la propiedades de completitud y correctitud, si una fórmula no es una tautología tampoco puede ser un teorema, por lo que A no es teorema de L.

*// tampoco preserva el MP*

## c. Decir si A es una tautología

De acuerdo a la propiedades de completitud y correctitud, si una fórmula no es una tautología tampoco puede ser un teorema, por lo que A no es teorema de L.

# 3. Sean A, B y C tres fórmulas bien formadas del sistema formal L, dar una demostración sintáctica en L de las siguientes deducciones. Justificar cada paso en la derivación, indicando cuáles son los axiomas instanciados y las reglas de inferencia utilizadas.

{ $((A → B) → C), B$ } |- <sub>L</sub> $(A → C)$

1. $B → (A → B)$ - Instancia de L1 con $A = B$ y $B = A$.
2. $B$ - Hipótesis.
3. $A → B$ - MP entre 1 y 2.
4. $(A → B) → C$ - Hipótesis.
5. $C$ - MP entre 3 y 4.
6. $C → (A → C)$ - Instancia de L1 con $A = C$ y $B = A$.
7. $A → C$ - MP entre 5 y 6.

# 4. Sea Γ un conjunto de FBFs del Cálculo de Enunciados, se sabe que Γ |-<sub>L</sub> A. ¿Es cierto que, para todo Γ<sub>i</sub>, tal que Γ<sub>i</sub> ⊂ Γ, Γ<sub>i</sub> |-<sub>L</sub> A? Fundar.

*// traducción: es cierto que para todo Γ<sub>i</sub> que es subconjunto de Γ, se cumple que Γ<sub>i</sub> |- <sub>L</sub> A?*

Es falso. Pueden darse casos en el que, al tratarse de un subconjunto, falten premisas en Γ<sub>i</sub> para concluir A.

Por ejemplo, siguiendo el ejercicio anterior:
* Γ = { $((A → B) → C), B$ }
* Γ<sub>i</sub> = { $B$ } es un subconjunto válido de Γ.
* Sólo los elementos de Γ<sub>i</sub> no podría deducirse la conclusión $A → C$.

# 5. Sean Γ y Γ<sub>0</sub> conjuntos de FBF del Cálculo de Enunciados, ¿es cierto que para todo Γ existe algún Γ<sub>0</sub> ⊆ Γ tal que si Γ |-<sub>L</sub> A, entonces Γ<sub>0</sub> |-<sub>L</sub> A? Fundar.

*// traducción: es cierto que para todo Γ<sub>0</sub> que es subconjunto de Γ o igual que él, se cumple que Γ<sub>0</sub> |- <sub>L</sub> A?*

En este caso sí es posible, ya que se considera la posibilidad de que Γ<sub>0</sub> sea igual que Γ, por lo que en dicho caso podría deducirse A a partir de Γ<sub>0</sub> realizando los mismos pasos que al deducirlo desde Γ.

# 6. Sean A, B y C FBFs del Cálculo de Enunciados. Sea Γ un subconjunto de FBFs del Cálculo de Enunciados. Se sabe que Γ ∪ {A, B} |-<sub>L</sub> C y también se sabe que Γ |-<sub>L</sub> A.

## a. ¿Es cierto que Γ |-<sub>L</sub> (C → B)? Fundar.

Primero se utilizará el meta-teorema de la deducción para igualar Γ ∪ {A, B} a Γ.

Caso 1:
1. Γ ∪ {A, B} |-<sub>L</sub> C
2. Γ ∪ { A } |-<sub>L</sub> (B → C)
3. Γ |-<sub>L</sub> (A → (B → C))

Caso 2:
1. Γ ∪ {A, B} |-<sub>L</sub> C
2. Γ ∪ { B } |-<sub>L</sub> (A → C)
3. Γ |-<sub>L</sub> (B → (A → C))

Γ = { (A → (B → C)), (B → (A → C)), A } *// A ya lo sabía por el enunciado que dice Γ |-<sub>L</sub> A*

Se quiere demostrar Γ |-<sub>L</sub> (C → B). Para esto se buscará un contraejemplo en el que la conclusión sea falsa pero las premisas sean verdaderas.

Para que la conclusión (C → B) sea falsa, debe darse $C = V$ y $B = F$.

De esta manera las premisas se resuelven como:
* (A → (B → C)) = (A → (F → V)) = (A → V) = $V$
* (B → (A → C)) = (F → (A → V)) = (F → V) = $V$
* A = $A$.

Dado el caso $A = V, $B = F, C = V$, todas las premisas serían verdaderas, a pesar de que la conclusión sea falsa. Por lo tanto, la argumentación es inválida.

## b. ¿Es cierto que |-<sub>L</sub> (A)? Fundar.

Para que A sea un teorema, debe ser una tautología.

A puede ser una FBF cualquiera, por lo que podría no ser una tautología.

Por lo tanto, A no es un teorema.