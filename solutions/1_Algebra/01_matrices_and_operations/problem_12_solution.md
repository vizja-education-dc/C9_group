# Exercise 12. Formula for a Matrix Power

## 1. Problem Statement

Given the matrix:
$$
A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}
$$

1. Compute $A^2$, $A^3$, and $A^4$.
2. Formulate a general conjecture for the matrix power $A^n$ where $n \in \mathbb{N}^+$.
3. Prove the formula by induction: assume the formula holds for $n$, compute $A^{n+1} = A^n A$, and show that the formula is established for $n+1$.

---

## 2. Theoretical Background and Concepts

### Matrix Powers and Mathematical Induction
For a square matrix $A$, integer powers are defined recursively:
- $A^1 = A$
- $A^{n+1} = A^n \cdot A \quad \text{for } n \ge 1$

To prove a statement $P(n)$ about matrices for all positive integers $n$:
1. **Base Case:** Verify that $P(1)$ is true.
2. **Induction Step:** Assume $P(k)$ is true (Induction Hypothesis), and deduce that $P(k+1)$ must also be true.
By the Principle of Mathematical Induction, $P(n)$ is true for all $n \ge 1$.

### Nilpotent Decomposition Perspective
Notice that $A = I + N$ where $N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$.
Because $I$ and $N$ commute ($IN = NI = N$) and $N^2 = 0$, by the binomial formula:
$$
A^n = (I + N)^n = I^n + \binom{n}{1} I^{n-1} N + \sum_{k=2}^n \binom{n}{k} I^{n-k} N^k = I + nN
$$

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $A^2, A^3, A^4$

**Computing $A^2$:**
$$
A^2 = A \cdot A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 1(0) & 1(1) + 1(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}
$$

$$
\boxed{A^2 = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}}
$$

**Computing $A^3$:**
$$
A^3 = A^2 \cdot A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 2(0) & 1(1) + 2(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}
$$

$$
\boxed{A^3 = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}}
$$

**Computing $A^4$:**
$$
A^4 = A^3 \cdot A = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 3(0) & 1(1) + 3(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}
$$

$$
\boxed{A^4 = \begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}}
$$

---

### 3.2. Formulating the Conjecture for $A^n$

Observing the sequence of powers:
- For $n=1$: $\begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$
- For $n=2$: $\begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$
- For $n=3$: $\begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}$
- For $n=4$: $\begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}$

The diagonal entries remain $1$, the lower-left entry remains $0$, and the upper-right entry increases by $1$ at each step, matching the exponent $n$.

**Conjecture:** For all $n \in \mathbb{N}^+$:
$$
\boxed{A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}}
$$

---

### 3.3. Proof by Mathematical Induction

1. **Base Case ($n = 1$):**
   $$
   A^1 = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}
   $$
   This matches the formula with $n = 1$. The base case holds.

2. **Induction Hypothesis:**
   Assume the formula holds for an arbitrary integer $k \ge 1$:
   $$
   A^k = \begin{pmatrix} 1 & k \\ 0 & 1 \end{pmatrix}
   $$

3. **Induction Step:**
   Multiply the hypothesis expression by $A$:
   $$
   A^{k+1} = A^k \cdot A = \begin{pmatrix} 1 & k \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}
   $$
   Compute the matrix product:
   - Row 1, Column 1: $(1)(1) + (k)(0) = 1$
   - Row 1, Column 2: $(1)(1) + (k)(1) = 1 + k = k + 1$
   - Row 2, Column 1: $(0)(1) + (1)(0) = 0$
   - Row 2, Column 2: $(0)(1) + (1)(1) = 1$

   Therefore:
   $$
   A^{k+1} = \begin{pmatrix} 1 & k+1 \\ 0 & 1 \end{pmatrix}
   $$
   This is precisely the claimed formula evaluated at $n = k + 1$.

**Conclusion:** By mathematical induction, the formula $A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}$ holds for all positive integers $n \ge 1$.

---

## 4. Verification and Consistency Checks

1. **Check for $A^0$ and $A^{-1}$:**
   - For $n = 0$: $\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \quad \checkmark$
   - For $n = -1$: $\begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I \implies A^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \quad \checkmark$
   The formula extends consistently to all integers $n \in \mathbb{Z}$.

2. **Index Power Law Check ($A^a A^b = A^{a+b}$):**
   $$
   A^a A^b = \begin{pmatrix} 1 & a \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & b \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & a + b \\ 0 & 1 \end{pmatrix} = A^{a+b} \quad \checkmark
   $$
   Matrix multiplication aligns identically with exponent addition.
