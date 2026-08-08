# What You Should Know About the Normal Approximation to the Binomial

> **Prerequisites:** the binomial PMF and its mean and variance are in 08. The normal distribution is in 10. Z-scores and $\Phi$ are in 11.
>
> This file was split out of the Normal notes because it is a **bridge between two distributions**, not a fact about either one. Filing it under only the normal makes it invisible when you are thinking about binomials.

These notes cover: why a large binomial starts to look normal, how to set up the approximation, the conditions under which it is valid, why the **continuity correction** is needed, and how accurate the result actually is.

---

# 1. A large binomial resembles a normal distribution

Look back at the fair-coin table in 08. Even with only 5 trials, the shape was already faintly bell-like: low at the ends, peaked in the middle, symmetric.

As $n$ grows, that resemblance becomes very close.

Suppose:

$$
X\sim\text{Binomial}(100,0.5)
$$

This represents $n=100$ independent trials with $p=0.5$ — for example, 100 independent fair coin flips. Plotted, the PMF is a tight, symmetric bell.

## Why this happens

This is not a coincidence about coins. Recall from 08 that a binomial is a **sum of $n$ independent Bernoulli trials**:

$$
X = Y_1 + Y_2 + \cdots + Y_n
$$

And recall from 10 that sums of many independent random quantities tend toward a normal distribution. That result is the **Central Limit Theorem**, and the binomial is one of its cleanest examples.

$$
\boxed{\text{A binomial is a sum of many independent pieces, so it drifts toward a bell}}
$$

---

# 2. The approximation matches the mean and standard deviation

To approximate a binomial with a normal, use a normal that has the **same center and the same spread**. From 08:

$$
\boxed{\mu = np \qquad \sigma = \sqrt{np(1-p)}}
$$

So the approximation is:

$$
\boxed{X\sim\text{Binomial}(n,p) \quad\approx\quad Y\sim N\!\left(np,\; np(1-p)\right)}
$$

## Example

For $X\sim\text{Binomial}(100,0.5)$:

$$
\mu = 100(0.5) = 50
$$

$$
\sigma = \sqrt{100(0.5)(0.5)} = \sqrt{25} = 5
$$

So this binomial is approximated by $N(50, 25)$ — a bell centered at 50 with a standard deviation of 5.

That is exactly why a $\text{Binomial}(100,0.5)$ has a bell-like shape centered around 50.

---

# 3. Conditions for the approximation

A binomial can usually be approximated by a normal when **both** of these hold:

$$
\boxed{np\geq10 \qquad\text{and}\qquad n(1-p)\geq10}
$$

In words: you need at least about 10 expected **successes** and at least about 10 expected **failures**.

## Checking the example

For $n=100$ and $p=0.5$:

$$
np=100(0.5)=50 \qquad n(1-p)=100(0.5)=50
$$

Both are comfortably greater than 10, so the normal approximation works well.

## A note on the threshold

Some textbooks use 5 instead of 10, and some use $np(1-p)\geq10$ as a single combined condition. These are rules of thumb, not exact boundaries — the approximation degrades gradually rather than failing at a cliff. Use whichever your course specifies.

---

# 4. Why the conditions matter

Recall from 08 that $p$ controls the shape. When $p=0.5$ the binomial is symmetric, but when $p$ is far from $0.5$ it becomes **skewed**.

A normal distribution is always symmetric. So it cannot match a skewed binomial, and the approximation gets worse the more lopsided the binomial is.

The two conditions are really one idea: **the bell must have room on both sides**. A count cannot go below 0 or above $n$, so if the center sits too close to either boundary, the distribution gets squashed against it and turns skewed.

## What failure looks like

Take $X\sim\text{Binomial}(20, 0.05)$, so $np=1$, which badly fails the condition.

$$
\mu = 20(0.05) = 1 \qquad \sigma = \sqrt{20(0.05)(0.95)} \approx 0.975
$$

Now ask what the approximating normal $N(1, 0.95)$ says about negative counts:

$$
P(Y<0) = \Phi\!\left(\frac{0-1}{0.975}\right) = \Phi(-1.026) \approx 0.153
$$

**About 15 percent of the approximating normal sits on impossible negative values.** A count of successes can never be negative, so the approximation is putting substantial probability where no probability can exist.

The numbers confirm it: the exact answer for $P(X\leq1)$ is $0.7358$, while the normal approximation gives $0.6960$ — an error of about 4 percentage points, compared with essentially zero error in the well-conditioned example in section 7.

## What to use instead

When $n$ is large but $p$ is very small, the right approximation is the **Poisson** distribution rather than the normal. Poisson is a later topic, but it is the tool for rare events.

