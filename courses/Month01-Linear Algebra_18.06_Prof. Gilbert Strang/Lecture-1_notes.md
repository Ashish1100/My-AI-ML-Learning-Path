# Lecture 1: The Geometry of Linear Equations

**Instructor:** Gilbert Strang  
**Course:** MIT 18.06 Linear Algebra  
**Lecture:** 1  
**Topic:** The Geometry of Linear Equations  
**Video:** [Watch on YouTube](https://www.youtube.com/watch?v=ZK3O402wf1c)  
**Course Page:** [web.mit.edu/18.06](http://web.mit.edu/18.06)

---

## Table of Contents
- [Overview](#overview)
- [The Fundamental Problem](#the-fundamental-problem)
- [Three Perspectives on Linear Systems](#three-perspectives-on-linear-systems)
  - [Row Picture](#row-picture)
  - [Column Picture](#column-picture)
  - [Matrix Form](#matrix-form)
- [2x2 System Example](#2x2-system-example)
- [3x3 System Example](#3x3-system-example)
- [Matrix-Vector Multiplication](#matrix-vector-multiplication)
- [Key Concepts](#key-concepts)
- [Questions for Understanding](#questions-for-understanding)

---

## Overview

The fundamental problem of linear algebra is to **solve systems of linear equations**. This lecture introduces three different ways to visualize and understand systems of linear equations:

1. **Row Picture** - One equation at a time (geometric view)
2. **Column Picture** - Linear combinations of column vectors (most important)
3. **Matrix Form** - Compact algebraic representation

We start with n equations and n unknowns (square system).

---

## The Fundamental Problem

Given a system of linear equations, find the values of unknowns that satisfy all equations simultaneously.

**Standard Form:**
```
a₁₁x₁ + a₁₂x₂ + ⋯ + a₁ₙxₙ = b₁  
a₂₁x₁ + a₂₂x₂ + ⋯ + a₂ₙxₙ = b₂  
⋮  
aₙ₁x₁ + aₙ₂x₂ + ⋯ + aₙₙxₙ = bₙ
```
---

## Three Perspectives on Linear Systems

### Row Picture

**Geometric interpretation:** Each equation represents a geometric object
- In 2D: each equation is a **line**
- In 3D: each equation is a **plane**
- In nD: each equation is a **hyperplane**

**Solution:** The point(s) where all geometric objects intersect.

### Column Picture

**Key Concept:** View the system as a **linear combination** of column vectors.

**Linear Combination:** Taking vectors and multiplying each by a scalar, then adding them together.

```
x₁ (column 1) + x₂ (column 2) + ⋯ + xₙ (column n) = b
```

This is the **most fundamental operation** in linear algebra!

**Question to ask:** What combination of the column vectors produces the right-hand side vector b?

### Matrix Form

Compact representation: **Ax = b**

Where:
- **A** = coefficient matrix (m × n)
- **x** = vector of unknowns (n × 1)
- **b** = right-hand side vector (m × 1)

---

## 2x2 System Example

### Problem Setup

```
2x - y = 0
-x + 2y = 3
```

**Coefficient Matrix A:**
```
A = [ 2  -1]
    [-1   2]
```

**Unknown Vector x:**
```
x = [x]
    [y]
```

**Right-hand Side b:**
```
b = [0]
    [3]
```

**Matrix Form:** Ax = b

### Row Picture (2D)

**Equation 1:** 2x - y = 0  
- Passes through origin (0, 0) 
- Another point: (1, 2) 
- This is a **line** through these points  

**Equation 2:** -x + 2y = 3  
- When y = 0: x = -3 → point (-3, 0)  
- When x = -1: y = 1 → point (-1, 1)  
- This is a **line** through these points  

**Solution:** Where the two lines intersect → **(x, y) = (1, 2)**  

**Verification:**  
- Equation 1: 2(1) - 2 = 0 
- Equation 2: -1 + 2(2) = 3

### Column Picture (2D) 

Rewrite as linear combination:
```
x[2 ] + y[-1] = [0]
 [-1]    [2 ]   [3]
```

**Interpretation:** 
- Find scalars x and y such that x times column 1 plus y times column 2 equals b

**Geometric View:**
- Column 1: vector (2, -1)
- Column 2: vector (-1, 2)
- Goal: Combine these to get (0, 3)

**Solution Process:**
1. Take 1 of column 1: (2, -1)
2. Add 2 of column 2: 2(-1, 2) = (-2, 4)
3. Result: (2, -1) + (-2, 4) = (0, 3) 

**Answer:** x = 1, y = 2

**Important Question:** Can we solve for **every** right-hand side b?

**Answer for this 2×2 case:** YES!  
All linear combinations of these two vectors fill the entire 2D plane.

---

## 3x3 System Example

### Problem Setup

```
2x - y     = 0
-x + 2y - z = -1
   - 3y + 4z = 4
```

**Matrix Form:**
```
A = [ 2  -1   0]     x = [x]     b = [ 0]
    [-1   2  -1]         [y]         [-1]
    [ 0  -3   4]         [z]         [ 4]
```

### Row Picture (3D)

**Each equation represents a plane in 3D space**

**Equation 1:** 2x - y = 0
- A plane through origin
- Points: (0,0,0), (1,2,0), (0,0,1)

**Equation 2:** -x + 2y - z = -1
- Another plane
- Points: (1,0,0), (0,-1/2,0), (0,0,1)

**Equation 3:** -3y + 4z = 4
- Third plane
- Points: (0,-4/3,0), (0,0,1), (any x, -4/3, 0)

**Solution:** The single point where all three planes meet

### Column Picture (3D)

```
x[ 2] + y[-1] + z[ 0] = [ 0]
 [-1]    [ 2]    [-1]   [-1]
 [ 0]    [-3]    [ 4]   [ 4]
```

**Geometric View:**
- Three vectors in 3D space
- Find combination that produces b

**Special Case in This Example:**
- Notice b = (0, -1, 4) is exactly column 3!
- Solution: x = 0, y = 0, z = 1

### Alternative Right-hand Side

**New b = (1, 1, -3)** (sum of columns 1 and 2)

Solution becomes: **x = 1, y = 1, z = 0**

This shows: 1(column 1) + 1(column 2) + 0(column 3) = new b

### Big Question: Can We Solve for All b?

**Question:** Do the linear combinations of the three columns fill all of 3D space?

**Answer for this matrix:** YES! This is a **non-singular** (invertible) matrix.

**When would the answer be NO?**
- If all three columns lie in the same plane
- Example: column 3 = column 1 + column 2 (dependent columns)
- Then combinations only fill a **plane**, not all of 3D space
- Such matrices are **singular** (not invertible)

---

## Matrix-Vector Multiplication

**How to multiply a matrix A by a vector x?**

### Example:
```
[2  5] [1]   = ?
[1  3] [2]
```

### Method 1: Linear Combination of Columns (Preferred)

**Think:** 1 × (column 1) + 2 × (column 2)

```
1[2] + 2[5] = [2 + 10] = [12]
 [1]    [3]   [1 + 6 ]   [7 ]
```

**Key Insight:** Ax is a **linear combination of the columns of A**

### Method 2: Dot Product of Rows

**Think:** Each row dots with x

```
Row 1 · x = [2  5] · [1] = 2(1) + 5(2) = 12  
                     [2]  

Row 2 · x = [1  3] · [1] = 1(1) + 3(2) = 7  
                     [2]
```

Result: **[12, 7]**

### General Form

**For Ax = b:**
```
A·x = x₁ (column 1) + x₂ (column 2) + ⋯ + xₙ (column n) = b
```

This is the **fundamental way** to think about matrix-vector multiplication!

---

## Key Concepts

### Linear Combination
The **most fundamental operation** in linear algebra:
```
c₁v₁ + c₂v₂ + ⋯ + cₙvₙ
```
where c₁, c₂, …, cₙ are scalars and v₁, v₂, …, vₙ are vectors.

### Solvability
**Question:** Can we solve Ax = b for every right-hand side b?

**Depends on the columns of A:**
- If columns are **independent**: YES (non-singular, invertible)
- If columns are **dependent**: NO (singular, not invertible)

### Independence vs Dependence

**Independent columns:**
- Do not lie in the same lower-dimensional subspace
- Their combinations fill the entire space
- Matrix is invertible

**Dependent columns:**
- One or more columns can be written as combinations of others
- Their combinations fill only a subspace
- Matrix is singular

### Higher Dimensions (n × n systems)

**9 × 9 Example:**
- 9 equations, 9 unknowns
- 9 columns, each a vector in 9D space
- If columns are independent: combinations fill all of 9D space
- If column 9 = column 8: combinations fill only an 8D "plane" in 9D space

---

### Comparison of Methods

| Aspect | Column Method | Row Method |
|--------|---------------|------------|
| **Viewpoint** | Linear combinations | Dot products |
| **Conceptual** | Modern, preferred by Strang | Traditional |
| **Connects to** | Span, column space | Individual equations |
| **Best for** | Understanding structure | Quick calculation |
| **Generalizes** | Excellently to higher dimensions | Less intuitive in high-D |

**Both methods give the same answer!**

---

## Quick Reference

### Notation
- **A**: m × n matrix (m rows, n columns)
- **x**: n × 1 column vector (unknowns)
- **b**: m × 1 column vector (right-hand side)
- **aᵢ**: i-th column of A
- **rᵢ**: i-th row of A

### Key Formulas

**System of Equations:**  
A·x = b

**Column Picture:**  
x₁a₁ + x₂a₂ + ⋯ + xₙaₙ = b

**Linear Combination:**  
c₁v₁ + c₂v₂ + ⋯ + cₙvₙ

**Span:**  
span{v₁, … , vₙ} = { c₁v₁ + ⋯ + cₙvₙ | cᵢ ∈ ℝ }

**Linear Independence:**  
c₁v₁ + ⋯ + cₙvₙ = 0 ⇒ c₁ = ⋯ = cₙ = 0

**Column Space:**  
C(A) = span{columns of A}

---

### Fundamental Operations

**Linear Combination:**  
c₁v₁ + c₂v₂ + ⋯ + cₙvₙ  
→ Most important operation in linear algebra!

**Matrix-Vector Product:**  
A·x = x₁a₁ + x₂a₂ + ⋯ + xₙaₙ  
→ View as linear combination of columns!

#### 3. Solvability Condition

A·x = b is solvable for all b  
⇔ columns of A are linearly independent

---

### Key Terms

| Term | Meaning |
|------|---------|
| **Linear combination** | Weighted sum of vectors |
| **Span** | All possible linear combinations |
| **Linearly independent** | No vector is a combination of others |
| **Column space** | Span of columns of a matrix |
| **Non-singular** | Invertible, full rank, det ≠ 0 |
| **Singular** | Not invertible, dependent columns |
| **Solvable** | 𝒃 is in the column space |

---

## Higher Dimensions

### 9-Dimensional Example

**System:** 9 equations, 9 unknowns

A·x = b,   A ∈ ℝ⁹ˣ⁹,   x, b ∈ ℝ⁹

**Column Picture:**  
x₁c₁ + x₂c₂ + ⋯ + x₉c₉ = b

where each cᵢ ∈ ℝ⁹ (9-component vectors).

---

### Visualization Challenge

**Can't draw 9D space!** But we can think about it abstractly:

**Good Case (Non-singular):**
- 9 linearly independent vectors in ℝ⁹
- Their combinations **fill all of** ℝ⁹
- Can reach **any** b ∈ ℝ⁹
- Solution exists for **every** right-hand side

**Bad Case (Singular):**
- Example: 9th column = 8th column
- Only 8 independent columns
- Combinations fill an **8-dimensional hyperplane** in ℝ⁹
- Can reach only b in this hyperplane
- Most b values → no solution

---

### Random Matrices

**Fact:** Random n × n matrix is non-singular with probability 1.

**PYTHON Example:**
```python
import numpy as np

A = np.random.rand(9, 9)  # Almost certainly invertible

---

## Important Questions

### Q1: What are the three pictures of linear systems?
- **Row Picture:** Geometric objects (lines, planes, hyperplanes) intersecting
- **Column Picture:** Linear combinations of column vectors
- **Matrix Form:** Ax = b

### Q2: What is a linear combination?
Multiplying vectors by scalars and adding them:
```
c₁v₁ + c₂v₂ + ⋯ + cₙvₙ
```

### Q3: What does Ax represent geometrically?
A **linear combination** of the columns of A, with weights given by components of x.

### Q4: When can we solve Ax = b for all b?
**Equivalent Questions:**
- Do the columns of A span the entire space?
- Are the columns linearly independent?
- Is A invertible (non-singular)?

**Answer:**
- **YES** — If columns are linearly independent  
  → They span the entire space  
  → A is invertible  
  → Unique solution exists for every 𝒃  

- **NO** — If columns are linearly dependent  
  → They do NOT span the space  
  → A is singular  
  → No solution for some 𝒃


### Q5: What makes a matrix singular?
When its columns are **linearly dependent** - some column can be written as a combination of others.

### Q6: Why is the column picture important?
It reveals the **fundamental structure** of linear systems and helps understand:
- When solutions exist
- The span of vectors
- Linear independence
- Vector spaces (coming in future lectures)

### Q7: When is there no solution for some 𝒃?

**Answer:**
There is **no solution** when:

- Columns of A lie in the **same plane** (in 3D)
- All linear combinations stay **inside that plane**
- Any 𝒃 **outside the plane** cannot be reached
- Therefore, system becomes **inconsistent**

**Conclusion:**  
No solution exists for those 𝒃 outside the column space.

---

## Summary

This lecture introduced the **geometric intuition** behind linear systems:

1. **Row picture:** intersecting geometric objects
2. **Column picture:** combinations of column vectors (most important)
3. **Matrix form:** compact Ax = b notation

**Central Question:** What combinations of column vectors can we produce?

---

## Additional Resources

- **Course Textbook:** *Introduction to Linear Algebra* by Gilbert Strang
- **Course Website:** [web.mit.edu/18.06](http://web.mit.edu/18.06)
- **MIT OCW:** [ocw.mit.edu/18-06S05](http://ocw.mit.edu/18-06S05)
- **Video Lecture:** [MIT OpenCourseWare YouTube](https://www.youtube.com/watch?v=ZK3O402wf1c)

---
