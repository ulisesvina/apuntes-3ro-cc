## 1. Espacios Vectoriales

**Definición 1.1**
Un espacio vectorial sobre un campo $K$ (o un $K$-espacio vectorial) es un conjunto $V$, cuyos elementos se llaman vectores, provisto de dos operaciones:
1. **Suma:** $+: V \times V \to V, \quad (v, w) \mapsto v + w$
2. **Producto por escalares:** $\cdot: K \times V \to V, \quad (\lambda, v) \mapsto \lambda v$

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
*   Para $n \in \mathbb{N}$, el espacio $V = K^n = \{ (a_{1}, a_{2}, \dots, a_{n}) \mid a_{i} \in K \, \forall i \}$.
*   $V = {}_{K}K$ (el campo $K$ como espacio vectorial sobre sí mismo).
*   El espacio trivial $V = \{0\}$ con la suma de vectores y producto por escalares naturales.
*   El espacio de polinomios $V = K[x] = \left\{ \sum_{i=0}^n a_{i}x^i \;\middle|\; a_{i} \in K \, \forall i, n \in \mathbb{N} \cup \{0\} \right\}$.

---

## 2. Subespacios Vectoriales

**Definición 2.1**
Sea $_{K}V$. Un subconjunto $W \subseteq V$ es un subespacio vectorial de $V$ (denotado como $W \le V$) si cumple:
1. $0 \in W$ (lo que equivale a $W \neq \emptyset$).
2. $u, v \in W \implies u + v \in W$.
3. $v \in W, \lambda \in K \implies \lambda v \in W$.

**Observación:** Si $_{K}V$ y $W \le V$, entonces $W$ es un $K$-espacio vectorial con las mismas operaciones de $V$.

**Ejemplos:**
*   $\{0\} \le V$ y $V \le V$ para cualquier espacio vectorial (subespacios trivial y total).
*   Si $K = \mathbb{R}$:
    *   En $\mathbb{R}$, los subespacios son $\{0\}$ y $\mathbb{R}$.
    *   En $\mathbb{R}^2$, son $\{0\}$, $\mathbb{R}^2$ y las rectas que pasan por el origen.
    *   En $\mathbb{R}^3$, son $\{0\}$, $\mathbb{R}^3$, y las rectas y planos que pasan por el origen.
*   Matrices cuadradas simétricas: $\text{Sim}_{n\times n}(K) = \{ A = (a_{ij}) \in K^{n\times n} \mid A \text{ es simétrica} \}$.
*   Polinomios de grado acotado: $K_{n}[x] = \{ p(x) \in K[x] \mid \text{gr}(p) \le n \} \le K[x]$. *(Nota: se define $\text{gr}(0) = -\infty$)*.
*   Si $K \le L$ es una extensión de campos, entonces $_{K}L$ es un espacio vectorial y $K \le L$.
*   El espacio de funciones $\mathbb{R}^{[a,b]} = \{ f: [a,b] \to \mathbb{R} \}$.
*   Para un conjunto $S$, el espacio de funciones de soporte finito: $K^{(S)} = \{ f: S \to K \mid f(x) = 0 \text{ para casi todo } x \in S \}$.

### Resultados

**Proposición 2.1**
Si $V_{i} \le V$ para todo $i \in I$, entonces $\bigcap_{i \in I} V_{i} \le V$.

### Demostraciones

**Demostración de la Proposición 2.1:**
Sea $W = \bigcap_{i \in I} V_{i}$.
1. Como $0 \in V_{i}$ para todo $i \in I$, se concluye que $0 \in W$.
2. Si $v, w \in W$, entonces $v, w \in V_{i}$ para todo $i \in I$. Al ser cada $V_{i}$ subespacio, $v+w \in V_{i}$ para todo $i$, por lo que $v+w \in W$.
3. Si $v \in W$ y $\lambda \in K$, entonces $v \in V_{i}$ para todo $i \in I$. Así, $\lambda v \in V_{i}$ para todo $i$, de donde $\lambda v \in W$. $\blacksquare$

*(Nota: La unión de subespacios no necesariamente es un subespacio).*

---

## 3. Combinaciones Lineales

