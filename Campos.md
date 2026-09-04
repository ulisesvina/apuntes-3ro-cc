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
    *  ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIDqnUc6Yu+sUgYCpyUOSKQzRX0JbP5ML7Qd5G5haxst2 deadbeef@cheese
 En $\mathbb{R}^3$, son $0$, $\mathbb{R}^3$, y las rectas y planos por el origen.
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

**Definición 5.1** La dim. de $V$ es $dimV=\#\beta, \beta$ para cualquier base de $V$. Si $\beta$ es finita, $dimV=\#\beta=n\in \mathbb{N}$, y si $\beta$ es infinita, $dimV\not\in \mathbb{N}$ y decimos simplemente que $dimV=\infty$.

**Proposición 5.3** $V$ f.g. $\iff dimV<\infty (\iff dim\mathbb{N})$ 

**Demostración $(\implies)$**
Si $V$ f.g., ent. $\exists S \subseteq V$ finito tal que $\mathcal{L}(S)=V$.
$\therefore \exists \beta \subseteq S$ base $\therefore \beta$ finita $\therefore dimV<\infty$ $\blacksquare$

**Demostración $(\impliedby)$**
Si $dimV \in \mathbb{N} \implies\exists$ base $\beta$ finita $\therefore\beta$ es un generador finito. $\blacksquare$

**Proposición  5.4** Si $dimV\in \mathbb{N}$ ent.:
1. Todo subconjunto l.i. $I\subseteq V$ con $\#I-n$ es base
2. Todo generador $G\subseteq V$ con $\#G=n$ es base

**Demostración 5.4.1**
*Teorema 5.2 $\star$*

**Demostración 5.4.2**
*Prop. 5.3* $\star$

**Proposición 5.5**
Si $dimV=n$ y $W \le V \implies dimW \le n$

**Proposición 5.6**
$dimV=n, W\le V \land dimW=dimV \implies W=V$

**Demostración 5.5**
Sea $\gamma$ base de $W : \gamma$ es un subconjunto l.i. de $V \therefore \exists \beta$ base de $V : \gamma \subseteq \beta \implies dimW=\#Y\le\#\beta=dimV$.

**Demostración 5.6**

**Lema 5.1**
Sea $V$ un $K$-e.v. (no necesariamente f.g.), $S\subseteq V$, ent. $S$ es base de $V \iff \forall v \in V \exists! (\lambda_{s})_{s\in S} \in K^(S) : v=\sum_{x\in S} \lambda_{x}x$

*Nota: $(\lambda_{s})$ (entre parentesis) significa que casi todos son cero.*

**Demostración 5.1 $(\implies)$**
Si $S$ es base y $v\in V$, existen los $\lambda_{s}$ pues $\mathcal{L}(S)=V$, y ademas es unico si tambien $v=\sum_{\alpha\in S} \mu_{x}x$

$\therefore \sum_{\alpha\in S} (\mu_{x} - \lambda_{x})x=0$
$\therefore \mu_{x}-\lambda_{x}=0 \forall x\in S$ (pues $S$ es l.i.)
$\therefore \mu_{x}=\lambda_{x}\forall x\in S$
$\therefore (\mu_{x})_{x\in S} = (\lambda_{x})_{x \in S}$
$\therefore$ es unico.

**Demostración 5.1 $(\impliedby)$** (sup. la condicion del lema)
$\therefore \mathcal{L}(S)=V$ (por la existencia)

Sup. que $\exists$ c.l. tal que $0= \sum_{x\in S} \lambda_{x}x = \sum_{x\in S} 0x$ 

Por la unicidad, $\lambda_{x}=0 \forall x\in S \therefore S$ l.i.

**Definición 5.2** Si $\beta= \{ v_{1},v_{2},\dots,v_{n} \}$ es una base (ordenada) de $V$ y $w\in V$, ent. la unica n-ada ordenada $(a_{1}, a_{2}, \dots, a_{n}) \in K^n$ tal que $W=\sum^n_{i=1} a_{i}w_{i}$ se llama el vector de coordenadas de $W$ con respecto a la base $\beta$.

**Obs. 5.2** Si $\gamma=\{ e_{1}, e_{2}, \dots, e_{n} \} \subseteq K^n$ es la base canonica de $K_{n}$ y se toma un vector $v\in K^n, [v]_{\gamma} = v$.

**Obs. 5.3** Si $S \subset K^n$ es finito, tenemos forma de determinar si $S$ es l.i. y para dar una base $\langle S \rangle$. En otros espacios esto puede ser menos simple.