---

# 5. Continuity correction: why it is needed

Here is the core mismatch:

$$
\boxed{\text{A binomial is DISCRETE. A normal is CONTINUOUS.}}
$$

A binomial PMF is a set of separate bars at $0, 1, 2, \ldots, n$. A normal PDF is a smooth curve. You are using a curve to estimate the total height of some bars, and the edges do not line up.

## The clearest demonstration

Ask for $P(X=50)$ exactly.

The true binomial answer is $0.0796$ — a real, substantial probability.

But from 06, a continuous distribution assigns **zero** probability to any single exact value:

$$
P(Y=50)=0
$$

So without a correction, the approximation returns 0 for something that happens about 8 percent of the time. That is not a small error; it is completely wrong.

## The fix

Treat each discrete bar as occupying a **width of 1**, running from $k-0.5$ to $k+0.5$. Then measure the area of the normal curve across that whole width instead of at the single point.

$$
P(X=50) \approx P(49.5 < Y < 50.5)
$$

Standardizing with $\mu=50$ and $\sigma=5$:

$$
z_1 = \frac{49.5-50}{5} = -0.1 \qquad z_2 = \frac{50.5-50}{5} = 0.1
$$

$$
\Phi(0.1)-\Phi(-0.1) = 0.5398-0.4602 = 0.0797
$$

Against the exact answer of $0.0796$, that is essentially perfect.

$$
\boxed{\text{Each discrete bar is treated as being 0.5 wide on each side}}
$$

---

# 6. The continuity correction rules

Every case follows one principle:

$$
\boxed{\text{Expand by 0.5 to INCLUDE a value. Shrink by 0.5 to EXCLUDE it.}}
$$

| You want (binomial, discrete) | Use (normal, continuous) |
|---|---|
| $P(X = k)$ | $P(k-0.5 < Y < k+0.5)$ |
| $P(X \leq k)$ | $P(Y < k+0.5)$ |
| $P(X < k)$ | $P(Y < k-0.5)$ |
| $P(X \geq k)$ | $P(Y > k-0.5)$ |
| $P(X > k)$ | $P(Y > k+0.5)$ |
| $P(a \leq X \leq b)$ | $P(a-0.5 < Y < b+0.5)$ |

## How to get the direction right without memorizing

Ask which whole numbers you actually want, then take the outer edges of their bars.

- $P(X\leq55)$ includes the bar at 55, and that bar ends at $55.5$. So the boundary is $55.5$.
- $P(X<55)$ excludes 55, so the largest value included is 54, whose bar ends at $54.5$. So the boundary is $54.5$.

The strict and non-strict versions differ by a whole integer bar, which is why the two boundaries are a full unit apart.

## The most common mistake

Adding $0.5$ in every case out of habit. The direction depends on whether the endpoint is being included or excluded, and getting it backwards shifts the answer by a full bar.

---

# 7. Full worked example

**Problem.** A fair coin is flipped 100 times. What is the probability of getting **at most 55 heads**?

## Step 1: Identify the distribution

$$
X\sim\text{Binomial}(100,0.5) \qquad\text{and we want } P(X\leq55)
$$

## Step 2: Check the conditions

$$
np = 100(0.5) = 50 \geq 10 \qquad\checkmark
$$

$$
n(1-p) = 100(0.5) = 50 \geq 10 \qquad\checkmark
$$

The approximation is valid.

## Step 3: Find the mean and standard deviation

$$
\mu = np = 50 \qquad \sigma = \sqrt{np(1-p)} = \sqrt{25} = 5
$$

## Step 4: Apply the continuity correction

We want $P(X\leq55)$, which **includes** the bar at 55. That bar ends at $55.5$:

$$
P(X\leq55) \approx P(Y<55.5)
$$

## Step 5: Standardize

Using the z-score formula from 11:

$$
z = \frac{55.5-50}{5} = \frac{5.5}{5} = 1.10
$$

## Step 6: Look up the probability

$$
P(Y<55.5) = \Phi(1.10) = 0.8643
$$

## Answer

$$
\boxed{P(X\leq55) \approx 0.8643 \text{, or about } 86.4\%}
$$

---

# 8. How good is the approximation?

The exact binomial answer, computed by summing all 56 terms from $x=0$ to $x=55$, is:

$$
P(X\leq55) = 0.8644
$$

Compare the three results:

| Method | Result | Error |
|---|---|---|
| Exact binomial | $0.8644$ | — |
| Normal **with** continuity correction | $0.8643$ | $0.0001$ |
| Normal **without** continuity correction | $0.8413$ | $0.0230$ |

Two things stand out.

**The approximation is excellent.** With the correction, it is accurate to four decimal places.

