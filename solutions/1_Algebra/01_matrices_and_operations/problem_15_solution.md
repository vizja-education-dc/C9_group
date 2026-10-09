# Exercise 15. Associativity of Multiplication and Different Calculation Paths

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}, \qquad C = \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}
$$

1. Compute the product $(AB)C$.
2. Compute the product $A(BC)$.
3. Compare the resulting matrices.
4. Compare the number of intermediate scalar operations required by each path.
5. Explain what the associativity of matrix multiplication means in this example.

---

## 2. Theoretical Background and Concepts

### Associativity of Matrix Multiplication
For any matrices $A \in \mathbb{R}^{m \times k}$, $B \in \mathbb{R}^{k \times p}$, and $C \in \mathbb{R}^{p \times n}$, matrix multiplication satisfies the associative law:
$$
(AB)C = A(BC)
$$
While the order of matrices cannot be permuted ($AB \neq BA$ in general), the grouping of operations via parentheses does not affect the final result.

### Computational Complexity (Matrix Chain Multiplication)
Multiplying a matrix of size $u \times v$ by a matrix of size $v \times w$ requires:
$$
u \cdot v \cdot w \quad \text{scalar multiplications (and } u \cdot (v - 1) \cdot w \text{ additions)}
$$
Different parenthesizations of the same matrix product sequence can have different computational costs, even though they yield identical outputs.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Calculation Path 1: $(AB)C$

**Step 1: Compute $M_1 = AB$**
- $A \in \mathbb{R}^{2 \times 3}$ and $B \in \mathbb{R}^{3 \times 2} \implies AB \in \mathbb{R}^{2 \times 2}$:
$$
AB = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}
$$
- Entry $(1,1)$: $(1)(1) + (2)(2) + (0)(-1) = 1 + 4 + 0 = 5$
- Entry $(1,2)$: $(1)(0) + (2)(1) + (0)(3) = 0 + 2 + 0 = 2$
- Entry $(2,1)$: $(0)(1) + (1)(2) + (1)(-1) = 0 + 2 - 1 = 1$
- Entry $(2,2)$: $(0)(0) + (1)(1) + (1)(3) = 0 + 1 + 3 = 4$

$$
AB = \begin{pmatrix} 5 & 2 \\ 1 & 4 \end{pmatrix}
$$

**Step 2: Compute $(AB)C$**
- $(AB) \in \mathbb{R}^{2 \times 2}$ and $C \in \mathbb{R}^{2 \times 2} \implies (AB)C \in \mathbb{R}^{2 \times 2}$:
$$
(AB)C = \begin{pmatrix} 5 & 2 \\ 1 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}
$$
- Entry $(1,1)$: $(5)(2) + (2)(0) = 10 + 0 = 10$
- Entry $(1,2)$: $(5)(1) + (2)(-1) = 5 - 2 = 3$
- Entry $(2,1)$: $(1)(2) + (4)(0) = 2 + 0 = 2$
- Entry $(2,2)$: $(1)(1) + (4)(-1) = 1 - 4 = -3$

$$
\boxed{(AB)C = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}}
$$

---

### 3.2. Calculation Path 2: $A(BC)$

**Step 1: Compute $M_2 = BC$**
- $B \in \mathbb{R}^{3 \times 2}$ and $C \in \mathbb{R}^{2 \times 2} \implies BC \in \mathbb{R}^{3 \times 2}$:
$$
BC = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}
$$
- Entry $(1,1)$: $(1)(2) + (0)(0) = 2$
- Entry $(1,2)$: $(1)(1) + (0)(-1) = 1$
- Entry $(2,1)$: $(2)(2) + (1)(0) = 4$
- Entry $(2,2)$: $(2)(1) + (1)(-1) = 2 - 1 = 1$
- Entry $(3,1)$: $(-1)(2) + (3)(0) = -2$
- Entry $(3,2)$: $(-1)(1) + (3)(-1) = -1 - 3 = -4$

$$
BC = \begin{pmatrix} 2 & 1 \\ 4 & 1 \\ -2 & -4 \end{pmatrix}
$$

**Step 2: Compute $A(BC)$**
- $A \in \mathbb{R}^{2 \times 3}$ and $(BC) \in \mathbb{R}^{3 \times 2} \implies A(BC) \in \mathbb{R}^{2 \times 2}$:
$$
A(BC) = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 4 & 1 \\ -2 & -4 \end{pmatrix}
$$
- Entry $(1,1)$: $(1)(2) + (2)(4) + (0)(-2) = 2 + 8 + 0 = 10$
- Entry $(1,2)$: $(1)(1) + (2)(1) + (0)(-4) = 1 + 2 + 0 = 3$
- Entry $(2,1)$: $(0)(2) + (1)(4) + (1)(-2) = 0 + 4 - 2 = 2$
- Entry $(2,2)$: $(0)(1) + (1)(1) + (1)(-4) = 0 + 1 - 4 = -3$

$$
\boxed{A(BC) = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}}
$$

---

### 3.3. Comparison and Associativity

Both paths produce the exact same matrix:
$$
\boxed{(AB)C = A(BC) = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}}
$$

### 3.4. Comparison of Computational Workload

Count the number of scalar multiplications:
- **Path 1: $(AB)C$**
  - Computing $AB$ ($2 \times 3 \times 2$): $12$ multiplications.
  - Computing $(AB)C$ ($2 \times 2 \times 2$): $8$ multiplications.
  - **Total:** $12 + 8 = \mathbf{20}$ multiplications.
- **Path 2: $A(BC)$**
  - Computing $BC$ ($3 \times 2 \times 2$): $12$ multiplications.
  - Computing $A(BC)$ ($2 \times 3 \times 2$): $12$ multiplications.
  - **Total:** $12 + 12 = \mathbf{24}$ multiplications.

**Meaning of Associativity:**
The grouping of intermediate operations does not change the algebraic outcome or geometric map of the composite transformation. However, **Path 1 is computationally cheaper (20 multiplications vs 24 multiplications)**. This demonstrates the core idea of algorithmic matrix chain optimization: choosing the optimal parenthesization order can significantly reduce execution time.

---

## 4. Verification and Consistency Checks

1. **Determinant Multiplicativity Check:**
   - $\det(AB) = (5)(4) - (2)(1) = 20 - 2 = 18$
   - $\det(C) = (2)(-1) - (1)(0) = -2$
   - Predicted determinant: $\det((AB)C) = \det(AB) \times \det(C) = 18 \times (-2) = -36$.
   - Direct determinant from final result:
     $$
     \det \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix} = (10)(-3) - (3)(2) = -30 - 6 = -36 \quad \checkmark
     $$

2. **Column Consistency Check:**
   Columns of $(AB)C$ using column form:
   - First column of $C$ is $\begin{pmatrix} 2 \\ 0 \end{pmatrix} \implies 2 \times (\text{column 1 of } AB) = 2 \begin{pmatrix} 5 \\ 1 \end{pmatrix} = \begin{pmatrix} 10 \\ 2 \end{pmatrix} \quad \checkmark$
   - Second column of $C$ is $\begin{pmatrix} 1 \\ -1 \end{pmatrix} \implies 1 \begin{pmatrix} 5 \\ 1 \end{pmatrix} - 1 \begin{pmatrix} 2 \\ 4 \end{pmatrix} = \begin{pmatrix} 3 \\ -3 \end{pmatrix} \quad \checkmark$

