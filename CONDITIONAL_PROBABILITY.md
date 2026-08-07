# What You Should Know About Conditional Probability

Conditional probability is about calculating the probability of an event **given that another event has already happened**.

The most important ideas are:

- What "given that" means
- How a condition changes the sample space
- Conditional-probability notation
- The difference between $P(A\mid B)$ and $P(B\mid A)$
- The conditional-probability formula
- The general product rule
- How independence relates to conditional probability
- How to recognize conditional-probability problems

---

## 1. Conditional probability means probability GIVEN information

A conditional probability asks:

**What is the probability of one event happening, given that we already know another event happened?**

It is written:

$$
P(A\mid B)
$$

and read as:

**The probability of A GIVEN B.**

The vertical bar:

$$
\mid
$$

means:

$$
\mid=\text{given that}
$$

Therefore:

$$
P(A\mid B)=\text{probability of A given that B occurred}
$$

---

# 2. A condition changes the sample space

This is the biggest conceptual idea behind conditional probability.

Normally, probability is calculated from all possible outcomes.

But once you are told that a certain event already happened, some outcomes are no longer possible.

Therefore, the **sample space becomes smaller**.

In simple terms:

$$
\text{Conditioning removes outcomes that no longer fit the given information}
$$

---

# 3. Coin example: No condition

Suppose you flip a coin twice.

The complete sample space is:

$$
\{HH,HT,TH,TT\}
$$

There are:

$$
4
$$

equally likely outcomes.

Suppose we want the probability of getting two heads:

$$
P(HH)
$$

Only one outcome is:

$$
HH
$$

Therefore:

$$
P(HH)=\frac{1}{4}
$$

So without any additional information:

$$
P(HH)=\frac14
$$

---

# 4. Coin example: GIVEN that the first flip is heads

Now suppose the question is:

**What is the probability of getting two heads GIVEN that the first flip is heads?**

We now know the first flip is:

$$
H
$$

Therefore, outcomes beginning with tails are impossible.

The original sample space:

$$
\{HH,HT,TH,TT\}
$$

becomes:

$$
\{HH,HT\}
$$

There are now only:

$$
2
$$

possible outcomes.

One of them is:

$$
HH
$$

Therefore:

$$
P(HH\mid\text{first is H}) = \frac12
$$

So:

$$
P(HH\mid\text{first is H})=\frac12
$$

Notice the difference:

$$
P(HH)=\frac14
$$

but:

$$
P(HH\mid\text{first is H})=\frac12
$$

The condition changed the sample space and therefore changed the probability.

---

# 5. A condition can make an event impossible

Suppose instead we ask:

**What is the probability of getting two heads GIVEN that the first flip is tails?**

If the first flip is known to be:

$$
T
$$

then the only possible outcomes are:

$$
\{TH,TT\}
$$

The outcome:

$$
HH
$$

is impossible.

Therefore:

$$
P(HH\mid\text{first is T})=0
$$

So:

$$
\text{A condition can increase, decrease, or even reduce a probability to 0}
$$

---

# 6. Conditional-probability formula

The general formula is:

$$
P(A\mid B) = \frac{P(A\cap B)}{P(B)}
$$

where:

- $A$ = event you want
- $B$ = condition you are given
- $A\cap B$ = both A and B happen
- $P(B)$ = probability of the condition

In words:

$$
P(A\mid B) = \frac{\text{probability of A AND B}} {\text{probability of B}}
$$

Another way to think about it is:

$$
P(A\mid B) = \frac{\text{favorable outcomes inside B}} {\text{all outcomes inside B}}
$$

---

# 7. Why the denominator changes

Without a condition, you divide by the size or probability of the entire sample space.

With a condition:

$$
B
$$

you only look at outcomes where:

$$
B
$$

occurred.

That is why the denominator becomes:

$$
P(B)
$$

instead of the probability of the entire original sample space.

Therefore:

$$
\text{Conditioning means your new universe is B}
$$

---

# 8. Intersection versus conditional probability

Do not confuse:

$$
P(A\cap B)
$$

with:

$$
P(A\mid B)
$$

They mean different things.

### Intersection

$$
P(A\cap B)
$$

means:

**Probability that A AND B both happen.**

### Conditional probability

$$
P(A\mid B)
$$

means:

**Probability of A, GIVEN that B already happened.**

The relationship between them is:

$$
P(A\mid B) = \frac{P(A\cap B)}{P(B)}
$$

Therefore:

| Expression | Meaning |
|---|---|
| $P(A\cap B)$ | Probability of A AND B |
| $P(A\mid B)$ | Probability of A GIVEN B |

---

# 9. The order of the condition matters

In general:

$$
P(A\mid B)\neq P(B\mid A)
$$

These answer different questions.

For example:

$$
P(\text{rain}\mid\text{cloudy})
$$

asks:

**What is the probability of rain given that it is cloudy?**

But:

$$
P(\text{cloudy}\mid\text{rain})
$$

asks:

**What is the probability that it is cloudy given that it is raining?**

Those probabilities do not have to be the same.

Therefore:

$$
\text{Always pay attention to which event comes after the vertical bar}
$$

---

# 10. The general product rule

Start with the conditional-probability formula:

$$
P(B\mid A) = \frac{P(A\cap B)}{P(A)}
$$

Multiply both sides by:

$$
P(A)
$$

to obtain:

$$
P(A\cap B) = P(A)P(B\mid A)
$$

This is called the **General Product Rule**.

In words:

$$
\text{Probability of A AND B} = P(A)\times P(B\mid A)
$$

This formula works whether the events are:

- Independent
- Dependent

---

# 11. General product rule versus independent-event product rule

