## 1. Espacios Vectoriales

**Definición 1.1**
Un espacio vectorial sobre un campo $K$ (o un $K$-espacio vectorial) es un conjunto $V$, cuyos elementos se llaman vectores, provisto de dos operaciones:
1. Suma: $+: V \times V \to V, \quad (v, w) \mapsto v + w$
2. Producto por escalares: $\cdot: K \times V \to V, \quad (\lambda, v) \mapsto \lambda v$

Estas operaciones deben satisfacer los siguientes ocho axiomas:
1. $u + (v + w) = (u + v) + w \quad \forall u, v, w \in V$
2. $\exists 0 \in V : u + 0 = 0 + u = u \quad \forall u \in V$
3. $\forall v \in V, \exists -v \in V : -v + v = v - v = 0$
4. $\forall v, w \in V, v + w = w + v$
5. $\lambda(\mu v) = (\lambda\mu)v \quad \forall \lambda, \mu \in K, \forall v \in V$
6. $1v = v \quad \forall v \in V$
7. $(\alpha + \beta)v = \alpha v + \beta v \quad \forall \alpha, \beta \in K, \forall v \in V$
8. $\alpha(u + v) = \alpha u + \alpha v \quad \forall \alpha \in K, \forall u, v \in V$

**Notación:** $_{K}V$ significa que $V$ es un $K$-espacio vectorial.

**Ejemplos:**
*   Para $n \in \mathbb{N}$, el espacio $V = K^n = \{ (a_{1}, a_{2}, \dots, a_{n}) \mid a_{i} \in K \forall i \}$.
*   $V = {}_{K}K$ (el campo $K$ como espacio vectorial sobre sí mismo).
*   El espacio trivial $V = \{ 0 \}$ con la suma de vectores y producto por escalares naturales.
*   El espacio de polinomios $V = K[x] = \left\{ \sum_{i=0}^n a_{i}x^i \mid a_{i} \in K \forall i, n \in \mathbb{N} \cup \{0\} \right\}$.

---

## 2. Subespacios Vectoriales

**Definición 2.1**
Sea $_{K}V$. Un subconjunto $W \subseteq V$ es un subespacio vectorial de $V$ (denotado como $W \le V$) si cumple:
1. $0 \in W$ (lo que equivale a $W \neq \emptyset$).
2. $u, v \in W \implies u + v \in W$.
3. $v \in W, \lambda \in K \implies \lambda v \in W$.

**Observación:** Si $_{K}V$ y $W \le V$, entonces $W$ es un $K$-espacio vectorial con las mismas operaciones de $V$.

**Ejemplos:**
*   $0 \le V$ y $V \le V$ para cualquier espacio vectorial (subespacios trivial y total).
*   Si $K = \mathbb{R}$:
    *   En $\mathbb{R}$, los subespacios son $0$ y $\mathbb{R}$.
    *   En $\mathbb{R}^2$, son $0$, $\mathbb{R}^2$ y las rectas que pasan por el origen.
    *   En $\mathbb{R}^3$, son $0$, $\mathbb{R}^3$, y las rectas y planos por el origen.
*   Matrices cuadradas simétricas: $\text{Sim}_{n\times n}(K) = \{ A = (a_{ij}) \in K^{n\times n} \mid A \text{ es simétrica} \}$.
*   Polinomios de grado acotado: $K_{n}[x] = \{ p(x) \in K[x] \mid \text{gr}(p) \le n \} \le K[x]$. *(Nota: se define $\text{gr}(0) = -\infty$)*.
*   Si $K \le L$ es una extensión de campos, entonces $_{K}L$ es espacio vectorial y $K \le L$.
*   El espacio de funciones $\mathbb{R}^{[a,b]} = \{ f: [a,b] \to \mathbb{R} \}$.
*   Para un conjunto $S$, el espacio de funciones de soporte finito: $K^{(S)} = \{ f: S \to K \mid f(x) = 0 \text{ para casi todo } x \in S \}$.

**Proposición 2.1**
Si $V_{i} \le V$ para todo $i \in I$, entonces $\bigcap_{i \in I} V_{i} \le V$.

**Demostración de la Proposición 2.1**
Sea $W = \bigcap_{i \in I} V_{i}$.
1. Como $0 \in V_{i}$ para todo $i \in I$, entonces $0 \in W$.
2. Si $v, w \in W$, entonces $v, w \in V_{i}$ para todo $i$. Al ser subespacios, $v+w \in V_{i}$ para todo $i$, por lo que $v+w \in W$.
3. Si $v \in W$ y $\lambda \in K$, entonces $v \in V_{i}$ para todo $i$. Así, $\lambda v \in V_{i}$ para todo $i$, concluyendo que $\lambda v \in W$. $\blacksquare$

