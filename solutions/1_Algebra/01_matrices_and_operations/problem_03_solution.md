# Exercise 3. When Can Matrices Be Multiplied?

## 1. Problem Statement

Given matrices with the following dimensions:
$$
A \in \mathbb{R}^{2 \times 3}, \qquad B \in \mathbb{R}^{3 \times 4}, \qquad C \in \mathbb{R}^{4 \times 2}, \qquad D \in \mathbb{R}^{2 \times 2}
$$

For each of the following matrix products:
$$
AB, \quad BA, \quad BC, \quad CB, \quad AC, \quad CA, \quad AD, \quad DA
$$
determine whether the product is defined. If so, determine the size of the resulting matrix. Justify each decision using the dimension compatibility condition.

---

## 2. Theoretical Background and Concepts

### Dimension Compatibility Rule for Matrix Multiplication
Let $M$ and $N$ be two matrices. The matrix product $MN$ is defined if and only if the **number of columns in the first matrix ($M$) equals the number of rows in the second matrix ($N$)**.

Formally:
- If $M$ is of size $m \times k$ and $N$ is of size $k \times p$, the product $P = MN$ is defined and has dimension:
  $$
  \dim(MN) = m \times p
  $$
- The inner dimensions must match:
  $$
  (m \times \mathbf{k}) \times (\mathbf{k} \times p) \longrightarrow m \times p
  $$
- If the inner dimensions do not match ($k_1 \neq k_2$), the entry formula:
  $$
  (MN)_{ij} = \sum_{r=1}^{k} M_{ir} N_{rj}
  $$
  cannot be evaluated because the row vector of $M$ and the column vector of $N$ have differing numbers of components, making their dot product undefined.

---

## 3. Detailed Step-by-Step Solution

### 1. Product $AB$
- Left factor: $A_{2 \times 3}$ (3 columns)
- Right factor: $B_{3 \times 4}$ (3 rows)
- Compatibility check: The inner dimensions match ($3 = 3$).
- **Result:** Defined.
- **Dimension:** $\boxed{2 \times 4}$

### 2. Product $BA$
- Left factor: $B_{3 \times 4}$ (4 columns)
- Right factor: $A_{2 \times 3}$ (2 rows)
- Compatibility check: Inner dimensions do not match ($4 \neq 2$).
- **Result:** $\boxed{\text{Undefined}}$

### 3. Product $BC$
- Left factor: $B_{3 \times 4}$ (4 columns)
- Right factor: $C_{4 \times 2}$ (4 rows)
- Compatibility check: The inner dimensions match ($4 = 4$).
- **Result:** Defined.
- **Dimension:** $\boxed{3 \times 2}$

### 4. Product $CB$
- Left factor: $C_{4 \times 2}$ (2 columns)
- Right factor: $B_{3 \times 4}$ (3 rows)
- Compatibility check: Inner dimensions do not match ($2 \neq 3$).
- **Result:** $\boxed{\text{Undefined}}$

### 5. Product $AC$
- Left factor: $A_{2 \times 3}$ (3 columns)
- Right factor: $C_{4 \times 2}$ (4 rows)
- Compatibility check: Inner dimensions do not match ($3 \neq 4$).
- **Result:** $\boxed{\text{Undefined}}$

### 6. Product $CA$
- Left factor: $C_{4 \times 2}$ (2 columns)
- Right factor: $A_{2 \times 3}$ (2 rows)
- Compatibility check: The inner dimensions match ($2 = 2$).
- **Result:** Defined.
- **Dimension:** $\boxed{4 \times 3}$

### 7. Product $AD$
- Left factor: $A_{2 \times 3}$ (3 columns)
- Right factor: $D_{2 \times 2}$ (2 rows)
- Compatibility check: Inner dimensions do not match ($3 \neq 2$).
- **Result:** $\boxed{\text{Undefined}}$

### 8. Product $DA$
- Left factor: $D_{2 \times 2}$ (2 columns)
- Right factor: $A_{2 \times 3}$ (2 rows)
- Compatibility check: The inner dimensions match ($2 = 2$).
- **Result:** Defined.
- **Dimension:** $\boxed{2 \times 3}$

---

## 4. Verification and Consistency Checks

### Summary Table

| Product | Factors & Sizes | Inner Match? | Status | Resulting Size |
| :---: | :---: | :---: | :---: | :---: |
| $AB$ | $(2 \times 3) \times (3 \times 4)$ | $3 = 3$ | **Defined** | $2 \times 4$ |
| $BA$ | $(3 \times 4) \times (2 \times 3)$ | $4 \neq 2$ | **Undefined** | — |
| $BC$ | $(3 \times 4) \times (4 \times 2)$ | $4 = 4$ | **Defined** | $3 \times 2$ |
| $CB$ | $(4 \times 2) \times (3 \times 4)$ | $2 \neq 3$ | **Undefined** | — |
| $AC$ | $(2 \times 3) \times (4 \times 2)$ | $3 \neq 4$ | **Undefined** | — |
| $CA$ | $(4 \times 2) \times (2 \times 3)$ | $2 = 2$ | **Defined** | $4 \times 3$ |
| $AD$ | $(2 \times 3) \times (2 \times 2)$ | $3 \neq 2$ | **Undefined** | — |
| $DA$ | $(2 \times 2) \times (2 \times 3)$ | $2 = 2$ | **Defined** | $2 \times 3$ |

### Consistency Observations:
1. **Asymmetry of definition**: Notice that $AB$ is defined ($2 \times 4$), but $BA$ is completely undefined. Similarly, $CA$ is defined ($4 \times 3$), but $AC$ is undefined; $DA$ is defined ($2 \times 3$), but $AD$ is undefined. This highlights that matrix multiplication does not commute, even at the level of whether the operation can be legally formed.
2. **Linear Map Interpretation**: A matrix of size $m \times n$ represents a linear map $T: \mathbb{R}^n \to \mathbb{R}^m$.
   - $A: \mathbb{R}^3 \to \mathbb{R}^2$
   - $B: \mathbb{R}^4 \to \mathbb{R}^3$
   - $C: \mathbb{R}^2 \to \mathbb{R}^4$
   - $D: \mathbb{R}^2 \to \mathbb{R}^2$
   
   The product $MN$ corresponds to the composition $(T_M \circ T_N)(x) = T_M(T_N(x))$, which is valid only when the codomain of $T_N$ matches the domain of $T_M$:
   - $A \circ B: \mathbb{R}^4 \xrightarrow{B} \mathbb{R}^3 \xrightarrow{A} \mathbb{R}^2$ (Valid: $\mathbb{R}^4 \to \mathbb{R}^2 \implies 2 \times 4$) $\checkmark$
   - $B \circ C: \mathbb{R}^2 \xrightarrow{C} \mathbb{R}^4 \xrightarrow{B} \mathbb{R}^3$ (Valid: $\mathbb{R}^2 \to \mathbb{R}^3 \implies 3 \times 2$) $\checkmark$
   - $C \circ A: \mathbb{R}^3 \xrightarrow{A} \mathbb{R}^2 \xrightarrow{C} \mathbb{R}^4$ (Valid: $\mathbb{R}^3 \to \mathbb{R}^4 \implies 4 \times 3$) $\checkmark$
   - $D \circ A: \mathbb{R}^3 \xrightarrow{A} \mathbb{R}^2 \xrightarrow{D} \mathbb{R}^2$ (Valid: $\mathbb{R}^3 \to \mathbb{R}^2 \implies 2 \times 3$) $\checkmark$
