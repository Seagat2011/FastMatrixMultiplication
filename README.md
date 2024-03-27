# FastMatrixMultiplication
Fast Matrix Multiplication Algorithm, Implemented in Javascript.
Certainly! Here's the LaTeX content converted to Markdown format:

---

Yes, it is possible to rewrite the expressions for \(c_{11}\), \(c_{12}\), \(c_{21}\), and \(c_{22}\) in a manner that includes all terms on the right-hand side (RHS) of the original equation, but arranges them such that unwanted terms cancel out, leaving only the desired terms. To achieve this, we need to introduce terms in such a way that they sum to zero for the parts we don't want to keep in each expression.

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
