# MIT 18.06 Linear Algebra - Lecture 1: The Geometry of Linear Equations
## Complete Solutions & Detailed Formulas

**Course:** MIT 18.06 Linear Algebra, Spring 2005  
**Instructor:** Professor Gilbert Strang  
**Lecture:** 1 - The Geometry of Linear Equations  
**Video:** [YouTube Link](https://youtu.be/ZK3O402wf1c)  
**Textbook:** Introduction to Linear Algebra by Gilbert Strang  
**Course Website:** [web.mit.edu/18.06](http://web.mit.edu/18.06)

---

## Table of Contents
- [Course Introduction](#course-introduction)
- [Fundamental Problem of Linear Algebra](#fundamental-problem-of-linear-algebra)
- [Three Perspectives on Linear Systems](#three-perspectives-on-linear-systems)
- [Example 1: 2Ã—2 System - Complete Solution](#example-1-2Ã—2-system---complete-solution)
- [Example 2: 3Ã—3 System - Complete Solution](#example-2-3Ã—3-system---complete-solution)
- [Example 3: Alternative Right-Hand Side](#example-3-alternative-right-hand-side)
- [Linear Combinations - Deep Dive](#linear-combinations---deep-dive)
- [Matrix-Vector Multiplication - Complete Methods](#matrix-vector-multiplication---complete-methods)
- [Solvability Theory](#solvability-theory)
- [Geometric Interpretation in n-Dimensions](#geometric-interpretation-in-n-dimensions)
- [Practice Problems](#practice-problems)
- [Key Formulas Reference](#key-formulas-reference)

---

## Course Introduction

### Course Fundamentals
**Goal:** Understand and solve systems of linear equations using matrix algebra

**Standard Form:** Given \( n \) equations with \( n \) unknowns:
\[
\begin{cases}
a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n = b_1 \\
a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n = b_2 \\
\vdots \quad\quad\quad\quad \vdots \\
a_{n1}x_1 + a_{n2}x_2 + \cdots + a_{nn}x_n = b_n
\end{cases}
\]

Where:
- \( a_{ij} \) = coefficient in row \( i \), column \( j \)
- \( x_j \) = \( j \)-th unknown variable
- \( b_i \) = \( i \)-th right-hand side value

---

## Fundamental Problem of Linear Algebra

### Problem Statement

**Given:** Coefficient matrix \( A \) and right-hand side vector \( \mathbf{b} \)

**Find:** Solution vector \( \mathbf{x} \) such that \( A\mathbf{x} = \mathbf{b} \)

### Matrix Equation Form

\[
\underbrace{\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{n1} & a_{n2} & \cdots & a_{nn}
\end{bmatrix}}_{A}
\underbrace{\begin{bmatrix}
x_1 \\ x_2 \\ \vdots \\ x_n
\end{bmatrix}}_{\mathbf{x}}
=
\underbrace{\begin{bmatrix}
b_1 \\ b_2 \\ \vdots \\ b_n
\end{bmatrix}}_{\mathbf{b}}
\]

**Matrix Dimensions:**
- \( A \): \( n \times n \) (square matrix)
- \( \mathbf{x} \): \( n \times 1 \) (column vector)
- \( \mathbf{b} \): \( n \times 1 \) (column vector)

---

## Three Perspectives on Linear Systems

### 1. Row Picture (Equation-by-Equation View)

**Concept:** Each equation defines a geometric object; solution is the intersection.

**Geometric Objects by Dimension:**
- **1D:** Point
- **2D:** Line (equation: \( ax + by = c \))
- **3D:** Plane (equation: \( ax + by + cz = d \))
- **nD:** Hyperplane (\( n-1 \) dimensional object in \( n \)-space)

**General Line Equation (2D):**
\[
ax + by = c
\]

**Properties:**
- If \( c = 0 \): Line passes through origin
- If \( c \neq 0 \): Line does NOT pass through origin
- Slope-intercept form: \( y = -\frac{a}{b}x + \frac{c}{b} \)

**General Plane Equation (3D):**
\[
ax + by + cz = d
\]

**Normal Vector:** \( \mathbf{n} = \begin{bmatrix} a \\ b \\ c \end{bmatrix} \) is perpendicular to the plane

---

### 2. Column Picture â­ (Linear Combination View)

**Concept:** Find scalar multipliers for column vectors to produce \( \mathbf{b} \)

**Mathematical Form:**
\[
x_1 \begin{bmatrix} a_{11} \\ a_{21} \\ \vdots \\ a_{n1} \end{bmatrix} + x_2 \begin{bmatrix} a_{12} \\ a_{22} \\ \vdots \\ a_{n2} \end{bmatrix} + \cdots + x_n \begin{bmatrix} a_{1n} \\ a_{2n} \\ \vdots \\ a_{nn} \end{bmatrix} = \begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_n \end{bmatrix}
\]

**Compact Notation:**
\[
x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n = \mathbf{b}
\]

where \( \mathbf{a}_j \) is the \( j \)-th column of \( A \).

**Key Insight:** \( A\mathbf{x} \) produces a **linear combination** of columns of \( A \)

---

### 3. Matrix Form (Compact Algebraic Representation)

\[
A\mathbf{x} = \mathbf{b}
\]

**Augmented Matrix Form:**
\[
\left[\begin{array}{cccc|c}
a_{11} & a_{12} & \cdots & a_{1n} & b_1 \\
a_{21} & a_{22} & \cdots & a_{2n} & b_2 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
a_{n1} & a_{n2} & \cdots & a_{nn} & b_n
\end{array}\right]
\]

---

## Example 1: 2Ã—2 System - Complete Solution

### System Definition

\[
\begin{cases}
2x - y = 0 \quad\quad (\text{Equation 1}) \\
-x + 2y = 3 \quad\quad (\text{Equation 2})
\end{cases}
\]

### Solution Method 1: Row Picture (Geometric)

#### Step 1: Plot Equation 1 (\( 2x - y = 0 \))

**Rearrange to slope-intercept form:**
\[
y = 2x
\]

**Properties:**
- Slope: \( m = 2 \)
- y-intercept: \( 0 \) (passes through origin)

**Find points:**
- When \( x = 0 \): \( y = 0 \) â†’ Point: \( (0, 0) \)
- When \( x = 1 \): \( y = 2 \) â†’ Point: \( (1, 2) \)
- When \( x = 2 \): \( y = 4 \) â†’ Point: \( (2, 4) \)

**Verification:**
- \( (0, 0) \): \( 2(0) - 0 = 0 \) âœ“
- \( (1, 2) \): \( 2(1) - 2 = 0 \) âœ“

#### Step 2: Plot Equation 2 (\( -x + 2y = 3 \))

**Rearrange to slope-intercept form:**
\[
2y = x + 3 \implies y = \frac{1}{2}x + \frac{3}{2}
\]

**Properties:**
- Slope: \( m = \frac{1}{2} \)
- y-intercept: \( \frac{3}{2} = 1.5 \)

**Find points:**
- When \( x = 0 \): \( y = \frac{3}{2} \) â†’ Point: \( (0, 1.5) \)
- When \( x = -3 \): \( y = 0 \) â†’ Point: \( (-3, 0) \)
- When \( x = 1 \): \( y = 2 \) â†’ Point: \( (1, 2) \)

**Verification:**
- \( (-3, 0) \): \( -(-3) + 2(0) = 3 \) âœ“
- \( (1, 2) \): \( -(1) + 2(2) = 3 \) âœ“

#### Step 3: Find Intersection

**Solution:** \( (x, y) = (1, 2) \)

**Verify in both equations:**
- Eq 1: \( 2(1) - 2 = 2 - 2 = 0 \) âœ“
- Eq 2: \( -(1) + 2(2) = -1 + 4 = 3 \) âœ“

---

### Solution Method 2: Column Picture

#### Step 1: Write as Linear Combination

\[
x \begin{bmatrix} 2 \\ -1 \end{bmatrix} + y \begin{bmatrix} -1 \\ 2 \end{bmatrix} = \begin{bmatrix} 0 \\ 3 \end{bmatrix}
\]

**Notation:**
- Column 1: \( \mathbf{c}_1 = \begin{bmatrix} 2 \\ -1 \end{bmatrix} \)
- Column 2: \( \mathbf{c}_2 = \begin{bmatrix} -1 \\ 2 \end{bmatrix} \)
- Right-hand side: \( \mathbf{b} = \begin{bmatrix} 0 \\ 3 \end{bmatrix} \)

#### Step 2: Try Solution \( x = 1, y = 2 \)

\[
1 \cdot \begin{bmatrix} 2 \\ -1 \end{bmatrix} + 2 \cdot \begin{bmatrix} -1 \\ 2 \end{bmatrix}
\]

**Calculate component-wise:**

**First component:**
\[
1 \cdot 2 + 2 \cdot (-1) = 2 - 2 = 0 \quad âœ“
\]

**Second component:**
\[
1 \cdot (-1) + 2 \cdot 2 = -1 + 4 = 3 \quad âœ“
\]

**Result:**
\[
\begin{bmatrix} 2 \\ -1 \end{bmatrix} + \begin{bmatrix} -2 \\ 4 \end{bmatrix} = \begin{bmatrix} 0 \\ 3 \end{bmatrix} \quad âœ“
\]

#### Step 3: Geometric Interpretation

**Vector Addition (Graphically):**
1. Start at origin
2. Draw \( \mathbf{c}_1 = \begin{bmatrix} 2 \\ -1 \end{bmatrix} \): Move right 2, down 1 â†’ Point: \( (2, -1) \)
3. From \( (2, -1) \), add \( 2\mathbf{c}_2 = \begin{bmatrix} -2 \\ 4 \end{bmatrix} \): Move left 2, up 4
4. End at \( (2-2, -1+4) = (0, 3) \) âœ“

---

### Solution Method 3: Matrix Form

\[
\begin{bmatrix} 2 & -1 \\ -1 & 2 \end{bmatrix}
\begin{bmatrix} x \\ y \end{bmatrix}
=
\begin{bmatrix} 0 \\ 3 \end{bmatrix}
\]

#### Direct Calculation

\[
\begin{bmatrix} 2x - y \\ -x + 2y \end{bmatrix}
=
\begin{bmatrix} 0 \\ 3 \end{bmatrix}
\]

**This gives us the original system:**
- \( 2x - y = 0 \)
- \( -x + 2y = 3 \)

#### Algebraic Solution

**From Equation 1:** \( y = 2x \)

**Substitute into Equation 2:**
\[
-x + 2(2x) = 3
\]
\[
-x + 4x = 3
\]
\[
3x = 3 \implies x = 1
\]

**Back-substitute:**
\[
y = 2(1) = 2
\]

**Solution:** \( \mathbf{x} = \begin{bmatrix} 1 \\ 2 \end{bmatrix} \)

---

### All Possible Right-Hand Sides

**Question:** Can we solve for ANY \( \mathbf{b} = \begin{bmatrix} b_1 \\ b_2 \end{bmatrix} \)?

**Answer:** YES! The columns \( \begin{bmatrix} 2 \\ -1 \end{bmatrix} \) and \( \begin{bmatrix} -1 \\ 2 \end{bmatrix} \) are **linearly independent**.

**Span:** All linear combinations fill the entire 2D plane (\( \mathbb{R}^2 \))

\[
\text{span}\left\{ \begin{bmatrix} 2 \\ -1 \end{bmatrix}, \begin{bmatrix} -1 \\ 2 \end{bmatrix} \right\} = \mathbb{R}^2
\]

**Matrix Properties:**
- **Non-singular** (invertible)
- **Full rank** (rank = 2)
- **Determinant:** \( \det(A) = 2(2) - (-1)(-1) = 4 - 1 = 3 \neq 0 \)

---

## Example 2: 3Ã—3 System - Complete Solution

### System Definition

\[
\begin{cases}
2x - y + 0z = 0 \quad\quad (\text{Equation 1}) \\
-x + 2y - z = -1 \quad\quad (\text{Equation 2}) \\
0x - 3y + 4z = 4 \quad\quad (\text{Equation 3})
\end{cases}
\]

---

### Solution Method 1: Row Picture (3D Planes)

#### Equation 1: \( 2x - y = 0 \)

**Properties:**
- \( z \) can be ANY value (no \( z \) term)
- Forms a **vertical plane** parallel to z-axis
- In xy-plane: Line \( y = 2x \)

**Points on plane:**
- \( (0, 0, 0) \) âœ“
- \( (1, 2, 0) \) âœ“
- \( (1, 2, 5) \) âœ“ (any \( z \))

#### Equation 2: \( -x + 2y - z = -1 \)

**Properties:**
- General plane (all variables present)
- Does NOT pass through origin

**Points on plane:**
- When \( x = 1, y = 0, z = 0 \): \( -1 + 0 - 0 = -1 \) âœ“
- When \( x = 0, y = 0, z = 1 \): \( 0 + 0 - 1 = -1 \) âœ“
- When \( x = 1, y = 1, z = 2 \): \( -1 + 2 - 2 = -1 \) âœ“

#### Equation 3: \( -3y + 4z = 4 \)

**Properties:**
- No \( x \) term â†’ \( x \) can be any value
- Vertical plane parallel to x-axis

**Rearrange:** \( z = \frac{3y + 4}{4} \)

**Points on plane:**
- When \( y = 0, z = 1 \), any \( x \): \( -3(0) + 4(1) = 4 \) âœ“
- When \( y = 4, z = 4 \), any \( x \): \( -3(4) + 4(4) = 4 \) âœ“

#### Intersection

Three planes meet at **one point**: \( (x, y, z) = (0, 0, 1) \)

---

### Solution Method 2: Column Picture â­

#### Step 1: Express as Linear Combination

\[
x \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix} + y \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix} + z \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix} = \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
\]

**Notation:**
- \( \mathbf{c}_1 = \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix} \) (Column 1)
- \( \mathbf{c}_2 = \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix} \) (Column 2)
- \( \mathbf{c}_3 = \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix} \) (Column 3)
- \( \mathbf{b} = \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix} \) (Right-hand side)

#### Step 2: Observation

**KEY INSIGHT:** \( \mathbf{b} = \mathbf{c}_3 \) (Right-hand side equals Column 3!)

Therefore: \( x = 0, y = 0, z = 1 \)

#### Step 3: Verify Solution

\[
0 \cdot \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix} + 0 \cdot \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix} + 1 \cdot \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
\]

\[
= \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix} + \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix} + \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix} = \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix} \quad âœ“
\]

#### Step 4: Verify in Original Equations

**Equation 1:** \( 2(0) - 0 + 0(1) = 0 \) âœ“

**Equation 2:** \( -(0) + 2(0) - 1 = -1 \) âœ“

**Equation 3:** \( 0(0) - 3(0) + 4(1) = 4 \) âœ“

---

### Solution Method 3: Matrix Form

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

#### Matrix Multiplication Check

\[
\begin{bmatrix}
2x - y + 0z \\
-x + 2y - z \\
0x - 3y + 4z
\end{bmatrix}
=
\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
\]

**With \( x = 0, y = 0, z = 1 \):**

\[
\begin{bmatrix}
2(0) - 0 + 0(1) \\
-(0) + 2(0) - 1 \\
0(0) - 3(0) + 4(1)
\end{bmatrix}
=
\begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix} \quad âœ“
\]

