---
description: Robert Lu
---

# Lecture 1

## Logic and Proofs

* **Logic** is directly related to digital circuit design, and **proofs by induction** play a central role in analyzing programs.
* **Modular arithmetic** leads directly to schemes for computer security, and for storing and transmitting data so that it is immune to noise.

## Propositional Forms

* Proposition is simply a statement which is either <mark style="color:green;">true</mark> or <mark style="color:red;">false</mark>.
  * “3 is odd"
  * Propositions should not include fuzzy terms.
    * Arnold Schwarzenegger often eats broccoli. (What is “often?")
    * Henry VIII was unpopular. (What is “unpopular?")
* Propositions **may be joined together** to form more complex statements. \
  Let P, Q, and R be variables representing propositions. S<mark style="color:red;">tatements like these, with variables, are called</mark> <mark style="color:red;"></mark>_<mark style="color:red;">**propositional forms**</mark>_.
  * **Conjunction**: P ∧Q (“P and Q"). True only when both P and Q are true.
  * **Disjunction**: P ∨Q (“P or Q"). True when at least one of P and Q is true.
  * **Negation**: ¬P (“not P"). True when P is false.

{% hint style="info" %}
Note that P ∨¬P is always true, regardless of the truth value of P. A propositional form that is <mark style="color:red;">always true</mark> regardless of the truth values of its variables is called a <mark style="color:red;">**tautology**</mark>. Conversely, a statement such as P ∧¬P, which is <mark style="color:red;">always false</mark>, is called a <mark style="color:red;">**contradiction**</mark>.
{% endhint %}

## Truth Table

A useful tool for <mark style="color:red;">describing</mark> <mark style="color:red;"></mark><mark style="color:red;">**the possible values**</mark> <mark style="color:red;"></mark><mark style="color:red;">of a propositional form</mark> is a **truth table**.

<figure><img src=".gitbook/assets/截屏2025-03-30 16.02.12.png" alt="" width="375"><figcaption></figcaption></figure>

* Intuitive:
  * $$(T \land Q) \equiv Q$$
  * &#x20;$$(F \land Q) \equiv F$$
  * &#x20;$$(T \lor Q) \equiv T$$
  * &#x20;$$(F \lor Q) \equiv Q$$
* De Morgan’s Laws
  * $$\lnot (P \lor Q) \equiv \lnot P \land \lnot Q$$
  * $$\lnot (P \land Q) \equiv \lnot P \lor \lnot Q$$

<figure><img src=".gitbook/assets/截屏2025-03-27 23.18.25.png" alt="" width="275"><figcaption></figcaption></figure>

* Distributive
  * $$P \land (Q \lor R) \equiv (P \land Q) \lor (P\land R)$$, to prove is to consider P is False and P is True
  * $$P \lor (Q \land R) \equiv (P \lor Q) \land (P\lor R)$$
* Foil
  * $$(A \lor B) \land (C \lor D) \equiv (A \land C) \lor (A \land D) \lor (B \land C) \lor (B \land D)$$
  * $$(A \land B) \lor (C \land D) \equiv (A \lor C) \land (A \lor D) \land (B \lor C) \land (B \lor D)$$

## Implication

<mark style="color:red;">The most important and subtle propositional form is an implication</mark>: $$P \implies Q$$, “P implies Q"

* P is the hypothesis
* Q is the conclusion.

Here are some of the different ways of saying it:

1. if P, then Q;
2. Q if P;
3. P only if Q: P can only be true if Q is true. since if Q is false P must have been false.
4. P is sufficient for Q: Proving P allows you to conclude that Q is true.
5. Q is necessary for P: P to be true it is necessary that Q is true. Or if Q is false then we know that P is false.
6. Q unless not P.

## Contrapositive and Converse

* Contrapositive: $$\lnot Q \implies \lnot P$$
* Converse: $$Q \implies P$$

## Truth Table of Implication

Example: If chemical plant pollutes river, fish die.

* P: chemical plant pollutes river.
* Q: fish die.

<figure><img src=".gitbook/assets/image.png" alt="" width="248"><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (1).png" alt="" width="563"><figcaption></figcaption></figure>

* An implication $$P \implies Q$$ is false <mark style="color:red;">**only when**</mark> <mark style="color:red;"></mark><mark style="color:red;">P is true and Q is false</mark>.
* $$P \iff Q \equiv (P \implies Q) \land (Q \implies P)$$
  * “P if and only if Q" (abbreviated “P iff Q"). Formally, we write $$P \iff Q$$.&#x20;
  * Note that $$P \iff Q$$ is true only when <mark style="color:red;">P and Q have the same truth values (both true or both false)</mark>.
* De Morgan’s Laws: $$P \implies Q \equiv \lnot Q \implies \lnot P$$
  * $$P \implies Q \equiv \lnot P \lor Q \equiv \lnot (\lnot Q) \lor \lnot P \equiv \lnot Q \implies \lnot P$$.
* Use propositional formulas to describe implication: $$((P \implies Q) \land P) \implies Q$$.
* If $$P \implies Q$$ is True:
  * <mark style="color:red;">**False implies nothing**</mark>, P is False means Q can be True or False.
  * <mark style="color:red;">**Anything implies true**</mark>, P can be True or False when Q is True.
    * This means that <mark style="color:red;">many statements that sound nonsensical in English are true.</mark> Examples are statements like: “<mark style="color:red;">If pigs can fly, then horses can read</mark>" or “If 14 is odd then 1 + 2= 18." (These are statements that we never make in everyday life, but are perfectly natural in mathematics.) When an implication is stupidly true because the hypothesis is false, we say that it is _<mark style="color:red;">**vacuously true**</mark>_.
* If  $$P \implies Q$$  and Q are True, does <mark style="color:red;">**not**</mark> mean P is True.
* If  $$P \implies Q$$  and P are True, does mean Q is True .

## Predicates

Statements with free variables (<mark style="color:red;">Statements about boolean valued functions</mark>.).

$$F (x)$$ = “Person x flew.”

$$C(x)$$ = “Person x went to Chicago

$$C(x) \implies F (x)$$. Theory from Wason’s. If person x goes to Chicago then person x flew.

## Quantifiers

Propositions should <mark style="color:red;">have an underlying “universe"</mark> and the statements are then <mark style="color:red;">quantified over that universe</mark>.&#x20;

* 3 is odd.
* x2 + 3x = 5
* For all natural numbers n, n2 + n + 41 is prime.

To express these statements mathematically we need <mark style="color:red;">two quantifiers</mark>: &#x20;

* The universal quantifier <mark style="color:red;">∀(“for all”)</mark>
  * $$(\exists x \in S)(P(x))$$ means “There exists an $$x$$ in $$S$$ where $$P(x)$$ is true.”
* the existential quantifer <mark style="color:red;">∃(“there exists”)</mark>
  * $$(\forall x \in S) (P(x))$$. means “For all $$x$$ in $$S$$, $$P(x)$$ is True .”

{% hint style="info" %}
Note that in a finite universe, we can express existentially and universally quantified propositions without quantifiers, <mark style="color:red;">using disjunctions and conjunctions respectively</mark>.&#x20;

For example, if our universe U is {1, 2, 3, 4}, then ∃xP(x) is logically equivalent to P(1) ∨P(2) ∨P(3) ∨P(4), and ∀xP(x) is logically equivalent to P(1) ∧P(2) ∧P(3) ∧P(4).&#x20;

However, in an infinite universe, such as the natural numbers, this is not possible.
{% endhint %}

## **Statements with Multiple Quantifiers**

<mark style="color:red;">Quantifiers do not commute</mark>.&#x20;

* Example 1: \
  Quantifying over two universes: T= {times when I ride on the subway} and P = {people}.&#x20;
  * $$(\forall t \in T )(\exist p \in P)(p \ gets\ stabbed\ at\ time\ t)$$:
    * “Every time I ride the subway in New York, somebody gets stabbed." (it could be a different person each time):&#x20;
  * $$(\exist p \in P)(\forall t \in T )(p \ gets\ stabbed\ at\ time\ t)$$
    * “There is someone, such that every time I ride the subway in New York, that someone gets stabbed.":&#x20;
* Example 2:
  * $$(\forall x \in Z)(\exist y \int Z)(x < y)$$:&#x20;
    * Given an integer, I can find a larger one. (True)
  * $$(\exist y \in Z)(\forall x \in Z)(x < y)$$:&#x20;
    * There is a largest integer. (False)

## Much Ado About Negation

### De Morgan’s Laws

* ¬(P ∧Q) ≡(¬P ∨¬Q)
* ¬(P ∨Q) ≡(¬P ∧¬Q)

### Analogous laws

negating propositions involving quantifiers follows analogous law.

* ¬(∀xP(x)) ≡∃x¬P(x)
* ¬(∃xP(x)) ≡∀x¬P(x)

Example:

* The universe: {1, 2, 3, 4}
* P(x) : x > 10.

∃xP(x) is true and ∀xP(x) is false

¬(∀xP(x)) and ∃x¬P(x) are true, since P(1) is false.

∀x¬P(x) and¬(∃xP(x)) are false, since P(4) is true.&#x20;

### Analogous laws for more complex example

to push the negation operator inside the quantifiers (the quantifiers “flip” as we go):

¬(∀x∃yP(x, y)) ≡∃x¬(∃yP(x, y)) ≡∃x∀y¬P(x, y).

Let’s look at a trickier example:

* $$P: \exist x \exist y \exist z(x \neq y \land y \neq z \land z \neq x \land P(x) \land P(y) \land P(z))$$.
  * “there are at least three distinct integers x that satisfy P(x)"
* $$Q:  \exist x \exist y \exist z \forall d (P(d) \implies d = x \lor d = y \lor d= z)$$.
  * “there are at most three distinct integers x that satisfy P(x)"
  * Here is an equivalent way to do it:
  * $$\forall x \forall y \forall v \forall z ((x \neq y \land y \neq v \land v \neq x \land x \neq z \land y \neq z \land v \neq z) \implies \lnot (P(x) \land P(y) \land P(v) \land P(z)))$$
* $$P \land Q$$
  * “there are exactly three distinct integers x that satisfy P(x)", This is now easy: we can just use the conjunction of the two propositions above.

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