**The continuity correction is not optional.** Skipping it produced an error of over 2 percentage points — more than 200 times larger than the corrected error. The correction is doing most of the work here, not the normal curve itself.

## Another check

For $P(45\leq X\leq55)$, the correction gives $P(44.5<Y<55.5)$:

$$
\Phi(1.1)-\Phi(-1.1) = 0.7287
$$

The exact binomial answer is also $0.7287$.

---

# 9. When to use this

## The historical reason

Before computers, computing $P(X\leq55)$ exactly meant evaluating and summing 56 separate binomial terms, each with its own factorial. That was genuinely impractical. The normal approximation reduced it to one subtraction and one table lookup.

## Today

Software gives the exact answer instantly. In Python, `scipy.stats.binom.cdf(55, 100, 0.5)` returns $0.8644$ with no approximation at all. If you have a computer, use the exact binomial.

## Why it still matters

- **Exams and coursework** still ask for it, and the continuity correction is a standard test question
- **It explains the Central Limit Theorem** in the most concrete possible setting — you can watch a discrete count turn into a bell
- **Tests for proportions** use exactly this idea. The sample proportion $\hat{p}=\frac{X}{n}$ is approximately normal for large $n$:

$$
\boxed{\hat{p} \approx N\!\left(p,\; \frac{p(1-p)}{n}\right)}
$$

which is the foundation of z-tests and confidence intervals for proportions, including A/B testing.

- **It builds intuition** about when a bell shape is a reasonable model and when it is not

---

# Most Important Definitions and Distinctions to Remember

## The approximation

$$
\boxed{\text{Binomial}(n,p) \approx N\!\left(np,\; np(1-p)\right)}
$$

$$
\boxed{\mu = np \qquad \sigma = \sqrt{np(1-p)}}
$$

---

## The conditions

$$
\boxed{np\geq10 \qquad\text{and}\qquad n(1-p)\geq10}
$$

Enough expected successes **and** enough expected failures, so the bell has room on both sides.

---

## Continuity correction

$$
\boxed{\text{Discrete bars have width 1, so shift each boundary by } 0.5}
$$

| Want | Use |
|---|---|
| $P(X=k)$ | $P(k-0.5<Y<k+0.5)$ |
| $P(X\leq k)$ | $P(Y<k+0.5)$ |
| $P(X<k)$ | $P(Y<k-0.5)$ |
| $P(X\geq k)$ | $P(Y>k-0.5)$ |
| $P(X>k)$ | $P(Y>k+0.5)$ |

---

## Why it is needed

A binomial is discrete and a normal is continuous. Without the correction, $P(X=k)$ would come out as 0, since a continuous distribution assigns no probability to a single point.

---

# Main Rules to Put in Your Notebook

| Step | Action |
|---|---|
| 1 | Confirm $np\geq10$ and $n(1-p)\geq10$ |
| 2 | Compute $\mu=np$ and $\sigma=\sqrt{np(1-p)}$ |
| 3 | Apply the continuity correction, shifting by $0.5$ |
| 4 | Standardize: $z=\dfrac{\text{corrected boundary}-\mu}{\sigma}$ |
| 5 | Look up $\Phi(z)$ and adjust for direction |

$$
\boxed{\text{Binomial}(n,p) \approx N(np,\, np(1-p)) \quad\text{when } np\geq10 \text{ and } n(1-p)\geq10}
$$

$$
\boxed{P(X\leq k) \approx \Phi\!\left(\frac{k+0.5-np}{\sqrt{np(1-p)}}\right)}
$$

$$
\boxed{\text{Include a value} \rightarrow \text{expand by } 0.5 \qquad \text{Exclude it} \rightarrow \text{shrink by } 0.5}
$$

The biggest idea is:

**A binomial is a sum of many independent trials, and sums of independent things tend toward a bell. So for large $n$ you can replace the binomial with a normal that has the same mean and standard deviation. Because you are using a smooth curve to measure discrete bars, every boundary must be shifted by half a unit — and skipping that correction causes a far larger error than the approximation itself.**

---

# Where This Goes Next

| Idea from this file | Where it comes from or leads |
|---|---|
| $\mu=np$, $\sigma=\sqrt{np(1-p)}$ | **08 — Bernoulli and Binomial** |
| $\Phi(z)$ lookups | **11 — Z-Scores and the Standard Normal** |
| Sums of independent variables tending to a bell | The Central Limit Theorem, a later topic |
| $\hat{p}\approx N\!\left(p,\frac{p(1-p)}{n}\right)$ | Confidence intervals and tests for proportions |
| Poisson for small $np$ | The alternative approximation for rare events |
