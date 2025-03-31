---
description: Lecture1
---

# Lecture 1

## Logic and Proofs

**Logic** is directly related to digital circuit design, and **proofs by induction** play a central role in analyzing programs.

Modular arithmetic leads directly to schemes for computer security, and for storing and transmitting data so that it is immune to noise.

## Propositional Forms

* Proposition is simply a statement which is either <mark style="color:green;">true</mark> or <mark style="color:red;">false</mark>.
  *   Propositions should not include fuzzy terms.

      (1) Arnold Schwarzenegger often eats broccoli. (What is “often?")

      (2) Henry VIII was unpopular. (What is “unpopular?")
* Propositions may be joined together to form more complex statements.&#x20;
  * Let P, Q, and R be variables representing propositions (for example, P could stand for “3 is odd"). The simplest way of joining these propositions together is to use the connectives “and”, “or” and “not."
  * (1) Conjunction: P ∧Q (“P and Q"). True only when both P and Q are true.
  * (2) Disjunction: P ∨Q (“P or Q"). True when at least one of P and Q is true.
  * (3) Negation: ¬P (“not P"). True when P is false.
* Statements like these, with variables Statements like these, with variables, are called _**propositional forms**_.
  * <mark style="color:red;">tautology:</mark> A propositional form that is always true regardless of the truth values of its variables
  * <mark style="color:red;">contradiction:</mark> a statement such as P ∧¬P, which is always false.

## Truth Table

A useful tool for describing the possible values of a propositional form is a **truth table**.

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

The most important and subtle propositional form is an implication: $$P \implies Q$$

“P implies Q", P is called the hypothesis of the implication, and Q is the conclusion.

Here are some of the different ways of saying it:

1. if P, then Q;
2. Q if P;
3. P only if Q;
   1. Remember if P is true then Q must be true. this suggests that P can only be true if Q is true. since if Q is false P must have been false.
4. P is sufficient for Q;
   1. This means that proving P allows you to conclude that Q is true.
   2. Example: Showing n > 4 is sufficient for showing n > 3.
5. Q is necessary for P;
   1. For P to be true it is necessary that Q is true. Or if Q is false then we know that P is false.
   2. Example: It is necessary that n > 3 for n > 4.
6. Q unless not P.

## Implication Truth Table

<figure><img src=".gitbook/assets/image.png" alt="" width="372"><figcaption></figcaption></figure>

* Logically Equivalent: $$\lnot P \lor Q \equiv P \implies Q$$
* An implication $$P \implies Q$$ is false <mark style="color:red;">**only when**</mark> <mark style="color:red;"></mark><mark style="color:red;">P is true and Q is false</mark>.

{% hint style="info" %}
This means that many statements that sound nonsensical in English are true, mathematically speaking. Examples are statements like: “If pigs can fly, then horses can read" or “If 14 is odd then 1 + 2= 18." (These are statements that we never make in everyday life, but are perfectly natural in mathematics.) When an implication is stupidly true because the hypothesis is false, we say that it is _<mark style="color:red;">**vacuously true**</mark>_.
{% endhint %}

## Implication Properites

* Logically Equivalent: $$\lnot P \lor Q \equiv P \implies Q$$
  * $$P \implies Q \equiv \lnot P \lor Q \implies \lnot (\lnot Q) \lor \lnot P \implies \lnot Q \implies \lnot P$$.
* $$P \iff Q$$
  * If both P= ⇒Q and Q= ⇒P are true, then we say “P if and only if Q" (abbreviated “P iff Q"). Formally, we write P ⇐⇒Q. Note that P ⇐⇒Q is true only when P and Q have the same truth values (both true or both false).
* Contrapositive: ¬Q= ⇒¬P
* Converse: Q= ⇒P
* Note that P= ⇒Q and its contrapositive have the same truth values everywhere in their truth tables, so they are logically equivalent: (P= ⇒Q) ≡(¬Q= ⇒¬P).

<figure><img src=".gitbook/assets/image (1).png" alt="" width="563"><figcaption></figcaption></figure>

If chemical plant pollutes river, fish die.

Use propositional formulas to describe implication: $$((P \implies Q) \land P) \implies Q$$.

* False implies nothing, P False means Q can be True or False
* Anything implies true, P can be True or False when Q is True
* $$P \implies Q$$ and Q are True does not mean P is True
* $$P \implies Q$$ and P are True does mean Q is True .

## Predicates

Statements with free variables.

$$F (x)$$ = “Person x flew.”

$$C(x)$$ = “Person x went to Chicago

$$C(x) \implies F (x)$$. Theory from Wason’s. If person x goes to Chicago then person x flew.

<mark style="color:red;">Statements about boolean valued functions</mark>.

## Quantifiers

Propositions should have an underlying “universe" and the statements are then quantified over that universe.&#x20;

* 3 is odd.
* x2 + 3x = 5
* For all natural numbers n, n2 + n + 41 is prime.

To express these statements mathematically we need two quantifiers: The universal quantifier ∀(“for all”) and the existential quantifer ∃(“there exists”).

Note that in a finite universe, we can express existentially and universally quantified propositions without quantifiers, using disjunctions and conjunctions respectively.&#x20;

For example, if our universe U is {1, 2, 3, 4}, then ∃xP(x) is logically equivalent to P(1) ∨P(2) ∨P(3) ∨P(4), and ∀xP(x) is logically equivalent to P(1) ∧P(2) ∧P(3) ∧P(4).&#x20;

However, in an infinite universe, such as the natural numbers, this is not possible.

<mark style="color:red;">**Some statements can have multiple quantifiers**</mark>.&#x20;

* quantifiers do not commute.&#x20;
  * Example 1: \
    Quantifying over two universes: T= {times when I ride on the subway} and P = {people}.&#x20;
    * “Every time I ride the subway in New York, somebody gets stabbed." (it could be a different person each time): (∀t ∈T )(∃p ∈P)(p gets stabbed at time t)
    * “There is someone, such that every time I ride the subway in New York, that someone gets stabbed.": (∃p ∈P)(∀t ∈T )(p gets stabbed at time t)
  * Example 2:
    * (∀x ∈Z)(∃y ∈Z)(x < y): Given an integer, I can find a larger one. (True)
    * (∃y ∈Z)(∀x ∈Z)(x < y): There is a largest integer. (False)

## Much Ado About Negation

First, let’s look at how to negate conjunctions and disjunctions:

¬(P ∧Q) ≡(¬P ∨¬Q)

¬(P ∨Q) ≡(¬P ∧¬Q)

These two equivalences are known as De Morgan’s Laws, and they are quite intuitive: for example, if it is

not the case that P ∧Q is true, then either P or Q must be false.

Negating propositions involving quantifiers actually follows analogous laws. Let’s start with a simple example. Assume that the universe is {1, 2, 3, 4}and let P(x) denote the propositional formula “x2 > 10." Check that ∃xP(x) is true but ∀xP(x) is false. Observe that both¬(∀xP(x)) and ∃x¬P(x) are true because P(1) is false. Also note that both ∀x¬P(x) and¬(∃xP(x)) are false, since P(4) is true. The fact that each pair of statements had the same truth value is no accident, as the equivalences

¬(∀xP(x)) ≡∃x¬P(x)

¬(∃xP(x)) ≡∀x¬P(x)

are laws that hold for any proposition P quantified over any universe (including infinite ones).

It is helpful to think of English sentences to convince yourself (informally) that these laws are true. For

example, assume that we are working within the universe Z (the set of all integers), and that P(x) is the

proposition “x is odd." We know that the statement (∀xP(x)) is false, since not every integer is odd. Therefore, we expect its negation,¬(∀xP(x)), to be true. But how would you say the negation in English? Well, if it is not true that every integer is odd, then that must mean there is some integer which is not odd (i.e., even). How would this be written in propositional form? That’s easy, it’s just: (∃x¬P(x)).

To see a **more complex example, fix some universe and propositional formula P(x, y)**. Assume we have the proposition¬(∀x∃yP(x, y)) and we want to push the negation operator inside the quantifiers. By the above laws, we can do it as follows:

¬(∀x∃yP(x, y)) ≡∃x¬(∃yP(x, y)) ≡∃x∀y¬P(x, y).

Notice that we broke the complex negation into a smaller, easier problem as the negation propagated itself through the quantifiers. Note also that the quantifiers “flip” as we go.

Let’s look at a trickier example:

Write the sentence “there are at least three distinct integers x that satisfy P(x)" as a proposition using

quantifiers! One way to do it is

∃x∃y∃z(x ̸= y ∧y ̸= z ∧z ̸= x ∧P(x) ∧P(y) ∧P(z)).

(Here all quantifiers are over the universe Z of integers.) Now write the sentence “there are at most three

distinct integers x that satisfy P(x)" as a proposition using quantifiers. One way to do it is

∃x∃y∃z∀d(P(d) = ⇒d= x ∨d= y ∨d= z).

Here is an equivalent way to do it:

∀x∀y∀v∀z((x ̸= y ∧y ̸= v ∧v ̸= x ∧x ̸= z ∧y ̸= z ∧v ̸= z) = ⇒¬(P(x) ∧P(y) ∧P(v) ∧P(z))).

\[Check that you understand both of the above alternatives.] Finally, what if we want to express the sentence “there are exactly three distinct integers x that satisfy P(x)"? This is now easy: we can just use the conjunction of the two propositions above.

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
