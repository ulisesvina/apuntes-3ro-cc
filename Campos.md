## Subcampos

**Def.** Un espacio vectorial sobre $K$ (o un $K$-espacio vectorial, $K$=e.v.) es un conjunto $V$ cuyos elementos se llaman vectores junto con dos operaciones $+:V\times V \to V_{(v,w \mapsto v+w)}$, $\cdot: V\times V\to V_{v,w \mapsto vw }$ deben satisfacerse los siguientes ocho axiomas:

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
7. Si $S$ conjunto, $K^{(S)} = \{ f: S \to K | f(x) = 0 \dot{\forall}x \in S \}$ (las funciones de soporte finito de $S$ a $K$)

==**Nota**== $gr(0) = -\infty$

En sup. 1 aparecen como ==espacios generados==