**Definición 3.1**
Sea $V$ un $K$-espacio vectorial y $S \subseteq V$. Una **combinación lineal** de los vectores de $S$ es cualquier vector de la forma:
$$ v = \sum_{s \in S} \lambda_{s} s \quad \text{donde } \lambda_{s} \in K $$
De forma implícita, se asume que $\lambda_{s} = 0$ para casi todo $s \in S$ (soporte finito).

**Notación:** $\mathcal{L}(S) = \{ v \in V \mid v \text{ es combinación lineal de los elementos de } S \}$. A este conjunto también se le denota como $\langle S \rangle$ y se le llama el **subespacio generado** por $S$. Si $W = \langle S \rangle$, se dice que $S$ es un sistema de generadores de $W$. Si existe un subconjunto finito $S$ tal que $W = \langle S \rangle$, se dice que $W$ es finitamente generado.

### Resultados

*   **Lema 3.1:** $S \subseteq \mathcal{L}(S)$ y $0 \in \mathcal{L}(S)$.
*   **Lema 3.2:** Si $W \subseteq V$, entonces $W \le V \iff \mathcal{L}(W) \subseteq W \iff W = \mathcal{L}(W)$.
*   **Lema 3.3:** Si $S \subseteq V$, entonces $\mathcal{L}(S) \le V$.
*   **Proposición 3.1:** Si $S \subseteq V$, $\mathcal{L}(S)$ es el mínimo subespacio de $V$ que contiene a $S$.
*   **Proposición 3.2:** Si $S \subseteq V$, entonces $\mathcal{L}(S) = \bigcap \{ W \le V \mid S \subseteq W \}$.

### Demostraciones

**Demostración del Lema 3.1:**
Para cualquier $s_0 \in S$, podemos escribir $s_0 = 1 \cdot s_0$, que es una combinación lineal finita de elementos de $S$; por lo tanto, $S \subseteq \mathcal{L}(S)$. Para el vector nulo, $0 = \sum_{s \in S} 0 \cdot s$ (con coeficientes nulos para todo $s$), luego $0 \in \mathcal{L}(S)$. $\blacksquare$

**Demostración del Lema 3.2:**
*   $(\implies)$ Si $W \le V$, $W$ es cerrado bajo sumas finitas y producto por escalares. Sea $v \in \mathcal{L}(W)$, entonces $v = \sum_{x \in W} \lambda_{x} x$. Como la suma es finita y cada término pertenece a $W$, se concluye que $v \in W$. Por tanto, $\mathcal{L}(W) \subseteq W$.
*   $(\impliedby)$ Si $\mathcal{L}(W) \subseteq W$, en particular $0 \in \mathcal{L}(W) \subseteq W$. Para cualquier $\lambda \in K$ y $w \in W$, $\lambda w \in \mathcal{L}(W) \subseteq W$. Análogamente, para $u, v \in W$, $u+v \in \mathcal{L}(W) \subseteq W$. Por lo tanto, $W \le V$. La equivalencia con $W = \mathcal{L}(W)$ sigue directamente del Lema 3.1. $\blacksquare$

**Demostración del Lema 3.3:**
Por el Lema 3.1, $0 \in \mathcal{L}(S)$. Sean $u = \sum_{s \in S} \lambda_{s} s$ y $v = \sum_{s \in S} \mu_{s} s$ en $\mathcal{L}(S)$. Su suma $u+v = \sum_{s \in S} (\lambda_{s} + \mu_{s}) s$ es una combinación lineal con soporte finito, luego $u+v \in \mathcal{L}(S)$. De igual forma, para $\alpha \in K$, $\alpha u = \sum_{s \in S} (\alpha \lambda_{s}) s \in \mathcal{L}(S)$. Así, $\mathcal{L}(S) \le V$. $\blacksquare$

**Demostración de la Proposición 3.1:**
Por el Lema 3.3, $\mathcal{L}(S) \le V$ y por el Lema 3.1, $S \subseteq \mathcal{L}(S)$. Sea $W \le V$ tal que $S \subseteq W$. Por el Lema 3.2, $\mathcal{L}(W) \subseteq W$. Puesto que $S \subseteq W$, se tiene $\mathcal{L}(S) \subseteq \mathcal{L}(W) \subseteq W$. Por ende, $\mathcal{L}(S)$ es el menor subespacio que contiene a $S$. $\blacksquare$