**Solution:** \( \mathbf{x} = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} \)

---

## Example 3: Alternative Right-Hand Side

### Modified System

**Same matrix \( A \), different \( \mathbf{b} \):**

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

---

### Column Picture Analysis

#### Step 1: Observe New \( \mathbf{b} \)

\[
\mathbf{b}_{\text{new}} = \begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}
\]

**Check if it's a combination of columns:**

\[
\mathbf{c}_1 + \mathbf{c}_2 = \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix} + \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix} = \begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix}
\]

**Perfect match!** \( \mathbf{b}_{\text{new}} = \mathbf{c}_1 + \mathbf{c}_2 \)

#### Step 2: Solution

\[
x\mathbf{c}_1 + y\mathbf{c}_2 + z\mathbf{c}_3 = \mathbf{c}_1 + \mathbf{c}_2
\]

**Therefore:** \( x = 1, y = 1, z = 0 \)

#### Step 3: Verify

\[
1 \cdot \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix} + 1 \cdot \begin{bmatrix} -1 \\ 2 \\ -3 \end{bmatrix} + 0 \cdot \begin{bmatrix} 0 \\ -1 \\ 4 \end{bmatrix}
\]

**Component-wise:**
- First: \( 2 + (-1) + 0 = 1 \) âœ“
- Second: \( -1 + 2 + 0 = 1 \) âœ“
- Third: \( 0 + (-3) + 0 = -3 \) âœ“

