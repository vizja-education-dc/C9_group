# Exercise 9. Area and the Determinant

## 1. Problem Statement

Given the vectors:
$$
u = \begin{pmatrix} 3 \\ 1 \end{pmatrix}, \qquad v = \begin{pmatrix} 1 \\ 4 \end{pmatrix}
$$
which span a parallelogram in $\mathbb{R}^2$.

1. Compute the area of this parallelogram using a determinant.
2. Form the matrix with the vectors in reversed order ($v$ first, then $u$).
3. Explain what changes in the determinant and what does not change in the geometric area.

---

## 2. Theoretical Background and Concepts

### Geometric Interpretation of the $2 \times 2$ Determinant
The determinant of a $2 \times 2$ matrix formed by two column vectors $u = \begin{pmatrix} u_1 \\ u_2 \end{pmatrix}$ and $v = \begin{pmatrix} v_1 \\ v_2 \end{pmatrix}$ computes the **signed (oriented) area** of the parallelogram spanned by $u$ and $v$:
$$
\det \begin{pmatrix} u & v \end{pmatrix} = \begin{vmatrix} u_1 & v_1 \\ u_2 & v_2 \end{vmatrix}
$$

- The **geometric area** is the absolute value:
  $$
  \text{Area} = \left| \det \begin{pmatrix} u & v \end{pmatrix} \right|
  $$
- The **sign of the determinant** reflects the **orientation** of the ordered pair $(u, v)$:
  - $\det > 0$: The shortest rotation from $u$ to $v$ is **counterclockwise** (standard/positive orientation).
  - $\det < 0$: The shortest rotation from $u$ to $v$ is **clockwise** (reversed/negative orientation).

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing the Area with Ordered Pair $(u, v)$

Construct the matrix with columns $u$ and $v$:
$$
M_1 = \begin{pmatrix} u & v \end{pmatrix} = \begin{pmatrix} 3 & 1 \\ 1 & 4 \end{pmatrix}
$$

Compute its determinant:
$$
\det(M_1) = (3)(4) - (1)(1) = 12 - 1 = 11
$$

The geometric area is the absolute value:
$$
\text{Area} = |\det(M_1)| = |11| = 11
$$

$$
\boxed{\text{Area} = 11}
$$

---

### 3.2. Reversing the Order of the Vectors

Construct the matrix with columns $v$ and $u$:
$$
M_2 = \begin{pmatrix} v & u \end{pmatrix} = \begin{pmatrix} 1 & 3 \\ 4 & 1 \end{pmatrix}
$$

Compute its determinant:
$$
\det(M_2) = (1)(1) - (3)(4) = 1 - 12 = -11
$$

$$
\boxed{\det(M_2) = -11}
$$

---

### 3.3. What Changes vs. What Does Not Change

1. **What changes:**
   - **The sign of the determinant:** Swapping the two columns reverses the sign from $+11$ to $-11$.
   - **The geometric orientation:** In the pair $(u, v)$, vector $v$ lies in the counterclockwise direction from $u$, giving a positive signed area. In the reversed pair $(v, u)$, vector $u$ lies clockwise from $v$, reversing the orientation of the ordered basis.
2. **What does not change:**
   - **The physical area:** The geometric area is an unsigned magnitude defined by:
     $$
     \text{Area} = |\det(M_2)| = |-11| = 11
     $$
     The physical parallelogram formed by the two line segments in $\mathbb{R}^2$ remains identical regardless of the order in which its spanning vectors are named.

---

## 4. Verification and Consistency Checks

1. **Cross Product Verification:**
   Embed $u$ and $v$ into $\mathbb{R}^3$ as $u = (3, 1, 0)$ and $v = (1, 4, 0)$.
   The area of the parallelogram is given by the norm of the cross product:
   $$
   u \times v = \begin{pmatrix} 0 \\ 0 \\ (3)(4) - (1)(1) \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 11 \end{pmatrix} \implies \|u \times v\| = 11 \quad \checkmark
   $$
   Reversing order:
   $$
   v \times u = - (u \times v) = \begin{pmatrix} 0 \\ 0 \\ -11 \end{pmatrix} \implies \|v \times u\| = 11 \quad \checkmark
   $$

2. **Shoelace Formula Check:**
   The vertices of the parallelogram are $(0,0)$, $(3,1)$, $(4,5)$, $(1,4)$.
   By the Shoelace formula:
   $$
   \text{Area} = \frac{1}{2} |(0 \cdot 1 - 0 \cdot 3) + (3 \cdot 5 - 1 \cdot 4) + (4 \cdot 4 - 5 \cdot 1) + (1 \cdot 0 - 4 \cdot 0)|
   $$
   $$
   \text{Area} = \frac{1}{2} |0 + (15 - 4) + (16 - 5) + 0| = \frac{1}{2} |11 + 11| = \frac{1}{2}(22) = 11 \quad \checkmark
   $$
