## Subcampos

**Def. 3.1** Un espacio vectorial sobre $K$ (o un $K$-espacio vectorial, $K$=e.v.) es un conjunto $V$ cuyos elementos se llaman vectores junto con dos operaciones $+:V\times V \to V_{(v,w \mapsto v+w)}$, $\cdot: V\times V\to V_{v,w \mapsto vw }$ deben satisfacerse los siguientes ocho axiomas:

1. $u+(v+w)=(u+v)+w \forall u,v,w \in V$
2. $\exists 0 \in V:u+0=0+u=u\forall u\in V$
3. $\forall v \in V \exists -v\in V:-v+u=u-u=0$
4. $\forall v,w\in V, v+w=w+v$
5. $\lambda(\mu v) = (\lambda\mu)v \forall \lambda,\mu,v \in V$
6. $1w=w|\forall w\in V$
7. $(\alpha+\beta)v = \alpha v+\beta v \forall \alpha,\beta \in K, v\in V$
8. $\alpha(u+v) = \alpha u+\alpha v\forall a\in K,\forall u,v\in V$

**Not.** ==$_{K}V$ significa que V es un $K$-e.v.==

**Ejemplos**
1. $n \in \mathbb{N}, V=K^n = \{ (a_{1},a_{2},\dots,a_{n}) | a_{i} \in K \forall i \}$
2. $V= _KK$ ($K$-e.v. regular)
3. $0 = \{ 0 \}$ con la suma de vectores y producto por escalares naturales $_{K}0 \forall \lambda \in K$
4. $V=K[x] = \{\sum_{i=0}^n a_{i}x^i | _{a_{i} \in K \forall i}^{n \in \mathbb{N} \setminus \{ 0 \}}\}$

## Subespacios vectoriales

**Def.** Si $_{K}V$ u nsubconjunto $W \subseteq V$ es un subespacio vectorial de V

**Not.** $W \le V$

1. $0 \in W \equiv W \ne \varnothing$
2. $u,v \in W \implies u+v=w$
3. $v\in W, \lambda \in K \implies \lambda v \in W$

**Obs.** Si $_{K}V$ y $W \le V$ entonces $_{K}W$ con las mismas operaciones de $V$.

**Ejemplos**

1. $0 \le V, V\le V$ para cualquier espacio vectorial en cualquier campo (subespacios trivial y total).
2. Si $K = \mathbb{R}$, sabemos que los subespacios de
	1. $_{\mathbb{R}}\mathbb{R}$ son $0\le\mathbb{R}$ y $\mathbb{R} \le \mathbb{R}$
	2. $_{\mathbb{R}}\mathbb{R}^2$ son igualmente $0\le\mathbb{R}^2$ y $\mathbb{R}^2 \le \mathbb{R}^2$, como las rectas por el origen
	3. $_{\mathbb{R}}\mathbb{R}^3$ son igualmente $0 \le \mathbb{R}^3$ y $\mathbb{R}^3 \le \mathbb{R}^3$, como las rectas y planos por el origen
	4. $_{\mathbb{R}}\mathbb{R}^n$ son $0 \le \mathbb{R}^n$ y $\mathbb{R}^n \le \mathbb{R}^n$
3. Matrices cuadradas simetricas. $Sim_{n\times m}(K) = \{ A = (a_{i_{j}}) \in K^{n\times m} | \text{A simetrica}\}$
4. $K_{n}[x] = \{ p(x) \in K[x] | gr(p) \le n \} \ne K[x]$
5. Si $K \le L, _{K}L$ y $_{K}K \le _{K}L$
6. Si $K=\mathbb{R}$ y $V = \mathbb{R}^{[a,b]} = \{ f: [a,b] \to \mathbb{R} | f \text{ funcion} \}$.
7. Si $S$ conjunto, $K^{(S)} = \{ f: S \to K | f(x) = 0 \dot{\forall}x \in S \}$ (las funciones de soporte finito de $S$ a $K$). $K^{(S)} \le K$

==**Nota**== $gr(0) = -\infty$

En sup. 1 aparecen como ==espacios generados==

**Prop. 1**
Si $V_{i} \le _{K}V \forall i \in I \implies \cap_{i \in I} V_{i} \le V$

**Dem.**
1. $0 \in V_{i} \forall i \in I \implies 0 \in W$
2. $\therefore v+w \in V_{i} \forall i \in I$
3. $\therefore v+w \in W$
4. $v\in W, \lambda \in K, v \in V_{i} \forall i \in I \land \lambda v\in V_{i}\forall i \in I\therefore \lambda v \in W$

**Obs. 2**
La union de subespacios no necesariamente es subespacio

## Combinaciones Lineales

