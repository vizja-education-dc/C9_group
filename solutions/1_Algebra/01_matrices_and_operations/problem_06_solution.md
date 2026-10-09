# Exercise 6. Transpose

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}
$$

1. Compute $A^T$.
2. Compute $B^T$.
3. Compute the product $AB$.
4. Verify in this example that $(AB)^T = B^T A^T$.

---

## 2. Theoretical Background and Concepts

### Matrix Transposition
The transpose of an $m \times n$ matrix $M = (m_{ij})$ is the $n \times m$ matrix $M^T = (m_{ji}^T)$ obtained by interchanging rows and columns:
$$
(M^T)_{ij} = M_{ji}
$$
The rows of $M$ become the columns of $M^T$, and the columns of $M$ become the rows of $M^T$.

### Transpose of a Product Property
For any two compatible matrices $A$ and $B$, the transpose of their product reverses the order of factors:
$$
(AB)^T = B^T A^T
$$
**Reason for the reversal of factors:**
If $A$ is $m \times k$ and $B$ is $k \times n$, their product $AB$ has size $m \times n$, so $(AB)^T$ has size $n \times m$.
Transposing each matrix gives $A^T$ ($k \times m$) and $B^T$ ($n \times k$).
Notice that $A^T B^T$ is of size $(k \times m) \times (n \times k)$, which is generally not even defined (unless $m = n = k$).
However, $B^T A^T$ has size $(n \times k) \times (k \times m) = n \times m$, which matches the dimension of $(AB)^T$ and yields identical entries:
$$
\left((AB)^T\right)_{ij} = (AB)_{ji} = \sum_{r=1}^k a_{jr} b_{ri} = \sum_{r=1}^k (B^T)_{ir} (A^T)_{rj} = (B^T A^T)_{ij}
$$

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $A^T$
Matrix $A$ has size $2 \times 3$, so $A^T$ has size $3 \times 2$:
$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix} \implies
\boxed{A^T = \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix}}
$$

---

### 3.2. Computing $B^T$
Matrix $B$ has size $3 \times 2$, so $B^T$ has size $2 \times 3$:
$$
B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix} \implies
\boxed{B^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix}}
$$

---

### 3.3. Computing the Product $AB$
$A$ is $2 \times 3$ and $B$ is $3 \times 2$, so $AB$ is $2 \times 2$:
$$
AB = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}
$$

- Entry $(1,1)$: $(1)(1) + (2)(2) + (3)(-1) = 1 + 4 - 3 = 2$
- Entry $(1,2)$: $(1)(0) + (2)(1) + (3)(3) = 0 + 2 + 9 = 11$
- Entry $(2,1)$: $(4)(1) + (5)(2) + (6)(-1) = 4 + 10 - 6 = 8$
- Entry $(2,2)$: $(4)(0) + (5)(1) + (6)(3) = 0 + 5 + 18 = 23$

$$
\boxed{AB = \begin{pmatrix} 2 & 11 \\ 8 & 23 \end{pmatrix}}
$$

---

### 3.4. Verification of $(AB)^T = B^T A^T$

First, compute the left-hand side $(AB)^T$:
$$
(AB)^T = \begin{pmatrix} 2 & 11 \\ 8 & 23 \end{pmatrix}^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}
$$

Next, compute the right-hand side $B^T A^T$:
$$
B^T A^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix} \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix}
$$

- Entry $(1,1)$: $(1)(1) + (2)(2) + (-1)(3) = 1 + 4 - 3 = 2$
- Entry $(1,2)$: $(1)(4) + (2)(5) + (-1)(6) = 4 + 10 - 6 = 8$
- Entry $(2,1)$: $(0)(1) + (1)(2) + (3)(3) = 0 + 2 + 9 = 11$
- Entry $(2,2)$: $(0)(4) + (1)(5) + (3)(6) = 0 + 5 + 18 = 23$

$$
B^T A^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}
$$

Comparing both matrices:
$$
\boxed{(AB)^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix} = B^T A^T}
$$
The identity $(AB)^T = B^T A^T$ holds true.

---

## 4. Verification and Consistency Checks

1. **Dimensional Consistency**:
   - $\dim((AB)^T) = (\dim(AB))^T = (2 \times 2)^T = 2 \times 2$
   - $\dim(B^T A^T) = (2 \times 3) \times (3 \times 2) = 2 \times 2$
   Both sides have the expected size $2 \times 2$.

2. **Diagonal Entries / Trace Check**:
   The diagonal entries of any matrix and its transpose are always identical:
   - $(AB)_{11} = ((AB)^T)_{11} = 2$
   - $(AB)_{22} = ((AB)^T)_{22} = 23$
   - $\mathrm{tr}((AB)^T) = 2 + 23 = 25$
   - $\mathrm{tr}(B^T A^T) = 2 + 23 = 25 \quad \checkmark$
