# Exercise 11. When Do Matrices Commute?

## 1. Problem Statement

Given the matrices:
$$
A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} a & b \\ c & d \end{pmatrix}
$$
where $a, b, c, d \in \mathbb{R}$.

1. Find the necessary and sufficient conditions on the entries $a, b, c, d$ under which $AB = BA$.
2. Describe the general form of all such commuting matrices $B$.

---

## 2. Theoretical Background and Concepts

### Commutator and Centralizer
In general matrix algebra, two square matrices $A$ and $B$ are said to **commute** if:
$$
AB = BA \iff [A, B] = AB - BA = 0
$$
The set of all matrices that commute with a given matrix $A$ is called the **centralizer** (or commutant) of $A$:
$$
C(A) = \{ B \in M_n(\mathbb{R}) : AB = BA \}
$$
$C(A)$ forms a linear subspace and a subring of $M_n(\mathbb{R})$. In particular, any scalar multiple of the identity $aI$ and any polynomial in $A$ always commutes with $A$.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $AB$
$$
AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} a & b \\ c & d \end{pmatrix}
$$

- Entry $(1,1)$: $(1)(a) + (1)(c) = a + c$
- Entry $(1,2)$: $(1)(b) + (1)(d) = b + d$
- Entry $(2,1)$: $(0)(a) + (1)(c) = c$
- Entry $(2,2)$: $(0)(b) + (1)(d) = d$

$$
AB = \begin{pmatrix} a + c & b + d \\ c & d \end{pmatrix}
$$

---

### 3.2. Computing $BA$
$$
BA = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}
$$

- Entry $(1,1)$: $(a)(1) + (b)(0) = a$
- Entry $(1,2)$: $(a)(1) + (b)(1) = a + b$
- Entry $(2,1)$: $(c)(1) + (d)(0) = c$
- Entry $(2,2)$: $(c)(1) + (d)(1) = c + d$

$$
BA = \begin{pmatrix} a & a + b \\ c & c + d \end{pmatrix}
$$

---

### 3.3. Deriving the Commutativity Conditions

Equating $AB = BA$ entry by entry:
1. **Entry $(1,1)$:** $a + c = a \implies \mathbf{c = 0}$
2. **Entry $(2,1)$:** $c = c$ (identically satisfied for any $c$)
3. **Entry $(2,2)$:** $d = c + d \implies \mathbf{c = 0}$
4. **Entry $(1,2)$:** $b + d = a + b \implies \mathbf{d = a}$

The parameter $b$ cancels out from the equation $b + d = a + b$, which means that $b$ is completely free and unconstrained.

Thus, the necessary and sufficient conditions are:
$$
\boxed{c = 0 \quad \text{and} \quad d = a, \quad \text{with } a, b \in \mathbb{R} \text{ arbitrary}}
$$

---

### 3.4. General Form of Matrix $B$

Substituting $c = 0$ and $d = a$ into $B$:
$$
\boxed{B = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix}, \quad \text{for any } a, b \in \mathbb{R}}
$$

This family of matrices can be expressed as:
$$
B = a \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + b \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = a I + b N
$$
Since $A = I + N$ (where $N = A - I$), any such matrix $B$ can also be written as a linear polynomial in $A$:
$$
B = a I + b(A - I) = (a - b)I + bA
$$
which confirms that the centralizer of $A$ consists of all linear combinations of $I$ and $A$.

---

## 4. Verification and Consistency Checks

1. **Direct Substitution Check:**
   Let $B = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix}$. Compute both products:
   $$
   AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} a & b \\ 0 & a \end{pmatrix} = \begin{pmatrix} a & b + a \\ 0 & a \end{pmatrix}
   $$
   $$
   BA = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} a & a + b \\ 0 & a \end{pmatrix}
   $$
   Since $b + a = a + b$, $AB = BA$ holds identically for all $a, b \in \mathbb{R} \quad \checkmark$

2. **Counterexample for Non-commuting Choices:**
   - If $c \neq 0$, say $c = 1, a = 1, d = 1, b = 0$:
     $$
     AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \neq \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix} = BA \quad \checkmark
     $$
   - If $d \neq a$, say $a = 1, d = 2, c = 0, b = 0$:
     $$
     AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ 0 & 2 \end{pmatrix} \neq \begin{pmatrix} 1 & 1 \\ 0 & 2 \end{pmatrix} = BA \quad \checkmark
     $$
