---
layout: base
title: Matrices &#124; Vectors and Matrices
---

# Matrices

As described in [Linear Maps](linear-maps.md), matrices can be used to represent linear transformations.
Just like [vectors](vectors.md), we can do all sorts of algebraic operations on matrices.

## Addition

Let $\mathcal{A}: V \to W$ and $\mathcal{B}: V \to W$ be linear maps.
The linear map $(\mathcal{A} + \mathcal{B}): V \to W$ is defined by

$$
(\mathcal{A} + \mathcal{B})(\mathbf{x}) = \mathcal{A}(\mathbf{x}) + \mathcal{B}(\mathbf{x})
$$

For matrices $\mathsf{A}, \mathsf{B}, \mathsf{A} + \mathsf{B}$ associated with the maps, we have

$$
(\mathsf{A} + \mathsf{B})_{ij} x_j = (\mathsf{A} + \mathsf{B})(\mathbf{x})_i = \mathsf{A}(\mathbf{x})_i + \mathsf{B}(\mathbf{x})_i = (\mathsf{A}_{ij} + \mathsf{B}_{ij}) x_j
$$

Hence,

$$
\mathsf{A} + \mathsf{B} = \Set{\mathsf{A}_{ij} + \mathsf{B}_{ij}}
$$

## Multiplication by Scalar

Let $\mathcal{A}: V \to W$ be a linear map.
For a given $\lambda \in \mathbb{F}$, the linear map $\lambda\mathcal{A}$ is defined by

$$
(\lambda\mathcal{A})(\mathbf{x}) = \lambda(\mathcal{A}(\mathbf{x}))
$$

We have

$$
(\lambda\mathsf{A})_{ij} x_j = (\lambda\mathsf{A})(\mathbf{x})_i = \lambda(\mathsf{A}(\mathbf{x})_i) = \lambda(\mathsf{A}_{ij} x_j) = (\lambda\mathsf{A}_{ij}) x_j

$$

Hence,

$$
\lambda\mathsf{A} = \Set{\lambda\mathsf{A}_{ij}}
$$

We can see that with the above definitions, after some checks, matrix forms a vector space.

### Matrix Multiplication

Let $\mathcal{S}: U \to V$ and $\mathcal{T}: V \to W$ be linear maps.
Consider the composite map $\mathcal{T}\mathcal{S}: U \to W$, we have

$$
(\mathsf{T}\mathsf{S})_{ik} x_k = (\mathcal{T}\mathcal{S})(\mathbf{x})_i = \mathcal{T}(\mathcal{S}(\mathbf{x}))_i = \mathsf{T}_{ij}(\mathsf{S}_{jk} x_k) = (\mathsf{T}_{ij}\mathsf{S}_{jk}) x_k
$$

Hence,

$$
(\mathsf{T}\mathsf{S})_{ik} = \mathsf{T}_{ij}\mathsf{S}_{jk}
$$

Matrix multiplication is _associative_ but _not commutative_.

## Transpose

### Definition

Let $\mathsf{A} = \Set{A_{ij}}$ be a $m \times n$ matrix.
The _transpose_ $\mathsf{A}^\intercal$ of $\mathsf{A}$ is defined to be a $n \times m$ matrix with

$$
(\mathsf{A}^\intercal)_{ij} = (\mathsf{A})_{ji} = A_{ji}
$$

From definition, we can see that

$$
(\mathsf{A}^\intercal)^\intercal = \mathsf{A}
$$

Also,

$$
\begin{align*}
((\mathsf{A}\mathsf{B})^\intercal)_{ik} &= (\mathsf{A}\mathsf{B})_{ki} \\
&= \mathsf{A}_{kj} \mathsf{B}_{ji} \\
&= (\mathsf{B}^\intercal)_{ij} (\mathsf{A}^\intercal)_{jk} \\
&= (\mathsf{B}^\intercal \mathsf{A}^\intercal)_{ik}
\end{align*}
$$

