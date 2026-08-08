# What You Should Know About Z-Scores and the Standard Normal

> **Prerequisites:** the normal distribution and its PDF are in 10. The linear-transformation rules $E[aX+b]$ and $\text{Var}(aX+b)$ are in 07. The CDF subtraction rule is in 06.
>
> This file was split out of the Normal notes because standardization is a **reusable skill**, not a fact about one distribution. You will use it again for hypothesis tests, confidence intervals, outlier detection, and feature scaling.

These notes cover: why standardization exists, the z-score formula, the standard normal distribution, how to read probabilities from a z-table, how to work backwards from a probability to a value, and what standardization does and does not do.

---

# 1. Why standardization exists

File 10 ended with a problem. Normal probabilities require the area under the curve:

$$
P(a<X<b)=\int_a^b \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}\,dx
$$

and that integral **has no closed-form solution**. It cannot be evaluated by hand, ever.

The obvious fallback would be to publish a table of areas. But there are infinitely many normal distributions — one for every pair $(\mu,\sigma)$ — so you would need infinitely many tables.

## The solution

Convert **every** normal distribution into the same one.

$$
\boxed{\text{Standardize, then use one single table}}
$$

Standardization rescales any normal distribution onto a common reference curve, so that a single table of areas answers every question about every normal distribution.

---

# 2. The z-score formula

A **z-score** tells you how many standard deviations a value is above or below the mean.

$$
\boxed{z=\frac{x-\mu}{\sigma}}
$$

where:

- $z$: z-score
- $x$: observed value
- $\mu$: population mean
- $\sigma$: population standard deviation

## Reading the formula

It does two things in order:

1. **$x-\mu$ centers the value.** Now it is a distance from the mean rather than a raw measurement.
2. **Dividing by $\sigma$ rescales it.** Now that distance is counted in standard deviations rather than in the original units.

## A z-score has no units

If $x$ is in dollars, then $\mu$ is in dollars and $\sigma$ is in dollars, so the units cancel:

$$
\frac{\text{dollars}}{\text{dollars}} = \text{a pure number}
$$

This is exactly why z-scores let you compare quantities measured on completely different scales, as section 7 shows.

---

# 3. Interpreting z-scores

| $z$ | Meaning |
|---|---|
| $z=0$ | The value is exactly at the mean |
| $z=1$ | One standard deviation **above** the mean |
| $z=-1$ | One standard deviation **below** the mean |
| $z=2$ | Two standard deviations above the mean |
| $z=-2$ | Two standard deviations below the mean |

So:

$$
\boxed{\text{The sign gives direction, and the size gives distance}}
$$

A positive z is above average, a negative z is below average, and $|z|$ measures how unusual the value is. Using the empirical rule from 10, a $|z|$ above 2 is already uncommon and a $|z|$ above 3 is rare.

---

# 4. The standard normal distribution

After standardization, the resulting variable is written $Z$ and follows:

$$
\boxed{Z\sim N(0,1)}
$$

The **standard normal distribution** has:

$$
\mu=0 \qquad \sigma=1 \qquad \sigma^2=1
$$

It is still a normal distribution with all the properties from 10 — symmetric, bell-shaped, total area 1 — just centered at zero with a standard deviation of one.

Its CDF gets its own symbol:

$$
\boxed{\Phi(z)=P(Z\leq z)}
$$

The capital Greek letter phi is standard notation, and $\Phi$ is what a z-table actually contains.

---

# 5. Why standardizing gives mean 0 and standard deviation 1

This is not a convention or a coincidence. It follows from the rules in 07.

Rewrite the z-score in the form $aX+b$:

$$
Z=\frac{X-\mu}{\sigma}=\left(\frac{1}{\sigma}\right)X-\frac{\mu}{\sigma}
\qquad\text{so}\qquad
a=\frac{1}{\sigma},\quad b=-\frac{\mu}{\sigma}
$$

Apply $E[aX+b]=aE[X]+b$:

$$
E[Z]=\frac{1}{\sigma}\mu-\frac{\mu}{\sigma}=0
$$

Apply $\text{Var}(aX+b)=a^2\text{Var}(X)$:

