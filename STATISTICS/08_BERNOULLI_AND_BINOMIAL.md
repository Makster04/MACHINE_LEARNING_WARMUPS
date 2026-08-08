# What You Should Know About the Bernoulli and Binomial Distributions

> **Prerequisites:** the product rule for independent events and $p^n$ are in 02. PMF notation and $X$ versus $x$ are in 06. Expected value and variance are in 07.

These notes teach how to model the **number of successes in a fixed number of repeated trials**: what a single Bernoulli trial is, how the binomial probability formula is constructed, what $n$, $p$, $X$, and $x$ mean, why the **binomial coefficient** is necessary, and what the mean and variance are.

---

# 1. A Bernoulli trial is a single success/failure experiment

Before counting successes, you need to understand a single trial.

A **Bernoulli trial** is one experiment with exactly two possible outcomes. One is chosen and labelled the **success**, and the other is the **failure**:

$$
\boxed{p = P(\text{success}) \qquad 1-p = P(\text{failure})}
$$

Examples of a single Bernoulli trial:

- Flip a coin once. Is it heads?
- Roll a die once. Is it a 1?
- Check one email. Is it spam?
- Test one patient. Are they sick?
- Inspect one item. Is it defective?

## The Bernoulli random variable

Define the random variable so that success is 1 and failure is 0:

$$
X =
\begin{cases}
1, & \text{success, with probability } p \cr
0, & \text{failure, with probability } 1-p
\end{cases}
$$

Written in notation:

$$
\boxed{X \sim \text{Bernoulli}(p)}
$$

## Its mean and variance

Using the definitions from 07:

$$
E[X] = 1(p) + 0(1-p) = p
$$

Because $X$ only takes the values 0 and 1, squaring changes nothing: $X^2 = X$. So $E[X^2] = p$ as well, and the computational formula gives:

$$
\text{Var}(X) = E[X^2]-\left(E[X]\right)^2 = p - p^2 = p(1-p)
$$

Therefore:

$$
\boxed{\text{Bernoulli}(p): \quad \mu = p \qquad \sigma^2 = p(1-p)}
$$

## Where variance is largest

$p(1-p)$ is largest at $p=0.5$, where it equals $0.25$:

| $p$ | 0.01 | 0.10 | 0.25 | 0.50 | 0.75 | 0.90 | 0.99 |
|---|---|---|---|---|---|---|---|
| $p(1-p)$ | 0.0099 | 0.0900 | 0.1875 | **0.2500** | 0.1875 | 0.0900 | 0.0099 |

This makes sense. A fair coin is the most unpredictable single trial there is. When $p$ is near 0 or near 1 the outcome is almost certain, so there is very little variability.

---

# 2. A binomial distribution counts successes across $n$ trials

A **binomial distribution** models the number of times the success occurs across a fixed number of repeated Bernoulli trials.

$$
\boxed{\text{Binomial} = \text{count of successes across } n \text{ Bernoulli trials}}
$$

For example, suppose you flip a coin 5 times and define:

$$
X = \text{number of heads in 5 coin tosses}
$$

Then $X$ can be $0, 1, 2, 3, 4, 5$.

Each individual flip is a Bernoulli trial. The binomial is what you get when you stop caring about a single flip and start counting across all of them.

Therefore:

$$
\boxed{\text{Binomial distribution} = \text{distribution of the number of successes}}
$$

The same idea works for any repeated yes/no outcome:

- Roll a 1 / do not roll a 1
- Patient gets sick / does not get sick
- Item is defective / not defective

---

# 3. The conditions behind a binomial distribution

Four conditions must hold. If any of them fails, it is not a binomial.

1. There is a **fixed** number of trials, $n$, decided in advance.
2. Each trial is a **Bernoulli trial** with two outcomes.
3. The probability of success, $p$, is the **same on every trial**.
4. The trials are **independent** (see 02).

Then:

$$
\boxed{X = \text{number of successes in } n \text{ trials}}
$$

## Where condition 4 usually breaks

Drawing cards **without replacement** is the classic failure. As shown in 03, removing a card changes the probability for the next draw, so the trials are dependent and $p$ is not constant. Drawing **with replacement** restores both conditions.

---

# 4. The two parameters are $n$ and $p$

A binomial distribution is completely determined by two values:

| Symbol | Meaning |
| --- | --- |
| $n$ | Number of trials |
| $p$ | Probability of success on each trial |

These are called the **parameters of the binomial distribution**. Fix $n$ and $p$ and every probability in the distribution is determined.

---

# 5. Binomial-distribution notation

A binomial random variable is written:

$$
\boxed{X \sim \text{Binomial}(n, p)}
$$

The symbol $\sim$ means:

> **"is distributed as"** or **"follows."**

So $X \sim \text{Binomial}(5, 0.5)$ means:

> $X$ follows a binomial distribution with **5 trials** and a **0.5 probability of success on each trial**.

Therefore:

$$
\boxed{n = \text{number of trials} \qquad p = \text{probability of success}}
$$

Note that a Bernoulli trial is just the special case with one trial:

$$
\boxed{\text{Bernoulli}(p) = \text{Binomial}(1, p)}
$$

---

# 6. The binomial probability formula

Recall from 06 that $X$ is the random variable and $x$ is one particular value it takes. Here $X$ is "the number of successes" and $x = 2$ means exactly 2 successes.

The main binomial formula is the PMF:

$$
\boxed{P(X = x) = \binom{n}{x} p^x (1-p)^{n-x}}
$$

This gives the probability of getting **exactly $x$ successes** in **$n$ trials** when the probability of success on each trial is **$p$**.

For the 5-coin example:

$$
p_X(x) = \binom{5}{x} p^x (1-p)^{5-x}
$$

---

# 7. What every symbol in the formula means

For $P(X = x) = \binom{n}{x} p^x (1-p)^{n-x}$:

| Symbol | Meaning |
| --- | --- |
| $X$ | Random variable counting successes |
| $x$ | Particular number of successes |
| $P(X=x)$ | Probability of exactly $x$ successes |
| $n$ | Total number of trials |
| $p$ | Probability of success |
| $1-p$ | Probability of failure |
| $x$ in $p^x$ | Number of successes |
| $n-x$ | Number of failures |
| $\binom{n}{x}$ | Number of ways the successes can be arranged |

---

# 8. The binomial coefficient counts arrangements

The expression $\binom{n}{x}$ is called the **binomial coefficient**. It answers:

> How many different ways can $x$ successes occur among $n$ trials?

It is read as "**$n$ choose $x$**," and the formula is:

$$
\boxed{\binom{n}{x} = \frac{n!}{x!\,(n-x)!}}
$$

## Example

Suppose $n = 5$ and $x = 2$. Then:

$$
\binom{5}{2} = \frac{5!}{2!\,(5-2)!} = \frac{5!}{2!\,3!}
$$

Expand:

$$
\frac{5 \cdot 4 \cdot 3 \cdot 2 \cdot 1}{(2 \cdot 1)(3 \cdot 2 \cdot 1)}
$$

Cancel:

$$
\frac{5 \cdot 4}{2 \cdot 1} = 10
$$

Therefore:

$$
\boxed{\binom{5}{2} = 10}
$$

There are **10 different ways to get exactly 2 heads in 5 tosses**.

---

# 9. Why the binomial coefficient is necessary

Suppose you want exactly 2 heads in 5 tosses. One possible sequence is:

$$
HHTTT
$$

But you could also get:

$$
HTHTT, \quad HTTHT, \quad TTHHT, \quad \ldots
$$

and many others. All of them have exactly 2 heads, so all of them count.

Every one of these sequences has the **same probability**, because each is 2 successes and 3 failures multiplied together in some order, and multiplication does not care about order.

So the calculation splits into two questions:

$$
\boxed{\text{How likely is ONE such sequence?} \quad\times\quad \text{How MANY such sequences are there?}}
$$

The first question is answered by $p^x(1-p)^{n-x}$. The second is answered by $\binom{n}{x}$, and here that is 10.

Therefore:

$$
\boxed{\binom{n}{x} = \text{number of possible arrangements}}
$$

Forgetting this factor is the single most common binomial mistake. It gives the probability of one *specific* sequence rather than of the *count*.

---

# 10. The formula has three main pieces

It helps to read the formula as three separate factors:

$$
\boxed{\underbrace{\binom{n}{x}}_{\text{arrangements}} \times \underbrace{p^x}_{\text{successes}} \times \underbrace{(1-p)^{n-x}}_{\text{failures}}}
$$

## What $p^x$ represents

This is the probability contribution from the **successes**. There are $x$ of them, each with probability $p$, and because the trials are independent you multiply — this is the $p^n$ rule from 02.

If $x = 2$, then $p^x = p^2$.

## What $(1-p)^{n-x}$ represents

This is the probability contribution from the **failures**. The probability of failure on one trial is $1-p$, and if there are $n$ trials with $x$ successes, then the number of failures is:

$$
\boxed{n-x}
$$

For example, $n = 5$ and $x = 2$ gives $n - x = 3$, so:

$$
(1-p)^{n-x} = (1-p)^3
$$

## A quick check on your work

The two exponents must always add back to the number of trials:

$$
x + (n-x) = n
$$

If they do not, you have set up the problem wrong.

So in words:

$$
\boxed{\text{Probability} = \text{ways} \times \text{success probability} \times \text{failure probability}}
$$

> **Count all possible arrangements of the successes, then multiply by the probability of the successes and failures occurring.**

---

# 11. Full example: exactly 2 heads in 5 fair coin flips

