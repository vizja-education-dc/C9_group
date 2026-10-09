# Exercise 2 — Presentation Script

## Part 1. Introduction and Problem Statement
**Estimated time: 1 minute**

"Hello everyone.

Today, I am going to present Exercise 2, which covers three basic operations in linear algebra: matrix addition, matrix subtraction, and scalar multiplication.

The purpose of this exercise is not only to calculate the results but also to understand the mathematical rules behind these operations.

Let's start with the problem statement.

We are given two matrices, A and B.

Matrix A contains the numbers one and two in the first row, and negative one and three in the second row.

Matrix B contains four and negative two in the first row, and zero and five in the second row.

Both matrices have two rows and two columns. Therefore, their dimensions are two by two.

We are asked to perform three calculations: A plus B, A minus B, and three A minus two B.

We also need to explain why matrix addition requires matrices to have identical dimensions.

Before performing the calculations, I will briefly introduce the theoretical background."

---

## Part 2. Theoretical Background — Matrix Addition
**Estimated time: 1 minute**

"Let's begin with matrix addition.

In general, we represent the elements of matrix A using the notation a sub i j, and the elements of matrix B using b sub i j.

Here, the index i represents the row number, while j represents the column number.

When we add two matrices, we add their corresponding entries.

In mathematical notation, the element in position i, j of A plus B is equal to a sub i j plus b sub i j.

In other words, we add the elements that occupy exactly the same positions.

For example, the element in the first row and first column of matrix A is added to the element in the first row and first column of matrix B.

We apply the same operation to every other position.

An important condition is that both matrices must have the same dimensions.

The resulting matrix also has the same dimensions as the original matrices."

---

## Part 3. Matrix Subtraction and Scalar Multiplication
**Estimated time: 1 minute**

"Matrix subtraction follows a very similar principle.

Instead of adding corresponding elements, we subtract them.

The element in position i, j of A minus B equals a sub i j minus b sub i j.

Again, both matrices must have identical dimensions.

Now let's discuss scalar multiplication.

A scalar is simply a number. In our exercise, the scalars are three and two.

When we multiply a matrix by a scalar, we multiply every element of that matrix by the same number.

For example, multiplying matrix A by three means that every entry of A is multiplied by three.

The dimensions of the matrix do not change.

This operation is important because it allows us to scale a matrix while preserving its structure.

Now that we've covered the fundamental rules, let's apply them to our example."

---

## Part 4. Step-by-Step Solution — A Plus B
**Estimated time: 1 minute**

"Let's start with the first calculation: A plus B.

First, we check the dimensions.

Both matrices are two by two, so addition is allowed.

Now we add the corresponding elements, one position at a time.

In the first row and first column, we calculate one plus four, which equals five.

In the first row and second column, we calculate two plus negative two, which equals zero.

Moving to the second row, negative one plus zero equals negative one.

Finally, three plus five equals eight.

Therefore, the result of A plus B is a matrix with five and zero in the first row, and negative one and eight in the second row.

Notice that the dimensions of the resulting matrix are still two by two.

This illustrates the fundamental rule of matrix addition: we add corresponding elements without changing the dimensions."

---

## Part 5. Step-by-Step Solution — A Minus B
**Estimated time: 1 minute**

"Now let's move to the second calculation: A minus B.

The procedure is almost identical to addition, but this time we subtract corresponding entries.

Let's begin with the first row.

One minus four equals negative three.

Two minus negative two equals four.

This is worth highlighting because subtracting a negative number is equivalent to adding a positive number.

Now let's move to the second row.

Negative one minus zero equals negative one.

And three minus five equals negative two.

Therefore, the result of A minus B is a matrix containing negative three and four in the first row, and negative one and negative two in the second row.

Again, the resulting matrix has dimensions two by two.

This completes our second calculation."

---

## Part 6. Step-by-Step Solution — Three A Minus Two B
**Estimated time: 1.5 minutes**

"Now let's consider the third calculation: three A minus two B.

This expression combines scalar multiplication and matrix subtraction.

We will solve it in three steps.

**Step one: Calculate three A.**

We multiply every element of matrix A by three.

One multiplied by three gives three.

Two multiplied by three gives six.

Negative one multiplied by three gives negative three.

And three multiplied by three gives nine.

So three A contains three and six in the first row, and negative three and nine in the second row.

**Step two: Calculate two B.**

We multiply every element of matrix B by two.

Four multiplied by two gives eight.

Negative two multiplied by two gives negative four.

Zero multiplied by two remains zero.

And five multiplied by two gives ten.

Therefore, two B contains eight and negative four in the first row, and zero and ten in the second row.

**Step three: Subtract two B from three A.**

Now both scalar multiplications are complete, and we can subtract the matrices element by element.

Three minus eight equals negative five.

Six minus negative four equals ten.

Negative three minus zero equals negative three.

And nine minus ten equals negative one.

Therefore, our final result is a matrix with negative five and ten in the first row, and negative three and negative one in the second row.

This example demonstrates how scalar multiplication and matrix subtraction can be combined in a single expression."

---

## Part 7. Why Matrix Dimensions Must Match
**Estimated time: 1 minute**

"Now let's discuss an important theoretical question.

Why is matrix addition possible only when the matrices have the same dimensions?

The answer comes directly from the definition of matrix addition.

Addition is an element-wise operation.

Every element in matrix A must have a corresponding element in matrix B, located in exactly the same row and column.

Suppose that matrix A has two rows and three columns, while matrix B has three rows and two columns.

Although both matrices contain six elements, their shapes are different.

Some positions in one matrix do not exist in the other.

For example, matrix A has an element in the first row and third column, but matrix B does not have a third column.

As a result, we cannot perform addition according to the standard definition.

This is why checking dimensions is always the first step before adding or subtracting matrices.

We can summarize the rule as follows: two matrices can be added or subtracted if and only if they have the same number of rows and the same number of columns."

---

## Part 8. Verification and Consistency Checks
**Estimated time: 1.5 minutes**

"After calculating the results, it is good mathematical practice to verify that our answers are correct.

Let's perform three simple consistency checks.

**First, verification of A plus B.**

We take our calculated sum and subtract matrix B.

If the original addition was correct, the result should be matrix A.

When we perform this subtraction, we obtain one and two in the first row, and negative one and three in the second row.

This is exactly our original matrix A.

So our first result is verified.

**Second, verification of A minus B.**

This time, we take the calculated difference and add matrix B.

Because subtraction and addition are inverse operations, we should recover matrix A.

After adding the corresponding elements, we once again obtain the original matrix A.

Therefore, our subtraction is also correct.

**Third, verification of three A minus two B.**

We begin with our calculated result and add two B.

If our calculation is correct, we should obtain three A.

After adding the matrices, we get three and six in the first row, and negative three and nine in the second row.

This is exactly three A.

As an additional check, we can divide every element by three, which returns the original matrix A.

Therefore, all three calculations have been successfully verified."

---

## Part 9. Final Summary and Conclusion
**Estimated time: 45 seconds**

"Let's summarize the main points of this exercise.

First, matrix addition is performed by adding corresponding elements.

Second, matrix subtraction is performed by subtracting corresponding elements.

Third, scalar multiplication means multiplying every matrix entry by the same number.

We also established an important condition: matrix addition and subtraction are defined only for matrices of identical dimensions.

Finally, we verified our results by applying inverse operations.

These concepts form a foundation for more advanced topics in linear algebra, including matrix multiplication, linear transformations, and systems of linear equations.

That concludes my presentation of Exercise 2.

Thank you for your attention. Are there any questions?"