Hence,

$$
(\mathsf{A}\mathsf{B})^\intercal = \mathsf{B}^\intercal \mathsf{A}^\intercal
$$

### Hermitian Conjugate

Let $\mathsf{A} = \Set{A_{ij}}$ be a matrix, with $A_{ij} \in \mathbb{C}$.
The _Hermitian conjugate_ or _conjugate transpose_ or _adjoint_ is defined to be

$$
\mathsf{A}^\dagger = (\mathsf{A}^\intercal)^\ast = (\mathsf{A}^\ast)^\intercal
$$

We also have

$$
\mathsf{A}^{\dagger\dagger} = \mathsf{A}
$$

and

$$
(\mathsf{A}\mathsf{B})^\dagger = \mathsf{B}^\dagger \mathsf{A}^\dagger
$$

### Symmetric Matrices

A square matrix is _symmetric_ if

$$
\mathsf{A} = \mathsf{A}^\intercal \iff A_{ij} = A_{ji}
$$

and is _antisymmetric_ if

$$
\mathsf{A} = -\mathsf{A}^\intercal \iff A_{ij} = -A_{ji}
$$

For an antisymmetric matrix, as $A_{11} = -A_{11}, A_{22} = -A_{22}, ...$, the diagonal elements have to be zero.

### Hermitian Matrices

A square complex matrix is _Hermitian_ if

$$
\mathsf{A} = \mathsf{A}^\dagger \iff A_{ij} = A_{ji}^\ast
$$

and is _skew-Hermitian_ if

$$
\mathsf{A} = -\mathsf{A}^\dagger \iff A_{ij} = -A_{ji}^\ast
$$

For Hermitian and skew-Hermitian matrices, the diagonal elements are real and pure imaginary respectively.

## Trace

The _trace_ of a square matrix is equal to the sum of the diagonal elements, i.e.

$$
Tr(\mathsf{A}) = A_{ii}
$$

Let $\mathsf{B}$ be $m \times n$ matrix and $\mathsf{C}$ be $n \times m$ matrix,
though $\mathsf{BC}$ and $\mathsf{CB}$ are not necessary equal (or even of different sizes),

$$
Tr(\mathsf{BC}) = (\mathsf{BC})_{ii} = B_{ij}C_{ji} = C_{ij}B_{ji} = (\mathsf{CB})_{ii} = Tr(\mathsf{CB})
$$

## Identity Matrix

The _unit_ or _identity_ matrix is defined to be

$$
\mathsf{I} = \begin{pmatrix}
1 & 0 & \dots & 0 \\
0 & 1 & \dots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \dots & 1 \\
\end{pmatrix} = \Set{\delta_{ij}}
$$

We have

$$
\begin{align*}
(\mathsf{IA})_{ij} &= \delta_{ik}A_{kj} = A_{ij} \\
(\mathsf{AI})_{ij} &= A_{ik}\delta_{kj} = A_{ij}
\end{align*}
$$

Hence,

$$
\mathsf{IA} = \mathsf{AI} = \mathsf{A}
$$

## Decomposition of Square Matrix

For a square matrix $\mathsf{B}$, we construct

$$
\begin{align*}
\mathsf{A} &= {1 \over 2} \left( \mathsf{B} - \mathsf{B}^\intercal \right) \\
\mathsf{S} &= {1 \over 2} \left( \mathsf{B} + \mathsf{B}^\intercal \right)
\end{align*}
$$

As

$$
\begin{align*}
\mathsf{A}^\intercal &= {1 \over 2} \left( \mathsf{B}^\intercal - \mathsf{B} \right) = -\mathsf{A} \\
\mathsf{S}^\intercal &= {1 \over 2} \left( \mathsf{B}^\intercal + \mathsf{B} \right) = \mathsf{S} \\
\mathsf{A} + \mathsf{S} &= \mathsf{B} \\
\end{align*}
$$