$$
\text{Var}(Z)=\left(\frac{1}{\sigma}\right)^2\sigma^2=1
$$

Therefore:

$$
\boxed{\text{Every standardized variable has mean } 0 \text{ and standard deviation } 1}
$$

Note that this part works for **any** distribution, not only normal ones. Subtracting the mean and dividing by the standard deviation always produces mean 0 and SD 1. What requires normality is the *next* step — using a z-table. Section 13 returns to this.

---

# 6. Z-score example

Suppose test scores follow:

$$
X\sim N(70,10^2)
$$

Therefore $\mu=70$ and $\sigma=10$.

Suppose a student scores $x=85$. Then:

$$
z=\frac{x-\mu}{\sigma}=\frac{85-70}{10}=\frac{15}{10}=1.5
$$

Therefore, the student's score is:

**1.5 standard deviations above the mean.**

A second student scores $x=60$:

$$
z=\frac{60-70}{10}=-1
$$

which is one standard deviation **below** the mean.

---

# 7. Comparing values measured on different scales

This is the everyday use of z-scores, separate from any probability calculation.

Suppose one student takes the SAT and another takes the ACT:

| Student | Test | Score | Distribution | z-score |
|---|---|---|---|---|
| A | SAT | 1300 | $N(1050,200^2)$ | $\dfrac{1300-1050}{200}=1.25$ |
| B | ACT | 28 | $N(21,5.5^2)$ | $\dfrac{28-21}{5.5}\approx1.27$ |

The raw scores, 1300 and 28, cannot be compared at all — they are on different scales with different ranges. The z-scores can be: both students are about 1.25 standard deviations above average, with student B very slightly ahead.

$$
\boxed{\text{Standardization makes different scales comparable}}
$$

---

# 8. Using a z-table

A **z-table** gives values of $\Phi(z)=P(Z\leq z)$, the area to the **left** of $z$ under the standard normal curve.

Some common values:

| $z$ | $\Phi(z)$ | | $z$ | $\Phi(z)$ |
|---|---|---|---|---|
| $-3.0$ | $0.0013$ | | $0.5$ | $0.6915$ |
| $-2.0$ | $0.0228$ | | $1.0$ | $0.8413$ |
| $-1.5$ | $0.0668$ | | $1.5$ | $0.9332$ |
| $-1.0$ | $0.1587$ | | $1.96$ | $0.9750$ |
| $-0.5$ | $0.3085$ | | $2.0$ | $0.9772$ |
| $0$ | $0.5000$ | | $3.0$ | $0.9987$ |

## The three-step procedure

$$
\boxed{\text{Standardize} \rightarrow \text{look up } \Phi \rightarrow \text{adjust for the direction you want}}
$$

## Example: probability below a value

Using $X\sim N(70,10^2)$, what is $P(X<85)$?

Standardize:

$$
z=\frac{85-70}{10}=1.5
$$

Look up:

$$
P(X<85)=\Phi(1.5)=0.9332
$$

So about **93.3 percent** of students score below 85.

## Example: probability above a value

For $P(X>85)$, use the complement rule from 01:

$$
P(X>85)=1-\Phi(1.5)=1-0.9332=0.0668
$$

So about **6.7 percent** score above 85.

## Symmetry saves table space

Because the standard normal is symmetric about zero:

$$
\boxed{\Phi(-z)=1-\Phi(z)}
$$

Check it: $\Phi(-1)=0.1587$ and $1-\Phi(1)=1-0.8413=0.1587$. This is why some tables only list positive values of $z$.

---

# 9. Probability between two values

Recall the subtraction rule from 06:

$$
P(a<X<b)=F_X(b)-F_X(a)
$$

Standardize **both** endpoints, then subtract:

$$
\boxed{P(a<X<b)=\Phi\!\left(\frac{b-\mu}{\sigma}\right)-\Phi\!\left(\frac{a-\mu}{\sigma}\right)}
$$

## Example

Using $X\sim N(70,10^2)$, find $P(60<X<85)$.

Standardize each endpoint:

$$
z_1=\frac{60-70}{10}=-1 \qquad z_2=\frac{85-70}{10}=1.5
$$

Look both up and subtract:

$$
P(60<X<85)=\Phi(1.5)-\Phi(-1)=0.9332-0.1587=0.7745
$$

So about **77.5 percent** of students score between 60 and 85.

## The most common mistake

Standardizing only one endpoint. Both endpoints must be converted, because the table only understands z-values.

---

# 10. Working backwards: from probability to a value

Sometimes the probability is given and the value is unknown. For example: what score puts a student in the top 10 percent?

Run the process in reverse.

$$
\boxed{\text{Find } z \text{ from the probability, then convert back with } x=\mu+z\sigma}
$$

The rearranged formula is:

$$
\boxed{x=\mu+z\sigma}
$$

## Example

The top 10 percent means the 90th percentile, so we need the $z$ with $\Phi(z)=0.90$. From the table, $z\approx1.2816$. Convert back:

$$
x=70+1.2816(10)=82.8
$$

So a score of about **82.8** puts a student in the top 10 percent.

## Critical values worth memorizing

These appear constantly in confidence intervals and hypothesis tests:

| Central probability | $z$ | One-tailed percentile | $z$ |
|---|---|---|---|
| $90\%$ | $\pm1.645$ | $90$th | $1.282$ |
| $95\%$ | $\pm1.960$ | $95$th | $1.645$ |
| $99\%$ | $\pm2.576$ | $99$th | $2.326$ |

Note that $1.645$ appears in both columns but means different things: as a two-tailed bound it captures the central 90 percent, and as a one-tailed value it marks the 95th percentile. Always check whether the problem is one-tailed or two-tailed.

---

# 11. The empirical rule restated in z-scores

The 68-95-99.7 rule from 10 is really just three z-table lookups:

| Interval in $X$ | Interval in $Z$ | Probability |
|---|---|---|
| $\mu\pm\sigma$ | $-1<Z<1$ | $0.6827$ |
| $\mu\pm2\sigma$ | $-2<Z<2$ | $0.9545$ |
| $\mu\pm3\sigma$ | $-3<Z<3$ | $0.9973$ |

Verify the first one with the table:

$$
\Phi(1)-\Phi(-1)=0.8413-0.1587=0.6827
$$

This is why the same three percentages hold for every normal distribution. The rule was always stated in standard-deviation units, which means it was always a statement about $Z$, not about any particular $X$.

$$
\boxed{\text{The empirical rule is the z-table, memorized at three points}}
$$

---

# 12. Standardization in machine learning

Outside of probability tables, standardization has a second life as **feature scaling**. In scikit-learn this is `StandardScaler`, and it performs exactly the same calculation on every column:

$$
z=\frac{x-\mu}{\sigma}
$$

## Why it matters

Consider a dataset with income in dollars (0 to 100,000) and years of experience (0 to 50). Without scaling, income dominates purely because its numbers are larger. This breaks several families of model:

- **Distance-based methods** — k-nearest neighbours, k-means, SVM with an RBF kernel. Distance is computed across all features at once, so a large-scale feature drowns out the others.
- **Gradient descent** — converges much faster when features have comparable scales, because the loss surface is more evenly shaped.
- **Regularized models** — ridge and lasso penalize coefficient size, so an unscaled feature is penalized for its units rather than its usefulness.

Models that are **not** affected include decision trees and random forests, which split one feature at a time and do not care about relative scale.

## The rule that is easy to get wrong

$$
\boxed{\text{Fit the scaler on training data only, then apply the same } \mu \text{ and } \sigma \text{ to the test data}}
$$

Computing $\mu$ and $\sigma$ from the entire dataset leaks information about the test set into training and produces optimistic results that do not hold up.

## A related but different transformation

**Min-max normalization** rescales to a fixed range instead:

$$
x' = \frac{x - \min}{\max - \min}
$$

This forces every value into $[0,1]$. Standardization does not bound the range — it fixes the mean and spread. The two are different operations solving different problems, and "normalization" is often used loosely for either, so check what is meant.

---

# 13. What standardization does NOT do

This is the most important warning in the file.

$$
\boxed{\text{Standardizing does NOT make data normal}}
$$

The z-score formula subtracts a constant and divides by a constant. Section 5 showed that this changes the mean to 0 and the standard deviation to 1 — and it changes **nothing else**.

