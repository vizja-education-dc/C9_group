# Exercise 14. Rotation Matrices

## 1. Problem Statement

The matrix representing a counterclockwise rotation through an angle $\theta$ in $\mathbb{R}^2$ is:
$$
R(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}
$$

1. Compute the product $R(\alpha) R(\beta)$.
2. Use the angle-sum trigonometric identities for sine and cosine to show that:
   $$
   R(\alpha) R(\beta) = R(\alpha + \beta)
   $$
3. Explain this result geometrically.

---

## 2. Theoretical Background and Concepts

### 2D Rotation Matrices
In Cartesian coordinates, rotating a vector $\begin{pmatrix} x \\ y \end{pmatrix}$ by an angle $\theta$ counterclockwise yields:
$$
\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} x \cos\theta - y \sin\theta \\ x \sin\theta + y \cos\theta \end{pmatrix} = R(\theta) \begin{pmatrix} x \\ y \end{pmatrix}
$$

### Trigonometric Angle-Sum Identities
For any angles $\alpha, \beta \in \mathbb{R}$:
- **Cosine sum formula:**
  $$
  \cos(\alpha + \beta) = \cos\alpha \cos\beta - \sin\alpha \sin\beta
  $$
- **Sine sum formula:**
  $$
  \sin(\alpha + \beta) = \sin\alpha \cos\beta + \cos\alpha \sin\beta
  $$

---

## 3. Detailed Step-by-Step Solution

### 3.1. Computing $R(\alpha) R(\beta)$

Write out the two rotation matrices:
$$
R(\alpha) = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix}, \qquad R(\beta) = \begin{pmatrix} \cos\beta & -\sin\beta \\ \sin\beta & \cos\beta \end{pmatrix}
$$

Multiply the two matrices:
$$
R(\alpha) R(\beta) = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix} \begin{pmatrix} \cos\beta & -\sin\beta \\ \sin\beta & \cos\beta \end{pmatrix}
$$

Compute each entry:
- **Entry $(1,1)$:**
  $$
  (\cos\alpha)(\cos\beta) + (-\sin\alpha)(\sin\beta) = \cos\alpha \cos\beta - \sin\alpha \sin\beta
  $$
- **Entry $(1,2)$:**
  $$
  (\cos\alpha)(-\sin\beta) + (-\sin\alpha)(\cos\beta) = -(\sin\alpha \cos\beta + \cos\alpha \sin\beta)
  $$
- **Entry $(2,1)$:**
  $$
  (\sin\alpha)(\cos\beta) + (\cos\alpha)(\sin\beta) = \sin\alpha \cos\beta + \cos\alpha \sin\beta
  $$
- **Entry $(2,2)$:**
  $$
  (\sin\alpha)(-\sin\beta) + (\cos\alpha)(\cos\beta) = \cos\alpha \cos\beta - \sin\alpha \sin\beta
  $$

---

### 3.2. Applying Angle-Sum Identities

Substitute the trigonometric identities into the matrix entries:
- Entry $(1,1) = \cos(\alpha + \beta)$
- Entry $(1,2) = -\sin(\alpha + \beta)$
- Entry $(2,1) = \sin(\alpha + \beta)$
- Entry $(2,2) = \cos(\alpha + \beta)$

Thus:
$$
R(\alpha) R(\beta) = \begin{pmatrix} \cos(\alpha + \beta) & -\sin(\alpha + \beta) \\ \sin(\alpha + \beta) & \cos(\alpha + \beta) \end{pmatrix} = R(\alpha + \beta)
$$

$$
\boxed{R(\alpha) R(\beta) = R(\alpha + \beta)}
$$

---

### 3.3. Geometric Explanation

1. **Composition of Rotations:**
   The product $R(\alpha) R(\beta)$ represents the composition of two geometric transformations:
   - First, the plane is rotated counterclockwise about the origin by angle $\beta$.
   - Next, the resulting plane is rotated counterclockwise about the origin by angle $\alpha$.
   Geometrically, performing two successive planar rotations about the same center (the origin) is equivalent to a single rotation by the sum of the angles $\alpha + \beta$.

2. **Commutativity of 2D Rotations:**
   Because scalar addition is commutative ($\alpha + \beta = \beta + \alpha$):
   $$
   R(\alpha) R(\beta) = R(\alpha + \beta) = R(\beta + \alpha) = R(\beta) R(\alpha)
   $$
   This proves that **planar rotations always commute with each other** (the special orthogonal group $\mathrm{SO}(2)$ is abelian).

---

## 4. Verification and Consistency Checks

1. **Identity Rotation ($\beta = 0$):**
   $$
   R(0) = \begin{pmatrix} \cos 0 & -\sin 0 \\ \sin 0 & \cos 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I
   $$
   $$
   R(\alpha) R(0) = R(\alpha + 0) = R(\alpha) \quad \checkmark
   $$

2. **Inverse Rotation ($\beta = -\alpha$):**
   $$
   R(\alpha) R(-\alpha) = R(\alpha - \alpha) = R(0) = I
   $$
   Using parity of trigonometric functions ($\cos(-\alpha) = \cos\alpha$, $\sin(-\alpha) = -\sin\alpha$):
   $$
   R(-\alpha) = \begin{pmatrix} \cos\alpha & \sin\alpha \\ -\sin\alpha & \cos\alpha \end{pmatrix} = (R(\alpha))^T = (R(\alpha))^{-1} \quad \checkmark
   $$
   Every 2D rotation matrix is orthogonal ($R^T = R^{-1}$) with $\det(R) = \cos^2\theta + \sin^2\theta = 1$.