\[
= \begin{bmatrix} 1 \\ 1 \\ -3 \end{bmatrix} \quad âœ“
\]

#### Step 4: Verify in Original System

**Equation 1:** \( 2(1) - 1 + 0(0) = 2 - 1 = 1 \) âœ“

**Equation 2:** \( -(1) + 2(1) - 0 = -1 + 2 = 1 \) âœ“

**Equation 3:** \( 0(1) - 3(1) + 4(0) = -3 \) âœ“

**Solution:** \( \mathbf{x} = \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix} \)

---

## Linear Combinations - Deep Dive

### Definition

Given vectors \( \mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n \) and scalars \( c_1, c_2, \ldots, c_n \):

\[
\text{Linear Combination} = c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n
\]

**Properties:**
- Result is a vector in the same space
- \( c_i \) can be any real number (positive, negative, zero)
- Order doesn't matter (commutative)

---

### Example Calculations

#### Example A: 2D Vectors

\[
\mathbf{v}_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}, \quad \mathbf{v}_2 = \begin{bmatrix} 3 \\ 1 \end{bmatrix}
\]

**Linear combination:** \( 2\mathbf{v}_1 + 3\mathbf{v}_2 \)

\[
2\begin{bmatrix} 1 \\ 2 \end{bmatrix} + 3\begin{bmatrix} 3 \\ 1 \end{bmatrix} = \begin{bmatrix} 2 \\ 4 \end{bmatrix} + \begin{bmatrix} 9 \\ 3 \end{bmatrix} = \begin{bmatrix} 11 \\ 7 \end{bmatrix}
\]