This is one of the most important distinctions to remember.

### General Product Rule

Always valid:

$$
P(A\cap B) = P(A)P(B\mid A)
$$

### If A and B are independent

Then knowing A happened does not change B.

Therefore:

$$
P(B\mid A)=P(B)
$$

So the formula becomes:

$$
P(A\cap B) = P(A)P(B)
$$

Therefore:

$$
\text{General case: }P(A)P(B\mid A)
$$

$$
\text{Independent shortcut: }P(A)P(B)
$$

---

# 12. Independence can be expressed using conditional probability

If A and B are independent:

$$
P(B\mid A)=P(B)
$$

and:

$$
P(A\mid B)=P(A)
$$

Why?

Because learning that one event happened provides no information that changes the probability of the other.

Therefore:

$$
\text{Independent} \Rightarrow \text{conditioning does not change the probability}
$$

---

# 13. Dependent events behave differently

If A and B are dependent, then knowing A happened **does change** the probability of B.

Therefore:

$$
P(B\mid A)\neq P(B)
$$

in general.

For dependent events, you cannot simply use:

$$
P(A)P(B)
$$

Instead, use:

$$
P(A\cap B) = P(A)P(B\mid A)
$$

---

# 14. Dice example: Probability of a sum of 10

Suppose two fair dice are rolled.

There are:

$$
6\times6=36
$$

possible ordered outcomes.

The outcomes producing a sum of 10 are:

$$
(4,6),(5,5),(6,4)
$$

Therefore:

$$
P(\text{sum}=10) = \frac{3}{36}
$$

$$
= \frac{1}{12}
$$

So without any condition:

$$
P(\text{sum}=10)=\frac{1}{12}
$$

---

# 15. Dice example: Sum of 10 GIVEN first die is 6

Now suppose we know:

$$
\text{first die}=6
$$

The possible outcomes become:

$$
(6,1),(6,2),(6,3),(6,4),(6,5),(6,6)
$$

There are only:

$$
6
$$

possible outcomes remaining.

To obtain a sum of 10, the second die must be:

$$
4
$$

So only:

$$
(6,4)
$$

works.

Therefore:

$$
P(\text{sum}=10\mid\text{first die}=6) = \frac16
$$

Thus:

$$
P(\text{sum}=10\mid\text{first die}=6)=\frac16
$$

Compare:

$$
P(\text{sum}=10)=\frac{1}{12}
$$

with:

$$
P(\text{sum}=10\mid\text{first die}=6)=\frac16
$$

The condition changed the probability.

---

# 16. Dice example: Sum of 10 GIVEN first die is 1

Suppose instead:

$$
\text{first die}=1
$$

The second die can only be:

$$
1,2,3,4,5,6
$$

The largest possible sum is:

$$
1+6=7
$$

Therefore, obtaining a sum of 10 is impossible.

So:

$$
P(\text{sum}=10\mid\text{first die}=1)=0
$$

Therefore:

$$
\text{Conditions can completely eliminate certain outcomes}
$$

---

# 17. Conditional probability can be used inside AND problems

Suppose:

$$
A=\text{first die is 6}
$$

and:

$$
B=\text{sum is 10}
$$

We want:

$$
P(A\cap B)
$$

Use:

$$
P(A\cap B) = P(A)P(B\mid A)
$$

We know:

$$
P(A)=\frac16
$$

and:

$$
P(B\mid A)=\frac16
$$

Therefore:

$$
P(A\cap B) = \frac16\cdot\frac16
$$

$$
= \frac{1}{36}
$$

So:

$$
P(\text{first die is 6 AND sum is 10}) = \frac{1}{36}
$$

---

# 18. Conditional probability is different from Bayes' theorem

Conditional probability is the broader concept.

It asks:

$$
P(A\mid B)
$$

when the relationship between A and B is available directly.

Bayes' theorem is used when you know probabilities in the opposite direction, such as:

$$
P(B\mid A)
$$

but want:

$$
P(A\mid B)
$$

Therefore:

$$
\text{Conditional Probability} \rightarrow \text{foundation for Bayes' Theorem}
$$

Bayes' theorem builds on conditional probability but is a separate topic.

---

# Most Important Definitions and Distinctions to Remember

## Conditional probability

$$
P(A\mid B) = \text{probability of A given B}
$$

---

## Vertical bar

$$
\mid=\text{given that}
$$

---

## Conditional-probability formula

$$
P(A\mid B) = \frac{P(A\cap B)}{P(B)}
$$

---

## Intersection

$$
P(A\cap B) = \text{probability of A AND B}
$$

---

## General Product Rule

$$
P(A\cap B) = P(A)P(B\mid A)
$$

This works in the general case.

---

## Independent-event shortcut

If A and B are independent:

$$
P(B\mid A)=P(B)
$$

Therefore:

$$
P(A\cap B) = P(A)P(B)
$$

---

## Order matters

$$
P(A\mid B)\neq P(B\mid A)
$$

in general.

---

# Main Rules to Put in Your Notebook

$$
\mid=\text{GIVEN THAT}
$$

$$
P(A\mid B) = \frac{P(A\cap B)}{P(B)}
$$

$$
\text{Conditioning shrinks the sample space to B}
$$

$$
P(A\cap B) = P(A)P(B\mid A)
$$

If independent:

$$
P(B\mid A)=P(B)
$$

and:

$$
P(A\cap B)=P(A)P(B)
$$

Remember:

$$
P(A\mid B)\neq P(B\mid A)
$$

The biggest idea is:

**Conditional probability changes the sample space. Once you are told that B happened, only outcomes consistent with B remain. The probability of A is then calculated within that smaller sample space.**
