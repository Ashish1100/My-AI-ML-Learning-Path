# MIT 18.06 Linear Algebra - Lecture 1: The Geometry of Linear Equations

**Course:** MIT 18.06 Linear Algebra, Spring 2005  
**Instructor:** Professor Gilbert Strang  
**Lecture:** 1 - The Geometry of Linear Equations  
**Video:** [YouTube Link](https://youtu.be/ZK3O402wf1c)  
**Textbook:** Introduction to Linear Algebra by Gilbert Strang  
**Course Website:** [web.mit.edu/18.06](http://web.mit.edu/18.06)

---

## Table of Contents
- [Overview](#overview)
- [Fundamental Problem](#fundamental-problem)
- [Three Pictures of Linear Systems](#three-pictures-of-linear-systems)
  - [1. Row Picture](#1-row-picture)
  - [2. Column Picture](#2-column-picture-â­)
  - [3. Matrix Form](#3-matrix-form)
- [Examples](#examples)
  - [2x2 System](#example-1-2x2-system)
  - [3x3 System](#example-2-3x3-system)
- [Key Concepts](#key-concepts)
- [Matrix-Vector Multiplication](#matrix-vector-multiplication)
- [Important Questions](#important-questions)

---

## Overview

This lecture introduces the **fundamental problem of linear algebra**: solving systems of linear equations. We examine three complementary perspectives for understanding linear systems:

1. **Row Picture** - View equations one at a time (geometric interpretation as lines/planes)
2. **Column Picture** â­ - View columns as vectors (linear combinations)
3. **Matrix Form** - Compact algebraic representation using matrices

---

## Fundamental Problem

**Goal:** Solve a system of \( n \) linear equations with \( n \) unknowns

General form:
\[
\begin{cases}
a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\
a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_2 \\
\vdots \\
a_{n1}x_1 + a_{n2}x_2 + \cdots + a_{nn}x_n = b_n
\end{cases}
\]

---

## Three Pictures of Linear Systems

### 1. Row Picture

**Perspective:** Consider each equation individually as a geometric object.

- In 2D: Each equation represents a **line**
- In 3D: Each equation represents a **plane**
- In n-D: Each equation represents a **hyperplane**

**Solution:** The point(s) where all geometric objects intersect.

**Characteristics:**
- Traditional approach taught in high school
- Easy to visualize in 2D and 3D
- Becomes difficult to visualize in higher dimensions (4D+)

---

### 2. Column Picture â­

**Perspective:** View the system as a linear combination of column vectors.

**Key Idea:** Find the right combination of column vectors to produce the result vector \( \mathbf{b} \).

\[
x_1 \begin{bmatrix} a_{11} \\ a_{21} \\ \vdots \\ a_{n1} \end{bmatrix} + x_2 \begin{bmatrix} a_{12} \\ a_{22} \\ \vdots \\ a_{n2} \end{bmatrix} + \cdots + x_n \begin{bmatrix} a_{1n} \\ a_{2n} \\ \vdots \\ a_{nn} \end{bmatrix} = \begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_n \end{bmatrix}
\]

**Linear Combination:** The most fundamental operation in linear algebra
- Take vectors (columns)
- Multiply each by a scalar (coefficients)
- Add them together

**Advantages:**
- Works well in any dimension
- Central to modern linear algebra
- Connects to vector spaces and span concepts

---

### 3. Matrix Form

**Compact Representation:**

\[
A\mathbf{x} = \mathbf{b}
\]

Where:
- \( A \) is the **coefficient matrix** (\( n \times n \))
- \( \mathbf{x} \) is the **vector of unknowns** (\( n \times 1 \))
- \( \mathbf{b} \) is the **right-hand side vector** (\( n \times 1 \))

\[
\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{bmatrix}
\begin{bmatrix}
x_1 \\ x_2 \\ \vdots \\ x_n
\end{bmatrix}
=
\begin{bmatrix}
b_1 \\ b_2 \\ \vdots \\ b_n
\end{bmatrix}
\]

---

## Examples

### Example 1: 2x2 System

**System of Equations:**
\[
\begin{cases}
2x - y = 0 \\
-x + 2y = 3
\end{cases}
\]

#### Row Picture (2D - Lines)

**Equation 1:** \( 2x - y = 0 \)
- Passes through origin: \( (0, 0) \)
- Another point: \( (1, 2) \)
- Line: All points satisfying this equation

**Equation 2:** \( -x + 2y = 3 \)
- Does NOT pass through origin (since RHS â‰  0)
- When \( y = 0 \): \( x = -3 \), point: \( (-3, 0) \)
- When \( x = -1 \): \( y = 1 \), point: \( (-1, 1) \)

**Solution:** \( (x, y) = (1, 2) \) â€” the intersection point of both lines

#### Column Picture (Vector Combination)

\[
x \begin{bmatrix} 2 \\ -1 \end{bmatrix} + y \begin{bmatrix} -1 \\ 2 \end{bmatrix} = \begin{bmatrix} 0 \\ 3 \end{bmatrix}
\]

**Geometric Interpretation:**
- Column 1: Vector \( \begin{bmatrix} 2 \\ -1 \end{bmatrix} \) (right 2, down 1)
- Column 2: Vector \( \begin{bmatrix} -1 \\ 2 \end{bmatrix} \) (left 1, up 2)
- Find: \( x = 1 \) and \( y = 2 \)

**Vector Addition:**
1. Take 1 of column 1: \( \begin{bmatrix} 2 \\ -1 \end{bmatrix} \)
2. Add 2 of column 2: \( 2 \times \begin{bmatrix} -1 \\ 2 \end{bmatrix} = \begin{bmatrix} -2 \\ 4 \end{bmatrix} \)
3. Result: \( \begin{bmatrix} 2 \\ -1 \end{bmatrix} + \begin{bmatrix} -2 \\ 4 \end{bmatrix} = \begin{bmatrix} 0 \\ 3 \end{bmatrix} \) âœ“

#### Matrix Form

\[
\begin{bmatrix} 2 & -1 \\ -1 & 2 \end{bmatrix}
\begin{bmatrix} x \\ y \end{bmatrix}
=
\begin{bmatrix} 0 \\ 3 \end{bmatrix}
\]

**Solution:** \( \mathbf{x} = \begin{bmatrix} 1 \\ 2 \end{bmatrix} \)

---

### Example 2: 3x3 System

**System of Equations:**
\[
\begin{cases}
2x - y = 0 \\
-x + 2y - z = -1 \\
-3y + 4z = 4
\end{cases}
\]

#### Row Picture (3D - Planes)

- Each equation represents a **plane** in 3D space
- **Equation 1:** Plane containing the origin
- **Equation 2:** Plane not through origin
- **Equation 3:** Plane not through origin

**Visualization Challenge:**
- Two planes intersect in a **line**
- Third plane intersects this line at a **point** (the solution)
- Difficult to visualize accurately

**Note:** Row picture becomes impractical in higher dimensions!

#### Column Picture (Vector Combination)

\[
x \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix} + y \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix} + z \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix} = \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
\]

**Observation:** The right-hand side \( \mathbf{b} \) equals the third column!

**Solution:** \( x = 0, y = 0, z = 1 \)

**Interpretation:** We need:
- 0 of column 1
- 0 of column 2
- 1 of column 3

#### Matrix Form

\[
\begin{bmatrix}
2 & -1 & 0 \\
-1 & 2 & -1 \\
0 & -3 & 4
\end{bmatrix}
\begin{bmatrix} x \\ y \\ z \end{bmatrix}
=
\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
\]

**Solution:** \( \mathbf{x} = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} \)

---

### Example 3: Modified Right-Hand Side

**New System:** Same matrix \( A \), but new \( \mathbf{b} \):

\[
\begin{bmatrix}
2 & -1 & 0 \\
-1 & 2 & -1 \\
0 & -3 & 4
\end{bmatrix}
\begin{bmatrix} x \\ y \\ z \end{bmatrix}
=
\begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}
\]

**Column Picture Analysis:**

New \( \mathbf{b} = \) Column 1 + Column 2

\[
\begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix} + \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix} = \begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}
\]

**Solution:** \( x = 1, y = 1, z = 0 \)

---

## Key Concepts

### 1. Linear Combination

**Definition:** A linear combination of vectors \( \mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n \) is:

\[
c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n
\]

where \( c_1, c_2, \ldots, c_n \) are scalars.

**Most fundamental operation in linear algebra!**

---

### 2. Span (All Possible Linear Combinations)

**Question:** What are ALL possible linear combinations of given vectors?

**For the 2x2 example:**
- Columns: \( \begin{bmatrix} 2 \\ -1 \end{bmatrix} \) and \( \begin{bmatrix} -1 \\ 2 \end{bmatrix} \)
- All combinations: **Fill the entire 2D plane**
- Can reach any point \( (x, y) \) in \( \mathbb{R}^2 \)

**For the 3x3 example:**
- Three independent columns in 3D
- All combinations: **Fill entire 3D space**
- Can reach any point in \( \mathbb{R}^3 \)

**When can't we reach every \( \mathbf{b} \)?**
- If columns are **linearly dependent**
- Example: Third column is sum of first two
- All combinations lie in a **subspace** (plane in 3D)

---

### 3. Solvability: Can we solve \( A\mathbf{x} = \mathbf{b} \) for every \( \mathbf{b} \)?

**Good Case (Non-singular/Invertible Matrix):**
- Columns are **linearly independent**
- Columns **span** the entire space
- Solution exists for **every** \( \mathbf{b} \)
- Matrix is **invertible**

**Bad Case (Singular Matrix):**
- Columns are **linearly dependent** (e.g., one column = another column)
- Columns span only a **subspace** (not full space)
- Solution exists for **some** \( \mathbf{b} \), but not all
- Matrix is **not invertible**

**Example of Singular Matrix in 3D:**
- If column 3 = column 1 + column 2
- All combinations lie in a **plane** (2D subspace of 3D)
- Can only solve for \( \mathbf{b} \) in that plane

---

### 4. Higher Dimensions (n = 9 example)

**9 equations, 9 unknowns:**
- 9 column vectors in 9-dimensional space
- Each vector has 9 components
- Find linear combination to reach \( \mathbf{b} \in \mathbb{R}^9 \)

**Key Insight:**
- Can't visualize 9D space directly
- Think abstractly about linear combinations
- If columns are independent â†’ span all of \( \mathbb{R}^9 \)
- If 9th column = 8th column â†’ span only 8D subspace ("hyperplane")

**Random Matrices:**
- Random \( n \times n \) matrix is almost always **non-singular**
- MATLAB command `rand(9,9)` will give invertible matrix with probability 1

---

## Matrix-Vector Multiplication

**Two ways to think about** \( A\mathbf{x} \):

### Method 1: Linear Combination of Columns (â­ Preferred)

\[
A\mathbf{x} = \begin{bmatrix} | & | & & | \\ \mathbf{a}_1 & \mathbf{a}_2 & \cdots & \mathbf{a}_n \\ | & | & & | \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} = x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n
\]

**Interpretation:** \( A\mathbf{x} \) is a **linear combination of the columns of** \( A \)

---

### Method 2: Dot Product of Rows

\[
A\mathbf{x} = \begin{bmatrix} \text{---} & \mathbf{r}_1 & \text{---} \\ \text{---} & \mathbf{r}_2 & \text{---} \\ & \vdots & \\ \text{---} & \mathbf{r}_n & \text{---} \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} = \begin{bmatrix} \mathbf{r}_1 \cdot \mathbf{x} \\ \mathbf{r}_2 \cdot \mathbf{x} \\ \vdots \\ \mathbf{r}_n \cdot \mathbf{x} \end{bmatrix}
\]

**Interpretation:** Each component is the **dot product** of a row with \( \mathbf{x} \)

---

### Example Calculation

\[
\begin{bmatrix} 2 & 5 \\ 1 & 3 \end{bmatrix} \begin{bmatrix} 1 \\ 2 \end{bmatrix} = ?
\]

**Column Method:**
\[
1 \times \begin{bmatrix} 2 \\ 1 \end{bmatrix} + 2 \times \begin{bmatrix} 5 \\ 3 \end{bmatrix} = \begin{bmatrix} 2 \\ 1 \end{bmatrix} + \begin{bmatrix} 10 \\ 6 \end{bmatrix} = \begin{bmatrix} 12 \\ 7 \end{bmatrix}
\]

**Row Method:**
\[
\begin{bmatrix} 2(1) + 5(2) \\ 1(1) + 3(2) \end{bmatrix} = \begin{bmatrix} 12 \\ 7 \end{bmatrix}
\]

Both methods give the same result!

---

## Important Questions

### Q1: Can we solve \( A\mathbf{x} = \mathbf{b} \) for every \( \mathbf{b} \)?

**Equivalent Questions:**
- Do the columns of \( A \) span the entire space?
- Are the columns linearly independent?
- Is \( A \) invertible/non-singular?

**Answer depends on** \( A \):
- âœ… **Yes** if columns are independent (good matrix)
- âŒ **No** if columns are dependent (singular matrix)

---

### Q2: When is there no solution for some \( \mathbf{b} \)?

**Example in 3D:**
- If all columns lie in same plane
- All linear combinations stay in that plane
- Cannot reach \( \mathbf{b} \) outside the plane
- System has **no solution** for such \( \mathbf{b} \)

---

## Summary & Next Steps

### What We Learned (Lecture 1):

1. **Three perspectives** on linear systems:
   - Row picture (equations as geometric objects)
   - Column picture (linear combinations) â­
   - Matrix form (compact notation)

2. **Linear combinations** are fundamental

3. **Solvability** depends on column independence

4. **Matrix-vector multiplication** = linear combination of columns

---

### Coming Next (Lecture 2):

**Elimination:** Systematic algorithm to solve \( A\mathbf{x} = \mathbf{b} \)
- Used by all production software
- Works for any size system
- Gaussian elimination procedure
- Finding pivots and back-substitution

---

## Additional Notes

### Course Information
- **Prerequisites:** Calculus of several variables (18.02)
- **Meeting Times:** 3 lectures/week + 1 recitation
- **Textbook:** Strang, Introduction to Linear Algebra, 4th ed.
- **Software:** MATLAB for homework problems

### Key Course Goals
1. Using matrices AND understanding them
2. Solving systems: \( A\mathbf{x} = \mathbf{b} \)
3. Understanding four fundamental subspaces
4. Eigenvalues and eigenvectors
5. Applications to engineering and science

---

## Quick Reference

### Notation
- \( A \): Coefficient matrix (typically \( m \times n \))
- \( \mathbf{x} \): Vector of unknowns (\( n \times 1 \))
- \( \mathbf{b} \): Right-hand side vector (\( m \times 1 \))
- \( A\mathbf{x} = \mathbf{b} \): System of linear equations

### Key Terms
- **Linear Combination:** \( c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n \)
- **Span:** All possible linear combinations
- **Linearly Independent:** No vector is a combination of others
- **Non-singular:** Matrix has full rank, is invertible
- **Singular:** Matrix does not have full rank, not invertible

---

## Resources

- **MIT OpenCourseWare:** [ocw.mit.edu/18-06S05](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2005/)
- **Course Website:** [web.mit.edu/18.06](http://web.mit.edu/18.06)
- **Video Lectures:** [YouTube Playlist](https://www.youtube.com/playlist?list=PLE7DDD91010BC51F8)
- **Textbook:** [Introduction to Linear Algebra](http://math.mit.edu/linearalgebra/)

---

**License:** Creative Commons BY-NC-SA  
**Course:** MIT OpenCourseWare  

---

*Notes compiled from MIT 18.06 Linear Algebra Lecture 1 by Prof. Gilbert Strang*  
*For educational purposes - part of personal study repository*