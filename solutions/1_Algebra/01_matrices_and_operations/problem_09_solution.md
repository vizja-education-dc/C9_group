# Exercise 9. Composing Transformations

## 1. Problem Statement

Let:
$$
S = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix}, \qquad R = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}
$$
The matrix $S$ describes nonuniform scaling (stretching by a factor of $2$ along the $x$-axis), while $R$ describes a $90^\circ$ counterclockwise rotation.

For the vector:
$$
x = \begin{pmatrix} 1 \\ 2 \end{pmatrix}
$$
1. Compute $RSx$.
2. Compute $SRx$.
3. Compare the results and explain geometrically why the order of these transformations matters.

---

## 2. Theoretical Background and Concepts

### Matrix Transformations as Geometric Maps
A square matrix $M \in \mathbb{R}^{2 \times 2}$ acts as a linear transformation $T_M: \mathbb{R}^2 \to \mathbb{R}^2$ via matrix-vector multiplication $v \mapsto Mv$.

- **Composition of Maps:** The composition of two linear maps $(T_A \circ T_B)(x) = A(Bx) = (AB)x$ corresponds directly to the matrix product $AB$, where the rightmost transformation is applied first.
- **Geometric Interpretation of $S$ and $R$:**
  - $S\begin{pmatrix} u \\ v \end{pmatrix} = \begin{pmatrix} 2u \\ v \end{pmatrix}$: doubles the horizontal coordinate while preserving the vertical coordinate.
  - $R\begin{pmatrix} u \\ v \end{pmatrix} = \begin{pmatrix} -v \\ u \end{pmatrix}$: rotates the plane by $90^\circ$ counterclockwise.

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computation of $RSx$ (Scale First, then Rotate)

First, apply scaling $S$ to $x$:
$$
Sx = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} (2)(1) + (0)(2) \\ (0)(1) + (1)(2) \end{pmatrix} = \begin{pmatrix} 2 \\ 2 \end{pmatrix}
$$

Next, apply rotation $R$ to the resulting vector $Sx$:
$$
RSx = R(Sx) = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 \\ 2 \end{pmatrix} = \begin{pmatrix} (0)(2) + (-1)(2) \\ (1)(2) + (0)(2) \end{pmatrix} = \begin{pmatrix} -2 \\ 2 \end{pmatrix}
$$

$$
\boxed{RSx = \begin{pmatrix} -2 \\ 2 \end{pmatrix}}
$$

---

### 3.2. Computation of $SRx$ (Rotate First, then Scale)

First, apply rotation $R$ to $x$:
$$
Rx = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} (0)(1) + (-1)(2) \\ (1)(1) + (0)(2) \end{pmatrix} = \begin{pmatrix} -2 \\ 1 \end{pmatrix}
$$

Next, apply scaling $S$ to the resulting vector $Rx$:
$$
SRx = S(Rx) = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -2 \\ 1 \end{pmatrix} = \begin{pmatrix} (2)(-2) + (0)(1) \\ (0)(-2) + (1)(1) \end{pmatrix} = \begin{pmatrix} -4 \\ 1 \end{pmatrix}
$$

$$
\boxed{SRx = \begin{pmatrix} -4 \\ 1 \end{pmatrix}}
$$

---

### 3.3. Comparison and Geometric Explanation

Comparing the two results:
$$
RSx = \begin{pmatrix} -2 \\ 2 \end{pmatrix} \neq \begin{pmatrix} -4 \\ 1 \end{pmatrix} = SRx
$$

**Why does the order matter geometrically?**
1. **In $RSx$ (Scale first, rotate second):**
   - The original vector $\begin{pmatrix} 1 \\ 2 \end{pmatrix}$ has horizontal component $1$. Scaling doubles this horizontal component to $2$, producing $\begin{pmatrix} 2 \\ 2 \end{pmatrix}$.
   - Subsequent $90^\circ$ rotation moves this scaled horizontal component onto the vertical axis: the vector becomes $\begin{pmatrix} -2 \\ 2 \end{pmatrix}$.
2. **In $SRx$ (Rotate first, scale second):**
   - The vector $\begin{pmatrix} 1 \\ 2 \end{pmatrix}$ is rotated first, which sends its vertical component ($2$) onto the negative horizontal axis, giving $\begin{pmatrix} -2 \\ 1 \end{pmatrix}$.
   - Subsequent scaling doubles the **new** horizontal component (which was originally the vertical component): $-2 \times 2 = -4$, producing $\begin{pmatrix} -4 \\ 1 \end{pmatrix}$.

**Conclusion:** Nonuniform scaling is direction-dependent (it singles out the fixed Cartesian $x$-axis). Because rotation changes the orientation of the vector relative to the coordinate axes before scaling is applied, the two operations do not commute.

---

## 4. Verification and Consistency Checks

1. **Composite Matrix Verification:**
   Compute the composite transformation matrices directly:
   $$
   RS = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix}
   $$
   $$
   (RS)x = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 0(1) - 1(2) \\ 2(1) + 0(2) \end{pmatrix} = \begin{pmatrix} -2 \\ 2 \end{pmatrix} \quad \checkmark
   $$

   $$
   SR = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix}
   $$
   $$
   (SR)x = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 0(1) - 2(2) \\ 1(1) + 0(2) \end{pmatrix} = \begin{pmatrix} -4 \\ 1 \end{pmatrix} \quad \checkmark
   $$

2. **Area Scaling (Determinant) Check:**
   - $\det(S) = 2 \cdot 1 - 0 = 2$ (area is doubled)
   - $\det(R) = 0 - (-1) = 1$ (area is preserved)
   - $\det(RS) = \det(SR) = 2 \times 1 = 2$.
   Both composite matrices have determinant $2$, preserving the signed area scaling factor even though they transform individual points to different locations.

