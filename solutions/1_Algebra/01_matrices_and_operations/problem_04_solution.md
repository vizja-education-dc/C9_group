# Exercise 4. Matrix Multiplication and Noncommutativity

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix}
$$

1. Compute the product $AB$.
2. Compute the product $BA$.
3. Determine whether $AB = BA$.
4. Use this example to explain what the noncommutativity of matrix multiplication means.

---

## 2. Theoretical Background and Concepts

### Matrix Multiplication Formula
Let $A \in \mathbb{R}^{m \times k}$ and $B \in \mathbb{R}^{k \times n}$. The product $C = AB \in \mathbb{R}^{m \times n}$ has entries defined by the dot product of the $i$-th row of $A$ and the $j$-th column of $B$:
$$
c_{ij} = \sum_{r=1}^k a_{ir} b_{rj}
$$

For $2 \times 2$ matrices:
$$
\begin{pmatrix} a_{11} & a_{12} \\ a_{21} & a_{22} \end{pmatrix}
\begin{pmatrix} b_{11} & b_{12} \\ b_{21} & b_{22} \end{pmatrix}
=
\begin{pmatrix}
a_{11}b_{11} + a_{12}b_{21} & a_{11}b_{12} + a_{12}b_{22} \\
a_{21}b_{11} + a_{22}b_{21} & a_{21}b_{12} + a_{22}b_{22}
\end{pmatrix}
$$

### Noncommutativity
An algebraic binary operation $*$ on a set $S$ is commutative if $x * y = y * x$ for all $x, y \in S$. 
While ordinary multiplication in $\mathbb{R}$ is commutative ($ab = ba$), **matrix multiplication is generally non-commutative**: in general, $AB \neq BA$, even when both matrices are square and of the same size so that both products are defined and have the same dimensions.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $AB$

$$
AB = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix}
$$

Compute each entry:
- Entry $(1,1)$: $(1)(2) + (2)(3) = 2 + 6 = 8$
- Entry $(1,2)$: $(1)(0) + (2)(1) = 0 + 2 = 2$
- Entry $(2,1)$: $(0)(2) + (1)(3) = 0 + 3 = 3$
- Entry $(2,2)$: $(0)(0) + (1)(1) = 0 + 1 = 1$

$$
\boxed{AB = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix}}
$$

---

### 3.2. Computing $BA$

$$
BA = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}
$$

Compute each entry:
- Entry $(1,1)$: $(2)(1) + (0)(0) = 2 + 0 = 2$
- Entry $(1,2)$: $(2)(2) + (0)(1) = 4 + 0 = 4$
- Entry $(2,1)$: $(3)(1) + (1)(0) = 3 + 0 = 3$
- Entry $(2,2)$: $(3)(2) + (1)(1) = 6 + 1 = 7$

$$
\boxed{BA = \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}}
$$

---

### 3.3. Comparison: Is $AB = BA$?

Comparing corresponding entries:
$$
AB = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix} \neq \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix} = BA
$$
Specifically, entry $(1,1)$ yields $8 \neq 2$, entry $(1,2)$ yields $2 \neq 4$, and entry $(2,2)$ yields $1 \neq 7$.

Therefore:
$$
\boxed{AB \neq BA}
$$

---

### 3.4. What Noncommutativity Means

1. **Order Matters**: Unlike real numbers where $3 \times 5 = 5 \times 3$, in matrix algebra the order of multiplication is fundamental. Multiplying $A$ on the left by $B$ ($BA$) yields an entirely different result than multiplying $A$ on the right by $B$ ($AB$).
2. **Composition of Linear Transformations**: Geometrically, matrices represent linear transformations of vector space $\mathbb{R}^2$. Matrix multiplication represents function composition:
   - $(AB)x = A(Bx)$ means transformation $B$ is applied first, followed by $A$.
   - $(BA)x = B(Ax)$ means transformation $A$ is applied first, followed by $B$.
   In general, performing geometric transformations in different orders results in different final configurations (e.g., shearing followed by scaling is not equal to scaling followed by shearing).

---

## 4. Verification and Consistency Checks

1. **Determinant Multiplicativity Check**:
   A key identity of matrix multiplication is $\det(AB) = \det(A)\det(B) = \det(BA)$.
   - $\det(A) = (1)(1) - (2)(0) = 1$
   - $\det(B) = (2)(1) - (0)(3) = 2$
   - Theoretical product determinant: $\det(A)\det(B) = 1 \times 2 = 2$.
   - Check $AB$: $\det(AB) = (8)(1) - (2)(3) = 8 - 6 = 2 \quad \checkmark$
   - Check $BA$: $\det(BA) = (2)(7) - (4)(3) = 14 - 12 = 2 \quad \checkmark$
   Both products have determinant $2$, confirming computational correctness despite $AB \neq BA$.

2. **Trace Verification**:
   The trace of a product satisfies the cyclic property $\mathrm{tr}(AB) = \mathrm{tr}(BA)$:
   - $\mathrm{tr}(AB) = 8 + 1 = 9$
   - $\mathrm{tr}(BA) = 2 + 7 = 9$
   $\mathrm{tr}(AB) = \mathrm{tr}(BA) = 9 \quad \checkmark$