*(Nota: La unión de subespacios no necesariamente es un subespacio).*

---

## 3. Combinaciones Lineales

**Definición 3.1**
Sea $V$ un $K$-espacio vectorial y $S \subseteq V$. Una **combinación lineal** de los vectores de $S$ es cualquier vector de la forma:
$$ v = \sum_{s \in S} \lambda_{s} s \quad \text{donde } \lambda_{s} \in K $$
De forma implícita, se asume que $\lambda_{s} = 0$ para casi todo $s \in S$ (soporte finito).

**Notación:** $\mathcal{L}(S) = \{ v \in V \mid v \text{ es combinación lineal de los elementos de } S \}$. A este conjunto también se le denota como $\langle S \rangle$ y se le llama el **subespacio generado** por $S$. Si $W = \langle S \rangle$, se dice que $S$ es un sistema de generadores de $W$. Si existe un $S$ finito tal que $W = \langle S \rangle$, se dice que $W$ es finitamente generado.

**Lema 3.1** $S \subseteq \mathcal{L}(S)$ y $0 \in \mathcal{L}(S)$.
**Lema 3.2** Si $W \subseteq V$, entonces $W \le V \iff \mathcal{L}(W) \subseteq W \iff W = \mathcal{L}(W)$.
**Lema 3.3** Si $S \subseteq V$, entonces $\mathcal{L}(S) \le V$.
**Proposición 3.1** Si $S \subseteq V$, $\mathcal{L}(S)$ es el mínimo subespacio de $V$ que contiene a $S$.
**Proposición 3.2** Si $S \subseteq V$, entonces $\mathcal{L}(S) = \bigcap \{ W \le V \mid W \supseteq S \}$.

**Demostración del Lema 3.2**
$\implies$ Si $W \le V$, sabemos que $0 \in W$ y $W + W \subseteq W$. Sea $v \in \mathcal{L}(W)$, entonces $v = \sum_{x \in W} \lambda_{x} x$. Como $W$ es cerrado bajo suma y producto escalar, esta suma finita pertenece a $W$. Por tanto, $\mathcal{L}(W) \subseteq W$.
$\impliedby$ Si $\mathcal{L}(W) \subseteq W$, se cumple que para cualquier $\lambda \in K$, $\lambda W \subseteq \mathcal{L}(W) \subseteq W$. Igualmente, $0 \in \mathcal{L}(W) \subseteq W$ y $W + W \subseteq \mathcal{L}(W) \subseteq W$. Por lo tanto, $W \le V$. $\blacksquare$

**Demostración del Lema 3.3**
Por el Lema 3.1, $0 \in \mathcal{L}(S)$. Si tomamos dos elementos $\sum \lambda_{s} s$ y $\sum \mu_{s} s$ en $\mathcal{L}(S)$, su suma es $\sum (\lambda_{s} + \mu_{s}) s$, que sigue siendo una combinación lineal finita y, por tanto, pertenece a $\mathcal{L}(S)$. De manera análoga se cumple el producto por escalares. Así, $\mathcal{L}(S) \le V$. $\blacksquare$

**Demostración de la Proposición 3.1**
Por el Lema 3.3, $\mathcal{L}(S) \le V$. Por el Lema 3.1, $S \subseteq \mathcal{L}(S)$.
Sea $W \le V$ tal que $S \subseteq W$. Como $W$ es subespacio, contiene todas las combinaciones lineales de sus elementos. Al contener a $S$, también contiene a todas las combinaciones lineales de $S$, es decir, $\mathcal{L}(S) \subseteq W$. $\blacksquare$

**Demostración de la Proposición 3.2**
Consecuencia directa de la Proposición 3.1, ya que $\mathcal{L}(S)$ es la intersección de todos los subespacios que contienen a $S$. $\blacksquare$

---

## 4. Dependencia e Independencia Lineal

**Definiciones**
*   **Linealmente Dependiente (l.d.):** Una familia $(v_{i})_{i \in I}$ es l.d. si para algún $i \in I$, el vector $v_{i}$ es combinación lineal de los demás ($v_{j}$ con $j \neq i$).
*   **Linealmente Independiente (l.i.):** Una familia es l.i. si no es l.d.
*   **Base:** Un conjunto $\beta \subseteq V$ es una base de $V$ si $\beta$ es l.i. y $\mathcal{L}(\beta) = V$.

