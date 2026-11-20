# Linear Algebra for Machine Learning: Lecture-wise Overview (Lectures 2–10)

Topic-wise explanation of every lecture in the series, written in simple language with formulas and small examples. Each lecture has a link to the original video.

---

## Table of Contents

- **[Lecture 2: Vectors, Span and Basis](#lecture-2-vectors-span-and-basis)**
  - [Vector](#vector)
  - [Scaling a Vector](#scaling-a-vector)
  - [Standard Basis Vectors](#standard-basis-vectors)
  - [Alternative Basis](#alternative-basis)
  - [Linear Combination](#linear-combination)
  - [Span](#span)
    - [Span in 2D](#span-in-2d)
    - [Span in 3D](#span-in-3d)
  - [Linear Independence](#linear-independence)
  - [Basis](#basis)

- **[Lecture 3: Linear Transformations as Matrices](#lecture-3-linear-transformations-as-matrices)**
  - [What is a Transformation](#what-is-a-transformation)
  - [Condition for Linearity](#condition-for-linearity)
  - [Tracking Basis Vectors](#tracking-basis-vectors)
  - [Matrix as a Record of the Transformation](#matrix-as-a-record-of-the-transformation)
  - [Matrix-Vector Multiplication](#matrix-vector-multiplication)
  - [Common 2D Transformations](#common-2d-transformations)
    - [90 Degree Rotation](#90-degree-rotation)
    - [Shear](#shear)
    - [Squishing onto a Line](#squishing-onto-a-line)

- **[Lecture 4: 3D Linear Transformations](#lecture-4-3d-linear-transformations)**
  - [Extending to 3D](#extending-to-3d)
  - [The 3x3 Matrix](#the-3x3-matrix)
  - [Transforming a 3D Vector](#transforming-a-3d-vector)
  - [Applying Several Transformations](#applying-several-transformations)
  - [Order of Transformations](#order-of-transformations)
  - [Associativity](#associativity)

- **[Lecture 5: Matrix Product as Composite Transformation](#lecture-5-matrix-product-as-composite-transformation)**
  - [Composite Transformation](#composite-transformation)
  - [Order of Operation](#order-of-operation)
  - [Verification with Numbers](#verification-with-numbers)
    - [Step by Step Method](#step-by-step-method)
    - [Single Composite Matrix Method](#single-composite-matrix-method)
  - [Columns of the Product](#columns-of-the-product)
  - [Use in Deep Learning](#use-in-deep-learning)

- **[Lecture 6: Determinants](#lecture-6-determinants)**
  - [Determinant as a Scaling Factor](#determinant-as-a-scaling-factor)
  - [Unit Square as a Measuring Stick](#unit-square-as-a-measuring-stick)
  - [Determinant for Any Shape](#determinant-for-any-shape)
  - [Meaning of Determinant Values](#meaning-of-determinant-values)
  - [Examples of Determinants](#examples-of-determinants)
  - [Negative Determinant and Orientation](#negative-determinant-and-orientation)
  - [Determinants in 3D](#determinants-in-3d)
  - [Derivation of the Determinant Formula](#derivation-of-the-determinant-formula)
  - [Why Determinants Multiply](#why-determinants-multiply)
  - [Zero Determinant in Machine Learning](#zero-determinant-in-machine-learning)

- **[Lecture 7: Transformations with Non-Square Matrices](#lecture-7-transformations-with-non-square-matrices)**
  - [Square and Non-Square Matrices](#square-and-non-square-matrices)
  - [Reading the Dimensions of a Matrix](#reading-the-dimensions-of-a-matrix)
  - [3x2 Matrix from 2D to 3D](#3x2-matrix-from-2d-to-3d)
    - [Output Dimension](#output-dimension)
    - [Span Inside 3D](#span-inside-3d)
  - [2x3 Matrix from 3D to 2D](#2x3-matrix-from-3d-to-2d)
  - [2x1 Matrix from 1D to 2D](#2x1-matrix-from-1d-to-2d)
  - [1x2 Matrix from 2D to 1D](#1x2-matrix-from-2d-to-1d)
  - [Example of a 1x2 Transformation](#example-of-a-1x2-transformation)
  - [Non-Square Matrices in Neural Networks](#non-square-matrices-in-neural-networks)

- **[Lecture 8: Matrix Inverse](#lecture-8-matrix-inverse)**
  - [Linear and Non-Linear Equations](#linear-and-non-linear-equations)
  - [Linear Systems as Matrix Equations](#linear-systems-as-matrix-equations)
  - [Inverse as Undoing a Transformation](#inverse-as-undoing-a-transformation)
    - [Identity Matrix](#identity-matrix)
  - [Example of Rotation and Inverse](#example-of-rotation-and-inverse)
  - [When the Determinant is Zero](#when-the-determinant-is-zero)
    - [No Solution Case](#no-solution-case)
    - [Infinite Solutions Case](#infinite-solutions-case)
    - [Why No Inverse Exists](#why-no-inverse-exists)
  - [Example of a Squishing Matrix](#example-of-a-squishing-matrix)
  - [Column Space](#column-space)
  - [Rank](#rank)
  - [Null Space](#null-space)

- **[Lecture 9: Dot Product and Transformation](#lecture-9-dot-product-and-transformation)**
  - [Numeric Dot Product](#numeric-dot-product)
  - [Example of a 3D Dot Product](#example-of-a-3d-dot-product)
  - [Dot Product as Projection](#dot-product-as-projection)
  - [Symmetry of the Dot Product](#symmetry-of-the-dot-product)
  - [2D to 1D Transformation](#2d-to-1d-transformation)
    - [Tracking Basis Vectors in 1D](#tracking-basis-vectors-in-1d)
  - [Example of a 2D to 1D Transformation](#example-of-a-2d-to-1d-transformation)
  - [Duality of Vectors and Matrices](#duality-of-vectors-and-matrices)
    - [Row Matrix and Column Vector](#row-matrix-and-column-vector)
    - [Projection onto a Line](#projection-onto-a-line)

- **[Lecture 10: Eigenvalues and Eigenvectors](#lecture-10-eigenvalues-and-eigenvectors)**
  - [Meaning of Eigenvectors and Eigenvalues](#meaning-of-eigenvectors-and-eigenvalues)
    - [Preserving the Span](#preserving-the-span)
    - [Effect of the Eigenvalue](#effect-of-the-eigenvalue)
  - [Eigenvectors of a Shear](#eigenvectors-of-a-shear)
  - [Characteristic Equation](#characteristic-equation)
    - [Rewriting with the Identity Matrix](#rewriting-with-the-identity-matrix)
    - [Why the Determinant is Zero](#why-the-determinant-is-zero)
  - [Example of Finding Eigenvalues and Eigenvectors](#example-of-finding-eigenvalues-and-eigenvectors)
  - [Rotations and Eigenvectors](#rotations-and-eigenvectors)
    - [2D Rotation](#2d-rotation)
    - [3D Rotation](#3d-rotation)
  - [Diagonal Matrices](#diagonal-matrices)
  - [Fast Matrix Powers](#fast-matrix-powers)
  - [Eigenvectors in Machine Learning](#eigenvectors-in-machine-learning)

- [References](#references)

---

## Lecture 2: Vectors, Span and Basis

🎥 [Video link](https://www.youtube.com/watch?v=llV4uj58wuA)

### Vector

A vector is an arrow that starts at the origin $`(0, 0)`$ and points to a location in space. Two things define a vector: its direction and its length.

### Scaling a Vector

Multiplying a vector by a number (a scalar) $`c`$ moves the vector along its own line.

- $`c > 1`$: the vector becomes longer.
- $`0 < c < 1`$: the vector shrinks toward the origin.
- $`c < 0`$: the vector flips to the opposite direction.

```math
c\vec{v} = c\begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} cx \\ cy \end{bmatrix}
```

### Standard Basis Vectors

Points in a plane are normally described with two special vectors: $`\hat{i}`$ (one step along the x-axis) and $`\hat{j}`$ (one step along the y-axis). The vector $`(3, 2)`$ means 3 steps of $`\hat{i}`$ plus 2 steps of $`\hat{j}`$.

```math
\vec{v} = x\hat{i} + y\hat{j}
```

### Alternative Basis

The vectors $`\hat{i}`$ and $`\hat{j}`$ are only one possible choice. Any two vectors that do not lie on the same line can act as new axes. The same physical vector then gets different coordinates, which shows that coordinates always depend on the chosen basis.

### Linear Combination

Scaling vectors and adding the results together is called a linear combination.

```math
\vec{w} = c_1\vec{v}_1 + c_2\vec{v}_2
```

### Span

The span of a set of vectors is the collection of all points that can be reached through linear combinations of those vectors.

#### Span in 2D

- Two vectors in different directions: the span is the entire plane.
- Two vectors on the same line: the span is only a line.

#### Span in 3D

- Two vectors not on the same line: the span is a flat plane inside 3D space.

### Linear Independence

Vectors are added one at a time while the span is observed.

- A new vector that already lies inside the current span adds nothing new. Such a vector is **linearly dependent** (redundant).
- A new vector that opens a new dimension is **linearly independent**.

Example: start with one vector (the span is a line). Add a parallel vector (still a line, so redundant). Add a non-parallel vector (the span becomes a full plane). Add a vector lying inside that plane (redundant). Add a vector pointing out of the plane (the span becomes all of 3D space). After the redundant vectors are removed, three vectors remain.

### Basis

A basis is the smallest set of linearly independent vectors that spans an entire space: 2 vectors for 2D and 3 vectors for 3D.

---

## Lecture 3: Linear Transformations as Matrices

🎥 [Video link](https://www.youtube.com/watch?v=W49sCL5Lsxc)

### What is a Transformation

A transformation takes every vector in the plane and moves it to a new position. Rotating, stretching and tilting the whole grid are all transformations.

### Condition for Linearity

Two rules must hold for a transformation to be linear:

1. Straight lines stay straight (grid lines remain parallel and evenly spaced).
2. The origin $`(0, 0)`$ does not move.

### Tracking Basis Vectors

Transforming every vector one by one is unnecessary. Once the new positions of $`\hat{i}`$ and $`\hat{j}`$ are known, the new position of any vector is known too. A vector built as $`x\hat{i} + y\hat{j}`$ lands at the same combination of the new $`\hat{i}`$ and $`\hat{j}`$.

### Matrix as a Record of the Transformation

For the matrix

```math
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}
```

- the first column $`(a, c)`$ is the new position of $`\hat{i}`$,
- the second column $`(b, d)`$ is the new position of $`\hat{j}`$.

### Matrix-Vector Multiplication

Multiplying a vector by a matrix means taking the same amounts of each basis vector, but using the new basis vectors.

```math
A\begin{bmatrix} x \\ y \end{bmatrix} = x\begin{bmatrix} a \\ c \end{bmatrix} + y\begin{bmatrix} b \\ d \end{bmatrix}
```

### Common 2D Transformations

#### 90 Degree Rotation

For a 90° counter-clockwise rotation, $`\hat{i}`$ moves to $`(0, 1)`$ and $`\hat{j}`$ moves to $`(-1, 0)`$.

```math
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}
```

#### Shear

In a shear, $`\hat{i}`$ stays at $`(1, 0)`$ while $`\hat{j}`$ moves to $`(1, 1)`$. The square tilts into a parallelogram.

```math
\begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}
```

#### Squishing onto a Line

When both columns of a matrix point along the same line, the whole plane gets flattened onto that line.

---

## Lecture 4: 3D Linear Transformations

🎥 [Video link](https://www.youtube.com/watch?v=11GtIkzbGwo)

### Extending to 3D

The same rules apply in three dimensions. Three basis vectors are tracked: $`\hat{i}`$, $`\hat{j}`$ and $`\hat{k}`$, where $`\hat{k}`$ points along the z-axis.

### The 3x3 Matrix

The first, second and third columns of a $`3 \times 3`$ matrix are the new positions of $`\hat{i}`$, $`\hat{j}`$ and $`\hat{k}`$, in that order.

### Transforming a 3D Vector

A vector $`(x, y, z)`$ becomes the same combination of the new basis vectors.

```math
x\,\hat{i}_{new} + y\,\hat{j}_{new} + z\,\hat{k}_{new}
```

### Applying Several Transformations

When one transformation follows another, the matrices are multiplied from right to left. The matrix nearest to the vector acts first.

### Order of Transformations

Rotating first and shearing afterwards gives a different result from shearing first and rotating afterwards. Matrix multiplication is therefore not commutative.

```math
M_1 M_2 \neq M_2 M_1
```

### Associativity

Although the order of transformations matters, the grouping does not.

```math
A(BC) = (AB)C
```

Both groupings apply the same three transformations in the same sequence, which makes the rule easy to see geometrically.

---

## Lecture 5: Matrix Product as Composite Transformation

🎥 [Video link](https://www.youtube.com/watch?v=wBW1Y8NCc9s)

### Composite Transformation

Applying one transformation after another can be replaced by a single transformation. The matrix of that single transformation is the product of the two original matrices.

### Order of Operation

The product is read from right to left. In $`M_S M_R \vec{v}`$, the rotation $`M_R`$ acts on the vector first, and the shear $`M_S`$ acts on the result.

### Verification with Numbers

Given rotation $`M_R = \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}`$, shear $`M_S = \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}`$ and vector $`\vec{v} = \begin{bmatrix} 2 \\ 1 \end{bmatrix}`$:

#### Step by Step Method

- After the rotation: $`\begin{bmatrix} -1 \\ 2 \end{bmatrix}`$
- After the shear: $`\begin{bmatrix} 1 \\ 2 \end{bmatrix}`$

#### Single Composite Matrix Method

```math
M_S M_R = \begin{bmatrix} 1 & -1 \\ 1 & 0 \end{bmatrix}, \qquad \begin{bmatrix} 1 & -1 \\ 1 & 0 \end{bmatrix}\begin{bmatrix} 2 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 \\ 2 \end{bmatrix}
```

Both methods give exactly the same result.

### Columns of the Product

The columns of the product are found by taking the columns of the first matrix applied (the transformed $`\hat{i}`$ and $`\hat{j}`$) and passing each column through the second matrix.

### Use in Deep Learning

Neural networks and Transformer models pass data through layer after layer. Each layer multiplies the data by a weight matrix, which is a linear transformation that maps data from one dimension to another.

---

## Lecture 6: Determinants

🎥 [Video link](https://www.youtube.com/watch?v=X5AKfID0aXQ)

### Determinant as a Scaling Factor

Instead of being treated as a formula to memorise, the determinant is introduced through a physical question: when space is transformed, by what factor does the size of a region change? That factor is the determinant.

### Unit Square as a Measuring Stick

The unit square, formed by $`\hat{i}`$ and $`\hat{j}`$, has an area of 1. After the transformation, the square becomes a parallelogram formed by the two column vectors. The area of that parallelogram is the determinant.

### Determinant for Any Shape

Any shape can be filled with tiny squares. Each tiny square is scaled by the same factor, so the whole shape is scaled by the determinant as well. The determinant is therefore a property of the entire transformation, not of one particular shape.

### Meaning of Determinant Values

| Determinant | Effect on space |
|---|---|
| Greater than 1 | Area expands |
| Equal to 1 | Area is preserved (shear, rotation) |
| Between 0 and 1 | Area shrinks |
| Equal to 0 | Space collapses onto a line or a point; the columns are linearly dependent |
| Negative | Space is flipped; the area scales by the absolute value |

### Examples of Determinants

- $`\begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix}`$ has determinant **6**: area becomes 6 times larger.
- $`\begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}`$ has determinant **1**: the shape tilts but the area is unchanged.
- $`\begin{bmatrix} 3 & 1 \\ 1 & 3 \end{bmatrix}`$ has determinant **8**: strong expansion.
- $`\begin{bmatrix} 0.5 & 0.5 \\ -0.5 & 0 \end{bmatrix}`$ has determinant **0.25**: area shrinks to one quarter.
- $`\begin{bmatrix} 1 & 0.5 \\ 1 & 0.5 \end{bmatrix}`$ has determinant **0**: everything collapses onto a line.
- $`\begin{bmatrix} -2 & 0 \\ 2 & 2 \end{bmatrix}`$ has determinant **-4**: area scales by 4 and space is flipped.

### Negative Determinant and Orientation

Originally $`\hat{i}`$ lies to the right of $`\hat{j}`$. When a transformation pushes $`\hat{i}`$ to the left of $`\hat{j}`$, space is flipped like a sheet of paper, and the determinant becomes negative. Swapping the two columns of a matrix changes the sign of the determinant while the area stays the same.

### Determinants in 3D

For a $`3 \times 3`$ matrix, the determinant measures volume, with the unit cube having volume 1. The determinant becomes zero when 3D space collapses into:

- a flat plane,
- a single line, or
- a single point.

In all three cases the volume is zero.

### Derivation of the Determinant Formula

For the matrix $`\begin{bmatrix} a & b \\ c & d \end{bmatrix}`$, a large rectangle of size $`(a+b) \times (c+d)`$ is drawn around the parallelogram. The corner triangles and rectangles outside the parallelogram are then subtracted from the rectangle. The remaining area is:

```math
\text{Area} = ad - bc
```

The formula therefore comes from geometry rather than being an arbitrary rule.

### Why Determinants Multiply

Applying $`B`$ first multiplies the area by $`\det(B)`$. Applying $`A`$ afterwards multiplies the area by $`\det(A)`$. The combined transformation $`AB`$ must produce the same final area, so:

```math
\det(AB) = \det(A)\cdot\det(B)
```

### Zero Determinant in Machine Learning

- A determinant of 0 means a dimension is permanently lost, so the original data cannot be recovered (the matrix is not invertible).
- A determinant close to 0 means very strong compression, which can lead to numerical problems.

---

## Lecture 7: Transformations with Non-Square Matrices

🎥 [Video link](https://www.youtube.com/watch?v=RUtFveu7utU)

### Square and Non-Square Matrices

A **square matrix** has the same number of rows and columns ($`n \times n`$) and moves vectors within the same space (2D to 2D, 3D to 3D).

A **non-square matrix** has $`m \times n`$ entries with $`m \neq n`$ and moves vectors from an $`n`$-dimensional space into an $`m`$-dimensional space.

Review of a square case: for $`M = \begin{bmatrix} 3 & 2 \\ 1 & 4 \end{bmatrix}`$, $`\hat{i}`$ lands at $`(3, 1)`$ and $`\hat{j}`$ lands at $`(2, 4)`$, so any vector $`(x, y)`$ becomes:

```math
x\begin{bmatrix} 3 \\ 1 \end{bmatrix} + y\begin{bmatrix} 2 \\ 4 \end{bmatrix} = \begin{bmatrix} 3x + 2y \\ x + 4y \end{bmatrix}
```

### Reading the Dimensions of a Matrix

For an $`m \times n`$ matrix:

- **Columns ($`n`$)**: number of input basis vectors, which equals the dimension of the input space.
- **Rows ($`m`$)**: number of coordinates of each landing position, which equals the dimension of the output space.

A common slip is to read a $`3 \times 2`$ matrix as "3D to 2D". The correct reading is the opposite: 2 columns means 2D input and 3 rows means 3D output.

### 3x2 Matrix from 2D to 3D

This matrix takes a 2D vector and returns a 3D vector. Each of the two basis vectors $`\hat{i}`$ and $`\hat{j}`$ lands at a point with three coordinates.

#### Output Dimension

Every transformed vector now lives in 3D space, so the output has three coordinates $`(x, y, z)`$.

#### Span Inside 3D

Only two transformed vectors exist, and two vectors cannot fill 3D space. Their linear combinations form a **flat 2D plane through the origin, tilted inside 3D space**. The space moves into 3D, but the span stays 2D.

Small example: if $`\hat{i}`$ lands at $`(1, 0, 1)`$ and $`\hat{j}`$ lands at $`(0, 1, 1)`$, the vector $`(2, 3)`$ becomes $`2(1, 0, 1) + 3(0, 1, 1) = (2, 3, 5)`$.

### 2x3 Matrix from 3D to 2D

This matrix takes a 3D vector and returns a 2D vector. The three basis vectors $`\hat{i}`$, $`\hat{j}`$ and $`\hat{k}`$ each land at a point with two coordinates. Three vectors in 2D cannot all be independent, so at least one is redundant. The 3D space is squished onto a plane.

### 2x1 Matrix from 1D to 2D

The input is a single number on a number line (1D) and the output is a 2D vector. Only one basis vector exists, so the span in 2D is just a **straight line through the origin**.

### 1x2 Matrix from 2D to 1D

The input is a 2D vector and the output has a single coordinate on a number line.

```math
\begin{bmatrix} m_{1} & m_{2} \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = m_{1}v_1 + m_{2}v_2
```

### Example of a 1x2 Transformation

For $`M = \begin{bmatrix} 1 & 2 \end{bmatrix}`$ and $`\vec{v} = \begin{bmatrix} 3 \\ 2 \end{bmatrix}`$:

- Dimensions: $`(1 \times 2)(2 \times 1) = 1 \times 1`$
- Calculation: $`1 \times 3 + 2 \times 2 = 7`$

The vector $`(3, 2)`$ is squished onto the coordinate **7** of a 1D line.

### Non-Square Matrices in Neural Networks

Layer inputs are vectors and layer weights are matrices. When two layers have a different number of neurons, the weight matrix is non-square.

- 2 neurons to 3 neurons needs a $`3 \times 2`$ matrix (lower dimension to higher dimension).
- 3 neurons to 2 neurons needs a $`2 \times 3`$ matrix (dimension reduction).

---

## Lecture 8: Matrix Inverse

🎥 [Video link](https://www.youtube.com/watch?v=SyofJSMKoXg)

### Linear and Non-Linear Equations

A **linear equation** multiplies variables only by constants and combines them by addition or subtraction:

```math
\alpha x + \beta y + \dots = c
```

Multiplying variables together ($`xy`$), powers ($`x^2`$, $`y^3`$), logarithms ($`\log x`$) and trigonometric functions ($`\sin x`$, $`\cos y`$) are **non-linear**. They bend space and cannot be written as matrices.

### Linear Systems as Matrix Equations

A system of linear equations can be written in matrix form.

```math
\begin{aligned}
3x + y &= 2 \\
x + 2y &= 0
\end{aligned}
\quad\Longrightarrow\quad
\begin{bmatrix} 3 & 1 \\ 1 & 2 \end{bmatrix}\begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 2 \\ 0 \end{bmatrix}
```

In short form, $`A\vec{x} = \vec{v}`$. The matrix $`A`$ is a transformation, and solving the system means finding the vector $`\vec{x}`$ that lands on $`\vec{v}`$ after the transformation.

### Inverse as Undoing a Transformation

When $`\det(A) \neq 0`$, each vector lands on exactly one place and every landing place comes from exactly one vector. A transformation that reverses $`A`$ exists. It is called the **inverse** $`A^{-1}`$.

```math
A\vec{x} = \vec{v} \iff \vec{x} = A^{-1}\vec{v}
```

#### Identity Matrix

Applying $`A`$ and then $`A^{-1}`$ returns every vector to its starting place. The combined transformation does nothing and is the identity matrix.

```math
A^{-1}A = I = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
```

### Example of Rotation and Inverse

**Forward transformation:** 90° counter-clockwise rotation.

```math
A = \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}, \qquad A\begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} -y \\ x \end{bmatrix}
```

**Inverse transformation:** 90° clockwise rotation, where $`\hat{i}`$ goes to $`(0, -1)`$ and $`\hat{j}`$ goes to $`(1, 0)`$.

```math
B = \begin{bmatrix} 0 & 1 \\ -1 & 0 \end{bmatrix}, \qquad B\begin{bmatrix} -y \\ x \end{bmatrix} = \begin{bmatrix} x \\ y \end{bmatrix}
```

The original vector is recovered exactly, so $`BA = I`$ and $`B = A^{-1}`$.

### When the Determinant is Zero

When $`\det(A) = 0`$, the transformation squishes 2D space onto a line or a point. Such a matrix is called **singular**.

#### No Solution Case

If the target vector $`\vec{v}`$ lies off the squished line, no vector in the plane can reach it, so $`A\vec{x} = \vec{v}`$ has no solution.

#### Infinite Solutions Case

If $`\vec{v}`$ lies on the squished line, a whole line of original vectors collapses onto that single point, so the equation has infinitely many solutions.

#### Why No Inverse Exists

Undoing a squish would require sending one vector back to many vectors. A transformation must give exactly one output for each input, so such a reverse transformation cannot exist.

### Example of a Squishing Matrix

For $`A = \begin{bmatrix} 1 & 2 \\ 1 & 2 \end{bmatrix}`$:

- Determinant: $`1 \times 2 - 2 \times 1 = 0`$
- Transforming $`(-2, 3)`$: $`\begin{bmatrix} 1(-2) + 2(3) \\ 1(-2) + 2(3) \end{bmatrix} = \begin{bmatrix} 4 \\ 4 \end{bmatrix}`$
- Both coordinates are always equal, so every vector lands on the line $`y = x`$.
- For the target $`(2, 3)`$, which is not on that line, $`A\vec{x} = \vec{v}`$ has **no solution**.

### Column Space

The column space is the span of the columns of $`A`$. It contains every vector the transformation can produce.

### Rank

Rank is the number of dimensions of the column space.

| Result of the transformation | Rank |
|---|---|
| Fills the 2D plane | 2 |
| Squished onto a line | 1 |
| Collapsed to the origin | 0 |

### Null Space

The null space is the set of all vectors that land exactly on the origin after the transformation.

- If a 2D transformation squishes the plane onto a line, the null space is a line.
- If a 3D transformation squishes space onto a line, the null space is a plane.

---

## Lecture 9: Dot Product and Transformation

🎥 [Video link](https://www.youtube.com/watch?v=47c2138lFRI)

### Numeric Dot Product

The dot product takes two vectors of the same length and returns a single number (a scalar). Matching components are multiplied and the products are added.

```math
\vec{u}\cdot\vec{v} = u_1 v_1 + u_2 v_2 + \dots + u_n v_n
```

### Example of a 3D Dot Product

For $`\vec{u} = (1, 2, 3)`$ and $`\vec{v} = (3, 2, 1)`$:

```math
(1 \times 3) + (2 \times 2) + (3 \times 1) = 3 + 4 + 3 = 10
```

### Dot Product as Projection

Geometrically, $`\vec{v}`$ is projected straight down onto the line through $`\vec{u}`$ (like a shadow). The length of that projected piece is multiplied by the length of $`\vec{u}`$. The result is the dot product.

### Symmetry of the Dot Product

The order of the two vectors does not change the answer: $`\vec{u}\cdot\vec{v} = \vec{v}\cdot\vec{u}`$.

Reason: if $`\vec{v}`$ is doubled, the projection of $`\vec{u}`$ onto the line stays the same length, but the vector being projected onto is twice as long, so the product doubles. Projecting in the opposite direction doubles the projected piece while the other length stays fixed, giving the same doubled result.

```math
\vec{u}\cdot(2\vec{v}) = 2(\vec{u}\cdot\vec{v})
```

### 2D to 1D Transformation

A $`1 \times 2`$ matrix squishes the 2D plane onto a number line. Writing $`M = \begin{bmatrix} m_1 & m_2 \end{bmatrix}`$:

#### Tracking Basis Vectors in 1D

- $`\hat{i}`$ lands at $`m_1\hat{i}`$.
- $`\hat{j}`$ lands at $`m_2\hat{i}`$.

The 1D line has only one basis vector, so the landing places are written with $`\hat{i}`$ only. There is no $`\hat{j}`$ in 1D. For $`\vec{v} = (v_1, v_2)`$:

```math
M\vec{v} = (m_1 v_1 + m_2 v_2)\,\hat{i}
```

The result is formally a 1D vector, while a dot product is defined as a scalar. The numbers are identical.

### Example of a 2D to 1D Transformation

For $`M = \begin{bmatrix} 2 & -1 \end{bmatrix}`$ and $`\vec{v} = (3, 4)`$:

- $`\vec{v} = 3\hat{i} + 4\hat{j}`$
- $`\hat{i}`$ lands at $`2\hat{i}`$ and $`\hat{j}`$ lands at $`-1\hat{i}`$
- Result: $`3(2\hat{i}) + 4(-1\hat{i}) = 2\hat{i}`$

This matches the dot product $`(2, -1)\cdot(3, 4) = 6 - 4 = 2`$.

### Duality of Vectors and Matrices

#### Row Matrix and Column Vector

Every 2D-to-1D transformation has a matching 2D vector with the same numbers. The row matrix and the column vector are called **duals**.

```math
\begin{bmatrix} u_x & u_y \end{bmatrix} \longleftrightarrow \begin{bmatrix} u_x \\ u_y \end{bmatrix}
```

Multiplying the row matrix by a vector $`\vec{v}`$ gives $`u_x v_x + u_y v_y`$, which is exactly $`\vec{u}\cdot\vec{v}`$.

#### Projection onto a Line

The line through $`\vec{u}`$ can be treated as the 1D destination space.

- If $`\vec{u}`$ is a unit vector, the result is the exact coordinate of the projection of $`\vec{v}`$ onto that line.
- If $`\vec{u}`$ has length $`c`$, the projection coordinate is scaled by $`c`$.

---

## Lecture 10: Eigenvalues and Eigenvectors

🎥 [Video link](https://www.youtube.com/watch?v=-PmMvHPUto4)

### Meaning of Eigenvectors and Eigenvalues

```math
A\vec{x} = \lambda\vec{x}
```

Here $`A`$ is a square matrix, $`\vec{x}`$ is a non-zero vector called the **eigenvector**, and $`\lambda`$ is a number called the **eigenvalue**.

#### Preserving the Span

Most vectors get knocked off their own line when a transformation is applied. Eigenvectors are the special vectors that **stay on their original line through the origin**. The transformation only stretches, squishes or flips them along that line. Every non-zero multiple of an eigenvector is also an eigenvector, so an eigenvector stands for a whole line of vectors.

#### Effect of the Eigenvalue

- $`\lambda > 1`$: the vector is stretched.
- $`0 < \lambda < 1`$: the vector is squished.
- $`\lambda < 0`$: the vector is flipped to the opposite direction.

### Eigenvectors of a Shear

Take $`A = \begin{bmatrix} 2 & 1 \\ 0 & 2 \end{bmatrix}`$, where $`\hat{i}`$ lands at $`(2, 0)`$ and $`\hat{j}`$ lands at $`(1, 2)`$.

- **A vector on the x-axis**, $`(x, 0)`$, becomes $`(2x, 0) = 2\,(x, 0)`$. The vector stays on the x-axis and is doubled, so $`\lambda = 2`$ and every vector on the x-axis is an eigenvector.
- **A vector on the y-axis**, $`(0, 3)`$, becomes $`(3, 6)`$. This is not a multiple of $`(0, 3)`$, so the vector was knocked off its line and is **not** an eigenvector.

### Characteristic Equation

#### Rewriting with the Identity Matrix

A number cannot be subtracted from a matrix directly, so $`\lambda`$ is replaced by $`\lambda I`$:

```math
A\vec{x} = \lambda I\vec{x} \quad\Longrightarrow\quad (A - \lambda I)\vec{x} = \vec{0}
```

#### Why the Determinant is Zero

The matrix $`(A - \lambda I)`$ sends a non-zero vector $`\vec{x}`$ to the origin. As seen in Lectures 6 and 8, a transformation can do that only if it squishes space into a lower dimension, which means its determinant is zero.

```math
\det(A - \lambda I) = 0
```

This is the **characteristic equation**. Solving it gives the eigenvalues.

### Example of Finding Eigenvalues and Eigenvectors

For $`A = \begin{bmatrix} 4 & 1 \\ 2 & 3 \end{bmatrix}`$:

**Step 1: eigenvalues**

```math
\det\begin{bmatrix} 4-\lambda & 1 \\ 2 & 3-\lambda \end{bmatrix} = (4-\lambda)(3-\lambda) - 2 = \lambda^2 - 7\lambda + 10 = 0
```

```math
(\lambda - 5)(\lambda - 2) = 0 \quad\Longrightarrow\quad \lambda_1 = 5,\; \lambda_2 = 2
```

**Step 2: eigenvector for $`\lambda = 5`$**

```math
\begin{bmatrix} -1 & 1 \\ 2 & -2 \end{bmatrix}\begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} \quad\Longrightarrow\quad x = y
```

The line $`x = y`$ works, for example $`(1, 1)`$. Check: $`A(1, 1) = (5, 5) = 5\,(1, 1)`$ ✓

**Step 3: eigenvector for $`\lambda = 2`$**

```math
\begin{bmatrix} 2 & 1 \\ 2 & 1 \end{bmatrix}\begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} \quad\Longrightarrow\quad y = -2x
```

The line $`y = -2x`$ works, for example $`(1, -2)`$. Check: $`A(1, -2) = (2, -4) = 2\,(1, -2)`$ ✓

### Rotations and Eigenvectors

#### 2D Rotation

A 90° rotation moves every non-zero vector off its own line, so no vector keeps its direction. A 2D rotation has **no real eigenvectors or eigenvalues**.

#### 3D Rotation

When 3D space rotates around an axis, the vectors lying on that axis of rotation do not move. They are eigenvectors with eigenvalue $`\lambda = 1`$.

### Diagonal Matrices

A diagonal matrix has non-zero entries only on its main diagonal:

```math
\begin{bmatrix} a & 0 \\ 0 & b \end{bmatrix}
```

- The diagonal entries are the eigenvalues: $`\lambda_1 = a`$ and $`\lambda_2 = b`$.
- The eigenvectors are the vectors along the x-axis and along the y-axis.

Example: $`\begin{bmatrix} 7 & 0 \\ 0 & -3 \end{bmatrix}`$ has eigenvalues $`7`$ and $`-3`$.

### Fast Matrix Powers

Multiplying a diagonal matrix by itself $`n`$ times simply raises each diagonal entry to the power $`n`$.

```math
\begin{bmatrix} a & 0 \\ 0 & b \end{bmatrix}^n = \begin{bmatrix} a^n & 0 \\ 0 & b^n \end{bmatrix}
```

Example: $`\begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix}^4 = \begin{bmatrix} 16 & 0 \\ 0 & 81 \end{bmatrix}`$. Large powers such as $`A^{100}`$ can be found immediately, without repeated matrix multiplication.

### Eigenvectors in Machine Learning

Eigenvalues and eigenvectors combine basis tracking, determinants, span and transformations into one tool. They are used in algorithms such as Principal Component Analysis (PCA) and in spectral graph theory.

---

## References

| Lecture | Video |
|---|---|
| Lecture 2: Vectors, Span and Basis | https://www.youtube.com/watch?v=llV4uj58wuA |
| Lecture 3: Linear Transformations as Matrices | https://www.youtube.com/watch?v=W49sCL5Lsxc |
| Lecture 4: 3D Linear Transformations | https://www.youtube.com/watch?v=11GtIkzbGwo |
| Lecture 5: Matrix Product as Composite Transformation | https://www.youtube.com/watch?v=wBW1Y8NCc9s |
| Lecture 6: Determinants | https://www.youtube.com/watch?v=X5AKfID0aXQ |
| Lecture 7: Transformations with Non-Square Matrices | https://www.youtube.com/watch?v=RUtFveu7utU |
| Lecture 8: Matrix Inverse | https://www.youtube.com/watch?v=SyofJSMKoXg |
| Lecture 9: Dot Product and Transformation | https://www.youtube.com/watch?v=47c2138lFRI |
| Lecture 10: Eigenvalues and Eigenvectors | https://www.youtube.com/watch?v=-PmMvHPUto4 |
