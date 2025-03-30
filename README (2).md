---
description: Lecture1
---

# Lecture 1

## Propositions

Statements that are <mark style="color:blue;">true</mark> or <mark style="color:red;">false</mark>.

## Propositional Forms

<figure><img src=".gitbook/assets/截屏2025-03-30 16.02.12.png" alt="" width="375"><figcaption></figcaption></figure>

* $$(T \land Q) \equiv Q$$，看左边的表，P为T的时候，结果为Q。
* &#x20;$$(F \land Q) \equiv F$$
* &#x20;$$(T \lor Q) \equiv T$$, 看右边的表，P等于T的时候，结果为T
* &#x20;$$(F \lor Q) \equiv Q$$

Use truth table to decide the logical equivalence of propositional forms.

$$\lnot (P \lor Q) \equiv \lnot P \land \lnot Q$$, $$\lnot (P \land Q) \equiv \lnot P \lor \lnot Q$$

<figure><img src=".gitbook/assets/截屏2025-03-27 23.18.25.png" alt="" width="275"><figcaption></figcaption></figure>

Distributive

$$P \land (Q \lor R) \equiv (P \land Q) \lor (P\land R)$$

Simplify: $$(T \land Q) \equiv Q$$, $$(F \land Q) \equiv F$$

Cases:&#x20;

* P is True.
  * LHS: $$T \land (Q \lor R) \equiv (Q \lor R)$$
  * RHS: $$(T \land Q) \lor (T \land R) \equiv (Q \lor R)$$
* P is False
  * LHS: $$F \land (Q \lor R) \equiv F$$
  * RHS: $$(F \land Q) \lor (F \land R) \equiv F$$

$$P \lor (Q \land R) \equiv (P \lor Q) \land (P\lor R)$$

Simplify: $$(T \lor Q) \equiv T$$, $$(F \lor Q) \equiv Q$$

Foil:

$$(A \lor B) \land (C \lor D) \equiv (A \land C) \lor (A \land D) \lor (B \land C) \lor (B \land D)$$

$$(A \land B) \lor (C \land D) \equiv (A \lor C) \land (A \lor D) \land (B \lor C) \land (B \lor D)$$

## Implication

$$P \implies Q$$ interpreted as: If P, then Q.

True Statements: P, $$P \implies Q$$.

Conclude: Q is True.

The statement “$$P \implies Q$$”

only is False if P is True and Q is False .

False implies nothing

P False means Q can be True or False

Anything implies true.

P can be True or False when Q is True

If chemical plant pollutes river, fish die.

If fish die, did chemical plant pollute river?

Not necessarily.

$$P \implies Q$$ and Q are True does not mean P is True

Be careful!

Instead we have:

$$P \implies Q$$ and P are True does mean Q is True .

The chemical plant pollutes river. Can we conclude fish die?

Some Fun: use propositional formulas to describe implication?

$$((P \implies Q) \land P) \implies Q$$.

### Implication and English

$$P \implies Q$$&#x20;

* If P, then Q.
* Q if P.
  * Just reversing the order.
* P only if Q.
  * Remember if P is true then Q must be true. this suggests that P can only be true if Q is true. since if Q is false P must have been false.
* P is sufficient for Q.
  * This means that proving P allows you to conclude that Q is true.
  * Example: Showing n > 4 is sufficient for showing n > 3.
* Q is necessary for P.
  * For P to be true it is necessary that Q is true. Or if Q is false then we know that P is false.
  * Example: It is necessary that n > 3 for n > 4.

### True Table for Implication

<figure><img src=".gitbook/assets/image.png" alt="" width="375"><figcaption></figcaption></figure>

Logically Equivalent: $$\lnot P \lor Q \equiv P \implies Q$$

### Contrapositive, Converse

* Contrapositive of $$P \implies Q$$ is $$\lnot Q \implies \lnot P$$.
* If the plant pollutes, fish die.
* If the fish don’t die, the plant does not pollute. (contrapositive)
* If you stand in the rain, you get wet.
* If you did not stand in the rain, you did not get wet. (not contrapositive!) converse!
* If you did not get wet, you did not stand in the rain.(contrapositive.)

Logically equivalent! Notation: $$\equiv$$.

$$P \implies Q \equiv \lnot P \lor Q \implies \lnot (\lnot Q) \lor \lnot P \implies \lnot Q \implies \lnot P$$.

* Converse of $$P \implies Q$$ is $$Q \implies P$$.
* If fish die the plant pollutes.
* Not logically equivalent!
* Definition: If $$P \implies Q$$ and $$Q \implies P$$ is $$P$$ if and only if $$Q$$ or $$P \iff Q$$.
* (Logically Equivalent: $$\iff$$ )

## Predicates

Statements with free variables.

$$F (x)$$ = “Person x flew.”

$$C(x)$$ = “Person x went to Chicago

$$C(x) \implies F (x)$$. Theory from Wason’s. If person x goes to Chicago then person x flew.

<mark style="color:red;">Statements about boolean valued functions</mark>.

## Quantifiers

* "There exists" quantifier
  * $$(\exists x \in S)(P(x))$$ means “There exists an $$x$$ in $$S$$ where $$P(x)$$ is true.”
* "For all" quantifier
  * $$(\forall x \in S) (P(x))$$. means “For all $$x$$ in $$S$$, $$P(x)$$ is True .”



## Quantifiers..not commutative.

In English: “there is a natural number that is the square of every natural number”.

$$(\exist y \in N) (\forall x \in N) (y= x^2)$$ <mark style="color:red;">False</mark>

In English: “the square of every natural number is a natural number.”

$$(\forall x \in N)(\exist y \in N) (y = x^2)$$ <mark style="color:blue;">True</mark>

## Quantifiers....negation...DeMorgan again.

Consider

$$\lnot (\forall x \in S)(P(x))$$,

not all x in S, P(x) holds

English: there is an $$x$$ in $$S$$ where $$P(x)$$ does not hold.

That is,

$$\lnot (\forall x \in S)(P(x)) \iff \exist (x \in S)(\lnot P(x))$$.

What we do in this course! We consider claims.

Claim: $$(\forall x) P(x)$$ “For all inputs x the program works.”

For False , find x, where$$\lnot P(x)$$.

Counter example.

Bad input.

Case that illustrates bug.

For True : prove claim. Next lectures...



Negation of exists.

Consider

$$\lnot (\exist x \in S)(P(x))$$

English: means that there is no $$x \in S$$ where $$P(x)$$ is true. English:

means that for all $$x \in S$$, $$P(x)$$ does not hold.

That is,

$$\lnot (\exist x \in S)(P(x))  \iff \forall (x \in S) \lnot P(x)$$.



## Summary.

Propositions are statements that are true or false.

Proprositional forms use ∧, ∨, ¬.

Propositional forms correspond to truth tables.

Logical equivalence of forms means same truth tables.

Implication: $$P \implies Q \iff \lnot P \lor Q$$.

Contrapositive:$$\lnot Q \implies \lnot P$$

Converse: $$Q \implies P$$

Predicates: Statements with “free” variables.

Quantifiers: $$\forall x P(x)$$, $$\exist y Q(y )$$

Now can state theorems! And disprove false ones!

DeMorgans Laws: “Flip and Distribute negation”

$$\lnot (P \lor Q) \iff (\lnot P \land \lnot Q)$$

$$\lnot \forall x P(x) \iff \exist x \lnot P(x)$$.