**Demostración de la Proposición 3.2:**
Es consecuencia directa de la Proposición 3.1, ya que el mínimo subespacio que contiene a $S$ es igual a la intersección de todos los subespacios de $V$ que contienen a $S$. $\blacksquare$

---

## 4. Dependencia e Independencia Lineal

**Definiciones:**
*   **Linealmente Dependiente (l.d.):** Una familia $(v_{i})_{i \in I}$ es l.d. si para algún $i \in I$, el vector $v_{i}$ es combinación lineal de los demás ($v_{j}$ con $j \neq i$).
*   **Linealmente Independiente (l.i.):** Una familia es l.i. si no es l.d.
*   **Base:** Un conjunto $\beta \subseteq V$ es una base de $V$ si $\beta$ es l.i. y $\mathcal{L}(\beta) = V$.

### Resultados

*   **Lema 4.1:** Un conjunto $S$ es linealmente independiente $\iff$ si $\sum_{s \in S} \lambda_{s} s = 0$, entonces $\lambda_{s} = 0$ para todo $s \in S$.
*   **Lema 4.2:** Si $S \subseteq V$ es l.i. y $w \in V \setminus \langle S \rangle$, entonces $S \cup \{w\}$ es l.i.
*   **Lema 4.3:** 
    1. Si $S \subseteq V$ es un conjunto l.i. maximal, entonces $S$ es base de $V$.
    2. Si $S \subseteq V$ es un generador minimal de $V$, entonces $S$ es base de $V$.
    3. $S$ es base de $V \iff S$ es l.i. maximal $\iff S$ es generador minimal.
*   **Lema 4.4:** Si $T$ es generador de $V$ y $S \subseteq T$ es un conjunto l.i. maximal en $T$, entonces $S$ es base de $V$.

### Demostraciones

**Demostración del Lema 4.1:**
*   $(\implies)$ Supongamos que $S$ es l.i. y $\sum_{s \in S} \lambda_{s} s = 0$. Si existiera algún $\lambda_{s_0} \neq 0$, podríamos despejar $s_0$:
    $$ s_0 = -\frac{1}{\lambda_{s_0}} \left( \sum_{s \neq s_0} \lambda_{s} s \right) $$
    Esto implicaría que $s_0$ es combinación lineal del resto, contradiciendo la independencia de $S$.
*   $(\impliedby)$ Supongamos que la única solución a $\sum \lambda_{s} s = 0$ es la trivial. Si $S$ fuese dependiente, existiría $s_0 \in S$ tal que $s_0 = \sum_{s \neq s_0} \lambda_{s} s$. Restando $s_0$, tendríamos $\sum_{s \neq s_0} \lambda_{s} s - 1 \cdot s_0 = 0$, una combinación lineal nula con el coeficiente de $s_0$ igual a $-1 \neq 0$, lo cual es una contradicción. $\blacksquare$

**Demostración del Lema 4.2:**
Supongamos que $\sum_{s \in S} \lambda_{s} s + \lambda w = 0$. Si $\lambda \neq 0$, despejando $w$ tendríamos $w = \sum_{s \in S} (-\lambda_{s}/\lambda) s \in \mathcal{L}(S)$, contradiciendo que $w \notin \langle S \rangle$. Por tanto, debe ser $\lambda = 0$. La ecuación se reduce a $\sum_{s \in S} \lambda_{s} s = 0$, y por ser $S$ l.i., $\lambda_{s} = 0$ para todo $s \in S$. Así, $S \cup \{w\}$ es l.i. $\blacksquare$

**Demostración del Lema 4.3:**
1. Supongamos $S$ l.i. maximal. Si existiera $w \in V \setminus \mathcal{L}(S)$, por el Lema 4.2, $S \cup \{w\}$ sería l.i., contradiciendo la maximalidad de $S$. Luego, $\mathcal{L}(S) = V$ y $S$ es base.
2. Supongamos $S$ generador minimal. Si $S$ fuera l.d., existiría $s_0 \in S$ tal que $s_0 \in \mathcal{L}(S \setminus \{s_0\})$. Esto implica $\mathcal{L}(S \setminus \{s_0\}) = \mathcal{L}(S) = V$, lo cual contradice que $S$ sea minimal.
3. Se deduce directamente al combinar (1) y (2). $\blacksquare$