**Def. 3.2**
Sea $V$ un $K$-e.v. y sea $S$ un conjunto de vectores en $V$ ($S \subseteq V$), una comb. lineal de los vectores de $S$ es cualquier vector de la forma

$$
v=\sum_{s\in S} \lambda _{s}S : \lambda_{s}\in K \forall s \in S
$$
de forma implicita, $\lambda_{s}=0\dot{\forall} s \in S$.

**Ejemplo** Todo polinomio $f \in K[x]$ es comb. lineal de las potencias de $x: S = \{ 1,x,x^2, \dots \}$ en efecto, $f=\sum^{\infty}_{i=0} a_{i}x^i$ con $^{a_{i}\in K\forall i}_{a_{i}=0\dot{\forall}i}$
**Not.** Si $S \subset V \implies$
$$
\mathcal{L}(s)=\{ v \in V |v \text{ es comb. lineal de los elementos de S} \}
$$

**Lema 1**
$$
S \subseteq \mathcal{L}(s) \land 0 \in \mathcal{L}(s)
$$
**Lema 2**
Si $W\subseteq V \implies$
$$
W\le V \iff \mathcal{L}(W) \subseteq W \left(\iff W = \mathcal{L}(W)\right)
$$
**Dem.** $\implies$

$$
0\in W, W+W\subseteq W
$$

Sea $v\in \mathcal{L}(W) \therefore v=\sum_{x\in W} \lambda_{x}x$

**Dem** $\Longleftarrow$
Si $\mathcal{L}(W) \subseteq W \implies \lambda W\subseteq \mathcal{L}(W)\subseteq W$

Igualmente,

$$
0 \in \mathcal{L}(W) \subseteq W
$$

$$
W+W\subseteq \mathcal{L}(W)\subseteq W
$$

$$
\therefore W \le V
$$
**Lema 3**
Si $S\subseteq_{k}V, \therefore \mathcal{L}(S) \le V$

**Dem.**

$$
0\in \mathcal{L}(S) \text{ (lema 1)}
$$

$$
\sum_{s\in S} \lambda_{s}S, \sum_{s \in S}\mu_{s}s \in \mathcal{L}(S)
$$

$$
\sum\lambda_{s}s\sum\mu_{s}s = \sum_{s\in S} (\lambda_{s}+\mu_{s})s \in \mathcal{L}(S)
$$
**Def. 3.3** Si $S\subseteq V$, $\mathcal{L}(S)$ se llama el subespacio vectorial de $V$ generado por $S$

**Not.** $\langle S \rangle$

**Prop. 2** Si $S\subset V, \langle S \rangle$ es el minimo subespacio de $V$ que contiene a $S$

**Dem.**


$$
\mathcal{L}(S) \le V \text{ (lema 3)}
$$

$$
\mathcal{L}(S) \ge S \text{ (lema 1)}
$$
Sea $W\le V : S \subset W \therefore \mathcal{L}(S) \le W$
$$
\mathcal{L}(S) \le \mathcal{L}(W)
$$
**Prop 3** Si $S\subseteq V, \mathcal{L}(S)=\cap \{ W\le V : W \supseteq S \}$
**Dem.**

Como $\mathcal{L}(S) \le V$ y $S\subseteq \mathcal{L}(S)$

**Def. 3.4** Si $S\subseteq V$ y $W=\mathcal{L}(S)\le V$
1. $W$ es generado por $S$
2. $S$ es un conjunto (o sistema) de generadores de $W$
3. $W$ es finitamente generado si $\exists S \text{ finito} : W = \mathcal{L}(S)$

**Ejemplo**

$$
 K_{n}[x] = \langle 1,x,x^2, \dots, x^n \rangle
$$
**Ejemplo**
1. $S\le \langle S \rangle$
2. $S\subseteq T \implies \langle S \rangle \subseteq \mathcal{L}(T)$
3. $\langle \langle S \rangle \rangle = \langle S \rangle$

## Dependencia e Independencia Lineal

**Def. 4.1** Si $_{k}V,$ sea $(V_{i})_{i \in I}$ una familia de vectores en $V$ $(\forall i \in I, v\in V)$. Una comb. lineal de esta forma de vectore ses cualquier vector de la forma
$$
v=\sum_{i\in I} \lambda_{i}v_{i}
$$
donde
$$
\lambda_{i} \in K \forall i,\lambda_{i}=0\dot\forall i 
$$
**Not.**

$$
\mathcal{L}((V_{i})_{i \in I}) = \{  v \in V | v \text{ c.l. de } (v_{i})_{i\in I} \}
$$
**Obs. 4.1**
La ==*def 4.1*== $\sim\equiv$ a la ==*def. 3.2*== 

