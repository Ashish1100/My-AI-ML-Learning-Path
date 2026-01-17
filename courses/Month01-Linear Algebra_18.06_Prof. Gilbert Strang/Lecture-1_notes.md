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
- [Fundamental Problem](#fundamental-problem-of-linear-algebra)
- [Three Perspectives](#three-perspectives-on-linear-systems)
- [Example 1: 2Ã—2 System](#example-1-2Ã—2-system---complete-solution)
- [Example 2: 3Ã—3 System](#example-2-3Ã—3-system---complete-solution)
- [Example 3: Alternative RHS](#example-3-alternative-right-hand-side)
- [Linear Combinations](#linear-combinations---deep-dive)
- [Matrix-Vector Multiplication](#matrix-vector-multiplication---complete-methods)
- [Solvability Theory](#solvability-theory)
- [n-Dimensions](#geometric-interpretation-in-n-dimensions)
- [Practice Problems](#practice-problems)
- [Formulas Reference](#key-formulas-reference)

---

## Course Introduction

### Course Fundamentals
**Goal:** Understand and solve systems of linear equations using matrix algebra

**Standard Form:** Given n equations with n unknowns:

| Equation | Form |
|----------|------|
| System | aâ‚â‚xâ‚ + aâ‚â‚‚xâ‚‚ + â‹¯ + aâ‚â‚™xâ‚™ = bâ‚ |
| | aâ‚‚â‚xâ‚ + aâ‚‚â‚‚xâ‚‚ + â‹¯ + aâ‚‚â‚™xâ‚™ = bâ‚‚ |
| | â‹® |
| | aâ‚™â‚xâ‚ + aâ‚™â‚‚xâ‚‚ + â‹¯ + aâ‚™â‚™xâ‚™ = bâ‚™ |

Where:
- aáµ¢â±¼ = coefficient in row i, column j
- xâ±¼ = j-th unknown variable
- báµ¢ = i-th right-hand side value

---

## Fundamental Problem of Linear Algebra

### Problem Statement

**Given:** Coefficient matrix A and right-hand side vector **b**

**Find:** Solution vector **x** such that A**x** = **b**

### Matrix Equation Form

Matrix form: A**x** = **b**

Where:
- A is n Ã— n (coefficient matrix)
- **x** is n Ã— 1 (unknown vector)
- **b** is n Ã— 1 (right-hand side vector)

**Component Form:**
```
A = [aâ‚â‚  aâ‚â‚‚  ...  aâ‚â‚™]     x = [xâ‚]     b = [bâ‚]
    [aâ‚‚â‚  aâ‚‚â‚‚  ...  aâ‚‚â‚™]         [xâ‚‚]         [bâ‚‚]
    [...  ...  ...  ...]         [â‹®]          [â‹®]
    [aâ‚™â‚  aâ‚™â‚‚  ...  aâ‚™â‚™]         [xâ‚™]         [bâ‚™]
```

---

## Three Perspectives on Linear Systems

### 1. Row Picture (Equation-by-Equation View)

**Concept:** Each equation defines a geometric object; solution is the intersection.

**Geometric Objects by Dimension:**
- **1D:** Point
- **2D:** Line (equation: ax + by = c)
- **3D:** Plane (equation: ax + by + cz = d)
- **nD:** Hyperplane (n-1 dimensional object in n-space)

**General Line Equation (2D):**
```
ax + by = c
```

**Properties:**
- If c = 0: Line passes through origin
- If c â‰  0: Line does NOT pass through origin
- Slope-intercept form: y = -(a/b)x + (c/b)

---

### 2. Column Picture â­ (Linear Combination View) - MOST IMPORTANT

**Concept:** Find scalar multipliers for column vectors to produce **b**

**Mathematical Form:**

We write:
```
xÂ·[aâ‚â‚]   +  yÂ·[aâ‚â‚‚]   +  ...  +  zÂ·[aâ‚â‚™]   =  [bâ‚]
  [aâ‚‚â‚]        [aâ‚‚â‚‚]              [aâ‚‚â‚™]        [bâ‚‚]
  [...]        [...]              [...]        [...]
  [aâ‚™â‚]        [aâ‚™â‚‚]              [aâ‚™â‚™]        [bâ‚™]
```

**Compact Notation:** xÂ·**a**â‚ + yÂ·**a**â‚‚ + â‹¯ + zÂ·**aâ‚™** = **b**

where **aâ±¼** is the j-th column of A.

---

### 3. Matrix Form (Compact Algebraic Representation)

**Equation:** A**x** = **b**

**Augmented Matrix:**
```
[aâ‚â‚  aâ‚â‚‚  ...  aâ‚â‚™ | bâ‚]
[aâ‚‚â‚  aâ‚‚â‚‚  ...  aâ‚‚â‚™ | bâ‚‚]
[...  ...  ...  ... | ...]
[aâ‚™â‚  aâ‚™â‚‚  ...  aâ‚™â‚™ | bâ‚™]
```

---

## Example 1: 2Ã—2 System - Complete Solution

### System Definition

```
2x - y = 0        (Equation 1)
-x + 2y = 3       (Equation 2)
```

### Solution Method 1: Row Picture (Geometric)

#### Step 1: Plot Equation 1 (2x - y = 0)

**Rearrange to slope-intercept form:**
```
y = 2x
```

**Properties:**
- Slope: m = 2
- y-intercept: 0 (passes through origin)

**Find points:**
- When x = 0: y = 0 â†’ Point: (0, 0)
- When x = 1: y = 2 â†’ Point: (1, 2) âœ“
- When x = 2: y = 4 â†’ Point: (2, 4) âœ“

#### Step 2: Plot Equation 2 (-x + 2y = 3)

**Rearrange to slope-intercept form:**
```
2y = x + 3
y = (1/2)x + 3/2
```

**Properties:**
- Slope: m = 1/2
- y-intercept: 3/2 = 1.5

**Find points:**
- When x = 0: y = 1.5 â†’ Point: (0, 1.5)
- When x = -3: y = 0 â†’ Point: (-3, 0)
- When x = 1: y = 2 â†’ Point: (1, 2) âœ“

#### Step 3: Find Intersection

**Solution:** (x, y) = (1, 2)

**Verify in both equations:**
- Eq 1: 2(1) - 2 = 0 âœ“
- Eq 2: -(1) + 2(2) = 3 âœ“

---

### Solution Method 2: Column Picture

#### Step 1: Write as Linear Combination

```
xÂ·[2]  + yÂ·[-1]  = [0]
  [-1]     [2]     [3]
```

**Notation:**
- Column 1: **c**â‚ = [2, -1]áµ€
- Column 2: **c**â‚‚ = [-1, 2]áµ€
- Right-hand side: **b** = [0, 3]áµ€

#### Step 2: Try Solution x = 1, y = 2

**Calculate:**
```
1 Ã— [2]   +  2 Ã— [-1]   =  [2]   +  [-2]   =  [0]  âœ“
    [-1]         [2]        [-1]      [4]       [3]  âœ“
```

**Component check:**
- First component: 1(2) + 2(-1) = 2 - 2 = 0 âœ“
- Second component: 1(-1) + 2(2) = -1 + 4 = 3 âœ“

---

### Solution Method 3: Matrix Form

**Matrix equation:**
```
[2   -1] [x]   [0]
[-1   2] [y] = [3]
```

#### Algebraic Solution

From Equation 1: y = 2x

Substitute into Equation 2:
```
-x + 2(2x) = 3
-x + 4x = 3
3x = 3
x = 1
```

Back-substitute:
```
y = 2(1) = 2
```

**Solution:** **x** = [1, 2]áµ€

---

### All Possible Right-Hand Sides

**Question:** Can we solve for ANY **b** = [bâ‚, bâ‚‚]áµ€?

**Answer:** YES! The columns are linearly independent.

**Span:** All linear combinations fill the entire 2D plane.

**Matrix Properties:**
- Non-singular (invertible)
- Full rank (rank = 2)
- Determinant: det(A) = 2(2) - (-1)(-1) = 4 - 1 = 3 â‰  0 âœ“

---

## Example 2: 3Ã—3 System - Complete Solution

### System Definition

```
2x - y + 0z = 0       (Equation 1)
-x + 2y - z = -1      (Equation 2)
0x - 3y + 4z = 4      (Equation 3)
```

### Solution Method 1: Row Picture (3D Planes)

**Equation 1: 2x - y = 0**
- z can be any value (vertical plane)
- Points: (0,0,0), (1,2,0), (1,2,5) âœ“

**Equation 2: -x + 2y - z = -1**
- General plane (all variables)
- Points: (1,0,0), (0,0,1), (1,1,2) âœ“

**Equation 3: -3y + 4z = 4**
- x can be any value (vertical plane)
- Points: (any,0,1), (any,4,4) âœ“

**Intersection:** Three planes meet at (x, y, z) = (0, 0, 1)

---

### Solution Method 2: Column Picture â­

#### Step 1: Express as Linear Combination

```
xÂ·[2]   + yÂ·[-1]  + zÂ·[0]   = [0]
  [-1]     [2]       [-1]     [-1]
  [0]      [-3]      [4]      [4]
```

**Notation:**
- **c**â‚ = [2, -1, 0]áµ€ (Column 1)
- **c**â‚‚ = [-1, 2, -3]áµ€ (Column 2)
- **c**â‚ƒ = [0, -1, 4]áµ€ (Column 3)
- **b** = [0, -1, 4]áµ€ (Right-hand side)

#### Step 2: KEY OBSERVATION

**The right-hand side equals Column 3!**

**b** = **c**â‚ƒ

Therefore: x = 0, y = 0, z = 1

#### Step 3: Verify Solution

```
0Â·[2]   + 0Â·[-1]  + 1Â·[0]   = [0]  âœ“
  [-1]     [2]       [-1]     [-1]
  [0]      [-3]      [4]      [4]
```

Verify in original equations:
- Equation 1: 2(0) - 0 + 0(1) = 0 âœ“
- Equation 2: -(0) + 2(0) - 1 = -1 âœ“
- Equation 3: 0(0) - 3(0) + 4(1) = 4 âœ“

**Solution:** **x** = [0, 0, 1]áµ€

---

## Example 3: Alternative Right-Hand Side

### Modified System

Same matrix A, different **b**:

```
[2   -1   0] [x]   [1]
[-1   2  -1] [y] = [1]
[0   -3   4] [z]   [-3]
```

### Column Picture Analysis

#### Step 1: Observe New b

**b**_new = [1, 1, -3]áµ€

Check if it's a combination of columns:
```
[2]    [-1]    [2-1]    [1]
[-1] + [2]  =  [-1+2] = [1]  âœ“
[0]    [-3]    [0-3]    [-3]
```

**Perfect match!** **b**_new = **c**â‚ + **c**â‚‚

#### Step 2: Solution

xÂ·**c**â‚ + yÂ·**c**â‚‚ + zÂ·**c**â‚ƒ = **c**â‚ + **c**â‚‚

**Therefore:** x = 1, y = 1, z = 0

#### Step 3: Verify

```
1Â·[2]    + 1Â·[-1]   + 0Â·[0]    = [1]  âœ“
  [-1]      [2]         [-1]     [1]
  [0]       [-3]        [4]      [-3]
```

Verify in original system:
- Equation 1: 2(1) - 1 + 0 = 1 âœ“
- Equation 2: -(1) + 2(1) - 0 = 1 âœ“
- Equation 3: 0(1) - 3(1) + 4(0) = -3 âœ“

**Solution:** **x** = [1, 1, 0]áµ€

---

## Linear Combinations - Deep Dive

### Definition

Given vectors **v**â‚, **v**â‚‚, ..., **vâ‚™** and scalars câ‚, câ‚‚, ..., câ‚™:

```
Linear Combination = câ‚Â·vâ‚ + câ‚‚Â·vâ‚‚ + â‹¯ + câ‚™Â·vâ‚™
```

**Properties:**
- Result is a vector in the same space
- cáµ¢ can be any real number (positive, negative, zero)
- Order doesn't matter (commutative)

---

### Example Calculations

#### Example A: 2D Vectors

```
vâ‚ = [1]    vâ‚‚ = [3]
     [2]         [1]
```

**Linear combination: 2vâ‚ + 3vâ‚‚**

```
2Â·[1]  + 3Â·[3]  = [2]  + [9]  = [11]
  [2]      [1]    [4]    [3]    [7]
```

#### Example B: 3D Vectors (Standard Basis)

```
uâ‚ = [1]    uâ‚‚ = [0]    uâ‚ƒ = [0]
     [0]         [1]         [0]
     [0]         [0]         [1]
```

**Linear combination: 5uâ‚ - 2uâ‚‚ + 3uâ‚ƒ**

```
5Â·[1]  - 2Â·[0]  + 3Â·[0]  = [5]
  [0]       [1]       [0]    [-2]
  [0]       [0]       [1]    [3]
```

These are standard basis vectors (eâ‚, eâ‚‚, eâ‚ƒ)

---

### Span - All Possible Combinations

**Definition:** The span of vectors {**v**â‚, **v**â‚‚, ..., **vâ‚™**} is the set of ALL possible linear combinations.

#### Cases in 2D

**Case 1: Two independent vectors**
```
vâ‚ = [1]    vâ‚‚ = [0]
     [0]         [1]
```
Span: All of â„Â² (entire plane)

**Case 2: Two dependent vectors (one is multiple of other)**
```
vâ‚ = [1]    vâ‚‚ = [2]  = 2Â·vâ‚
     [2]         [4]
```
Span: A line through origin (1D subspace)

**Case 3: Single vector**
```
vâ‚ = [3]
     [1]
```
Span: Line in direction of vâ‚

---

#### Cases in 3D

- **Case 1:** Three independent vectors â†’ Span all of â„Â³
- **Case 2:** Two independent vectors â†’ Span a plane through origin
- **Case 3:** One vector â†’ Span a line through origin
- **Case 4:** Zero vector only â†’ Span just the origin {0}

---

## Matrix-Vector Multiplication - Complete Methods

### Method 1: Linear Combination of Columns â­

**Key Insight:** A**x** = weighted sum of columns of A

**Formula:** If A = [**a**â‚ **a**â‚‚ â‹¯ **aâ‚™**], then:

```
A**x** = xâ‚Â·aâ‚ + xâ‚‚Â·aâ‚‚ + â‹¯ + xâ‚™Â·aâ‚™
```

#### Example

```
[2  5] [1]
[1  3] [2]
```

**Column 1:** **a**â‚ = [2, 1]áµ€
**Column 2:** **a**â‚‚ = [5, 3]áµ€

**Calculation:**
```
1Â·[2]  + 2Â·[5]  = [2]   + [10]  = [12]
  [1]       [3]    [1]     [6]     [7]
```

---

### Method 2: Dot Product of Rows

**Formula:** Each component is dot product of a row with **x**

```
(A**x**)áµ¢ = ráµ¢ Â· **x** = aáµ¢â‚xâ‚ + aáµ¢â‚‚xâ‚‚ + â‹¯ + aáµ¢â‚™xâ‚™
```

#### Same Example

**Row 1:** [2 5]
**Row 2:** [1 3]

**Calculation:**
```
Row 1: 2(1) + 5(2) = 2 + 10 = 12
Row 2: 1(1) + 3(2) = 1 + 6 = 7

Result: [12]
        [7]
```

---

### Method 3: Component-by-Component

```
(A**x**)áµ¢ = Î£â±¼ aáµ¢â±¼xâ±¼ = aáµ¢â‚xâ‚ + aáµ¢â‚‚xâ‚‚ + â‹¯ + aáµ¢â‚™xâ‚™
```

---

### Complete Example: 3Ã—3 System

```
[1  2  3] [2]
[4  5  6] [1]
[7  8  9] [-1]
```

**Using Column Method:**
```
2Â·[1]  + 1Â·[2]  + (-1)Â·[3]  = [2]   + [2]   + [-3]   = [1]
  [4]      [5]         [6]      [8]     [5]     [-6]     [7]
  [7]      [8]         [9]      [14]    [8]     [-9]     [13]
```

**Using Row Method:**
- First: 1(2) + 2(1) + 3(-1) = 2 + 2 - 3 = 1
- Second: 4(2) + 5(1) + 6(-1) = 8 + 5 - 6 = 7
- Third: 7(2) + 8(1) + 9(-1) = 14 + 8 - 9 = 13

Result: [1, 7, 13]áµ€

---

## Solvability Theory

### The Fundamental Question

**Can we solve A**x** = **b** for EVERY possible **b**?**

**Equivalent Questions:**
1. Do columns of A span the entire space?
2. Are columns linearly independent?
3. Is A invertible (non-singular)?
4. Is det(A) â‰  0?

---

### Linear Independence

**Definition:** Vectors **v**â‚, **v**â‚‚, ..., **vâ‚™** are linearly independent if:

```
câ‚Â·vâ‚ + câ‚‚Â·vâ‚‚ + â‹¯ + câ‚™Â·vâ‚™ = 0  âŸ¹  câ‚ = câ‚‚ = â‹¯ = câ‚™ = 0
```

**Meaning:** The ONLY way to get zero vector is with all zero coefficients.

**Linear Dependence:** If one vector is a combination of others:
```
vâ‚ƒ = câ‚Â·vâ‚ + câ‚‚Â·vâ‚‚
```
then vâ‚ƒ adds nothing new to the span.

---

### Test for Independence (2D)

**Two vectors in 2D:**
```
vâ‚ = [a]    vâ‚‚ = [c]
     [b]         [d]
```

**Independent if and only if:** det([a c; b d]) = ad - bc â‰  0

**Geometric Test:** Not parallel (not scalar multiples)

---

### Test for Independence (3D)

**Three vectors in 3D:**

Matrix form: A = [**v**â‚ **v**â‚‚ **v**â‚ƒ]

**Independent if and only if:** det(A) â‰  0

**Geometric Test:** Not coplanar (don't all lie in same plane)

---

### Singular vs Non-Singular Matrices

#### Non-Singular (Good!) Matrix

**Properties:**
- Columns linearly independent
- Rows linearly independent
- det(A) â‰  0
- Full rank: rank(A) = n
- Invertible: Aâ»Â¹ exists
- **Solution exists for EVERY b**
- Unique solution: **x** = Aâ»Â¹**b**

**Example (2Ã—2):**
```
A = [2   -1]
    [-1   2]

det(A) = 2(2) - (-1)(-1) = 4 - 1 = 3 â‰  0  âœ“
```

---

#### Singular (Problematic) Matrix

**Properties:**
- Columns linearly dependent
- det(A) = 0
- Deficient rank: rank(A) < n
- NOT invertible
- Solution may NOT exist for some **b**
- If solution exists, infinitely many solutions

**Example (2Ã—2):**
```
A = [1  2]
    [2  4]

Column 2 = 2 Ã— Column 1 (dependent!)

det(A) = 1(4) - 2(2) = 0  (Singular!)
```

Span: All combinations lie on line y = 2x (not full plane)

Solvable only if: **b** is on this line

---

### Example: When is There NO Solution?

**System:**
```
[1  2] [x]   [3]
[2  4] [y] = [7]
```

**Analysis:**
```
xÂ·[1]  + yÂ·[2]  = [3]
  [2]      [4]    [7]
```

Both columns lie on line y = 2x.

All combinations satisfy: second component = 2 Ã— first component

**Check b:** Is 7 = 2 Ã— 3? NO! (7 â‰  6)

**Conclusion:** NO SOLUTION exists

---

### Example: Singular 3Ã—3 Matrix

```
A = [1  2  3]
    [2  4  6]
    [0  1  1]
```

Row 2 = 2 Ã— Row 1 (dependent!)

det(A) = 1(4Â·1 - 6Â·1) - 2(2Â·1 - 6Â·0) + 3(2Â·1 - 4Â·0)
       = 1(-2) - 2(2) + 3(2)
       = -2 - 4 + 6 = 0

Span: All combinations lie in a 2D plane in 3D space

---

## Geometric Interpretation in n-Dimensions

### Extending to Higher Dimensions

**n equations, n unknowns:**

A**x** = **b**, where A âˆˆ â„â¿Ë£â¿, **x**, **b** âˆˆ â„â¿

---

### Row Picture in nD

**Each equation:** Hyperplane in n-dimensional space

Examples:
- 2D: Hyperplane = line (1D in 2D space)
- 3D: Hyperplane = plane (2D in 3D space)
- 4D: Hyperplane = 3D space in 4D
- nD: Hyperplane = (n-1)-D in n-D space

**Solution:** Point where all n hyperplanes intersect

**Challenge:** Impossible to visualize for n > 3

---

### Column Picture in nD â­ (More Practical)

```
xâ‚Â·aâ‚ + xâ‚‚Â·aâ‚‚ + â‹¯ + xâ‚™Â·aâ‚™ = b
```

**Each column:** n-dimensional vector

**Question:** Can we combine these n vectors to reach **b**?

**Key Insight:** Think abstractly about linear combinations, not geometry

---

### Example: 9D System

**System:** 9 equations, 9 unknowns

A âˆˆ â„â¹Ë£â¹, **x**, **b** âˆˆ â„â¹

**Column Picture:**
- 9 vectors in 9-dimensional space
- Each vector has 9 components
- Find combination to reach **b**

**Non-singular case:**
- 9 independent vectors
- Span: All of â„â¹
- Can reach ANY **b** âˆˆ â„â¹

**Singular case (e.g., column 9 = column 8):**
- Only 8 independent vectors
- Span: 8-dimensional "hyperplane" in 9D
- Can only reach **b** in this hyperplane

---

### Random Matrices

**Fact:** A random n Ã— n matrix is non-singular with probability 1

Example in MATLAB:
```matlab
A = rand(9, 9);  % Generate random 9Ã—9 matrix
det(A)           % Almost certainly non-zero
```

**Why?** The set of singular matrices has "measure zero"

---

## Practice Problems

### Problem 1: 2Ã—2 System

**Solve:**
```
3x + 2y = 7
x - y = 1
```

**Solution:**

From Eq 2: x = y + 1

Substitute into Eq 1:
```
3(y + 1) + 2y = 7
3y + 3 + 2y = 7
5y = 4
y = 4/5 = 0.8
```

```
x = 0.8 + 1 = 1.8
```

**Answer:** (1.8, 0.8) or (9/5, 4/5)

**Verification:**
- 3(1.8) + 2(0.8) = 5.4 + 1.6 = 7 âœ“
- 1.8 - 0.8 = 1 âœ“

---

### Problem 2: Column Picture

**Solve:**
```
[1  3] [x]   [5]
[2  7] [y] = [11]
```

**Solution:**

```
xÂ·[1]  + yÂ·[3]  = [5]
  [2]      [7]    [11]
```

System:
```
x + 3y = 5
2x + 7y = 11
```

From Eq 1: x = 5 - 3y

Into Eq 2:
```
2(5 - 3y) + 7y = 11
10 - 6y + 7y = 11
y = 1
```

```
x = 5 - 3(1) = 2
```

**Answer:** **x** = [2, 1]áµ€

---

### Problem 3: Check Singularity

**Is this matrix singular?**
```
A = [1  2  3]
    [2  4  6]
    [1  1  1]
```

**Solution:**

Check columns:
- Column 2 = 2 Ã— Column 1
- Column 3 = 3 Ã— Column 1

Columns are dependent!

det(A) = 1(4Â·1 - 6Â·1) - 2(2Â·1 - 6Â·1) + 3(2Â·1 - 4Â·1)
       = 1(-2) - 2(-4) + 3(-2)
       = -2 + 8 - 6 = 0

**Answer:** YES, matrix is singular (det(A) = 0)

---

### Problem 4: Span Question

**Do these vectors span â„Â³?**
```
vâ‚ = [1]    vâ‚‚ = [0]    vâ‚ƒ = [1]
     [0]         [1]         [1]
     [1]         [1]         [0]
```

**Solution:**

Matrix form:
```
A = [1  0  1]
    [0  1  1]
    [1  1  0]
```

det(A) = 1(1Â·0 - 1Â·1) - 0 + 1(0Â·1 - 1Â·1)
       = 1(-1) + 1(-1)
       = -2 â‰  0

**Answer:** YES, they span â„Â³ (independent, det â‰  0)

---

## Key Formulas Reference

### System Representation

A**x** = **b**

```
[aâ‚â‚  ...  aâ‚â‚™] [xâ‚]   [bâ‚]
[...  ...  ...]  [â‹®]  = [â‹®]
[aâ‚™â‚  ...  aâ‚™â‚™] [xâ‚™]   [bâ‚™]
```

---

### Linear Combination

```
câ‚Â·vâ‚ + câ‚‚Â·vâ‚‚ + â‹¯ + câ‚™Â·vâ‚™
```

---

### Matrix-Vector Multiplication

**Column view:**
```
A**x** = xâ‚Â·aâ‚ + xâ‚‚Â·aâ‚‚ + â‹¯ + xâ‚™Â·aâ‚™
```

**Row view:**
```
(A**x**)áµ¢ = aáµ¢â‚xâ‚ + aáµ¢â‚‚xâ‚‚ + â‹¯ + aáµ¢â‚™xâ‚™
```

---

### Determinant (2Ã—2)

```
det([a  b]) = ad - bc
    [c  d]
```

---

### Determinant (3Ã—3)

```
det([a  b  c])
    [d  e  f] = a(ei - fh) - b(di - fg) + c(dh - eg)
    [g  h  i]
```

---

### Linear Independence

Vectors are independent if:
```
câ‚Â·vâ‚ + â‹¯ + câ‚™Â·vâ‚™ = 0  âŸ¹  câ‚ = â‹¯ = câ‚™ = 0
```

---

### Solvability Conditions

For square matrix A, these are equivalent:

1. A**x** = **b** has unique solution for every **b**
2. Columns of A are linearly independent
3. Columns of A span â„â¿
4. det(A) â‰  0
5. A is invertible (non-singular)
6. rank(A) = n

---

## Summary

### What We Learned

1. **Three perspectives** on linear systems:
   - Row picture: Geometric objects (lines, planes, hyperplanes)
   - Column picture: Linear combinations of vectors â­
   - Matrix form: Compact algebraic notation

2. **Linear combinations** are the foundation
   - Matrix-vector multiplication produces linear combination
   - Solution means finding right coefficients

3. **Solvability** depends on column independence
   - Independent columns â†’ span full space â†’ solution for all **b**
   - Dependent columns â†’ span subspace â†’ some **b** unreachable

4. **Column picture scales** to higher dimensions

---

### Next Lecture

**Elimination:** Systematic algorithm to solve A**x** = **b**
- Gaussian elimination
- Forward elimination and back substitution
- Finding pivots
- When elimination fails (singular cases)

---

## Additional Resources

- **MIT OpenCourseWare:** ocw.mit.edu/18-06S05
- **Course Website:** web.mit.edu/18.06
- **Video Lectures:** YouTube playlist for 18.06
- **Textbook:** Introduction to Linear Algebra (Strang)

---

**License:** Creative Commons BY-NC-SA  
**Course:** MIT OpenCourseWare  
**Instructor:** Professor Gilbert Strang, Spring 2005

---

*Complete notes with solutions compiled from MIT 18.06 Linear Algebra Lecture 1*  
*For educational purposes - part of personal study repository*