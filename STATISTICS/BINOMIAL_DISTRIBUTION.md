Absolutely — here is the **Binomial Distribution only**, organized the same way as the Normal Distribution notes: the main definitions, distinctions, equations, examples, and rules worth memorizing.

# What You Should Know About the Binomial Distribution

These slides are mainly teaching how to model the **number of successes in a fixed number of repeated trials**, how the binomial probability formula is constructed, what (n), (p), (X), and (x) mean, and why the **binomial coefficient** is necessary.

---

# 1. A binomial distribution counts successes

A **binomial distribution** models the number of times a particular outcome occurs during a fixed number of trials.

For example, suppose you flip a coin 5 times and define:

$$
X=\text{number of heads in 5 coin tosses}
$$

Then (X) can be:

$$
0,1,2,3,4,5
$$

The slides first build this idea using 3, 4, and 5 coin flips and show the probability associated with each possible number of heads. 

Therefore:

$$
\boxed{
\text{Binomial distribution}
============================

\text{distribution of the number of successes}
}
$$

---

# 2. A binomial experiment has repeated success/failure trials

In the slides, each coin toss has two possible outcomes:

* Heads
* Tails

We choose one outcome to call the **success**.

For example:

$$
\text{Success}=\text{Heads}
$$

Then:

$$
p=P(\text{Heads})
$$

and the probability of the other outcome is:

$$
1-p=P(\text{Tails})
$$

The source explicitly uses (p) for the probability of heads and (1-p) for tails. 

The same idea works for other yes/no outcomes such as:

* Roll a 1 / do not roll a 1
* Patient gets sick / does not get sick
* Item is defective / not defective

---

# 3. The main conditions behind a binomial distribution

The slides describe the binomial distribution as counting successes in a **fixed number of independent trials**. 

The important setup is:

1. There is a fixed number of trials, (n).
2. Each trial has a success/failure outcome.
3. The probability of success is (p).
4. The trials are independent.
5. (X) counts the number of successes.

Therefore:

$$
\boxed{
X=\text{number of successes in }n\text{ trials}
}
$$

---

# 4. The two parameters are (n) and (p)

A binomial distribution is determined by two values:

$$
\boxed{n}
$$

and:

$$
\boxed{p}
$$

where:

| Symbol | Meaning                              |
| ------ | ------------------------------------ |
| (n)    | Number of trials                     |
| (p)    | Probability of success on each trial |

The slides call (n) and (p) the **parameters of the binomial distribution**. 

---

# 5. Binomial-distribution notation

The slides write a binomial random variable as:

$$
\boxed{
X\sim\operatorname{Binomial}(n,p)
}
$$

The symbol:

$$
\sim
$$

means:

> **"is distributed as"** or **"follows."**

So:

$$
X\sim\operatorname{Binomial}(5,0.5)
$$

means:

> (X) follows a binomial distribution with **5 trials** and a **0.5 probability of success on each trial**.

The slides explain this notation using (X\sim\operatorname{Binomial}(5,p)). 

Therefore:

$$
\boxed{
n=\text{number of trials}
}
$$

$$
\boxed{
p=\text{probability of success}
}
$$

---

# 6. Capital (X) versus lowercase (x)

This distinction is easy to mix up.

### Capital (X)

$$
X
$$

is the **random variable**.

For example:

$$
X=\text{number of heads in 5 tosses}
$$

### Lowercase (x)

$$
x
$$

is one particular possible value of (X).

For example:

$$
x=2
$$

means:

> exactly 2 heads.

Therefore:

$$
X=x
$$

means:

> the random variable (X) takes the particular value (x).

The slides explicitly distinguish the random variable from a particular number of heads. 

---

# 7. The binomial probability formula

The main binomial formula is:

$$
\boxed{
P(X=x)
======

\binom{n}{x}
p^x
(1-p)^{n-x}
}
$$

This gives the probability of getting:

$$
\boxed{\text{exactly }x\text{ successes}}
$$

in:

$$
\boxed{n\text{ trials}}
$$

when the probability of success on each trial is:

$$
\boxed{p}
$$

For the 5-coin example, the slides write:

$$
p_X(x)
======

\binom{5}{x}
p^x
(1-p)^{5-x}
$$



---

# 8. What every symbol in the formula means

For:

$$
P(X=x)
======

\binom{n}{x}
p^x(1-p)^{n-x}
$$

| Symbol         | Meaning                                      |
| -------------- | -------------------------------------------- |
| (X)            | Random variable counting successes           |
| (x)            | Particular number of successes               |
| (P(X=x))       | Probability of exactly (x) successes         |
| (n)            | Total number of trials                       |
| (p)            | Probability of success                       |
| (1-p)          | Probability of failure                       |
| (x) in (p^x)   | Number of successes                          |
| (n-x)          | Number of failures                           |
| (\binom{n}{x}) | Number of ways the successes can be arranged |

These meanings are laid out directly in the slides.  

---

# 9. The binomial coefficient counts arrangements

The expression:

$$
\boxed{
\binom{n}{x}
}
$$