#### Example B: 3D Vectors

\[
\mathbf{u}_1 = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \quad \mathbf{u}_2 = \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \quad \mathbf{u}_3 = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}
\]

**Linear combination:** \( 5\mathbf{u}_1 - 2\mathbf{u}_2 + 3\mathbf{u}_3 \)

\[
5\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} - 2\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} + 3\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} = \begin{bmatrix} 5 \\ -2 \\ 3 \end{bmatrix}
\]

**Note:** These are **standard basis vectors** (\( \mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3 \))

---

### Span - All Possible Combinations

**Definition:** The **span** of vectors \( \{\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n\} \) is the set of ALL possible linear combinations:

\[
\text{span}\{\mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n\} = \{c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n \mid c_i \in \mathbb{R}\}
\]

#### Cases in 2D

**Case 1:** Two independent vectors
\[
\mathbf{v}_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}, \quad \mathbf{v}_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix}
\]
- Span: All of \( \mathbb{R}^2 \) (entire plane)

**Case 2:** Two dependent vectors (one is multiple of other)
\[
\mathbf{v}_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}, \quad \mathbf{v}_2 = \begin{bmatrix} 2 \\ 4 \end{bmatrix} = 2\mathbf{v}_1
\]
- Span: A line through origin (1D subspace)

