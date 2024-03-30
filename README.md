## Fast Matrix Multiplication Algorithm, Implemented in Javascript:
  
// Algorithm 1 //  
// 8 Multiplications //  
// 4 Additions //  
// Time complexity O(N^3) //  

|      |      |     |      |      |     |      |      |
|------|------|-----|------|------|-----|------|------|
| `a1` | `a2` | `*` | `b1` | `b2` | `=` | `c1` | `c2` |
| `a3` | `a4` |     | `b3` | `b4` |     | `c3` | `c4` | 

c11 = a11 * b11 + a12 * b21  
c12 = a11 * b12 + a12 * b22  
c21 = a21 * b11 + a22 * b21  
c22 = a21 * b12 + a22 * b22  

---

// Algorithm 2 //  
// 8 Multiplications //  
// 4 Additions //  
// Time complexity O(N^3) //  

|      |      |     |      |      |     |      |      |
|------|------|-----|------|------|-----|------|------|
| `a1` | `a2` | `*` | `b1` | `b2` | `=` | `c1` | `c2` |
| `a3` | `a4` |     | `b3` | `b4` |     | `c3` | `c4` | 

a = a11 * b11  
b = a12 * b21  
c = a11 * b12  
d = a12 * b22  
e = a21 * b11  
f = a22 * b21  
g = a21 * b12  
h = a22 * b22  
  
c11 = a + b  
c12 = c + d  
c21 = e + f  
c22 = g + h  

---

// Algorithm 3 - Volker Strassen 69 - Fastest //  
// 7 Multiplications //  
// 15 Additions //  
// 10 Subtractions //  
// Time complexity O(N^2.8074) //  
  
|      |      |     |      |      |     |      |      |
|------|------|-----|------|------|-----|------|------|
| `a1` | `a2` | `*` | `b1` | `b2` | `=` | `c1` | `c2` |
| `a3` | `a4` |     | `b3` | `b4` |     | `c3` | `c4` | 
  
m1 = (a2 - a4)(b1 + b4)  
m2 = (a3 + a4)(b1)  
m3 = (b2 - b4)(a1)  
m4 = (b3 - b1)(a4)  
m5 = (a1 + a2)(b4)  
m6 = (a3 - a1)(b1 + b2)  
m7 = (a2 - a4)(b3 + b4)  
  
c1 = m1 + m4 - m5 + m7  
c2 = m3 + m5  
c3 = m2 + m4  
c4 = m1 - m2 + m3 + m6  

---
## Details

His reductions -- albeit algorithmically equivalent, are not **algebraically** equivalent. A crucial distinction between algorithmic equivalence and algebraic equivalence, particularly in the context of Strassen's algorithm for matrix multiplication should be made. Let's clarify these concepts:

- **Algorithmic Equivalence** refers to two algorithms performing the same task (in this case, matrix multiplication) with potentially different methods or steps but ultimately producing the same result. The efficiency or the number of operations might vary, but the output is identical given the same input.

- **Algebraic Equivalence** means that two expressions are identical in value for all values of their variables, following directly from algebraic laws and identities. In the context of matrix multiplication, this would mean performing the exact same series of algebraic operations. Directly manipulating these expressions reveals that the algebraic simplification and rearrangement through this (the Strassen) method might not straightforwardly reduce to the naive form due to its design to optimize and reduce computational steps, particularly in reducing the number of multiplications.

Strassen's algorithm, by introducing a clever rearrangement of operations and exploiting mathematical properties, reduces the number of multiplication operations required to perform matrix multiplication. This reduction is achieved not by finding an algebraically equivalent form of the naive multiplication method (where each element of the resulting matrix is computed directly from the corresponding row and column multiplications) but by transforming the problem into one where fewer multiplications can produce the necessary intermediate values for the final result.

The key insight of Strassen and similar algorithms is that they find a more efficient pathway (algorithmically) to arrive at the same result as the naive approach. They do this not by performing the same operations in a slightly optimized manner but by fundamentally changing the operations performed. This means:

- They are not algebraically equivalent in the sense that they perform the same operations in a different order or simply optimize the existing algebraic operations. Instead, they reorganize the computation itself, introducing auxiliary variables and exploiting mathematical properties to reduce the number of multiplications.
  
- The algorithms are equivalent in the sense that for any given identical inputs, they will produce identical outputs, despite the internal process being different. This equivalence is crucial for validating the correctness of Strassen’s algorithm and its utility as a replacement for the naive approach in practical applications.

Thus, Strassen’s reductions are algorithmically equivalent to the naive approach because they result in the same final matrix product, but they are not algebraically equivalent in terms of performing the same series of algebraic operations. This distinction is essential for understanding the innovation and efficiency improvements brought about by Strassen's algorithm and subsequent developments in fast matrix multiplication methods.

## ETC.

It is possible to rewrite the expressions for \(c_{11}\), \(c_{12}\), \(c_{21}\), and \(c_{22}\) in a manner that includes all terms on the right-hand side (RHS) of the original equation, but arranges them such that unwanted terms cancel out, leaving only the desired terms. To achieve this, we need to introduce terms in such a way that they sum to zero for the parts we don't want to keep in each expression.