**Lema 4.1** Un conjunto $S$ es linealmente independiente $\iff$ si $\sum_{s \in S} \lambda_{s} s = 0$, entonces $\lambda_{s} = 0$ para todo $s \in S$. (Un conjunto es linealmente dependiente si existe una relación de dependencia lineal no trivial donde al menos un escalar es distinto de cero).
**Lema 4.2** Si $S \subseteq V$ es l.i. y $w \in V \setminus \langle S \rangle$, entonces $S \cup \{ w \}$ es l.i.
**Lema 4.3** 
1. Si $S \subseteq V$ es un conjunto l.i. maximal, entonces $S$ es base de $V$.
2. Si $S \subseteq V$ es un generador minimal de $V$, entonces $S$ es base de $V$.
3. $S$ es base de $V \iff S$ es l.i. maximal $\iff S$ es generador minimal.
**Lema 4.4** Si $T$ es generador de $V$ y $S \subseteq T$ es un conjunto l.i. maximal en $T$, entonces $S$ es base de $V$.

**Demostración del Lema 4.1**
$\implies$ Supongamos que $S$ es l.i. y $\sum_{s \in S} \lambda_{s} s = 0$. Por demostrar que $\lambda_{s} = 0$. Si existiera algún $\lambda_{s_0} \neq 0$, podríamos despejar $s_0$:
$$ s_0 = -\frac{1}{\lambda_{s_0}} \left( \sum_{s \neq s_0} \lambda_{s} s \right) $$
Esto haría a $s_0$ combinación lineal del resto, contradiciendo la independencia.
$\impliedby$ Supongamos que la única solución a $\sum \lambda_{s} s = 0$ es la trivial. Si $S$ fuera dependiente, algún $s_0$ sería combinación del resto: $s_0 = \sum_{s \neq s_0} \lambda_{s} s$. Restando $s_0$, tendríamos una combinación lineal igual a cero con el coeficiente de $s_0$ igual a $-1 \neq 0$, lo cual es una contradicción. $\blacksquare$

**Demostración del Lema 4.2**
Supongamos que $\sum_{s \in S} \lambda_{s} s + \lambda w = 0$. Si $\lambda = 0$, entonces $\sum_{s \in S} \lambda_{s} s = 0$, y por ser $S$ independiente, todos los $\lambda_{s} = 0$. Si $\lambda \neq 0$, podríamos despejar $w = \sum_{s \in S} (-\lambda_{s}/\lambda) s$, lo que implicaría que $w \in \mathcal{L}(S)$, contradiciendo la hipótesis. Por ende, la unión es l.i. $\blacksquare$

**Demostración del Lema 4.3**
1. Supongamos que $S$ es l.i. maximal. Por demostrar que $\mathcal{L}(S) = V$. Si existiera $w \in V$ tal que $w \notin \mathcal{L}(S)$, por el Lema 4.2, $S \cup \{ w \}$ sería l.i. Esto contradice la maximalidad de $S$. Luego, $\mathcal{L}(S) = V$ y $S$ es base.
2. Supongamos que $S$ es generador minimal. Si no fuera l.i., existiría $s_0 \in S$ tal que $s_0 \in \mathcal{L}(S \setminus \{ s_0 \})$. Esto implica que $\mathcal{L}(S \setminus \{ s_0 \}) = \mathcal{L}(S) = V$, lo cual contradice que $S$ sea minimal. $\blacksquare$

**Demostración del Lema 4.4**
Si $T = V$, se cumple el Lema 4.3. Queremos probar que $T \subseteq \mathcal{L}(S)$. Para todo $t \in T$, supongamos que $t \notin \mathcal{L}(S)$. Entonces $S \cup \{ t \}$ sería l.i. dentro de $T$, lo que contradice que $S$ sea maximal en $T$. Por lo tanto, $t \in \mathcal{L}(S)$, lo que implica que $T \subseteq \mathcal{L}(S)$. Como $\mathcal{L}(T) = V$, y $\mathcal{L}(S) = \mathcal{L}(T)$, concluimos que $S$ genera a $V$ y es base. $\blacksquare$

---

## 5. Espacios Finitamente Generados

*(Nota: En adelante, consideramos espacios vectoriales finitamente generados).*

