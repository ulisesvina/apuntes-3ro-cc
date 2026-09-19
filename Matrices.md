## 1. El espacio de las matrices
El $K$-e.v., $K^{m\times n}$ (de las matrices $m\times n$ con entradas en $K$ y sistemas de ecuaciones lineales).

**Notación** $A\in K^{m\times n}, A=\begin{pmatrix} a_{ij} \end{pmatrix} i \in I_{m}, j\in I_{n}$, también pondremos $A_{ij} = a_{ij}$

**Definición 1.1** El producto de las matrices $A\in K^{m\times n}$ y $B\in K^{n\times p}$ es una matriz $AB\in K^{m\times p}$ (porque no se pueden multiplicar si el num. de columnas en $A$ no es igual al num. de renglones en $B$) donde $(AB)_{ik} = A_{i}\cdot B^{k} (i\in I_{m}, k\in I_{p}$.

También $(AB)=(C_{ik}),C_{ik}\sum^n_{i=1} a_{ij}b_{jk}$

**Ejemplo 1** 
$$
\begin{pmatrix}
1 & 2 & 3\\3&1&1
\end{pmatrix}

\begin{pmatrix}
2 & 0 \\ 4 & 1 \\ 6 & 8
\end{pmatrix} =
\begin{pmatrix}
28 & 26 \\ \\
16 & 9
\end{pmatrix}
$$

**Ejemplo 2**
$$
\begin{pmatrix}
2 & 0 \\ 4 & 1 \\ 6 & 8
\end{pmatrix}
\begin{pmatrix}
1 & 2 & 3\\3&1&1
\end{pmatrix} =
\begin{pmatrix}
2 & 4 & 6 \\
7 & 9 & 13  \\
30 & 20 & 26
\end{pmatrix}
$$

**Vectores renglón y vectores columna**
$$
C\in K^{1\times n}, D\in K^{n\times_{1}} \implies CD=C\cdot D\text{ producto punto}
$$

$$
CD=\begin{pmatrix}
c_{1} &c_{2} &\dots &c_{n}
\end{pmatrix}
\begin{pmatrix}
d_{1} \\
d_{2} \\
\dots \\
d_{n}
\end{pmatrix} = \sum^n_{i=1} c_{i}d_{i}
$$

**Lema 1.1** Sean $A\in K^{m\times n}, B\in K^{n\times p}, i\in I_{m},k\in I_{p}$
1. $(AB)_{i}=A_{i}B=\sum_{j\in I_{n}} a_{ij}B_{j}\in \mathcal{L}(B_{1},B_{2},\dots, B_{n})= \mathcal{R}(B)$
2. $(AB)^k = AB^k = \sum_{i\in I_{n}} A^{j}b_{jk} = \sum_{j\in I_{n}} b_{jk}A^j \in \mathcal{L}(A^1,A^2,\dots A^n)=\mathcal{C}(A)$

Los renglones del producto son combinaciones lineales de los renglones del 2do factor con las entradas del correspondiente renglón del 1er factor (A)

Las columnas del  producto son combinaciones lineales de las columnas del 1er factor )con las entradas de la correspondiente columna del 2do factor (B)

**Demostración**
1. Por def., $(AB)=(A_{i}B^1, A_{i}B^2, \dots, A_{i}B^p)$, y si $k\in I_{p}$ la entrada $k$ de este vector es $A_{i}B^k=\sum_{j\in I_{n}} a_{ij}b_{jk}$, la misma que la entrada $k$ del vector $\sum_{i\in I_{n}}a_{ij}B_{j}$
2. $\star$

**Ejemplo** Si $A\in K^{m\times n}$ y $B\in K^{i\times n}$, las soluciones del sistema $x^1A^1+X^2A^2+\dots+x^nA^n=B$ son las vectores $S=(s_{1},s_{2},\dots,s_{n})\in K^n : \sum_{i\in I_{n}}s_{i}A^i=B$
****

## 2. Producto de matrices

**Definición 2.0** En $K^n$ el producto punto de dos vectores $A$ de coordenadas $(a_{1},\dots,a_{n})$ y $B$ es coordenadas $(b_{1},\dots,b_{n})$ con $A,B\in K^n$ se denota por $A\cdot B$ y es igual a
$$
A\cdot B = \sum_{i = 1}^n a_{n}b_{n}
$$

*Propiedades del producto punto* $\star$
1. $(A+B)\cdot C = A\cdot C + B\cdot C$
2. $\lambda A\cdot B = \lambda(A\cdot B)$
3. $A\cdot B=B\cdot A$

**Teorema 2.1**
1. $A(B+C)=AB+AC \forall A\in K^{m\times n}; B,C \in K^{n\times p}$
2. $(A+B)C = AC+BC \forall A,B\in K^{m\times n},C\in K^{n\times p}$

**Desmotración 2.1.1**
1. $[A(B+C)]_{ik} = A_{i}\cdot(B+C)^k$
   $= A_{i}\cdot(B^k+C^k)=A_{i}\cdot B^k+A_{i}\cdot C^k$
   $=(AB)_{ik}+(AC)_{ik}=(AB+AC)_{ik}$
   $\therefore A(B+C)=AB+AC \blacksquare$
   
