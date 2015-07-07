Linear Algebra Cheatsheet
=========================

Operations
----------

### Transpose

First row becomes first column.

First column becomes first row.

Etc.

```
1 4   transposed   =   1 6 3
6 1                    4 1 5
3 5
```

### Addition

Add up all the stuff in the same row/column.

```
1 2   +   5 6   =    6  8
3 4       7 8       10 12
```

### Subtraction

Similar to Addition.

```
7 2   -   5 6   =    2 -4
3 4       7 8       -4 12
```

### Element-Wise Multiplication

Similar to Addition.

#### Vector

```
1   *   4   =    4
6       1        6
3       5       15
```

#### Matrix

```
1 2   *   5 6   =    5 12
3 4       7 8       21 32
```

### Scalar Multiplication

Multiply the scalar by each value.

```
3   *   3 5 4   =    9 15 12
        6 1 2       18  3  6
```

### Scalar Product (Dot Product)

Multiplies two vectors into one number.

Multiply corresponding row/columns. Then sum those.

```
1   *   6   =   36
7       2
3       5

1*6 + 7*2 + 3*5 = 6 + 14 + 15

                = 20 + 15

                = 36
```

### Matrix-Vector Multiplication

To multiply A * B = C:

* Treat each row in A as a vector.

* Multiply that row vector by B.

* Place the result in same row in C.

```
3 5 4 6   *   2   =   78
8 3 6 1       6       57
              3
              5

3 5 4 6   *   2   =   3   *   2   =   3*2 + 5*6 + 4*3 + 6*5
              6       5       6
              3       4       3
              5       6       5

                                  =   6 + 30 + 12 + 30

                                  =   60 + 18

                                  =   78

8 3 6 1   *   2   =   8   *   2   =   8*2 + 3*6 + 6*3 + 1*5
              6       3       6
              3       6       3
              5       1       5

                                  =   16 + 18 + 18 + 5

                                  =   17 + 20 + 20

                                  =   17 + 40

                                  =   57
```

### Matrix-Matrix Multiplication

To multiply A * B = C.

* Do matrix-vector multiplication on A.row_1 * B.column_1.

* Place result in C.row_1,column_1.

* Do matrix-vector multiplication on A.row_1 * B.column_2.

* Place result in C.row_1,column_2.

* Etc.

```
3 5 4 6   *   2 6   =   69 60
8 3 6 1       7 2       47 86
              1 5
              4 2

3 5 4 6   *   2   =   3   *   2   =   3*2 + 5*7 + 4*1 + 6*4
              7       5       7
              1       4       1
              4       6       4

                                  =   6 + 35 + 4 + 24

                                  =   10 + 35 + 24

                                  =   40 + 29

                                  =   69

3 5 4 6   *   6   =   3   *   6   =   3*6 + 5*2 + 4*5 + 6*2
              2       5       2
              5       4       5
              2       6       2

                                  =   18 + 10 + 20 + 12

                                  =   30 + 10 + 20

                                  =   60

8 3 6 1   *   2   =   8*2 + 3*7 + 6*1 + 1*4
              7
              1
              4

                  =   16 + 21 + 6 + 4

                  =   20 + 27

                  =   47

8 3 6 1   *   6   =   8*6 + 3*2 + 6*5 + 1*2
              2
              5
              2

                  =   48 + 6 + 30 + 2

                  =   50 + 36

                  =   86
```

#### Properties

##### Sizes

A(n by m)   *   B(m by p)   =   C(n by p)

##### Other

Associative.

  * (AB)C = A(BC)

Not Commutative.

  * AB != BA

### Outer Product

Multiplies two Vectors, A * B = C.

Result is a Matrix.

Steps:

  * Treat A and B as Matrices.

  * Perform A * B.transpose.
    * See Matrix-Matrix Multiplication.

```
3   outer_product   5   =   3   *   5 6 3 8   =   15
2                   6       2                     12
6                   3       6                     18
2                   8       2                     16

3*5   =   15

2*6   =   12

6*3   =   18

2*8   =   16
```

### Euclidean Norm

It's like absolute value for vectors.

It's the square root of the sum of the squares of each element.

```
 4   euclidean_norm   =   sqrt(4^2 + 3^2 + (-5)^2 + 1^2 + (-2)^2)
 3
-5
 1
-2

                      =   sqrt(16 + 9 + 25 + 1 + 4)

                      =   sqrt(20 + 25 + 10)

                      =   sqrt(55)

                      =   7.4162
```

Special Matrices
----------------

### Identity Matrix

Think of this in scalar terms: ```c * 1 = c```.

1 is the scalar multiplication identity because multiplying it by c doesn't
change c's value.

The identity matrix is the same thing for matrices.

The identity matrices always follow the same pattern as the one in these
examples.

```
9 3 5   *   1 0 0   =   9 3 5
4 1 2       0 1 0       4 1 2
            0 0 1
```

```
1 0 0   *   9 3 5   =   9 3 5
0 1 0       4 1 2       4 1 2
0 0 1
```

### Inverse Matrix

Think of this in scalar terms: ```c * 1/c = 1```.

```7 * 1/7 = 7```.

```1/c``` is the scalar inverse because multiplying it by c gives 1.

The inverse matrix a similar thing for matrices.

Multiplying a matrix A by its inverse gives the identity matrix.

A(A.inverse) = (A.inverse)A = Identity

#### Notes

The inverse matrix does not exist for every matrix.

The matrix A must be a square matrix.
