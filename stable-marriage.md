# Stable Marriage

## Stable Marriage Problem

* Small town with n boys and n girls.
* Each girl has a ranked preference list of boys.
* Each boy has a ranked preference list of girls.

How should they be matched?

## Count the ways..

Maximize total satisfaction.

Maximize number of first choices.

Maximize worse off.

Minimize difference between preference ranks.



## The Traditional Marriage Algorithm.

Each Day:

1\. Each boy proposes to his favorite girl on his list.

2\. Each girl rejects all but her favorite proposer (whom she puts on a string.)

3\. Rejected boy crosses rejecting girl off his list.

Stop when each girl gets exactly one proposal.

Does this terminate?

...produce a pairing?

....a stable pairing?

Do boys or girls do “better”?

## It gets better every day for girls..

Improvement Lemma: It just gets better for girls.

If on day t a girl g has a boy b on a string,

any boy, b′, on g’s string for any day t′> t

is at least as good as b.

Let’s apply lemma.

Girl “Alice” has boy “Bob” on string on day 5.

She has boy “Jim” on string on day 7.

Does Alice prefer “Jim” or “Bob”?

g - ’Alice’, b - ’Bob’, b′- ’Jim’, t= 5, t′

\= 7.

Improvement Lemma says she prefers ’Jim’.

On day 10, could Alice still have “Jim” on her string? Yes.

She likes her day 10 boy at least as much as her day 7 boy.

Here, b= b′

.

Why is lemma true?

Proof Idea: Because she can always keep the previous boy on the

string.

Improvement Lemma: It just gets better for girls.

If on day t a girl g has a boy b on a string, any boy, b′, on g’s string for

any day t′> t is at least as good as b.

Proof:

P(k )- - “boy on g’s string is at least as good as b on day t + k”

P(0)– true. Girl has b on string.

Assume P(k ). Let b′be boy on string on day t + k.

On day t + k + 1, boy b′comes back.

Girl can choose b′

, or do better with another boy, b′′

That is, b′≤b by induction hypothesis.

And b′′is better than b′by algorithm.

\= ⇒ Girl does at least as well as with b.

P(k ) = ⇒P(k + 1). And by principle of induction.

## Pairing when done.

Lemma: Every boy is matched at end.

Proof:

If not, a boy b must have been rejected n times.

Every girl has been proposed to by b,

and Improvement lemma

\= ⇒ each girl has a boy on a string.

and each boy is on at most one string.

n girls and n boys. Same number of each.

\= ⇒ b must be on some girl’s string!

Contradiction.

## Pairing is Stable.

Lemma: There is no rogue couple for the pairing formed by

traditional marriage algorithm.

Proof:

Assume there is a rogue couple; (b, g∗)

b∗ g∗ b likes g∗more than g.

g∗likes b more than b∗

.

b g

Boy b proposes to g∗before proposing to g.

So g∗rejected b (since he moved on)

By improvement lemma, g∗likes b∗better than b.

Contradiction!

## Good for boys? girls?

Is the TMA better for boys? for girls?

Definition: A pairing is x-optimal if x′s partner

is x’s best partner in any stable pairing.

Definition: A pairing is x-pessimal if x′s partner

is x’s worst partner in any stable pairing.

Definition: A pairing is boy optimal if it is x-optimal for all boys x.

..and so on for boy pessimal, girl optimal, girl pessimal.

Claim: Optimal partner for a boy must be first in his preference list.

True? False? False!

Subtlety here: Best partner in any stable pairing.

As well as you can be in a globally stable solution!

Question: Is there a boy or girl optimal pairing?

Is it possible:

b-optimal pairing different from the b′-optimal pairing!

Yes? No?

## Understanding Optimality: by example.

A: 1,2 1: A,B

B: 1,2 2: B,A

Consider pairing: (A, 1), (B, 2).

Stable? Yes.

Optimal for B?

Notice: only one stable pairing.

So this is the best B can do in a stable pairing.

So optimal for B.

Also optimal for A, 1 and 2. Also pessimal for A,B,1 and 2.

A: 1,2 1: B,A

B: 2,1 2: A,B

Pairing S: (A, 1), (B, 2). Stable? Yes.

Pairing T : (A, 2), (B, 1). Also Stable.

Which is optimal for A? S Which is optimal for B? S

Which is optimal for 1? T Which is optimal for 2? T

## TMA is optimal for one gender!

For boys? For girls?

Theorem: TMA produces a boy-optimal pairing.

Proof:

Assume not:

Some boy b not paired with optimal girl, g in TMA pairing T.

There is a stable pairing S where b and g are paired.

Let t be first day a boy b gets rejected

by his optimal girl g who he is paired with

in stable pairing S.

b∗- knocks b off of g’s string on day t= ⇒ g prefers b∗to b

By choice of t, b∗likes g at least as much as optimal girl.

\= ⇒ b∗prefers g to his partner g∗in S.

Rogue couple for S.

So S is not a stable pairing. Contradiction.

Notes: S - stable. (b∗

, g∗)and (b, g) ∈S. But (b∗

, g) is rogue couple!

Used Well-Ordering principle...Induction.



















