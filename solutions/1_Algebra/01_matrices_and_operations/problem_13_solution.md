# Exercise 13. A Recurrence Written in Matrix Form

## 1. Problem Statement

Let:
$$
F = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}
$$

1. Compute $F^2$, $F^3$, $F^4$, and $F^5$.
2. Compare the entries obtained with the Fibonacci sequence:
   $$
   0, 1, 1, 2, 3, 5, 8, 13, \ldots
   $$
   and describe the relationship you observe.
3. Compute the product $F \begin{pmatrix} a \\ b \end{pmatrix}$.
4. Explain how this matrix multiplication performs one recurrence step: creating the sum of two consecutive terms and saving one of them for the next step.

---

## 2. Theoretical Background and Concepts

### Fibonacci Numbers and Linear Recurrences
The Fibonacci sequence $(f_n)_{n \ge 0}$ is defined by:
$$
f_0 = 0, \quad f_1 = 1, \quad f_{n+1} = f_n + f_{n-1} \quad (n \ge 1)
$$
The first few terms are:
$$
f_0 = 0, \; f_1 = 1, \; f_2 = 1, \; f_3 = 2, \; f_4 = 3, \; f_5 = 5, \; f_6 = 8, \; f_7 = 13, \ldots
$$

### State Vector Representation
A second-order linear recurrence can be transformed into a first-order system of difference equations using state vectors:
$$
v_k = \begin{pmatrix} f_k \\ f_{k-1} \end{pmatrix}
$$
The transition to the next state $v_{k+1}$ is governed by a transition matrix $F$:
$$
v_{k+1} = \begin{pmatrix} f_{k+1} \\ f_k \end{pmatrix} = \begin{pmatrix} f_k + f_{k-1} \\ f_k \end{pmatrix} = F v_k
$$
Iterating this relationship yields:
$$
v_n = F^n v_0
$$
where $F^n$ directly encodes the Fibonacci numbers.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing Powers $F^2, F^3, F^4, F^5$

**Computing $F^2$:**
$$
F^2 = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 1(1) + 1(1) & 1(1) + 1(0) \\ 1(1) + 0(1) & 1(1) + 0(0) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}
$$

$$
\boxed{F^2 = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}}
$$

**Computing $F^3$:**
$$
F^3 = F^2 \cdot F = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 2(1) + 1(1) & 2(1) + 1(0) \\ 1(1) + 1(1) & 1(1) + 1(0) \end{pmatrix} = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix}
$$

$$
\boxed{F^3 = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix}}
$$

**Computing $F^4$:**
$$
F^4 = F^3 \cdot F = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 3(1) + 2(1) & 3(1) + 2(0) \\ 2(1) + 1(1) & 2(1) + 1(0) \end{pmatrix} = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix}
$$

$$
\boxed{F^4 = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix}}
$$

**Computing $F^5$:**
$$
F^5 = F^4 \cdot F = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 5(1) + 3(1) & 5(1) + 3(0) \\ 3(1) + 2(1) & 3(1) + 2(0) \end{pmatrix} = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix}
$$

$$
\boxed{F^5 = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix}}
$$

---

### 3.2. Comparison with the Fibonacci Sequence

Notice the pattern of entries in each power $F^n$:
- $F^1 = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} f_2 & f_1 \\ f_1 & f_0 \end{pmatrix}$
- $F^2 = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} = \begin{pmatrix} f_3 & f_2 \\ f_2 & f_1 \end{pmatrix}$
- $F^3 = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} = \begin{pmatrix} f_4 & f_3 \\ f_3 & f_2 \end{pmatrix}$
- $F^4 = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix} = \begin{pmatrix} f_5 & f_4 \\ f_4 & f_3 \end{pmatrix}$
- $F^5 = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix} = \begin{pmatrix} f_6 & f_5 \\ f_5 & f_4 \end{pmatrix}$

**General Relationship:**
For any integer $n \ge 1$:
$$
\boxed{F^n = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}}
$$
where $f_k$ is the $k$-th Fibonacci number.

---

### 3.3. Multiplication by an Arbitrary Vector $\begin{pmatrix} a \\ b \end{pmatrix}$

Compute the product:
$$
F \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1 \cdot a + 1 \cdot b \\ 1 \cdot a + 0 \cdot b \end{pmatrix} = \begin{pmatrix} a + b \\ a \end{pmatrix}
$$

$$
\boxed{F \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} a + b \\ a \end{pmatrix}}
$$

---

### 3.4. How Multiplication Performs One Recurrence Step

Suppose the current state vector holds two consecutive numbers in the sequence, $a = x_k$ and $b = x_{k-1}$:
$$
v_k = \begin{pmatrix} x_k \\ x_{k-1} \end{pmatrix}
$$
Multiplying by $F$ updates this vector to:
$$
F v_k = \begin{pmatrix} x_k + x_{k-1} \\ x_k \end{pmatrix}
$$
- **Top Row ($a + b$):** Computes the **sum of the two consecutive values**, generating the new term $x_{k+1} = x_k + x_{k-1}$.
- **Bottom Row ($a$):** Acts as a **memory buffer / shift register**, copying the previous term $x_k$ into the second position so that it is available to be added in the next step.

Thus, multiplying by $F$ advances the recurrence by exactly one time step.

---

## 4. Verification and Consistency Checks

1. **Cassini's Identity via Determinant**:
   - $\det(F) = 1(0) - 1(1) = -1$.
   - By the multiplicative property of determinants:
     $$
     \det(F^n) = (\det(F))^n = (-1)^n
     $$
   - Since $F^n = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}$, its determinant is:
     $$
     \det(F^n) = f_{n+1} f_{n-1} - f_n^2 = (-1)^n
     $$
   - Check for $n = 4$:
     $$
     f_5 f_3 - f_4^2 = (5)(2) - 3^2 = 10 - 9 = 1 = (-1)^4 \quad \checkmark
     $$
   - Check for $n = 5$:
     $$
     f_6 f_4 - f_5^2 = (8)(3) - 5^2 = 24 - 25 = -1 = (-1)^5 \quad \checkmark
     $$
   This proves Cassini's famous identity directly from matrix properties!