**Case 3:** Single vector
\[
\mathbf{v}_1 = \begin{bmatrix} 3 \\ 1 \end{bmatrix}
\]
- Span: Line in direction of \( \mathbf{v}_1 \)

---

#### Cases in 3D

**Case 1:** Three independent vectors
- Span: All of \( \mathbb{R}^3 \) (entire 3D space)

**Case 2:** Two independent vectors (third is combination)
- Span: A plane through origin (2D subspace)

**Case 3:** One vector (others are multiples)
- Span: A line through origin (1D subspace)

**Case 4:** Zero vector only
- Span: Just the origin {\( \mathbf{0} \)}

---

## Matrix-Vector Multiplication - Complete Methods

### Method 1: Linear Combination of Columns â­

**Formula:**
\[
A\mathbf{x} = \begin{bmatrix} | & | & & | \\ \mathbf{a}_1 & \mathbf{a}_2 & \cdots & \mathbf{a}_n \\ | & | & & | \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} = x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n
\]

**Key Insight:** Matrix times vector = weighted sum of columns

#### Example

\[
\begin{bmatrix} 2 & 5 \\ 1 & 3 \end{bmatrix} \begin{bmatrix} 1 \\ 2 \end{bmatrix}
\]

**Column 1:** \( \mathbf{a}_1 = \begin{bmatrix} 2 \\ 1 \end{bmatrix} \)

**Column 2:** \( \mathbf{a}_2 = \begin{bmatrix} 5 \\ 3 \end{bmatrix} \)

**Calculation:**
\[
1 \cdot \begin{bmatrix} 2 \\ 1 \end{bmatrix} + 2 \cdot \begin{bmatrix} 5 \\ 3 \end{bmatrix} = \begin{bmatrix} 2 \\ 1 \end{bmatrix} + \begin{bmatrix} 10 \\ 6 \end{bmatrix} = \begin{bmatrix} 12 \\ 7 \end{bmatrix}
\]

---

### Method 2: Dot Product of Rows

**Formula:**
\[
A\mathbf{x} = \begin{bmatrix} â€” & \mathbf{r}_1^T & â€” \\ â€” & \mathbf{r}_2^T & â€” \\ & \vdots & \\ â€” & \mathbf{r}_m^T & â€” \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} = \begin{bmatrix} \mathbf{r}_1^T \cdot \mathbf{x} \\ \mathbf{r}_2^T \cdot \mathbf{x} \\ \vdots \\ \mathbf{r}_m^T \cdot \mathbf{x} \end{bmatrix}
\]

**Dot Product Formula:**
\[
\mathbf{r}_i^T \cdot \mathbf{x} = r_{i1}x_1 + r_{i2}x_2 + \cdots + r_{in}x_n
\]

#### Same Example

\[
\begin{bmatrix} 2 & 5 \\ 1 & 3 \end{bmatrix} \begin{bmatrix} 1 \\ 2 \end{bmatrix}
\]

**Row 1:** \( \mathbf{r}_1^T = \begin{bmatrix} 2 & 5 \end{bmatrix} \)

**Row 2:** \( \mathbf{r}_2^T = \begin{bmatrix} 1 & 3 \end{bmatrix} \)

**Calculation:**
\[
\begin{bmatrix}
\mathbf{r}_1^T \cdot \mathbf{x} \\
\mathbf{r}_2^T \cdot \mathbf{x}
\end{bmatrix}
=
\begin{bmatrix}
2(1) + 5(2) \\
1(1) + 3(2)
\end{bmatrix}
=
\begin{bmatrix}
2 + 10 \\
1 + 6
\end{bmatrix}
=
\begin{bmatrix} 12 \\ 7 \end{bmatrix}
\]

---

### Method 3: Component-by-Component

**General Formula:**
\[
(A\mathbf{x})_i = \sum_{j=1}^{n} a_{ij}x_j
\]

**Meaning:** The \( i \)-th component of result is:
\[
(A\mathbf{x})_i = a_{i1}x_1 + a_{i2}x_2 + \cdots + a_{in}x_n
\]

---

### Complete Example: 3Ã—3 System

\[
\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{bmatrix}
\begin{bmatrix} 2 \\ 1 \\ -1 \end{bmatrix}
\]

#### Using Column Method

\[
2\begin{bmatrix} 1 \\ 4 \\ 7 \end{bmatrix} + 1\begin{bmatrix} 2 \\ 5 \\ 8 \end{bmatrix} + (-1)\begin{bmatrix} 3 \\ 6 \\ 9 \end{bmatrix}
\]

\[
= \begin{bmatrix} 2 \\ 8 \\ 14 \end{bmatrix} + \begin{bmatrix} 2 \\ 5 \\ 8 \end{bmatrix} + \begin{bmatrix} -3 \\ -6 \\ -9 \end{bmatrix} = \begin{bmatrix} 1 \\ 7 \\ 13 \end{bmatrix}
\]