- A skewed distribution stays exactly as skewed
- A bimodal distribution keeps both peaks
- Heavy tails stay heavy
- Bounded data stays bounded

Shifting and rescaling slides the picture along and stretches its axis. It cannot change the shape.

## Why this matters

Sections 8 through 11 all used a z-table, and that step is **only valid if the original data were already normal**. If they were not, the z-score is still a perfectly meaningful description of relative position — "this point is 2.1 standard deviations above average" — but $\Phi(2.1)$ does not give the right probability.

| What you want | Does standardization achieve it? |
|---|---|
| Mean 0, SD 1 | Yes, always, for any distribution |
| Comparable scales across features | Yes |
| A measure of relative position | Yes |
| Probabilities from a z-table | Only if the data were already normal |
| Turning skewed data into normal data | **No** |

## What to use instead

To actually change the shape of a distribution you need a **non-linear** transformation — a log transform, a square root, or a Box-Cox or Yeo-Johnson transform. Those can reduce skew. Standardization cannot, because it is linear.

---

# Most Important Definitions and Distinctions to Remember

## Z-score

$$
\boxed{z=\frac{x-\mu}{\sigma}}
$$

The number of standard deviations a value sits above or below the mean. Unitless.

---

## Standard normal distribution

$$
\boxed{Z\sim N(0,1) \qquad \mu=0 \qquad \sigma=1}
$$

Its CDF is written $\Phi(z)=P(Z\leq z)$, and this is what a z-table contains.

---

## Converting back

$$
\boxed{x=\mu+z\sigma}
$$

---

## Reading probabilities

$$
\boxed{P(X<x)=\Phi\!\left(\frac{x-\mu}{\sigma}\right)}
$$

$$
\boxed{P(X>x)=1-\Phi\!\left(\frac{x-\mu}{\sigma}\right)}
$$

$$
\boxed{P(a<X<b)=\Phi\!\left(\frac{b-\mu}{\sigma}\right)-\Phi\!\left(\frac{a-\mu}{\sigma}\right)}
$$

---

## Symmetry

$$
\boxed{\Phi(-z)=1-\Phi(z)}
$$

---

## The critical distinction

| | Effect |
|---|---|
| Standardization **does** | Set mean to 0 and SD to 1, make scales comparable |
| Standardization **does not** | Change the shape, or make skewed data normal |

---

# Main Rules to Put in Your Notebook

| Concept | Rule |
|---|---|
| Z-score | $z=\dfrac{x-\mu}{\sigma}$ |
| Convert back | $x=\mu+z\sigma$ |
| Standard normal | $Z\sim N(0,1)$ |
| Standard normal CDF | $\Phi(z)=P(Z\leq z)$ |
| Below a value | $P(X<x)=\Phi(z)$ |
| Above a value | $P(X>x)=1-\Phi(z)$ |
| Between two values | $\Phi(z_2)-\Phi(z_1)$ |
| Symmetry | $\Phi(-z)=1-\Phi(z)$ |
| Exact 95 percent | $z=\pm1.96$ |
| Exact 99 percent | $z=\pm2.576$ |
| $z=\pm1,\pm2,\pm3$ | $68.27\%$, $95.45\%$, $99.73\%$ |

The biggest idea is:

**A z-score converts a value into the number of standard deviations it sits from the mean, which removes the units and puts every normal distribution onto one common curve. That is what makes a single table of areas usable for all of them. Standardizing always produces mean 0 and standard deviation 1, but it never changes the shape of the distribution — so the table only applies if the data were already normal.**

---

# Where This Goes Next

| Idea from this file | Where it is used |
|---|---|
| $\Phi(z)$ and z-table lookups | **12 — Normal Approximation to the Binomial**: how the approximate answer is computed |
| $x=\mu+z\sigma$ | **12**: converting binomial counts into z-values |
| $z=\pm1.96$ | Confidence intervals and hypothesis testing |
| $\lvert z\rvert>3$ as unusual | Outlier detection |
| Feature scaling | Any distance-based or gradient-based model |
| Modelling a feature as normal | **13 — Naive Bayes**: Gaussian Naive Bayes uses the normal PDF per feature |
