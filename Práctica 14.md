# 1. Indicar y justificar (semánticamente, es decir sin utilizar axiomas y reglas) si valen o no las siguientes ternas de Hoare:

## a. {x > 0} while x ≠ 0 do x := x – 1 od {x = 0}

La terna realiza los siguientes pasos:
1. Toma como precondición que el valor de $x$ siempre debe ser mayor a 0.
2. Mientras $x$ sea distinto a 0, le resta 1.
3. El programa termina cuando $x = 0$.

Como la precondición garantiza que $x$ va a ser un número positivo, este programa va a terminar con $x = 0$ independientemente del valor inicial de $x$, por lo que la terna es válida.

## b. {true} while x ≠ 0 do x := x – 1 od {true}

La precondición "true" representa cualquier estado inicial. A su vez, la postcondición "true" significa que el programa finaliza.

En base a eso, se pueden dar dos casos según el valor de $x$:
* Si el valor de $x$ es un número mayor o igual a 0, el programa terminaría correctamente.
* Si el valor de $x$ es un número negativo, la terna sería inválida ya que el programa nunca terminaría.

# Asumiendo que se cumple {p} S {q}, es decir que a partir de todo estado inicial que satisface la precondición p, luego de la ejecución del programa S se alcanza un estado final que satisface la postcondición q, indicar y justificar si valen o no las afirmaciones siguientes:

## a. Si el programa S terminó en un estado final que no satisface q, entonces significa que empezó en un estado inicial que no satisface p.

Por definición, si la terna { $p$ } S { $q$ } es válida es porque termina en un estado en el cual se satisface $q$. Por lo tanto, si $q$ no se cumple es porque no se definió un estado inicial en el cual se rompa $p$.

## b. Si el programa S terminó en un estado final que satisface q, entonces significa que empezó en un estado inicial que satisface p.

La terna { $p$ } S { $q$ } implica que, dado un estado inicial $p$ se llega a un resultado final $q$. Sin embargo, esto no garantiza que sea el único camino posible para llegar a dicho estado final.

Por lo tanto, a partir de un estado final $q$ no puede determinarse el valor del estado inicial $p$.

# 3. Aplicar el axioma de asignación (ASI) para obtener las precondiciones correspondientes a las siguientes ternas de Hoare:

## a. {?} x := x + 1 {x + 1 ≠ 0}

{x + 2 ≠ 0} x := x + 1 {x + 1 ≠ 0}

## b. {?} x := y {x = y}

{y = y} x := y {x = y}

# 4. Especificar un programa que a partir de un estado inicial en el que x > 0, termine en un estado final en el que el valor de la variable y sea el doble del valor inicial de x.

*// Ayuda: la especificación (x > 0, y = 2.x) NO es correcta.*

La especificación $x > 0, y = 2*x$ no es válida ya que no tiene en cuenta el valor inicial de $x$. Para esto debe crearse una nueva variable $X$ en la que se almacene el valor inicial de la variable.

{x > 0} X = x; y = 2*X {y = 2*X}

# 5. Se cuenta con un programa que calcula en una variable prod el producto de dos números enteros x e y mayores o iguales que cero, sumando y veces el valor de x. Una terna de Hoare que expresa esto es la siguiente:
```c
{x ≥ 0 ∧ y ≥ 0 ∧ prod = 0 ∧ tope = 0}

while tope ≠ y do
    prod := prod + x;
    tope := tope + 1;
od

{ prod = x.y }
```

Para la verificación del programa, que es un while, puede servir utilizar como invariante el predicado $p = (prod = x.tope)$, y como variante la función $t = (y – tope)$. Se pide comprobar (informalmente, sin recurrir a los axiomas y reglas del método presentado en clase) que efectivamente $p$ y $t$ cumplen con las definiciones de invariante y variante, respectivamente. Es decir, se pide comprobar:

## a. $p$ se cumple antes del while.

* $prod = 0$
* $tope = 0$
* $x$ es cualquier número natural.
* Reemplazando $p$: $0 = x*0 = 0$.

Por lo tanto, el predicado es válido antes de entrar al bucle.

## b. $p$ se cumple después de toda iteración.

Se demostrará la validez del predicado con un ejemplo:

**Iteraciones:**
1. $x = 2; prod = 0; tope = 0$
    1. $prod = 0 + 2$
    2. $tope = 0 + 1$
    3. $p = 2 = 2*1 = 2$
2. $x = 2; prod = 2; tope = 1$
    1. $prod = 2 + 2$
    2. $tope = 1 + 1$
    3. $p = 4 = 2*2 = 4$
3. $x = 2; prod = 4; tope = 2$
    1. $prod = 4 + 2$
    2. $tope = 2 + 1$
    3. $p = 6 = 2*3 = 6$

Siguiendo este patrón en todas las iteraciones, se demuestra que $p$ se cummple en cada iteración.

## c. $t$ se decrementa después de toda iteración.

El valor inicial de $t$ es el valor de $y$, es decir, cualquier número mayor a 0.

Luego, en cada iteración el valor de $tope$ aumenta en 1, mientras que el de $y$ no se modifica. Por lo tanto, se le restará cada vez más a $y$ a medida que $tope$ crezca.

Por lo tanto, es verdad que $t$ se decrementa en cada iteración.

## d. $t$ siempre es mayor o igual que cero.

El valor de $t$ depende del valor que se le de a $tope$ en el bucle, ya que $y$ no cambia en toda la ejecución. Como $y$ siempre es mayor a 0 al iniciar el programa, $t$ también lo será.

Como el while finaliza cuando el valor de $tope = y$, se va a dar el caso de que $t = y - y = 0$, y luego de eso se va a dejar de modificar el valor de $tope$.

Por lo tanto, $t$ finalizará el programa con el valor 0, y nunca podrá ser menor.