#### Using Row Method

**First component:**
\[
1(2) + 2(1) + 3(-1) = 2 + 2 - 3 = 1
\]

**Second component:**
\[
4(2) + 5(1) + 6(-1) = 8 + 5 - 6 = 7
\]

**Third component:**
\[
7(2) + 8(1) + 9(-1) = 14 + 8 - 9 = 13
\]

**Result:** \( \begin{bmatrix} 1 \\ 7 \\ 13 \end{bmatrix} \)

---

## Solvability Theory

### The Fundamental Question

**Can we solve \( A\mathbf{x} = \mathbf{b} \) for EVERY possible \( \mathbf{b} \)?**

**Equivalent Questions:**
1. Do the columns of \( A \) span the entire space?
2. Are the columns linearly independent?
3. Is \( A \) invertible (non-singular)?
4. Is \( \det(A) \neq 0 \)?

---

### Linear Independence

**Definition:** Vectors \( \mathbf{v}_1, \mathbf{v}_2, \ldots, \mathbf{v}_n \) are **linearly independent** if:

\[
c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n = \mathbf{0} \implies c_1 = c_2 = \cdots = c_n = 0
\]

**Meaning:** The ONLY way to get zero vector is with all zero coefficients.

**Linear Dependence:** If we can write:
\[
\mathbf{v}_3 = c_1\mathbf{v}_1 + c_2\mathbf{v}_2
\]
then \( \mathbf{v}_3 \) adds **nothing new** to the span.

---

### Test for Independence (2D)

**Two vectors in 2D:**
\[
\mathbf{v}_1 = \begin{bmatrix} a \\ b \end{bmatrix}, \quad \mathbf{v}_2 = \begin{bmatrix} c \\ d \end{bmatrix}
\]

**Independent if and only if:**
\[
\det\begin{bmatrix} a & c \\ b & d \end{bmatrix} = ad - bc \neq 0
\]

**Geometric Test:** Not parallel (not scalar multiples)

---

### Test for Independence (3D)

**Three vectors in 3D:**

**Matrix form:**
\[
A = \begin{bmatrix} | & | & | \\ \mathbf{v}_1 & \mathbf{v}_2 & \mathbf{v}_3 \\ | & | & | \end{bmatrix}
\]

**Independent if and only if:**
\[
\det(A) \neq 0
\]

**Geometric Test:** Not coplanar (don't all lie in same plane)

---

### Singular vs Non-Singular Matrices

#### Non-Singular (Good!) Matrix

**Properties:**
- Columns are linearly independent
- Rows are linearly independent
- \( \det(A) \neq 0 \)
- Full rank: \( \text{rank}(A) = n \)
- Invertible: \( A^{-1} \) exists
- Solution exists for EVERY \( \mathbf{b} \)
- Unique solution: \( \mathbf{x} = A^{-1}\mathbf{b} \)

**Example (2Ã—2):**
\[
A = \begin{bmatrix} 2 & -1 \\ -1 & 2 \end{bmatrix}
\]
\[
\det(A) = 2(2) - (-1)(-1) = 4 - 1 = 3 \neq 0 \quad âœ“
\]

---

#### Singular (Problematic) Matrix

**Properties:**
- Columns are linearly dependent
- \( \det(A) = 0 \)
- Deficient rank: \( \text{rank}(A) < n \)
- NOT invertible
- Solution may not exist for some \( \mathbf{b} \)
- If solution exists, infinitely many solutions

**Example (2Ã—2):**
\[
A = \begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix}
\]

Column 2 = 2 Ã— Column 1 (dependent!)

\[
\det(A) = 1(4) - 2(2) = 4 - 4 = 0 \quad \text{(Singular!)}
\]

**Span:** All combinations lie on line \( y = 2x \) (not full plane)

**Solvable only if:** \( \mathbf{b} \) is on this line

---

### Example: When is There No Solution?

**System:**
\[
\begin{bmatrix} 1 & 2 \\ 2 & 4 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 3 \\ 7 \end{bmatrix}
\]

**Analysis:**
\[
x\begin{bmatrix} 1 \\ 2 \end{bmatrix} + y\begin{bmatrix} 2 \\ 4 \end{bmatrix} = \begin{bmatrix} 3 \\ 7 \end{bmatrix}
\]

**Both columns lie on line \( y = 2x \):**
- All combinations: \( (x + 2y, 2x + 4y) = (x + 2y, 2(x + 2y)) \)
- Must satisfy: second component = 2 Ã— first component

**Check \( \mathbf{b} \):** Is \( 7 = 2 \times 3 \)? NO! (\( 7 \neq 6 \))

**Conclusion:** NO SOLUTION exists

---

### Example: Singular 3Ã—3 Matrix