The expressions you've provided are essentially the result of matrix multiplication, where the resulting matrix \(C\) is the product of matrices \(A\) and \(B\) in standard matrix multiplication form:

\[ C = AB \]

where:

- \(c_{11} = a_{11} \cdot b_{11} + a_{12} \cdot b_{21}\)
- \(c_{12} = a_{11} \cdot b_{12} + a_{12} \cdot b_{22}\)
- \(c_{21} = a_{21} \cdot b_{11} + a_{22} \cdot b_{21}\)
- \(c_{22} = a_{21} \cdot b_{12} + a_{22} \cdot b_{22}\)

To include all terms in such a way that they cancel out, leaving the original terms, we can add and subtract the same terms within each equation. Let's do this explicitly for each \(c_{ij}\):

### For \(c_{11}\):

- To include all terms but ensure that only \(a_{11} \cdot b_{11} + a_{12} \cdot b_{21}\) remains, we can add \(0\) in the form of \((a_{21} \cdot b_{12} + a_{22} \cdot b_{22}) - (a_{21} \cdot b_{12} + a_{22} \cdot b_{22})\), and similarly for any other terms we wish to cancel.

### For \(c_{12}\), \(c_{21}\), and \(c_{22}\):

- A similar approach is used for the other elements of \(C\), adding and subtracting the same terms to ensure the sum of added terms is zero.

This approach is more of a theoretical exercise or a mathematical trick rather than a practical method, as it doesn't change the underlying operation or result. It just rewrites the expressions in a more complex form. In practice, this might not be useful or efficient, especially for computation, but it can serve as an interesting mathematical illustration.

To demonstrate this for one of the equations explicitly:

\[ c_{11} = a_{11} \cdot b_{11} + a_{12} \cdot b_{21} + (a_{11} \cdot b_{12} + a_{12} \cdot b_{22} - a_{11} \cdot b_{12} - a_{12} \cdot b_{22}) + (a_{21} \cdot b_{11} + a_{22} \cdot b_{21} - a_{21} \cdot b_{11} - a_{22} \cdot b_{21}) + (a_{21} \cdot b_{12} + a_{22} \cdot b_{22} - a_{21} \cdot b_{12} - a_{22} \cdot b_{22}) \]

Here, for each term that is not part of the original \(c_{11}\), we add and then subtract the same term, effectively adding \(0\) but including all possible terms in the expression. This can be done similarly for \(c_{12}\), \(c_{21}\), and \(c_{22}\), although it's a bit convoluted for practical purposes.

Certainly! To include all terms on the right-hand side in each of the statements and ensure they cancel out to leave only the desired terms remaining, we can add and subtract the unwanted terms appropriately. This technique allows us to formally include every term but ensure that only the specified terms effectively contribute to each equation. Let's illustrate this for \(c_{12}\), \(c_{21}\), and \(c_{22}\) to complete the example:

### For \(c_{12} = a_{11} \times b_{12} + a_{12} \times b_{22}\)

To include all terms while ensuring only \(a_{11} \times b_{12} + a_{12} \times b_{22}\) effectively remain, we can write:

\[
c_{12} = a_{11} \times b_{12} + a_{12} \times b_{22} + (a_{11} \times b_{11} + a_{12} \times b_{21} - a_{11} \times b_{11}
- \(a_{12} \times b_{21}) + (a_{21} \times b_{11} + a_{22} \times b_{21} - a_{21} \times b_{11} - a_{22} \times b_{21}) + (a_{21} \times b_{12} + a_{22} \times b_{22} - a_{21} \times b_{12} - a_{22} \times b_{22})
\]

### For \(c_{21} = a_{21} \times b_{11} + a_{22} \times b_{21}\)

Similarly, to only have \(a_{21} \times b_{11} + a_{22} \times b_{21}\) effectively contribute, we write:

\[
c_{21} = a_{21} \times b_{11} + a_{22} \times b_{21} + (a_{11} \times b_{11} + a_{12} \times b_{21} - a_{11} \times b_{11} - a_{12} \times b_{21}) + (a_{11} \times b_{12} + a_{12} \times b_{22} - a_{11} \times b_{12} - a_{12} \times b_{22}) + (a_{21} \times b_{12} + a_{22} \times b_{22} - a_{21} \times b_{12} - a_{22} \times b_{22})
\]

### For \(c_{22} = a_{21} \times b_{12} + a_{22} \times b_{22}\)

And for \(c_{22}\), to ensure \(a_{21} \times b_{12} + a_{22} \times b_{22}\) are the only effective terms, we use:

\[
c_{22} = a_{21} \times b_{12} + a_{22} \times b_{22} + (a_{11} \times b_{11} + a_{12} \times b_{21} - a_{11} \times b_{11} - a_{12} \times b_{21}) + (a_{11} \times b_{12} + a_{12} \times b_{22} - a_{11} \times b_{12} - a_{12} \times b_{22}) + (a_{21} \times b_{11} + a_{22} \times b_{21} - a_{21} \times b_{11} - a_{22} \times b_{21})
\]

By adding and subtracting the unwanted terms in this way, each equation formally includes all terms on the right-hand side while ensuring that only the desired terms remain effective. This method cleverly maintains the integrity of each original equation while theoretically considering the entirety of the polynomial's terms.