Let $n\sigma = Tr(\mathsf{S})$, so $\sigma = {1 \over n}S_{ii}$, and write

$$
\mathsf{E} = \mathsf{S} - \sigma\mathsf{I}
$$

$\mathsf{E}$ is a trace-free symmetric tensor, and

$$
\mathsf{B} = \sigma\mathsf{I} + \mathsf{E} + \mathsf{A}
$$

which represents the decomposition of a square matrix into _isotropic_, _symmetric trace-free_ and _antisymmetric_ parts.

## Inverse

Let $\mathsf{A}$ be a $m \times n$ matrix.
A $n \times m$ matrix $\mathsf{B}$ is a left inverse of $\mathsf{A}$ if $\mathsf{BA} = \mathsf{I}$ ($n \times n$).
A $n \times m$ matrix $\mathsf{C}$ is a right inverse of $\mathsf{A}$ if $\mathsf{AC} = \mathsf{I}$ ($m \times m$).

If both the left inverse $\mathsf{B}$ and right inverse $\mathsf{C}$ exist, then

$$
\mathsf{B} = \mathsf{BI} = \mathsf{BAC} = \mathsf{IC} = \mathsf{C}
$$

Let $\mathsf{A}$ be a square matrix. $\mathsf{A}$ is _invertible_ if there exists a matrix $\mathsf{A}^{-1}$, which is unique, such that

$$
\mathsf{A}^{-1}\mathsf{A} = \mathsf{A}\mathsf{A}^{-1} = \mathsf{I}
$$

We have

$$
(\mathsf{A}^{-1})^{-1} = \mathsf{A}
$$

and

$$
\mathsf{AB}^{-1} = \mathsf{B}^{-1}\mathsf{A}^{-1}
$$

## Orthogonal Matrix

A real square matrix is _orthogonal_ if

$$
\mathsf{A}\mathsf{A}^\intercal = \mathsf{I} = \mathsf{A}^\intercal\mathsf{A}
$$

i.e. if $\mathsf{A}$ is invertible and $\mathsf{A}^{-1} = \mathsf{A}^\intercal$

As

$$
(\mathsf{A}\mathsf{A}^\intercal)_{ij} = \mathsf{A}_{ik}(\mathsf{A}^\intercal)_{kj} = \mathsf{A}_{ik}\mathsf{A}_{jk} = \delta_{ij}
$$

it means the product of the $i$-th row with other rows is $0$ and product with itself is $1$.
It implies that the rows (and columns) of $\mathsf{A}$ form an orthonormal set.

A map $\mathcal{A}$ with orthogonal matrix $\mathsf{A}$ with repsect to an orthonormal basis transforms $\Set{\mathbf{e}_i}$ to an orthonormal set
(which may be right-handed or left handed depending on the sign of $\det \mathsf{A}$.

Rotation and reflection matrices are examples of orthogonal matrix.

The scalar product is preserved after the mapping represented by an orthogonal matrix with respect to an orthonormal basis as ($\mathbf{x} \cdot \mathbf{y} = \mathsf{x}^\intercal \mathsf{y}$ if the basis is orthonormal)

$$
\begin{align*}
\mathbf{x}' \cdot \mathbf{y}' &= (\mathsf{x}')^\intercal \mathsf{y}' \\
&= (\mathsf{x}^\intercal \mathsf{A}^\intercal) (\mathsf{A} \mathsf{y}) \\
&= \mathsf{x}^\intercal \mathsf{I} \mathsf{y} \\
&= \mathsf{x}^\intercal \mathsf{y} \\
&= \mathbf{x} \cdot \mathbf{y} \\
\end{align*}
$$

Hence, the map is an _isometry_, i.e. distances are preserved.

For a complex square matrix to be _unitary_ if its Hermitian conjugate is equal to its inverse, i.e.

$$
\mathsf{A}^\dagger = \mathsf{A}^{-1}
$$

which has similar properties as orthogonal real matrix.