\[
A = \begin{bmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 1
\end{bmatrix}
\]

**Row 2 = 2 Ã— Row 1** (dependent!)

**Determinant:**
\[
\det(A) = 1(4 \cdot 1 - 6 \cdot 1) - 2(2 \cdot 1 - 6 \cdot 0) + 3(2 \cdot 1 - 4 \cdot 0)
\]
\[
= 1(4 - 6) - 2(2 - 0) + 3(2 - 0) = -2 - 4 + 6 = 0
\]

**Span:** All combinations lie in a 2D plane in 3D space

---

## Geometric Interpretation in n-Dimensions

### Extending to Higher Dimensions

**n equations, n unknowns:**

\[
A\mathbf{x} = \mathbf{b}, \quad A \in \mathbb{R}^{n \times n}, \quad \mathbf{x}, \mathbf{b} \in \mathbb{R}^n
\]

---

### Row Picture in nD

**Each equation:** Hyperplane in \( n \)-dimensional space
- Hyperplane: \( (n-1) \)-dimensional object

**Examples:**
- 2D: Hyperplane = line (1D in 2D space)
- 3D: Hyperplane = plane (2D in 3D space)
- 4D: Hyperplane = 3D space in 4D
- nD: Hyperplane = \( (n-1) \)-D in \( n \)-D space

**Solution:** Point where all \( n \) hyperplanes intersect

**Challenge:** Impossible to visualize for \( n > 3 \)

---

### Column Picture in nD â­

**Much more tractable!**

\[
x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n = \mathbf{b}
\]

**Each column:** \( n \)-dimensional vector

**Question:** Can we combine these \( n \) vectors to reach \( \mathbf{b} \)?

**Key Insight:** Think abstractly about linear combinations, not geometry

---

### Example: 9D System

**System:** 9 equations, 9 unknowns

\[
A \in \mathbb{R}^{9 \times 9}, \quad \mathbf{x}, \mathbf{b} \in \mathbb{R}^9
\]

**Column Picture:**
- 9 vectors in 9-dimensional space
- Each vector has 9 components
- Find combination to reach \( \mathbf{b} \)

**Non-singular case:**
- 9 independent vectors
- Span: All of \( \mathbb{R}^9 \)
- Can reach ANY \( \mathbf{b} \in \mathbb{R}^9 \)

**Singular case (e.g., column 9 = column 8):**
- Only 8 independent vectors
- Span: 8-dimensional "hyperplane" in 9D
- Can only reach \( \mathbf{b} \) in this hyperplane

---

### Random Matrices

**Fact:** A random \( n \times n \) matrix is non-singular with probability 1

**MATLAB Example:**
```matlab
A = rand(9, 9);  % Generate random 9Ã—9 matrix
det(A)           % Almost certainly non-zero
```

**Why?** The set of singular matrices has "measure zero" (infinitely small probability)

---

## Practice Problems

### Problem 1: 2Ã—2 System

Solve:
\[
\begin{cases}
3x + 2y = 7 \\
x - y = 1
\end{cases}
\]

**Solution:**

**Method 1 - Substitution:**

From Eq 2: \( x = y + 1 \)

Substitute into Eq 1:
\[
3(y + 1) + 2y = 7
\]
\[
3y + 3 + 2y = 7 \implies 5y = 4 \implies y = \frac{4}{5}
\]

\[
x = \frac{4}{5} + 1 = \frac{9}{5}
\]

**Answer:** \( \left(\frac{9}{5}, \frac{4}{5}\right) \) or \( (1.8, 0.8) \)

**Verification:**
- \( 3(1.8) + 2(0.8) = 5.4 + 1.6 = 7 \) âœ“
- \( 1.8 - 0.8 = 1 \) âœ“

---

### Problem 2: Column Picture

Express as linear combination and solve:
\[
\begin{bmatrix} 1 & 3 \\ 2 & 7 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 5 \\ 11 \end{bmatrix}
\]

**Solution:**

\[
x\begin{bmatrix} 1 \\ 2 \end{bmatrix} + y\begin{bmatrix} 3 \\ 7 \end{bmatrix} = \begin{bmatrix} 5 \\ 11 \end{bmatrix}
\]

**System:**
- \( x + 3y = 5 \)
- \( 2x + 7y = 11 \)

From Eq 1: \( x = 5 - 3y \)

Into Eq 2:
\[
2(5 - 3y) + 7y = 11 \implies 10 - 6y + 7y = 11 \implies y = 1
\]

\[
x = 5 - 3(1) = 2
\]

**Answer:** \( \mathbf{x} = \begin{bmatrix} 2 \\ 1 \end{bmatrix} \)

---

### Problem 3: Check Singularity

Is this matrix singular?
\[
A = \begin{bmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 1 & 1 & 1 \end{bmatrix}
\]

**Solution:**

**Check columns:**
- Column 2 = 2 Ã— Column 1
- Column 3 = 3 Ã— Column 1

**Columns are dependent!**

**Check determinant:**
\[
\det(A) = 1(4 \cdot 1 - 6 \cdot 1) - 2(2 \cdot 1 - 6 \cdot 1) + 3(2 \cdot 1 - 4 \cdot 1)
\]
\[
= 1(-2) - 2(-4) + 3(-2) = -2 + 8 - 6 = 0
\]

**Answer:** YES, matrix is singular (\( \det(A) = 0 \))

---

### Problem 4: Span Question

Do these vectors span \( \mathbb{R}^3 \)?
\[
\mathbf{v}_1 = \begin{bmatrix} 1 \\ 0 \\ 1 \end{bmatrix}, \quad \mathbf{v}_2 = \begin{bmatrix} 0 \\ 1 \\ 1 \end{bmatrix}, \quad \mathbf{v}_3 = \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix}
\]

**Solution:**

**Matrix form:**
\[
A = \begin{bmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
1 & 1 & 0
\end{bmatrix}
\]

**Calculate determinant:**
\[
\det(A) = 1(1 \cdot 0 - 1 \cdot 1) - 0 + 1(0 \cdot 1 - 1 \cdot 1)
\]
\[
= 1(-1) + 1(-1) = -2 \neq 0
\]

**Answer:** YES, they span \( \mathbb{R}^3 \) (independent, \( \det \neq 0 \))

---

## Key Formulas Reference

### System Representation

\[
A\mathbf{x} = \mathbf{b}
\]

\[
\begin{bmatrix}
a_{11} & \cdots & a_{1n} \\
\vdots & \ddots & \vdots \\
a_{n1} & \cdots & a_{nn}
\end{bmatrix}
\begin{bmatrix}
x_1 \\ \vdots \\ x_n
\end{bmatrix}
=
\begin{bmatrix}
b_1 \\ \vdots \\ b_n
\end{bmatrix}
\]

---

### Linear Combination

\[
c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + \cdots + c_n\mathbf{v}_n
\]

---

### Matrix-Vector Multiplication

**Column view:**
\[
A\mathbf{x} = x_1\mathbf{a}_1 + x_2\mathbf{a}_2 + \cdots + x_n\mathbf{a}_n
\]

**Row view:**
\[
(A\mathbf{x})_i = \sum_{j=1}^{n} a_{ij}x_j = a_{i1}x_1 + a_{i2}x_2 + \cdots + a_{in}x_n
\]

---

### Determinant (2Ã—2)

\[
\det\begin{bmatrix} a & b \\ c & d \end{bmatrix} = ad - bc
\]

---

### Determinant (3Ã—3) - Cofactor Expansion

\[
\det\begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix} = a(ei - fh) - b(di - fg) + c(dh - eg)
\]

---

### Linear Independence

Vectors \( \mathbf{v}_1, \ldots, \mathbf{v}_n \) are independent if:
\[
c_1\mathbf{v}_1 + \cdots + c_n\mathbf{v}_n = \mathbf{0} \implies c_1 = \cdots = c_n = 0
\]

---

### Solvability Conditions

**For square matrix \( A \), these are equivalent:**

1. \( A\mathbf{x} = \mathbf{b} \) has unique solution for every \( \mathbf{b} \)
2. Columns of \( A \) are linearly independent
3. Columns of \( A \) span \( \mathbb{R}^n \)
4. \( \det(A) \neq 0 \)
5. \( A \) is invertible (non-singular)
6. \( \text{rank}(A) = n \)

---

## Summary

### What We Learned

1. **Three perspectives** on linear systems provide complementary insights
   - Row picture: Geometric objects (lines, planes, hyperplanes)
   - Column picture: Linear combinations of vectors â­
   - Matrix form: Compact algebraic notation

2. **Linear combinations** are the foundation of linear algebra
   - Matrix-vector multiplication produces linear combination
   - Solution means finding right coefficients

3. **Solvability** depends on column independence
   - Independent columns â†’ span full space â†’ solution for all \( \mathbf{b} \)
   - Dependent columns â†’ span subspace â†’ some \( \mathbf{b} \) unreachable

4. **Column picture scales better** to higher dimensions

### Next Lecture

**Elimination:** Systematic algorithm to solve \( A\mathbf{x} = \mathbf{b} \)
- Gaussian elimination
- Forward elimination and back substitution
- Finding pivots
- When elimination fails (singular cases)

---

## Additional Resources

- **MIT OpenCourseWare:** [ocw.mit.edu/18-06S05](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2005/)
- **Course Website:** [web.mit.edu/18.06](http://web.mit.edu/18.06)
- **Video Lectures:** [YouTube Playlist](https://www.youtube.com/playlist?list=PLE7DDD91010BC51F8)
- **Textbook:** Introduction to Linear Algebra (Strang)

---

**License:** Creative Commons BY-NC-SA  
**Course:** MIT OpenCourseWare  

---

*Complete notes with solutions compiled from MIT 18.06 Linear Algebra Lecture 1*  
*Professor Gilbert Strang, Spring 2005*  
*For educational purposes - part of personal study repository*