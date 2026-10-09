# Exercise 10. Columns of a Matrix Product

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix}
$$
Denote the columns of $B$ by $b_1$ and $b_2$:
$$
b_1 = \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix}, \qquad b_2 = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}
$$

1. Compute $Ab_1$ and $Ab_2$.
2. Compute the matrix product $AB$.
3. Compare the results and explain why the columns of $AB$ are precisely the vectors $Ab_1$ and $Ab_2$.

---

## 2. Theoretical Background and Concepts

### Column-by-Column Interpretation of Matrix Multiplication
If a matrix $B \in \mathbb{R}^{k \times n}$ is written as a block of column vectors:
$$
B = \begin{pmatrix} | & | & & | \\ b_1 & b_2 & \cdots & b_n \\ | & | & & | \end{pmatrix}
$$
then multiplying $A \in \mathbb{R}^{m \times k}$ by $B$ acts on each column of $B$ independently:
$$
AB = A \begin{pmatrix} b_1 & b_2 & \cdots & b_n \end{pmatrix} = \begin{pmatrix} Ab_1 & Ab_2 & \cdots & Ab_n \end{pmatrix}
$$

### Proof / Justification
The entry in row $i$ and column $j$ of the matrix product $AB$ is given by:
$$
(AB)_{ij} = \sum_{r=1}^k a_{ir} b_{rj}
$$
On the other hand, the $i$-th entry of the matrix-vector product $Ab_j$ is:
$$
(Ab_j)_i = \sum_{r=1}^k a_{ir} (b_j)_r = \sum_{r=1}^k a_{ir} b_{rj}
$$
Since $(AB)_{ij} = (Ab_j)_i$ for all $i$ and $j$, the $j$-th column of $AB$ is identical to the vector $Ab_j$.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $Ab_1$ and $Ab_2$

**For $Ab_1$:**
$$
Ab_1 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix} = \begin{pmatrix} (1)(1) + (2)(-1) + (0)(3) \\ (0)(1) + (1)(-1) + (1)(3) \end{pmatrix} = \begin{pmatrix} 1 - 2 + 0 \\ 0 - 1 + 3 \end{pmatrix} = \begin{pmatrix} -1 \\ 2 \end{pmatrix}
$$

$$
\boxed{Ab_1 = \begin{pmatrix} -1 \\ 2 \end{pmatrix}}
$$

**For $Ab_2$:**
$$
Ab_2 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix} = \begin{pmatrix} (1)(2) + (2)(0) + (0)(1) \\ (0)(2) + (1)(0) + (1)(1) \end{pmatrix} = \begin{pmatrix} 2 + 0 + 0 \\ 0 + 0 + 1 \end{pmatrix} = \begin{pmatrix} 2 \\ 1 \end{pmatrix}
$$

$$
\boxed{Ab_2 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}}
$$

---

### 3.2. Computing the Product $AB$

Matrix $A$ is $2 \times 3$ and $B$ is $3 \times 2$, so $AB$ is $2 \times 2$:
$$
AB = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix}
$$

- Entry $(1,1)$: $(1)(1) + (2)(-1) + (0)(3) = 1 - 2 + 0 = -1$
- Entry $(1,2)$: $(1)(2) + (2)(0) + (0)(1) = 2 + 0 + 0 = 2$
- Entry $(2,1)$: $(0)(1) + (1)(-1) + (1)(3) = 0 - 1 + 3 = 2$
- Entry $(2,2)$: $(0)(2) + (1)(0) + (1)(1) = 0 + 0 + 1 = 1$

$$
\boxed{AB = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}}
$$

---

### 3.3. Comparison and Explanation

Comparing the resulting matrix $AB$ with the vectors $Ab_1$ and $Ab_2$:
- Column 1 of $AB$: $\begin{pmatrix} -1 \\ 2 \end{pmatrix}$, which equals $Ab_1$.
- Column 2 of $AB$: $\begin{pmatrix} 2 \\ 1 \end{pmatrix}$, which equals $Ab_2$.

Thus:
$$
\boxed{AB = \begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix} = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}}
$$

**Why this holds:**
Multiplying a matrix $A$ by an entire matrix $B$ is equivalent to applying the linear transformation represented by $A$ simultaneously to each column vector of $B$. Therefore, column $j$ of the output $AB$ is simply the transformation of the input column $b_j$ under $A$.

---

## 4. Verification and Consistency Checks

1. **Dimensional Consistency**:
   - $A \in \mathbb{R}^{2 \times 3}$ and $b_j \in \mathbb{R}^3 \implies Ab_j \in \mathbb{R}^2$
   - Formed matrix $\begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix}$ has $2$ rows and $2$ columns, matching $\dim(AB) = 2 \times 2 \quad \checkmark$

2. **Linear Combination Form for Each Column**:
   - For column 1: $1 \begin{pmatrix} 1 \\ 0 \end{pmatrix} - 1 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 3 \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 1 - 2 + 0 \\ 0 - 1 + 3 \end{pmatrix} = \begin{pmatrix} -1 \\ 2 \end{pmatrix} \quad \checkmark$
   - For column 2: $2 \begin{pmatrix} 1 \\ 0 \end{pmatrix} + 0 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 1 \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 + 0 + 0 \\ 0 + 0 + 1 \end{pmatrix} = \begin{pmatrix} 2 \\ 1 \end{pmatrix} \quad \checkmark$