**Def. 4.2** Una familia $(v_{i})_{i\in I}$ es linealmente dependiente (l.d.) $\iff$ si para alguna $i \in I, v_{i}$ es c.l. de las otras $v_{j} : j\ne i$

**Def. 4.3** $(v_{i})_{i \in I}$ es linealmente independiente (l.i.) $\iff$ no es l.d.

**Def 4.4** Si $S\subseteq V$ y $W = \langle S \rangle \le V$,
1. $W$ es generado por $S$
2. $S$ e sun conjunto (o sistema) de generadores $W$
3. $W$ es finitamente generado si $\exists S \text{ finito } : W = \langle S \rangle$

**Obs. 4.2** Si $(V_{i})_{i \in I}$ es l.i. $\implies$ no tiene repeticiones.

**Lema 4.1** Un conjunto es l.i. $\iff$
$$
\sum_{x\in S} \lambda_{x}x = 0 \implies \lambda_{x} = 0 \forall a \in S
$$

**Dem. $\implies$** Sup. $S$ l.i. y sup. $\sum_{x\in S}\lambda_{x}x =0$

Sea $s\in S$ pd $\lambda_{s}=0$

Sup. $\lambda_{s} \ne 0$,

$$
S = \frac{-1}{\lambda _{s}} \left( \sum_{x\ne s} \lambda_{x}x \right)
$$

**Dem. $\Longleftarrow$** Sup. p.d. $S$ l.i.
$S_{0} \in \mathcal{L}(S \setminus \{  s_{0} \})$
$S_{0} = \sum_{x\in S; x\ne S_{0}} \lambda_{x}x$

**Corolario** $S$ es l.d. $\iff \exists (\lambda_{s})_{s \in S}$

$$
\sum_{s\in S} \lambda_{s} S = 0 \land \{  \lambda_{s} \} \ne \{ 0 \}
$$
esto quiere decir que no todo $\lambda_{s} =0$. Llamado una rel. de dependencia lineal.

**Ejercicio 4.1** Sean $S,T \subseteq V, S \subseteq T$, demostrar
1. Si $S$ genera a todo $V$, $\mathcal{L}(S)= V \implies \mathcal{L}(T) = V$
2. $T$ l.i. $\implies$ $S$ l.i.

**Lema 4.2** Si $S\subseteq V$ es l.i. y $w\in V\setminus \langle S \rangle \implies S \cup \{ w \}$ es l.i.

**Dem.** Supongamos que $\sum_{s\in S} \lambda_{s}s + \lambda w = 0$

Si $\lambda=0, \sum_{s\in S} \lambda_{s}s = 0 \therefore \lambda_{s} = 0 \forall s\in S$ ($s$ l.i.) 

Si $\lambda\ne_{0}, w=\sum_{s\in S} ()s \in \mathcal{L}(s)$ ↯

**Def 4.5** Una base de $_{K}V$ es un conjunto $\beta \subseteq V:$
1. $\beta$ l.i.
2. $\mathcal{L}(\beta)=V$

**Ejemplos**
1. $\beta=\varnothing$ es base de $V=0$
2. $\beta=\{ E_{1},E_{2}, \dots, E_{n} \}$ es base de $K^n, n \in \mathbb{N}$
   $= \{ e_{1},e_{2},\dots,e^n \}$
3. $\beta=\{ 1,x,x^2,\dots,x^n,x^{n+1} \}$ es base de $V = K[x]$

**Lema 4.3**
1. Si $S \subseteq V$ l.i. maximal$^*$ $\implies S$ base de $V$
   $^*: S \subset S\prime \implies S\prime$ ld.
2. Si $S\subseteq V$ es un generador minimal de $V \implies S$ base de $V$.
3. $S$ base de $V \iff S$ es base independiente maximal de $V \iff S$ generador minimal de $V$

**Dem.**
1. Sup. $S$ l.i. maximal, P.D. $\mathcal{L}(S)=V$, sup. $\exists w \in V : w\not\in \mathcal{L}(S)$
   Por el lema 4.2, sabemos que $S\subset S \cup \{ w \}$ l.i. ↯ $\therefore \mathcal{L}(S)=V \therefore S$  base
2. Sup. $S$ generador maximal de $V$, sup. $S$ l.i. $\therefore \exists s_{0} \in S : \mathcal{L}(S\setminus \{ s_{0} \})$, ent. $S \subseteq \mathcal{L}(S \setminus \{ s_{0} \}) \therefore \mathcal{L}(S) = V$ (por hip.), $V \subseteq \mathcal{L}\mathcal{L}(S\setminus \{ s_{0} \}) = \mathcal{L}(S\setminus \{ s_{0} \})=V$
3. 