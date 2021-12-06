# Descriptors

## Invertible/Nondegenerate/Nonsingular Matrix

A square matrix $\textbf{A}$ is called *invertible* if there exists some matrix $\textbf{B}$ such that

$$
\textbf{A}\textbf{B} = \textbf{I}
$$

Non-square matrices can have either left or right inverses, but not both. If a square matrix has a left inverse, it has a right and vice versa:

$$
\textbf{A}\textbf{B} = \textbf{C}\textbf{A} = \textbf{I}
$$

and

$$
\textbf{B} = \textbf{C} = \textbf{A}^{-1}
$$

## Rank

The rank of a matrix is the dimension of the vector space spanned by it's columns (or rows, the rank is the same in either case). This corresponds to the maximum number of linearly independant rows/columns.
