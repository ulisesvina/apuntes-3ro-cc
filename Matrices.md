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

**Demostración PP 1** Sup. por contradicción que $(A+B)\cdot C \ne A\cdot C + B\cdot C$

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

### Transpuesta de una matriz

**Definición 2.2** Si $A=(a_{ij}) \in K^{m\times n}$, la transpuesta de $A$ es la matriz $A^t \in K^{n\times m}$ definida por $A^t = (b_{ij})$ con $b_{ij} = a_{ji}$.

**Ejemplo:**
$$
\begin{pmatrix}
3 & 2 & 1 \\
0 & 6 & 5
\end{pmatrix}^t 
= 
\begin{pmatrix}
3 & 0 \\
2 & 6 \\
1 & 5
\end{pmatrix}
$$

**Observación 2.2** 
1. Los renglones de $A^t$ son las columnas de $A$.
2. Las columnas de $A^t$ son los renglones de $A$.
3. Sean $A, B \in K^{m\times n}$ y $\lambda \in K$, entonces:
   $$(A+B)^t = A^t + B^t \quad \text{y} \quad (\lambda A)^t = \lambda (A^t)$$

**Teorema 2.4** Sean $A \in K^{m\times n}$ y $B \in K^{n\times p}$ (por lo que $AB \in K^{m\times p}$), entonces:
$$(AB)^t = B^t A^t$$

**Demostración 2.4**
$$[(AB)^t]_{kj} = [AB]_{jk} = A_j \cdot B^k$$
$$[B^t A^t]_{kj} = B^t_k \cdot (A^t)^j = B^k \cdot A_j$$
$$\therefore [(AB)^t]_{kj} = [B^t A^t]_{kj} \quad \blacksquare$$

**Observación 2.3** Por el Teorema 2.4, las partes (i) y (ii) del Teorema 1 pueden deducirse una de la otra.

---

### Vectores canónicos e Identidad

**Observación 2.4** Si $e_1, e_2, \dots, e_n$ son los vectores básicos canónicos de $K^n$ y $A = (a_1, a_2, \dots, a_n)$, entonces $e_j \cdot A = a_j \quad (\forall j \in I_n)$.

**Observación 2.5**
* Si $i \in I_m$ y $A \in K^{m\times n}$, $e_i A = A_i \quad (e_i \in K^{1\times m})$.
* Si $j \in I_n$ y $A \in K^{m\times n}$, $A e_j = A^j \quad (e_j \in K^{n\times 1})$.

**Definición 2.3** Si $n \in \mathbb{N}$, la matriz identidad de orden $n \times n$ es $I \in K^{n\times n}$ dada por $I = (\delta_{ij})$, donde:
$$\delta_{xy} = \begin{cases} 1 & \text{si } x = y \\ 0 & \text{si } x \neq y \end{cases} \quad \to \text{Delta de Kronecker}$$

### Matrices Elementales
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

## 4. Matrices Invertibles
**Definición 4.1** Una matriz $P\in K^{n\times n}$ es invertible si $\exists Q \in K^{n\times n}$ tal que $PQ=QP = I\in K^{n\times n}$

**Observación 4.1** Si $P$ es invertible, la inversa $Q$ es única y se denota $P^{-1}$

**Definición 4.2** El grupo general lineal de índice $n$ sobre $k$ es $Gl_{n}(K) = \{ P \in K^{n\times n} | P \text{ invertible}\}$

**Lema 4.1** Con el producto de matrices, $Gl_{n}(K)$ es un grupo

**Demostración 4.1** *Asociatividad y neutro* El producto de matrices $K^{n\times n}\times K^{n\times n} \to K^{n\times n}$, $(A,B) \mapsto AB$. Se restringe a $Gl_{n}(K)$, pues $A,B \text{ invertible}\implies AB$ también de hecho $(AB)(B^{-1}A^{-1}) = AIA^{-1} = AA^{-1} = I$
$(B^{-1}A^{-1})(AB)=I, \therefore B^{-1}A^{-1}=(AB)^{-1}$.


$$
Gl_{n}(K)\times Gl_{n}(K)\to Gl_{n}(K)
$$
$$
(A,B)\mapsto AB
$$

El producto de matrices es asociativo en $K^{n\times n}, \therefore$ también en $Gl_{n}(K), I\in Gl_{n}(K)$ es el neutro multiplicativo.

*Inverso multiplicativo*
Si $P\in Gl_{n}(K) \implies \exists! P^{-1} : P(P^{-1}) = I = P^{-1}(P)$. También, $P=(P^{-1})^{-1}$ por la unicidad del inverso.

**Observación 4.2** $Gl_{n}(K)$ no es abeliano si $n\ge 2$

*Ejemplo*
$$
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix}
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix}
= \begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix}
$$
$$
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix}
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix}
= \begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}
$$

**Observación 4.3** $Gl_{n}(K)$ es el grupo de unidades (de invertibles) de $K^{n\times n}$
$$
(K^{n\times n})^{x} = Gl_{n}(K)
$$

*Nota: "elemental" es equivalente a "elemental por renglones" de tipo 1, 2' o 3*

**Lema 4.2** Sea $E \in K^{n\times n}$ una matriz elemental, ent. $E$ es invertible ($E\in Gl_{n}(K)$) y además, $E^{-1}$ también es elemental y del mismo tipo.

**Demostración 4.2 (todas son del mismo tipo)**

*Operación $T_{1}$*
Si $E$ intercambia los renglones $r$ y $s$, ent. $E^{-1}=E$, pues intercambiar los renglones en la invertida es volver a ella misma.

*Operación $T_{2}$*
Si $E$ suma $\lambda \ne 0$ veces el renglón $r$ al $s$, $E^{-1}$ suma $-\lambda$ veces el renglón $r$ al $s$.

*Operación $T_{3}$*
Si $E$ multiplica el renglón $r$ por un escalar $\lambda\ne 0$, $E^{-1}$ multiplica el renglón r por $\lambda^{-1}$

**Observación** Todas las matrices elementales son invertibles por *Lema 4.2*, y todos los productos (finitos) de matrices elementales son entonces invertibles por *Lema 4.1*. Producto de elementales no es elemental en general.

*todas las invertibles son productos de elementales*