**Demostración del Lema 4.4:**
Si $S$ es l.i. maximal en $T$, afirmamos que $T \subseteq \mathcal{L}(S)$. En efecto, si existiera $t \in T \setminus \mathcal{L}(S)$, por el Lema 4.2, $S \cup \{t\} \subseteq T$ sería l.i., contradiciendo la maximalidad de $S$ en $T$. Por tanto, $T \subseteq \mathcal{L}(S) \implies V = \mathcal{L}(T) \subseteq \mathcal{L}(S)$, concluyendo que $S$ es base. $\blacksquare$

---

## 5. Espacios Finitamente Generados

*(Nota: En adelante, consideramos espacios vectoriales finitamente generados).*

### Resultados (Generación y Bases)

**Proposición 5.1 (Teorema de Intercambio de Steinitz)**
Sea $V$ un espacio finitamente generado y $G \subseteq V$ tal que $\mathcal{L}(G) = V$. Si $I \subseteq V$ es un conjunto linealmente independiente, entonces la cardinalidad de $I$ es menor o igual a la cardinalidad de $G$ ($\#I \le \#G$).

**Proposición 5.2**
Si $V$ es finitamente generado y tenemos $I \subseteq G \subseteq V$ donde $I$ es l.i. y $\mathcal{L}(G) = V$, entonces existe una base $\beta$ de $V$ tal que $I \subseteq \beta \subseteq G$.

**Teorema 5.1:** Todo espacio vectorial finitamente generado tiene al menos una base.

**Teorema 5.2:** Si $V$ es finitamente generado, todo conjunto l.i. $I$ se puede extender a una base de $V$.

**Teorema 5.3:** Si $V$ es finitamente generado, todo conjunto generador contiene alguna base de $V$.

**Teorema 5.4:** Sean $\beta, \beta'$ bases de $V$ (finitamente generado). Entonces $\#\beta = \#\beta'$.

### Demostraciones (Generación y Bases)

**Demostración de la Proposición 5.1:**
Sean $n = \#G$, con $G = \{v_{1}, \dots, v_{n}\}$, y consideremos un subconjunto finito de $I$: $\{w_{1}, w_{2}, \dots, w_{m}\} \subseteq I$. Procederemos por reducción al absurdo suponiendo $m > n$.
Como $G$ genera a $V$, $w_{1} = \sum_{i=1}^n \lambda_{i} v_{i}$. Como $w_{1} \neq 0$, existe algún $j$ tal que $\lambda_{j} \neq 0$. Sin pérdida de generalidad, tomemos $j = 1$. Despejando $v_{1}$:
$$ v_{1} = \frac{1}{\lambda_{1}} w_{1} - \sum_{i=2}^n \frac{\lambda_{i}}{\lambda_{1}} v_{i} $$
Esto implica que $v_1 \in \mathcal{L}(w_1, v_2, \dots, v_n)$. Definiendo $G_{1} = \{w_{1}, v_{2}, \dots, v_{n}\}$, se cumple $\mathcal{L}(G_{1}) = V$.
Por inducción, supongamos que tras $k$ intercambios ($1 \le k < n$), el conjunto $G_{k} = \{w_{1}, \dots, w_{k}, v_{k+1}, \dots, v_{n}\}$ genera a $V$. Como $w_{k+1} \in \mathcal{L}(G_{k})$:
$$ w_{k+1} = \sum_{i=1}^k \lambda_{i} w_{i} + \sum_{i=k+1}^n \mu_{i} v_{i} $$
Como $I$ es l.i., $w_{k+1} \notin \mathcal{L}(w_{1}, \dots, w_{k})$, de modo que algún $\mu_{i} \neq 0$. Supongamos $\mu_{k+1} \neq 0$ y despejemos $v_{k+1}$:
$$ v_{k+1} = \frac{1}{\mu_{k+1}} \left( w_{k+1} - \sum_{i=1}^k \lambda_{i} w_{i} - \sum_{i=k+2}^n \mu_{i} v_{i} \right) $$
Así, $G_{k+1} = \{w_{1}, \dots, w_{k+1}, v_{k+2}, \dots, v_{n}\}$ genera a $V$.
Tras $n$ intercambios, $G_{n} = \{w_{1}, \dots, w_{n}\}$ genera a $V$. Pero como $m > n$, existirá $w_{n+1} \in I \subseteq \mathcal{L}(G_n)$, lo que contradice la independencia lineal de $I$. Por tanto, $m \le n$. $\blacksquare$

**Demostración de la Proposición 5.2:**
Si $I$ es l.i. maximal en $G$, por el Lema 4.4, $\beta = I$ es base. Si no lo es, se pueden ir añadiendo elementos de $G$ manteniendo la independencia lineal. Por la Proposición 5.1, el número de elementos independientes está acotado por $\#G < \infty$, por lo que el proceso termina en una base $\beta$ con $I \subseteq \beta \subseteq G$. $\blacksquare$

**Demostración del Teorema 5.1:**
Aplicamos la Proposición 5.2 con $I = \emptyset$ y $G = V$. $\blacksquare$

**Demostración del Teorema 5.2:**
Aplicamos la Proposición 5.2 tomando $I = I$ (el conjunto l.i.) y $G = V$. $\blacksquare$

**Demostración del Teorema 5.3:**
Aplicamos la Proposición 5.2 tomando $I = \emptyset$ y $G$ igual al generador dado. $\blacksquare$

**Demostración del Teorema 5.4:**
Como $\beta$ es l.i. y $\beta'$ genera a $V$, por la Proposición 5.1, $\#\beta \le \#\beta'$. Invirtiendo los roles, $\#\beta' \le \#\beta$. Por tricotomía, $\#\beta = \#\beta'$. $\blacksquare$

---

### Dimensión de un Espacio Vectorial

**Definición 5.1**
La **dimensión** de $V$ es $\dim(V) = \#\beta$, para cualquier base $\beta$ de $V$. Si $\beta$ es finita, $\dim(V) = \#\beta = n \in \mathbb{N} \cup \{0\}$, y si $\beta$ es infinita, escribimos $\dim(V) = \infty$.

### Resultados (Propiedades de la Dimensión)

**Proposición 5.3:** $V$ es finitamente generado $\iff \dim(V) < \infty$.

**Proposición 5.4:** Si $\dim(V) = n \in \mathbb{N} \cup \{0\}$, entonces:
1. Todo subconjunto l.i. $I \subseteq V$ con $\#I = n$ es base de $V$.
2. Todo generador $G \subseteq V$ con $\#G = n$ es base de $V$.

**Proposición 5.5:** Si $\dim(V) = n$ y $W \le V \implies \dim(W) \le n$.

**Proposición 5.6:** Si $\dim(V) = n$, $W \le V$ y $\dim(W) = n \implies W = V$.

**Lema 5.1**
Sea $V$ un $K$-espacio vectorial y $S \subseteq V$. $S$ es base de $V \iff \forall v \in V, \exists! (\lambda_{x})_{x\in S} \in K^{(S)} : v = \sum_{x\in S} \lambda_{x}x$.

### Demostraciones (Propiedades de la Dimensión)

**Demostración de la Proposición 5.3:**
*   $(\implies)$ Si $V$ es finitamente generado, existe $S \subseteq V$ finito tal que $\mathcal{L}(S)=V$. Por el Teorema 5.3, existe $\beta \subseteq S$ base de $V$, la cual es finita. Luego $\dim(V) < \infty$.
*   $(\impliedby)$ Si $\dim(V) = n \in \mathbb{N} \cup \{0\}$, existe una base finita $\beta$. Como $\mathcal{L}(\beta) = V$, $V$ es finitamente generado. $\blacksquare$

**Demostración de la Proposición 5.4:**
1. Sea $I \subseteq V$ l.i. con $\#I = n$. Por el Teorema 5.2, $I$ se extiende a una base $\beta$. Como $\#\beta = \dim(V) = n$ y $I \subseteq \beta$ con $\#I = n$, necesariamente $I = \beta$, de modo que $I$ es base.
2. Sea $G \subseteq V$ generador con $\#G = n$. Por el Teorema 5.3, $G$ contiene una base $\beta$. Como $\#\beta = n$ y $\beta \subseteq G$ con $\#G = n$, concluyo que $G = \beta$, luego $G$ es base. $\blacksquare$

**Demostración de la Proposición 5.5:**
Sea $\gamma$ una base de $W$. Como $\gamma$ es l.i. en $V$, por la Proposición 5.1 (Teorema de Steinitz), su cardinalidad no puede superar a la de una base de $V$. Por ende, $\dim(W) = \#\gamma \le \dim(V) = n$. $\blacksquare$

**Demostración de la Proposición 5.6:**
Sea $\gamma$ base de $W$. Entonces $\gamma$ es l.i. en $V$ y $\#\gamma = \dim(W) = n = \dim(V)$. Por la Proposición 5.4.1, $\gamma$ es base de $V$, por lo que $W = \mathcal{L}(\gamma) = V$. $\blacksquare$

**Demostración del Lema 5.1:**
*   $(\implies)$ Si $S$ es base, $\mathcal{L}(S) = V$, garantizando la existencia de los coeficientes. Si $v = \sum_{x \in S} \lambda_x x = \sum_{x \in S} \mu_x x$, restando se tiene $\sum_{x \in S} (\lambda_x - \mu_x) x = 0$. Por ser $S$ l.i., $\lambda_x - \mu_x = 0 \implies \lambda_x = \mu_x$ para todo $x \in S$.
*   $(\impliedby)$ La existencia implica $\mathcal{L}(S) = V$. Para la independencia lineal, si $\sum_{x \in S} \lambda_x x = 0$, como también $0 = \sum_{x \in S} 0x$, por la unicidad de representación se deduce que $\lambda_x = 0$ para todo $x \in S$. Así, $S$ es l.i. y por tanto base. $\blacksquare$

---

### Representación por Coordenadas

**Definición 5.2 (Coordenadas):** Si $\beta = \{v_{1}, v_{2}, \dots, v_{n}\}$ es una base ordenada de $V$ y $w \in V$, la única tupla $(a_{1}, a_{2}, \dots, a_{n}) \in K^n$ tal que $w = \sum_{i=1}^n a_{i}v_{i}$ se llama el **vector de coordenadas** de $w$ con respecto a $\beta$, denotado como $[w]_{\beta}$.

**Observación 5.2:** Si $\gamma = \{e_{1}, e_{2}, \dots, e_{n}\} \subseteq K^n$ es la base canónica de $K^n$ y $v \in K^n$, entonces $[v]_{\gamma} = v$.

**Observación 5.3:** Si $S \subset K^n$ es finito, mediante reducción gaussiana de matrices es posible determinar si $S$ es l.i. y hallar una base de $\langle S \rangle$. En espacios de dimensión infinita o de funciones, esto requiere métodos analíticos o algebraicos abstractos.
*Ejemplo:* Las funciones $\{1, \sin x, \sin 2x, \dots, \sin nx\} \subseteq \mathbb{R}^{[0, 2\pi)}$ son l.i.

---

## 6. Sumas y Sumas Directas

**Definición 6.1**
Si $U, W \le V$, la **suma** de $U$ y $W$ es:
$$ U+W = \{ u+w \mid u \in U, w \in W \} $$
En general, para una familia $\{W_i\}_{i \in I}$ de subespacios de $V$:
$$ \sum_{i \in I} W_{i} = \left\{ \sum_{i \in I} w_{i} \in V \;\middle|\; w_{i} \in W_{i} \, \forall i \in I, \; w_{i} = 0 \text{ para casi todo } i \right\} $$

**Observación 6.1:** $\sum_{i\in I} W_{i} \le V$ y es el mínimo subespacio que contiene a $\bigcup_{i\in I} W_{i}$. En consecuencia, $\sum_{i\in I} W_{i} = \mathcal{L}\left(\bigcup_{i\in I}W_{i}\right)$.

**Definición 6.2 (Suma Directa)**
Si $U, W \le V$, la suma $U+W$ es **directa** $\iff \forall x \in U+W, \exists! u \in U, w \in W : x = u+w$.
Para una familia $\{W_i\}_{i \in I}$, la suma $\sum_{i\in I} W_{i}$ es **directa** $\iff \forall x \in \sum_{i\in I} W_{i}, \exists! (w_{i})_{i \in I} : x = \sum_{i\in I} w_{i}$.

**Notación:** Denotamos la suma directa de $U$ y $W$ por $U \oplus W$, y la de una familia por $\bigoplus_{i \in I} W_{i}$.

### Resultados

**Lema 6.1:** Si $W_{i} = \mathcal{L}(G_{i})$ para todo $i \in I$, sea $G = \bigcup_{i\in I} G_{i}$, entonces $\mathcal{L}(G) = \sum_{i\in I} W_{i}$.

**Lema 6.2:** Sean $U, W \le V$. Entonces $V = U \oplus W \iff V = U+W \text{ y } U \cap W = \{0\}$.

**Lema 6.3:** Si $W_{i} \le V$ para todo $i \in I$:
$$ V = \bigoplus_{i\in I} W_{i} \iff V = \sum_{i\in I} W_{i} \quad \text{y} \quad W_{i} \cap \left( \sum_{j \neq i} W_{j} \right) = \{0\} \quad \forall i \in I $$

**Lema 6.4:** Sean $U, W \le V$ tales que $V = U+W$. Sean $\beta \subset U$ y $\gamma \subset W$ bases de $U$ y $W$. Entonces:
$$ V = U \oplus W \iff \beta \cup \gamma \text{ es base de } V \text{ y } \beta \cap \gamma = \emptyset $$

**Teorema 6.1 (Existencia de Complemento Directo)**
Sea $U$ un subespacio de un espacio finitamente generado $V$. Entonces $U$ tiene un complemento directo en $V$:
$$ U \le V \implies \exists W \le V : V = U \oplus W $$

**Teorema 6.2**
Sea $_{K}V$ finitamente generado y $U, W \le V$ con $U \cap W = \{0\}$. Entonces:
$$ \dim(U \oplus W) = \dim(U) + \dim(W) $$

**Teorema 6.3 (Fórmula de Grassmann)**
Sea $_{K}V$ finitamente generado y $U_{1}, U_{2} \le V$. Entonces:
$$ \dim(U_{1}+U_{2}) = \dim(U_{1}) + \dim(U_{2}) - \dim(U_{1} \cap U_{2}) $$

### Demostraciones

**Demostración del Lema 6.1:**
Sea $U \le V$. $G \subseteq U \iff G_{i} \subseteq U \, \forall i \iff W_{i} = \mathcal{L}(G_{i}) \subseteq U \, \forall i \iff \bigcup_{i\in I} W_i \subseteq U$. Al ser $\mathcal{L}(G)$ y $\sum W_i$ ambos el mínimo subespacio que contiene a $G$, son iguales. $\blacksquare$

**Demostración del Lema 6.2:**
*   $(\implies)$ Supongamos $V = U \oplus W$. Obviamente $V = U+W$. Si $v \in U \cap W$, se puede escribir como $v = v + 0$ ($v \in U, 0 \in W$) y como $v = 0 + v$ ($0 \in U, v \in W$). Por la unicidad de la representación, $v = 0$. Así, $U \cap W = \{0\}$.
*   $(\impliedby)$ Supongamos $V = U+W$ y $U \cap W = \{0\}$. Si $x = u+w = u'+w'$ con $u, u' \in U$ y $w, w' \in W$, se tiene $u - u' = w' - w$. Este vector pertenece a $U \cap W = \{0\}$, luego $u - u' = 0 \implies u = u'$ y $w' - w = 0 \implies w = w'$. Por tanto, la suma es directa. $\blacksquare$

**Demostración del Lema 6.3:**
*   $(\implies)$ Si la suma es directa, $V = \sum W_i$ por definición. Si $w \in W_i \cap \sum_{j \neq i} W_j$, expresando $w$ en términos de la suma de los demás espacios y restando, la unicidad de la representación del $0$ obliga a que $w = 0$.
*   $(\impliedby)$ Si $\sum w_i = \sum w'_i$, se tiene $w_i - w'_i = \sum_{j \neq i} (w'_j - w_j)$. El lado izquierdo está en $W_i$ y el derecho en $\sum_{j \neq i} W_j$. Por hipótesis, ambos lados son $0$, luego $w_i = w'_i$ para todo $i \in I$. $\blacksquare$

**Demostración del Lema 6.4:**
Sea $\delta = \beta \cup \gamma$. Por el Lema 6.1, $\mathcal{L}(\delta) = U+W = V$, por lo que $\delta$ siempre genera a $V$.
*   $(\implies)$ Supongamos $U \cap W = \{0\}$. Si $\sum_{x\in \beta} \lambda_x x + \sum_{y\in \gamma} \mu_y y = 0$, denotamos $u = \sum \lambda_x x \in U$ y $w = \sum \mu_y y \in W$. Entonces $u = -w \in U \cap W = \{0\} \implies u = 0$ y $w = 0$. Como $\beta$ y $\gamma$ son l.i., todos los $\lambda_x = 0$ y $\mu_y = 0$. Así, $\delta$ es l.i. y $\beta \cap \gamma = \emptyset$.
*   $(\impliedby)$ Si $\delta$ es base (en particular l.i.) y $\beta \cap \gamma = \emptyset$, sea $z \in U \cap W$. Escribiendo $z = \sum_{x \in \beta} \lambda_x x$ y $z = \sum_{y \in \gamma} \mu_y y$, restando obtenemos una combinación lineal nula de $\delta$. Por la independencia de $\delta$, todos los coeficientes son nulos, luego $z = 0$. Por el Lema 6.2, $V = U \oplus W$. $\blacksquare$

**Demostración del Teorema 6.1:**
Sea $\beta$ una base de $U$. Por el Teorema 5.2, existe una base $\delta$ de $V$ tal que $\beta \subseteq \delta$. Sea $\gamma = \delta \setminus \beta$ y definamos $W = \mathcal{L}(\gamma)$.
Puesto que $\delta = \beta \cup \gamma$ es base de $V$ y $\beta \cap \gamma = \emptyset$, aplicando el Lema 6.4 se concluye directamente que $V = U \oplus W$. $\blacksquare$

**Demostración del Teorema 6.2:**
Sin pérdida de generalidad supongamos $V = U \oplus W$. Sean $\beta$ base de $U$ y $\gamma$ base de $W$. Como $U \cap W = \{0\}$, por el Lema 6.4, $\delta = \beta \cup \gamma$ es base de $V$ y $\beta \cap \gamma = \emptyset$.
Por tanto, $\dim(U \oplus W) = \#\delta = \#\beta + \#\gamma = \dim(U) + \dim(W)$. $\blacksquare$

**Demostración del Teorema 6.3:**
Sea $I = U_{1} \cap U_{2} \le V$. Por el Teorema 6.1, existen subespacios $W_{1} \le U_{1}$ y $W_{2} \le U_{2}$ tales que:
$$ U_{1} = I \oplus W_{1} \quad \text{y} \quad U_{2} = I \oplus W_{2} $$
Demostraremos que $U_{1} + U_{2} = U_{1} \oplus W_{2}$:
1.  **Generación:** $U_{1} + U_{2} = U_{1} + (I + W_{2}) = (U_{1} + I) + W_{2} = U_{1} + W_{2}$ (pues $I \subseteq U_{1}$).
2.  **Suma directa:** $U_{1} \cap W_{2} \subseteq U_{1} \cap U_{2} = I$. Además $U_{1} \cap W_{2} \subseteq W_{2}$. Por ende, $U_{1} \cap W_{2} \subseteq I \cap W_{2} = \{0\}$.
Así, $U_{1} + U_{2} = U_{1} \oplus W_{2}$.
Aplicando el Teorema 6.2:
$$ \dim(U_{1} + U_{2}) = \dim(U_{1}) + \dim(W_{2}) $$
Como $U_{2} = I \oplus W_{2}$, nuevamente por el Teorema 6.2:
$$ \dim(U_{2}) = \dim(I) + \dim(W_{2}) \implies \dim(W_{2}) = \dim(U_{2}) - \dim(I) $$
Sustituyendo $\dim(W_{2})$ en la ecuación anterior obtenemos:
$$ \dim(U_{1} + U_{2}) = \dim(U_{1}) + \dim(U_{2}) - \dim(U_{1} \cap U_{2}) \quad \blacksquare $$
**Definición 6.3** Sea $U,W\le K$. El producto cartesiano de $U$ y $W$ denotado por $U\times W$ es igual a $$U\times W=\{ (u,w) | u\in U, w\in W \}$$
Las operaciones en el producto cartesiano son:
$+: (u,u\prime)+(w,w\prime) \implies (u+w, u\prime+w\prime)$
$+: (u,u\prime)\cdot(w,w\prime) \implies (uw, u\prime w\prime)$
(componente a componente)