**Proposición 5.1 (Teorema de Intercambio de Steinitz)**
Sea $V$ un espacio finitamente generado y $G \subseteq V$ tal que $\mathcal{L}(G) = V$. Si $I \subseteq V$ es un conjunto linealmente independiente, entonces la cardinalidad de $I$ es menor o igual a la cardinalidad de $G$ ($\#I \le \#G$).
**Proposición 5.2**
Si $V$ es finitamente generado y tenemos $I \subseteq G \subseteq V$ donde $I$ es l.i. y $\mathcal{L}(G) = V$, entonces existe una base $\beta$ de $V$ tal que $I \subseteq \beta \subseteq G$.

**Demostración de la Proposición 5.1**
Sean $n = \#G$, con $G = \{ v_{1}, \dots, v_{n} \}$, y supongamos un subconjunto finito de $I$: $\{ w_{1}, w_{2}, \dots, w_{m} \} \subseteq I$. Procederemos por reducción al absurdo suponiendo $m > n$.
Como $G$ genera a $V$, $w_{1}$ es combinación lineal $\sum_{i=1}^n \lambda_{i} v_{i}$. Como $w_{1} \neq 0$ (por ser de un conjunto l.i.), existe algún $j$ tal que $\lambda_{j} \neq 0$. Sin pérdida de generalidad, tomemos $j = 1$. Despejando $v_{1}$:
$$ v_{1} = -\frac{1}{\lambda_{1}} w_{1} - \sum_{i=2}^n \frac{\lambda_{i}}{\lambda_{1}} v_{i} $$
Esto significa que $v_1 \in \mathcal{L}(w_1, v_2, \dots, v_n)$. Sea $G_{1} = \{ w_{1}, v_{2}, \dots, v_{n} \}$. Se cumple que $G \subseteq \mathcal{L}(G_{1})$, por lo tanto $\mathcal{L}(G_{1}) = V$.
Por inducción, supongamos que tras $k$ intercambios ($1 \le k < n$), el conjunto:
$$ G_{k} = \{ w_{1}, \dots, w_{k}, v_{k+1}, \dots, v_{n} \} $$
es generador de $V$. Como $w_{k+1} \in V = \mathcal{L}(G_{k})$, lo podemos escribir como:
$$ w_{k+1} = \sum_{i=1}^k \lambda_{i} w_{i} + \sum_{i=k+1}^n \mu_{i} v_{i} $$
Como $I$ es independiente, $w_{k+1} \notin \mathcal{L}(w_{1}, \dots, w_{k})$, por lo que no todos los $\mu_{i}$ pueden ser cero. Sin pérdida de generalidad, $\mu_{k+1} \neq 0$. Despejando $v_{k+1}$:
$$ v_{k+1} = \frac{1}{\mu_{k+1}} \left( w_{k+1} - \sum_{i=1}^k \lambda_{i} w_{i} - \sum_{i=k+2}^n \mu_{i} v_{i} \right) $$
Esto muestra que $v_{k+1} \in \mathcal{L}(G_{k+1})$ donde $G_{k+1} = \{ w_{1}, \dots, w_{k+1}, v_{k+2}, \dots, v_{n} \}$. De nuevo, $\mathcal{L}(G_{k+1}) = V$.
Después de $n$ intercambios, tendríamos $G_{n} = \{ w_{1}, w_{2}, \dots, w_{n} \}$ generando a $V$. Pero como asumimos $m > n$, tendríamos un $w_{n+1} \in I$. Esto implicaría que $w_{n+1} \in \mathcal{L}(w_{1}, \dots, w_{n})$, lo cual es una contradicción directa con la independencia lineal de $I$. Por lo tanto, $m \le n$. $\blacksquare$

**Demostración de la Proposición 5.2**
Si $I$ es un subconjunto l.i. maximal en $G$, por el Lema 4.4, $\beta = I$ es base de $V$. Si no lo es, existe un conjunto $I'$ l.i. tal que $I \subset I' \subseteq G$. Por la Proposición 5.1, el tamaño de cualquier conjunto independiente está acotado por la cardinalidad de cualquier generador finito, garantizando que este proceso de añadir elementos termine, arrojando una base. $\blacksquare$

---

**Teorema 5.1** Todo espacio vectorial finitamente generado tiene al menos una base.
**Teorema 5.2** Si $V$ es finitamente generado, todo conjunto l.i. $I$ se puede extender a una base.
**Teorema 5.3** Si $V$ es finitamente generado, todo conjunto generador contiene alguna base.
**Teorema 5.4** Sean $\beta, \beta'$ bases de $V$ (finitamente generado). Entonces $\#\beta = \#\beta'$.

**Demostración del Teorema 5.1**
Aplicamos la Proposición 5.2 tomando $I = \emptyset$ y $G = V$. $\blacksquare$

**Demostración del Teorema 5.2**
Aplicamos la Proposición 5.2 tomando $I = I$ (el conjunto l.i. dado) y $G = V$. $\blacksquare$

**Demostración del Teorema 5.3**
Aplicamos la Proposición 5.2 tomando $I = \emptyset$ y $G$ igual al conjunto generador dado. $\blacksquare$

**Demostración del Teorema 5.4**
Como $\beta$ es independiente y $\beta'$ es generador, por la Proposición 5.1 se tiene $\#\beta \le \#\beta'$. Inviertiendo los roles, como $\beta'$ es independiente y $\beta$ es generador, se tiene $\#\beta' \le \#\beta$. Por tricotomía, $\#\beta = \#\beta'$. $\blacksquare$