*Ejemplo:* Las funcs. $\{  1, \sin x, \sin 2x, \dots, \sin nx \} \subseteq D [0, 2\pi)$ son l.i. (pero no se pueden probar escalando matrices).

## 6. Sumas y Sumas Directas

**Def. 6.1**  Si $U,W \le V$, ent. la suma de $U, W$ es $U+W = \{ u+w | u \in U, w \in W \}$ (si $W_{i}$ es un subespacio de $V$ para todo $i \in I$, su suma es $\sum_{i \in I} W_{i} = \left\{  \sum_{i \in I} w_{i} \in V | ^{w_{i} \in W_{i} \forall i \in I}_{w_{i} = 0 \dot{\forall} i \in I}  \right\}$

**Obs 6.1** Si $W_{i} \le V \forall i \in I, \sum_{i\in I}W_{i} \le V$, y es el min. subespacio de $V$ que contiene a todos los $W_{i}$ (i.e. el min. que contiene $\cup_{i\in I} W_{i}$, y en otras palabras, $\sum_{i\in I} W_{i} = \mathcal{L}(\cup_{i\in I}W_{i}) \star$), pero el min. subespacio que contiene a un conjunto es el generado.

*Esquema de la dem.*
1. $\sum_{i\in I} w_{i} + \sum_{i\in I} w_{i}\prime = \sum_{i\in I}(w_{i}, w_{i}\prime)$ 
   $\lambda \sum_{i\in I} w_{i} = \sum_{i\in I}(\lambda w_{i})$
   $0 = \sum_{i\in I}0$

**Lema 6.1** Si $W_{i} = \mathcal{L}(G_{i}) \forall i \in I$, sean $G= \cup_{i\in I} G_{i} \le V, W=\sum_{i\in I}W_{i}$, ent. $\mathcal{L}(G) = \sum_{i\in I}W_{i}$

**Dem.** Sea $U$ cualquier subespacio de $V$, $G\subseteq U \iff G_{i} \subseteq U \forall i\in I \iff W_{i} \subseteq U \forall i\in I \iff (\cup_{i\in I}W_{i}) \subseteq U \blacksquare$.

**Def. 6.2** Si $U,W \le V$, decimos que la suma $U+V$ es directa $\iff \forall x\in U+W \exists! u\in U,w\in W:x=u+w$, similarmente si tomamos $W_{i}\le  V \forall i \in I$, la suma $\sum_{i\in I}W_{i}$ es directa $\iff \forall x\in \sum_{i\in I} W_{i} \exists! w_{i}\in W_{i \in I} : x = \sum_{i\in I} w_{i}$

**Notación** Si $U+W$ es directa, lo denotamos por $U \oplus W$, simultáneamente, $\oplus_{i \in I} W_{i}$ denota "suma directa de las $W_i, i \in I$".

**Lema 6.1** $U,W \le V \implies V=U\oplus W \iff$
1. $V=U+W$
2. $U\cap W=0$

**Demostración $(\implies)$**
Sup. $V=U\oplus W$

1. $V=U+W$ por def.
2. Sea $v\in U\cap W$
   $v=v+0=0+v$
   $\therefore v=0 \blacksquare$

**Demostración $(\impliedby)$**
Sup. 1) y 11),
1. $V= U+W$
   Sup. $v\in V$ es tal que $v=u+w=u\prime+w\prime, ^{u,u\prime \in U}_{w,w\prime \in W}$
2. $u-u\prime=w\prime-w$, y notamos que esto está a la vez en $U$ y en $W$, y que es $0$
   $u-u\prime=0=w\prime-w$
   $\therefore u=u\prime \land w=w\prime \blacksquare$

**Lema. 6.1' (6.1 prima)**
Si $W_{i} \le V \forall i \in I$
$$
V=\oplus_{i\in I} W_{i} \iff \begin{cases}
& V=\sum_{i\in I} W_{i} \\
& W_{i} \cap \sum_{i\in I; j\ne i} W_{j} = 0
\end{cases}
$$

**Lema 6.2**
Sean $U,W$ dos subespacios cualesquiera tales que $U,W \le V$ con $V=U+W$ y sean $\beta \subset U, \gamma \subset W$ bases tales que  $\beta\cap \gamma=\varnothing$.

Entonces, $V=U\oplus W \iff \beta \cup \gamma$ base de $V$.