is called the **binomial coefficient**.

It tells you:

> How many different ways can (x) successes occur among (n) trials?

The formula is:

$$
\boxed{
\binom{n}{x}
============

\frac{n!}{x!(n-x)!}
}
$$

The slides also describe this as:

$$
\text{"}n\text{ choose }x\text{"}
$$



---

# 10. Example of the binomial coefficient

Suppose:

$$
n=5
$$

and:

$$
x=2
$$

Then:

$$
\binom{5}{2}
============

\frac{5!}{2!(5-2)!}
$$

# $$

\frac{5!}{2!3!}
$$

Expand:

# $$

\frac{5\cdot4\cdot3\cdot2\cdot1}
{(2\cdot1)(3\cdot2\cdot1)}
$$

Cancel:

# $$

\frac{5\cdot4}{2\cdot1}
$$

$$
=10
$$

Therefore:

$$
\boxed{
\binom52=10
}
$$

There are **10 different ways to get exactly 2 heads in 5 tosses**.

This is the example developed on pages 5–6 of the slides. 

---

# 11. Why the binomial coefficient is necessary

Suppose you want exactly 2 heads in 5 tosses.

One possible sequence is:

$$
HHTTT
$$

But you could also get:

$$
HTHTT
$$

or:

$$
HTTHT
$$

or many other arrangements.

The probability formula needs to account for **all possible orders** that produce 2 heads.

That is exactly what:

$$
\binom52
$$

does.

The slides show that there are 10 such arrangements. 

Therefore:

$$
\boxed{
\binom{n}{x}
============

\text{number of possible arrangements}
}
$$

---

# 12. What (p^x) represents

The expression:

$$
\boxed{
p^x
}
$$

represents the probability contribution from the **successes**.

If:

$$
x=2
$$

then:

$$
p^x=p^2
$$

because there are 2 successes.

The slides identify (p^x) as the portion corresponding to the heads/successes. 

---

# 13. What ((1-p)^{n-x}) represents

The probability of failure is:

$$
1-p
$$

If there are:

$$
n
$$

trials and:

$$
x
$$

successes, then the number of failures is:

$$
\boxed{n-x}
$$

Therefore:

$$
\boxed{
(1-p)^{n-x}
}
$$

represents the failure portion.

For example:

$$
n=5
$$

and:

$$
x=2
$$

gives:

$$
n-x=5-2=3
$$

so:

$$
(1-p)^{n-x}
===========

(1-p)^3
$$



---

# 14. The formula has three main pieces

It helps to think of:

$$
P(X=x)
======

\binom{n}{x}
p^x
(1-p)^{n-x}
$$

as three pieces:

$$
\boxed{
\underbrace{\binom{n}{x}}*{\text{arrangements}}
\times
\underbrace{p^x}*{\text{successes}}
\times
\underbrace{(1-p)^{n-x}}_{\text{failures}}
}
$$

So in words:

$$
\boxed{
\text{Probability}
==================

\text{ways}
\times
\text{success probability}
\times
\text{failure probability}
}
$$

More specifically:

> **Count all possible arrangements of the successes, then multiply by the probability of the successes and failures occurring.**

---

# 15. Full example: exactly 2 heads in 5 fair coin flips

Suppose:

$$
X=\text{number of heads in 5 flips}
$$

and the coin is fair.

Therefore:

$$
n=5
$$

$$
x=2
$$

$$
p=0.5
$$

$$
1-p=0.5
$$

Use:

$$
P(X=x)
======

\binom{n}{x}p^x(1-p)^{n-x}
$$

Substitute:

$$
P(X=2)
======

\binom52(0.5)^2(0.5)^{5-2}
$$

Calculate the coefficient:

$$
\binom52=10
$$

Therefore:

$$
P(X=2)
======

10(0.5)^2(0.5)^3
$$

# $$

10(0.25)(0.125)
$$

# $$

0.3125
$$

Therefore:

$$
\boxed{
P(X=2)=0.3125
}
$$

or:

$$
\boxed{31.25%}
$$

So there is a **31.25% probability of getting exactly 2 heads in 5 fair coin flips**. 

---

# 16. A fair coin produces a symmetric binomial distribution

For a fair coin:

$$
p=0.5
$$

The slides show the 5-flip distribution:

| Heads (x) | Probability |
| --------: | ----------: |
|         0 |      (1/32) |
|         1 |      (5/32) |
|         2 |     (10/32) |
|         3 |     (10/32) |
|         4 |      (5/32) |
|         5 |      (1/32) |

Notice:

$$
P(X=0)=P(X=5)
$$

$$
P(X=1)=P(X=4)
$$

$$
P(X=2)=P(X=3)
$$

So when:

$$
p=0.5
$$

the graph in the slides is symmetric. 

Therefore:

$$
\boxed{
p=0.5\rightarrow\text{symmetric binomial distribution}
}
$$

---

# 17. Changing (p) changes the shape of the distribution

The slides compare:

$$
n=5,\qquad p=0.5
$$

with:

$$
n=5,\qquad p=0.3
$$