**Demostración 2.1.2**
1. $\star$

**Teorema 2.2** Sea $A,B$ matrices cualesquiera y $\lambda$ un escalar cualquiera
$$
(\lambda A)B = \lambda(AB)
$$

**Demostración 2.2**
$$
[(\lambda A)B]_{ik} = (\lambda A)_{i} \cdot B^k = (\lambda A)_{i}\cdot B^k = \lambda(A_{i}B^k)=\lambda[AB]_{ik}=[\lambda(AB)]_{ik}  \blacksquare
$$

**Teorema 2.3**
$$
A\in K^{m\times n}, B\in K^{n\times p}, C\in K^{p\times q}= A(BC)=(AB)C
$$

**Demostración 2.3**
$$
A=(a_{ij}),B=(b_{jk}),C=(kl) = [i\in I_{m}, j\in I_{n}, k\in I_{p}, l\in I_{q}]
$$

$$
(AB)=(d_{ik}),BC=(e_{jl})
$$

$$
[(AB)C]_{il} = (AB)_{i}\cdot C^l \ \sum_{k\in I_{p}} d_{ik}\cdot c_{kl} = \sum_{k\in I_{p}}\left( \sum_{j\in I{n}} a_{ij}b_{jk} \right) \cdot c_{kl}
$$

$$
=\sum_{k\in I_{p};j\in I_{n}} a_{ij}b_{jk}c_{kl}
$$
$$
[A(BC)]_{il} = A_{i}\cdot(BC^l) \sum_{j\in I_{n}} a_{ij}\cdot e_{jl} = \sum_{j\in I_{n}}\left( \sum_{k\in I{p}} b_{jk}c_{kl} \right) \cdot a_{ij}
$$

$$
=\sum_{j\in I_{n};k\in I_{p}} a_{ij}b_{jk}c_{kl}
$$


## Matrices Elementales
**Proposición 3.1** Sean $A,B$ dos matrices tales que $A\in K^{m\times n}, B\in K^{n\times p}$, ent.
1. Si $A\prime$ se obtiene de $A$ por medio de una operación elemental de renglones, ent. $A\prime B$ se obtiene de $AB$ por medio de la misma op. elem. de renglones.
2. Si $B\prime$ se obtiene de $B$ por medio de una operación elemental de columnas, ent. $AB\prime$ se obtiene de $AB$ por medio de la misma op. elem. de columnas.

**Demostración 3.1.1** Según el tipo de la op. elemental:
$T_{1}$: Intercambiar los renglones $r,s$. Si $i\in I_{m}$
$$
\begin{cases}
& \text{si } i\ne r,s, (A\prime B)_{i} = A\prime_{i}B = A_{i}B=(AB)_{i} \\
& \text{si } i=r, (A\prime B)_{r} = A\prime_{r}B=A_{s}B = (AB)_{s} \\
& \text{si } i=s, (A\prime B)_{s} = A\prime_{s}B=A_{r}B = (AB)_{r}
\end{cases}
$$

$T_{2}$: Sumar un renglón $r$ al $s$; $(s\ne r)$
$$
\begin{cases}
& \text{si } i\ne s, (A\prime B)_{i} = A\prime_{i}B = A_{i}B = (AB)_{i} \\
& \text{si } i=s (A\prime B)_{s} = A\prime_{s}B = (A_{s}+A_{r})B = A_{s}B=A_{r}B = (AB)_{s}+(AB)_{r}
\end{cases}
$$

$T_{3}$: Multiplicar un renglón $r$por $\lambda\in K^x \star$

**Demostración 3.1.2** (pasando a transpuestas se reduce a la parte 1) $\star$

**Definición 3.1** Sea $A$ una matriz cuadrada ($A\in K^{n\times n}$) es elemental $\iff$ se obtiene de la identidad $I\in K^{n\times n}$ aplicando alguna operación elemental por renglones (de tipo $T_{1}, T_{2}, T_{2\prime}, T_{3}$). Conversamente, se definen las matrices elementales por columnas 

**Observación 3.1** Las matrices elementales por columnas son las transpuestas de las matrices elementales por renglones $\star$

**Proposición 3.2** Sea $A$ una matriz de $m\times n$, aplicar una operación elemental de renglones a $B$ es lo mismo que premultiplicar (poner del lado izquierdo) a $B$ por la matriz elemental $E\in K^{m\times m}$ obtenida de $I$ por medio de la misma operación elemental.

Similarmente $\star$ se tiene el análogo para operaciones por columnas y postmultiplicar.

**Demostración 3.2** Sea $IB = B$. Se aplica la prop. 3.1.1

**Ejemplo 3.2**
$$
\begin{pmatrix}
1 & 0 & 2 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 2 & 3 & 4 \\
5 & 6 & 7 & 8 \\
9 & 0 & 1 &2
\end{pmatrix}
=
\begin{pmatrix}
19 & 2 & 5 & 8 \\
5 & 6 & 7 & 8 \\
9 & 0 & 1 &2
\end{pmatrix}
$$