Sea $S=\beta\cup \gamma$, por el lema 6.1, $\langle \delta \rangle = U+W=V \therefore$ bastaría probar  $U\cap W=0 \iff \delta$ es l.i.

**Demostración $(\implies)$**
Sup. $U\cap W =0$ y sup. $\sum_{x\in \delta} \lambda_{x}x=0$
Sean $u=\sum_{x\in \beta}\lambda_{x}x,w=\sum_{x\in \gamma}\lambda_{x}x$
$\therefore u\in U, w\in W, u+w=0$
$u\in U = -w\in W$
$\therefore u=-w=0$
$\therefore \lambda_{x}=0 \forall x\in \beta, x\in \gamma$
$\therefore \lambda_{x}=0 \forall x\in \delta$

Finalmente, se cumple por el lema 6.1. $\blacksquare$

**Demostración $(\impliedby)$**
Sea $\delta$ l.i. y sea $z\in U\cap W$, $z=\sum_{x\in \beta} \lambda_{x}x,-z\sum_{x\in \gamma}\lambda_{x}x$
$0=\lambda_{x}=0\forall \beta \subseteq x\in \delta, \therefore z=0 \blacksquare$

**Teorema 6.1** Sea $U$ un subespacio finitamente generado cualquiera de $V$. $U$ tiene complemento directo.
$$
\text{Si } U \le V \implies \exists W \le V : V = U\oplus W
$$

**Demostración**
Sea $\beta$ una base de $U$ y sea $\delta$ una base de $V$ tal que $\beta \subseteq \delta$ (Teo. 5.2)

Sean $\gamma = \delta \setminus \beta$ y $W=\langle\gamma \rangle$, $\gamma$ base de $W$. $\mathcal{L}(\beta) =U, \mathcal{L}(\gamma)=W$
$$
\implies V= \mathcal{L}(\delta)= U+W \text{ (lema 6.1)}
$$
$$
\therefore V=U+W; \beta \subset U, \gamma \subset W \text{ bases}; \beta \cap \gamma = \varnothing
$$

Como $S$ l.i. $\implies U \oplus W$

**Teorema 6.2**
Sea $_{K}V$ un espacio finitamente generado y sean $U,W\le V : U\cap W=\{ 0 \}$, ent.
$$
dim(U \oplus W) = dim(U) + dim(W)
$$
**Demostración**
Se tiene $U+W = \le V$, s.p.g. $U+W =V$. Sean $\beta \subset U, \gamma \subset W$ bases, como $U\cap W=0 \implies \beta\cap \gamma=\varnothing$.

Sea $\delta = \beta \cup \gamma$, se necesita que $\delta$ sea l.i., para ello usamos el lema 6.2, ent. $\delta$ es base de $V$, esto era inmediato porque $\langle \delta \rangle = V$, ya que $\delta = \beta\cup \gamma$.

Como $\beta\cap \gamma=\varnothing, \delta=\beta\cup \gamma, \therefore \#\gamma = \#\beta + \#\delta \therefore dim(V) = dim(U) + dim(W) \blacksquare$.

**Teorema 6.3**
Sea $_{K}V$ un espacio finitamente generado y $U_{1}, U_{2} \le V$, ent.
$$dim(U_{1}+U_{2}) = dim(U_{1})+dim(U_{2}) - dim(U_{1} \cap U_{2})$$

**Demostración**
Decimos s.p.g. que $U_{1}+U_{2}=V$ (no se pierde generalidad porque trabajamos solamente dentro de $V$).

Sea $I=U_{1}\cup U_{2} \le V$. Sean $W_{1},W_{2} \le V : U_{1}=I\oplus W_{1}, U_{2}=I\oplus W_{2}$ (Teo. 6.1), ent.
$$
V=U_{1} \oplus  W_{2}
$$

1. $U_{1} \le U_{1}+W_{2} \land U_{2} = I + W_{2} \le U_{1}+W_{2}$
   $V=U_{1}+U_{2}\le U_{1}+W_{2} \therefore U_{1}+W_{2}=V$
2. $U_{1}\cap U_{2} \le U_{1}\cap U_{2} = I$
   $U_{1} \cap W_{2} = \star U_{1} \cap W_{2} \cap W_{2} = U_{1} \cap W_{2}=0$
   $U_{1}\cap W_{2}=0$
   $\therefore dim(V)= dim(U_{1})+dim(U_{2})=dim(U_{1}\cap U_{1})$