When:

$$
p=0.3
$$

successes are less likely.

Therefore, probability becomes concentrated around **smaller numbers of successes**.

For example, the slide gives approximately:

| (x) | (P(X=x)) |
| --: | -------: |
|   0 |  0.16807 |
|   1 |  0.36015 |
|   2 |   0.3087 |
|   3 |   0.1323 |
|   4 |  0.02835 |
|   5 |  0.00243 |



So:

$$
\boxed{
p\text{ controls how likely success is}
}
$$

and changing (p) changes where the distribution is concentrated.

---

# 18. The binomial distribution is not only about coins

Coins are just an easy example.

The slides also use dice.

Suppose you roll a die and define:

$$
\text{Success}=\text{rolling a 1}
$$

Then:

$$
p=\frac16
$$

and:

$$
1-p=\frac56
$$

Rolling a die repeatedly can therefore be treated like repeated success/failure trials:

$$
\text{1}=\text{success}
$$

$$
\text{not 1}=\text{failure}
$$

The slides describe this as treating the die like a **biased coin** for the chosen event. 

---

# 19. Example: roll 10 dice and count the number of ones

Suppose:

$$
X=\text{number of 1s obtained in 10 die rolls}
$$

Then:

$$
n=10
$$

and:

$$
p=\frac16
$$

Therefore:

$$
\boxed{
X\sim\operatorname{Binomial}\left(10,\frac16\right)
}
$$

The slide gives approximately:

$$
p=0.1666
$$

for this example. 

This demonstrates that the binomial distribution applies whenever you repeatedly ask:

> **Did the event happen or not?**

---

# 20. Binomial distribution versus a single trial

A binomial distribution counts the total successes across **multiple trials**.

For example:

$$
X=\text{number of heads in 5 flips}
$$

could be:

$$
0,1,2,3,4,5
$$

The slides end by showing the related one-trial success/failure setup, but the important binomial idea is:

$$
\boxed{
\text{Binomial}=\text{number of successes across }n\text{ trials}
}
$$

The notebook summary describes it as the probability of exactly (x) successes in a fixed number of independent trials. 

---

# Most Important Definitions and Distinctions to Remember

## Binomial distribution

A **binomial distribution** models:

$$
\boxed{
\text{the number of successes in a fixed number of independent trials}
}
$$

---

## Parameters

The two parameters are:

$$
\boxed{n=\text{number of trials}}
$$

and:

$$
\boxed{p=\text{probability of success}}
$$

Notation:

$$
\boxed{
X\sim\operatorname{Binomial}(n,p)
}
$$

---

## (X) versus (x)

$$
\boxed{
X=\text{random variable counting successes}
}
$$

while:

$$
\boxed{
x=\text{particular number of successes}
}
$$

Example:

$$
X=\text{number of heads in 5 flips}
$$

while:

$$
x=2
$$

means exactly 2 heads.

---

## Probability of success versus failure

$$
\boxed{
p=P(\text{success})
}
$$

and:

$$
\boxed{
1-p=P(\text{failure})
}
$$

---

## Binomial PMF

The probability of **exactly (x) successes** is:

$$
\boxed{
P(X=x)
======

\binom{n}{x}
p^x(1-p)^{n-x}
}
$$

---

## Binomial coefficient

$$
\boxed{
\binom{n}{x}
============

\frac{n!}{x!(n-x)!}
}
$$

It tells you:

$$
\boxed{
\text{number of ways to arrange }x\text{ successes among }n\text{ trials}
}
$$

---

## Successes

$$
\boxed{
p^x
}
$$

represents the (x) successes.

---

## Failures

$$
\boxed{
(1-p)^{n-x}
}
$$

represents the:

$$
\boxed{n-x}
$$

failures.

---

# Main Rules to Put in Your Notebook

$$
\boxed{
X\sim\operatorname{Binomial}(n,p)
}
$$

$$
\boxed{
n=\text{number of trials}
}
$$

$$
\boxed{
p=\text{probability of success}
}
$$

$$
\boxed{
1-p=\text{probability of failure}
}
$$

$$
\boxed{
x=\text{number of successes}
}
$$

$$
\boxed{
n-x=\text{number of failures}
}
$$

$$
\boxed{
P(X=x)
======

\binom{n}{x}p^x(1-p)^{n-x}
}
$$

$$
\boxed{
\binom{n}{x}
============

\frac{n!}{x!(n-x)!}
}
$$

And the **biggest idea to remember** is:

$$
\boxed{
\text{Binomial Probability}
===========================

\text{Number of Arrangements}
\times
\text{Success Portion}
\times
\text{Failure Portion}
}
$$

or:

$$
\boxed{
P(X=x)
======

\underbrace{\binom{n}{x}}*{\text{ways}}
\underbrace{p^x}*{\text{successes}}
\underbrace{(1-p)^{n-x}}_{\text{failures}}
}
$$

So in plain English: **the binomial distribution tells you the probability of getting exactly (x) successes out of (n) independent trials when each trial has the same success probability (p).** 