Suppose $X = \text{number of heads in 5 flips}$ and the coin is fair. Therefore:

$$
n = 5 \qquad x = 2 \qquad p = 0.5 \qquad 1 - p = 0.5
$$

Substitute into the PMF:

$$
P(X = 2) = \binom{5}{2}(0.5)^2 (0.5)^{5-2}
$$

The coefficient is $\binom{5}{2} = 10$, so:

$$
P(X = 2) = 10\,(0.5)^2 (0.5)^3 = 10(0.25)(0.125) = 0.3125
$$

Therefore:

$$
\boxed{P(X = 2) = 0.3125 = \frac{10}{32}}
$$

So there is a **31.25 percent probability of getting exactly 2 heads in 5 fair coin flips**.

---

# 12. Mean and variance of the binomial

A binomial variable is just the sum of $n$ independent Bernoulli variables:

$$
X = Y_1 + Y_2 + \cdots + Y_n \qquad\text{where each } Y_i \sim \text{Bernoulli}(p)
$$

Each $Y_i$ contributes a 1 when its trial succeeds and a 0 when it fails, so adding them counts the successes.

## The mean

Expected value adds, always:

$$
E[X] = E[Y_1]+\cdots+E[Y_n] = \underbrace{p + p + \cdots + p}_{n \text{ times}} = np
$$

$$
\boxed{\mu = np}
$$

## The variance

Variance adds too, but only because the trials are **independent** — this is the rule from 07:

$$
\text{Var}(X) = \text{Var}(Y_1)+\cdots+\text{Var}(Y_n) = n\,p(1-p)
$$

$$
\boxed{\sigma^2 = np(1-p) \qquad \sigma = \sqrt{np(1-p)}}
$$

This is exactly why condition 4 in section 3 matters. Without independence the mean would still be $np$, but the variance formula would fail.

## Example: 5 fair coin flips

$$
\mu = 5(0.5) = 2.5
$$

$$
\sigma^2 = 5(0.5)(0.5) = 1.25 \qquad \sigma = \sqrt{1.25} \approx 1.118
$$

Check this against the PMF directly. Using the masses in section 13:

$$
E[X] = \frac{0(1)+1(5)+2(10)+3(10)+4(5)+5(1)}{32} = \frac{80}{32} = 2.5 \quad\checkmark
$$

The shortcut $\mu = np$ saves you from ever doing that sum.

## Example: 10 dice, counting ones

With $n=10$ and $p=\frac16$:

$$
\mu = 10\left(\frac16\right) = \frac{5}{3} \approx 1.67
$$

$$
\sigma^2 = 10\left(\frac16\right)\left(\frac56\right) = \frac{25}{18} \approx 1.39 \qquad \sigma \approx 1.18
$$

So across 10 rolls you should expect between 1 and 2 ones, give or take about one.

---

# 13. A fair coin produces a symmetric binomial distribution

For a fair coin, $p = 0.5$. The full 5-flip distribution is:

| Heads ($x$) | Probability |
| ---: | ---: |
| 0 | $1/32$ |
| 1 | $5/32$ |
| 2 | $10/32$ |
| 3 | $10/32$ |
| 4 | $5/32$ |
| 5 | $1/32$ |

These sum to 1, as any PMF must (see 06).

Notice that $P(X=0) = P(X=5)$, $P(X=1) = P(X=4)$, and $P(X=2) = P(X=3)$. So when $p = 0.5$, the distribution is symmetric, and it is centred exactly on $\mu = 2.5$.

Therefore:

$$
\boxed{p = 0.5 \rightarrow \text{symmetric binomial distribution}}
$$

---

# 14. Changing $p$ changes the shape of the distribution

Compare $n = 5$ with $p = 0.5$ against $n = 5$ with $p = 0.3$.

When $p = 0.3$, successes are less likely, so probability becomes concentrated around **smaller numbers of successes**:

| $x$ | $P(X=x)$ |
| ---: | ---: |
| 0 | 0.16807 |
| 1 | 0.36015 |
| 2 | 0.30870 |
| 3 | 0.13230 |
| 4 | 0.02835 |
| 5 | 0.00243 |

The peak has moved from $x=2.5$ to around $x=1.5$, which is exactly $\mu = np = 5(0.3) = 1.5$. The distribution is no longer symmetric; it is skewed toward the low end.

So:

$$
\boxed{p \text{ controls how likely success is, and therefore where the distribution sits}}
$$

$$
\boxed{p<0.5 \rightarrow \text{skewed left-heavy} \qquad p=0.5 \rightarrow \text{symmetric} \qquad p>0.5 \rightarrow \text{skewed right-heavy}}
$$

---

# 15. The binomial distribution is not only about coins

Coins are just an easy example. Any repeated yes/no question works.

Suppose you roll a die and define $\text{Success} = \text{rolling a 1}$. Then:

$$
p = \frac{1}{6} \qquad 1 - p = \frac{5}{6}
$$

Rolling a die repeatedly can therefore be treated like repeated success/failure trials, where rolling a 1 is a success and anything else is a failure. In effect the die becomes a **biased coin** for the chosen event.

---

# 16. Example: roll 10 dice and count the number of ones

Suppose $X = \text{number of 1s obtained in 10 die rolls}$. Then $n = 10$ and $p = \frac{1}{6} \approx 0.1667$, so:

$$
\boxed{X \sim \text{Binomial}\left(10, \frac{1}{6}\right)}
$$

To find the probability of exactly two 1s:

$$
P(X = 2) = \binom{10}{2}\left(\frac16\right)^2\left(\frac56\right)^8
$$

This demonstrates that the binomial applies whenever you repeatedly ask:

> **Did the event happen or not?**

---

# 17. When $n$ is large: the normal approximation

Look again at the symmetric table in section 13. Even with only 5 trials, the shape is already starting to resemble a bell. As $n$ grows, that resemblance becomes very close.

This means a large binomial can be approximated by a normal distribution using the same mean and standard deviation from section 12:

$$
\mu = np \qquad \sigma = \sqrt{np(1-p)}
$$

The conditions under which this approximation is valid, and the **continuity correction** needed when using a continuous curve to approximate a discrete count, are covered in 12.

---

# Most Important Definitions and Distinctions to Remember

## Bernoulli trial

A single experiment with two outcomes.

$$
\boxed{X \sim \text{Bernoulli}(p) \qquad \mu = p \qquad \sigma^2 = p(1-p)}
$$

---

## Binomial distribution

The number of successes across $n$ independent Bernoulli trials.

$$
\boxed{\text{the number of successes in a fixed number of independent trials}}
$$

## Parameters

$$
\boxed{n = \text{number of trials} \qquad p = \text{probability of success}}
$$

Notation:

$$
\boxed{X \sim \text{Binomial}(n, p)}
$$

## The four conditions

Fixed $n$, two outcomes per trial, constant $p$, independent trials.

## Probability of success versus failure

$$
\boxed{p = P(\text{success}) \qquad 1 - p = P(\text{failure})}
$$

## Binomial PMF

$$
\boxed{P(X = x) = \binom{n}{x} p^x (1-p)^{n-x}}
$$

## Binomial coefficient

$$
\boxed{\binom{n}{x} = \frac{n!}{x!\,(n-x)!}}
$$

The number of ways to arrange $x$ successes among $n$ trials.

## Mean and variance

$$
\boxed{\mu = np \qquad \sigma^2 = np(1-p) \qquad \sigma = \sqrt{np(1-p)}}
$$

---

# Main Rules to Put in Your Notebook

| Rule | Meaning |
| --- | --- |
| $X \sim \text{Bernoulli}(p)$ | A single success/failure trial |
| $X \sim \text{Binomial}(n, p)$ | Successes across $n$ such trials |
| $n$ | Number of trials |
| $p$ | Probability of success |
| $1-p$ | Probability of failure |
| $x$ | Number of successes |
| $n-x$ | Number of failures |
| $P(X=x) = \binom{n}{x} p^x (1-p)^{n-x}$ | Binomial PMF |
| $\binom{n}{x} = \dfrac{n!}{x!(n-x)!}$ | Binomial coefficient |
| $\mu = np$ | Binomial mean |
| $\sigma^2 = np(1-p)$ | Binomial variance |
| $\mu = p$, $\sigma^2 = p(1-p)$ | Bernoulli mean and variance |

And the **biggest idea to remember** is:

$$
\boxed{\text{Binomial Probability} = \text{Number of Arrangements} \times \text{Success Portion} \times \text{Failure Portion}}
$$

or:

$$
\boxed{P(X = x) = \underbrace{\binom{n}{x}}_{\text{ways}} \underbrace{p^x}_{\text{successes}} \underbrace{(1-p)^{n-x}}_{\text{failures}}}
$$

So in plain English: **a Bernoulli trial is one yes/no experiment, and the binomial distribution tells you the probability of getting exactly $x$ successes out of $n$ independent trials when each trial has the same success probability $p$.**

---

# Where This Goes Next

| Idea from this file | Where it is used |
|---|---|
| $\mu = np$, $\sigma = \sqrt{np(1-p)}$ | **12 — Normal Approximation to the Binomial** |
| The bell-like shape at large $n$ | **12**: why the approximation works at all |
| Discrete counts versus a continuous curve | **12**: why a continuity correction is needed |
| $p$ as a class probability | **13 — Naive Bayes**: Bernoulli Naive Bayes models each feature this way |
| Counting successes in trials | **05 — Test Accuracy**: TP, FP, TN, FN are counts of exactly this kind |
