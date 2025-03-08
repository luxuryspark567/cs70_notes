# 1, Sets and Mathematical Notation

## 1. Sets

A set is a well defined collection of objects.

* &#x20;$$x \in A$$: x is an element of A.
* $$y \notin A$$: y is not an element of A.
* $$A=B$$: Two sets A and B are said to be equal.

### Cardinality (The size of a set)

* $$|A|$$: Cardinality of A. e.g., 4 for $$A = \lbrace 1,2,3,4 \rbrace$$
* $$\emptyset$$: Empty set.

### Subsets and Proper Subsets

* $$A \subseteq B$$ or $$B \supseteq A$$, If every element of a set A is also in set B, then we say that A is a **subset** of B
* $$A \subset B$$ or $$B \supset A$$, A proper subset is a set A that is strictly contained in B, meaning that A excludes at least one element of B

### Intersections and Unions

* $$A \cap B$$, The intersection of a set A with a set B
  * $$A \cap B = \emptyset$$, Two sets are said to be disjoint
* $$A \cup B$$, The union of a set A with a set B
* Properties:
  * $$A \cup B = B \cup A$$
  * $$A \cup \emptyset = A$$
  * $$A \cap B = B \cap A$$
  * $$A \cap \emptyset = \emptyset$$

### Complements

$$B-A$$, or $$B \backslash A$$: $$B \backslash A = \lbrace x \in B | x \notin A \rbrace$$, the relative complement of A in B, or the set difference between B and A

Properties:

* $$A \backslash A = \emptyset$$
* $$A \backslash \emptyset = A$$
* $$\emptyset \backslash A = \emptyset$$

### Significant Sets

* $$\Bbb N$$ denotes the set of all natural numbers: $$\lbrace 0, 1, 2, 3, ...\rbrace$$.
* $$\Bbb Z$$ denotes the set of all integer numbers: $$\lbrace . . . ,−2,−1, 0, 1, 2, . . .\rbrace$$.
* $$\Bbb Q$$ denotes the set of all rational numbers: $$\lbrace ab |a, b ∈Z, b ̸= 0 \rbrace$$$$\lbrace \frac{a}{b} \mid a,b \in \mathbb{Z}, b \neq 0\rbrace$$.
* $$\Bbb R$$ denotes the set of all real numbers.
* $$\Bbb C$$ denotes the set of all complex numbers

### Products and Power Sets

* $$A \times B = \lbrace (a,b) | a \in A, b \in B \rbrace$$, The Cartesian product (also called the cross product) of two sets A and B
* $${\cal P}(S)$$, Given a set S, the power set of S, is the set of all subsets of S: $$\lbrace T |T \subseteq S \rbrace$$.
  * For example, if $$S= \lbrace 1, 2, 3 \rbrace$$, then the power set of S is: $${\cal P} (S) = \lbrace \lbrace \rbrace , \lbrace 1 \rbrace , \lbrace 2 \rbrace , \lbrace 3 \rbrace , \lbrace 1, 2 \rbrace , \lbrace 1, 3 \rbrace , \lbrace 2, 3 \rbrace , \lbrace 1, 2, 3 \rbrace \rbrace$$. Note that, if $$|S|= k$$, then $$|{\cal P}(S)|= 2^k$$. \[Why?]

## 2. Mathematical notation

### Sums and Products

* $$\Sigma ^{n} _{i=m}f(i)$$, $$f(m) + f(m+1) +...+ f(n)$$
* $$\Pi ^{n} _{i=m}f(i)$$, $$f(m)f(m+1)...f(n)$$

### Universal and Existential Quantifiers

* universal quantifier $$\forall$$ ("for all")
  * the statement $$(\forall n \in \Bbb N)(n^2 + n + 41 \space is \space prime)$$ is false.
* existential quantifier $$\exists$$ ("there exists")
  * $$(\exists x \in \Bbb Z)(x < 2 \space and \space x^2 = 4)$$ is True
* Use Both:
  * $$(\forall x \in \Bbb Z)( \exists y \in \Bbb Z)(y > x)$$, given an integer, we can find a larger one, True
  * $$( \exists y \in \Bbb Z)(\forall x \in \Bbb Z)(y > x)$$, there is a largest integer, False

should be updated.



