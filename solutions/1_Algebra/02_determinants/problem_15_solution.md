# Exercise 15. Combining Determinant Properties

## 1. Problem Statement

Let $A$ and $B$ be invertible $2 \times 2$ matrices with:
$$
\det A = -2, \qquad \det B = 3
$$

Without determining the individual entries of matrices $A$ and $B$:
1. Compute $\det\left(B^{-1} A^T B\right)$.
2. State all the determinant properties used in exact order.
3. Explain why the factors involving matrix $B$ cancel out completely.

---

## 2. Theoretical Background and Concepts

The calculation relies on three foundational properties of the determinant:

1. **Multiplicativity (Product Rule):**
   For any square matrices $M_1, M_2, \dots, M_k$ of identical size:
   $$
   \det(M_1 M_2 \cdots M_k) = \det(M_1) \det(M_2) \cdots \det(M_k)
   $$

2. **Inverse Rule:**
   For any invertible matrix $M$:
   $$
   \det(M^{-1}) = \frac{1}{\det M}
   $$

3. **Transposition Invariance:**
   For any square matrix $M$:
   $$
   \det(M^T) = \det(M)
   $$

4. **Similarity Invariance:**
   Two matrices $X$ and $Y$ are similar ($Y = P^{-1} X P$) if they represent the same linear operator under different choices of basis. Similar matrices always share the exact same determinant, eigenvalues, and trace:
   $$
   \det(P^{-1} X P) = \det(X)
   $$

---

## 3. Detailed Step-by-Step Solution

### 3.1. Step-by-Step Application of Properties

We evaluate $\det\left(B^{-1} A^T B\right)$:

- **Step 1: Apply the Multiplicative Property**
  Decompose the determinant of the product of three matrices:
  $$
  \det\left(B^{-1} A^T B\right) = \det(B^{-1}) \cdot \det(A^T) \cdot \det(B)
  $$

- **Step 2: Apply the Inverse Property to $\det(B^{-1})$**
  Since $B$ is invertible and $\det B = 3 \neq 0$:
  $$
  \det(B^{-1}) = \frac{1}{\det B} = \frac{1}{3}
  $$

- **Step 3: Apply Transposition Invariance to $\det(A^T)$**
  $$
  \det(A^T) = \det A = -2
  $$

- **Step 4: Substitute and Evaluate**
  Substitute the scalar values into the product:
  $$
  \det\left(B^{-1} A^T B\right) = \left(\frac{1}{3}\right) \cdot (-2) \cdot (3)
  $$

  By commutativity of real multiplication:
  $$
  \left(\frac{1}{3}\right) \cdot (3) \cdot (-2) = 1 \cdot (-2) = -2
  $$

$$
\boxed{\det\left(B^{-1} A^T B\right) = -2}
$$

---

### 3.2. Why the Factors Involving $B$ Cancel

1. **Scalar Arithmetic Perspective:**
   The determinant function maps matrices into the field of real numbers $\mathbb{R}$. Once inside $\mathbb{R}$, scalar multiplication is commutative. The factors $\det(B^{-1}) = \frac{1}{\det B}$ and $\det(B)$ are multiplicative inverses of each other in $\mathbb{R}$:
   $$
   \det(B^{-1}) \cdot \det(B) = \frac{1}{\det B} \cdot \det B = 1
   $$
   They cancel to $1$, leaving only $\det(A^T) = \det A$.

2. **Geometric / Similarity Perspective:**
   The matrix operation $M \mapsto B^{-1} M B$ is a **similarity transformation (conjugation)** representing a change of coordinate basis.
   Changing the coordinate basis rotates, shears, or scales space during the change of coordinates, but the inverse basis change $B^{-1}$ immediately undoes that distortion at the end.
   Therefore, the net oriented volume scaling factor of $B^{-1} A^T B$ is solely determined by $A^T$, whose volume factor is identical to $A$.

---

## 4. Verification and Consistency Checks

1. **Concrete Matrix Example:**
   Choose concrete matrices with the specified determinants:
   - Let $A = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} \implies \det A = (-2)(1) = -2$.
     Then $A^T = A = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix}$.
   - Let $B = \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} \implies \det B = 3$.
     Then $B^{-1} = \begin{pmatrix} 1/3 & 0 \\ 0 & 1 \end{pmatrix}$.

   Compute the product directly:
   $$
   B^{-1} A^T B = \begin{pmatrix} 1/3 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} -2/3 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix}
   $$
   Taking the determinant:
   $$
   \det\left(B^{-1} A^T B\right) = (-2)(1) - 0 = -2 \quad \checkmark
   $$

2. **Nondiagonal Test:**
   Let $B = \begin{pmatrix} 1 & 1 \\ 0 & 3 \end{pmatrix}$ ($\det B = 3$), then $B^{-1} = \frac{1}{3}\begin{pmatrix} 3 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -1/3 \\ 0 & 1/3 \end{pmatrix}$.
   $$
   A^T B = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 3 \end{pmatrix} = \begin{pmatrix} -2 & -2 \\ 0 & 3 \end{pmatrix}
   $$
   $$
   B^{-1}(A^T B) = \begin{pmatrix} 1 & -1/3 \\ 0 & 1/3 \end{pmatrix} \begin{pmatrix} -2 & -2 \\ 0 & 3 \end{pmatrix} = \begin{pmatrix} -2 & -2 - 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} -2 & -3 \\ 0 & 1 \end{pmatrix}
   $$
   Determinant:
   $$
   \det \begin{pmatrix} -2 & -3 \\ 0 & 1 \end{pmatrix} = (-2)(1) - (-3)(0) = -2 \quad \checkmark
   $$

