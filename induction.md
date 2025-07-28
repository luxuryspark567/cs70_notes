# Induction

Principle of Induction.

P(0) ∧(∀n ∈N)P(n) ⇒P(n + 1)

Then we get:

(∀n ∈N)P(n).

“But aren’t you starting with the statement to prove the statement?”

In general, ∀n ∈N P(n) ̸≡P(n + 1).

“P(n)” is “different” statement than “P(n + 1)” for any fixed n.

Start with statement P(n) and prove P(n + 1).

Is this a statement or a predicate?

A little subtle;

we fix the natural number n (bind n in ∀n.)

BTW: Can you do induction over the reals? No.

The notion of “next” is undefinable.

## Two color theorem: example.

Any map formed by dividing the plane into regions by drawing straight

lines can be properly colored with two colors.

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Fact: Swapping red and blue gives another valid colors.

Base Case.

1\. Add line.

2\. Get inherited color for split regions

3\. Switch on one side of new line.

(Fixes conflicts along line, and makes no new ones.)

Algorithm gives P(k ) = ⇒P(k + 1).

{% hint style="danger" %}
This induction process give out an algorithm, to color the map, which is very important in algorithm design in computer science.

This is recursion.
{% endhint %}

## Strenthening Induction Hypothesis

Assume more to make the prove more powerful.

Theorem: The sum of the first n odd numbers is a perfect square.

Theorem: The sum of the first n odd numbers is n2

k th odd number is 2(k−1) + 1.

Base Case 1 (first odd number) is 12

Induction Hypothesis Sum of first k odds is perfect square a2 = k 2

Induction Step 1. The (k + 1)st odd number is 2k + 1.

2\. Sum of the first k + 1 odds is

a2 + 2k + 1= k 2 + 2k + 1

????

3\. k 2 + 2k + 1= (k + 1)2

... P(k+1)!

you want to prove some therom, and it does not work out, maybe you want to prove a slighter stronger therom.

With the stronger therom, then you can use the stronger statement as your induction hypothethys, to help you build up a proof.

## Tiling Cory Hall Courtyard.

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

## Strong Induction

Theorem: Every natural number n > 1 can be written as a (possibly

trivial) product of primes.

Definition: A prime n has exactly 2 factors 1 and n.

Base Case: n = 2.

Induction Step:

P(n) =“n can be written as a product of primes. “

Either n + 1 is a prime or n + 1= a·b where 1 < a, b < n + 1.

P(n) says nothing about a, b!

Strong Induction Principle: If P(0) and

(∀k ∈N)((P(0) ∧. . . ∧P(k )) = ⇒P(k + 1)),

then (∀k ∈N)(P(k )).

P(0) = ⇒P(1) = ⇒P(2) = ⇒P(3) = ⇒···

Strong induction hypothesis: “a and b are products of primes”

\= ⇒ “n + 1= a·b = (factorization of a)(factorization of b)”

n + 1 can be written as the product of the prime factors!

## Well Ordering Principle and Induction.

If (∀n)P(n) is not true, then (∃n)¬P(n).

Consider smallest m, with¬P(m), m ≥0

P(m−1) = ⇒P(m) must be false (assuming P(0) holds.)

This is a proof of the induction principle!

I.e.,

(¬∀n)P(n) = ⇒((∃n)¬(P(n−1) = ⇒P(n)).

(Contrapositive of Induction principle (assuming P(0))

It assumes that there is a smallest m where P(m) does not hold.

<mark style="color:blue;">The Well ordering principle states that for any subset of the natural numbers there is a smallest element.</mark>

Smallest may not be what you expect: the well ordering principal

holds for rationals but with different ordering!!

E.g. Reduced form is “smallest” representation of rational number

a/b.

Thm: All natural numbers are interesting.

0 is interesting...

Let n be the first uninteresting number.

But n−1 is interesting and n is uninteresting,

so n is the first uninteresting number.

But being first is interesting!

Thus, there is no smallest uninteresting natural number.

Thus: All natural numbers are interesting.

<mark style="color:$info;">Think of the first smallest counter example and prove that it can't exsit</mark>







