# What You Should Know About the Normal Distribution

These slides are mainly teaching **eleven important ideas** about how the normal distribution works, what its parameters mean, and how probability is calculated from it.

---

## 1. A normal distribution is a symmetric bell-shaped distribution

A **normal distribution** is a continuous, symmetric, bell-shaped probability distribution.

A normal distribution:

- Has most observations near the center
- Has fewer observations as you move farther from the center
- Is symmetric: the left and right sides mirror each other
- Extends across all real numbers
- Has a total area of **1**

Because the total area equals 1, areas under the curve represent probabilities.

$$
\text{Total area under the curve}=1
$$

For a perfectly normal distribution:

$$
\text{Mean}=\text{Median}=\text{Mode}
$$

All three are located at the center of the curve.

Because the distribution is symmetric, exactly half of the area is on each side of the mean:

$$
P(X<\mu)=0.50
$$

and:

$$
P(X>\mu)=0.50
$$

---

# 2. The mean controls the center

The population mean is written:

$$
\mu
$$

The mean determines where the **center and peak** of the normal distribution are located.

For example:

If:

$$
\mu=0
$$

the curve is centered at 0.

If:

$$
\mu=2
$$

the curve is centered at 2.

Changing $\mu$:

- Moves the curve left or right
- Changes the location of the center
- Does **not** change the width of the curve
- Does **not** change the overall bell shape

Therefore:

$$
\mu=\text{center of the distribution}
$$

---

# 3. Standard deviation controls the spread

The population standard deviation is written:

$$
\sigma
$$

Standard deviation measures how spread out the values are around the mean.

Therefore:

$$
\sigma=\text{spread of the distribution}
$$

### Small standard deviation

A small $\sigma$ produces a:

- Narrower curve
- Taller peak
- More concentrated distribution
- Greater concentration of values near the mean

### Large standard deviation

A large $\sigma$ produces a:

- Wider curve
- Shorter peak
- More spread-out distribution

For example:

$$
\sigma=1
$$

produces a relatively narrow curve, while:

$$
\sigma=3
$$

produces a wider curve.

The total area remains:

$$
1
$$

in both cases.

Because the total area must remain 1, making the curve wider also makes it shorter.

---

# 4. Mean versus standard deviation

The mean and standard deviation control different properties of the normal distribution.

| Parameter | Meaning | Effect on the Curve |
|---|---|---|
| $\mu$ | Mean | Moves the center left or right |
| $\sigma$ | Standard deviation | Makes the curve narrower or wider |

Remember:

$$
\mu=\text{center}
$$

$$
\sigma=\text{spread}
$$

Changing $\mu$ does **not** change the spread.

Changing $\sigma$ does **not** move the center.

---

# 5. Standard deviation versus variance

Standard deviation and variance are closely related, but they are **not the same thing**.

### Standard deviation

$$
\sigma
$$

Standard deviation is measured in the **same units as the original data**.

### Variance

$$
\sigma^2
$$

Variance is the square of the standard deviation.

Therefore:

$$
\sigma^2=\text{variance}
$$

and:

$$
\sigma=\sqrt{\sigma^2}
$$

### Example

Suppose:

$$
\sigma^2=25
$$

Then:

$$
\sigma=\sqrt{25}
$$

$$
=5
$$

So:

- Variance = 25
- Standard deviation = 5

---

# 6. Know the normal-distribution notation

A normal random variable is commonly written:

$$
X\sim N(\mu,\sigma^2)
$$

This means:

- $X$: random variable
- $\sim$: "is distributed as"
- $N$: normal distribution
- $\mu$: population mean
- $\sigma^2$: population variance

Therefore:

$$
X\sim N(\mu,\sigma^2)
$$

means:

**X follows a normal distribution with mean $\mu$ and variance $\sigma^2$.**

### Example

Suppose:

$$
X\sim N(50,25)
$$

This means:

$$
\mu=50
$$

and:

$$
\sigma^2=25
$$

Because:

$$
\sigma=\sqrt{\sigma^2}
$$

we get:

$$
\sigma=\sqrt{25}
$$

$$
=5
$$

Therefore:

$$
X\sim N(50,25)
$$

has:

- Mean = 50
- Variance = 25
- Standard deviation = 5

### Important distinction

The second number in:

$$
N(\mu,\sigma^2)
$$

is normally the **variance**, not the standard deviation.

However, some software may use:

$$
N(\mu,\sigma)
$$

instead.

Always check which notation is being used.

---

# 7. The normal PDF describes density

The **probability density function**, or PDF, for a normal distribution is:

$$
f_X(x)= \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}
$$

You should understand what the pieces of the formula mean, but you usually will **not** calculate the entire formula manually.

| Symbol | Meaning |
|---|---|
| $f_X(x)$ | Density of $X$ at $x$ |
| $x$ | Particular value being evaluated |
| $\mu$ | Population mean |
| $\sigma$ | Population standard deviation |
| $\sigma^2$ | Population variance |
| $e$ | Euler's number, approximately 2.718 |
| $\pi$ | Pi, approximately 3.14159 |

---

## What each part of the PDF does

The expression:

$$
x-\mu
$$

measures how far $x$ is from the mean.

The expression:

$$
\frac{x-\mu}{\sigma}
$$

measures how far $x$ is from the mean in **standard-deviation units**.

The exponential portion:

$$
e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}
$$

creates the bell-shaped curve.

The expression:

$$
\frac{1}{\sigma\sqrt{2\pi}}
$$

is a **scaling constant**.

It adjusts the curve so that the total area underneath it equals:

$$
1
$$

Without the scaling constant, the total area under:

$$
e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}
$$

would equal:

$$
\sigma\sqrt{2\pi}
$$

For example, if:

$$
\sigma=3
$$

the unscaled area would be:

$$
3\sqrt{2\pi}
$$

Multiplying by:

$$
\frac{1}{3\sqrt{2\pi}}
$$

makes the total area equal:

$$
1
$$

---

# 8. Probability is area, not the curve's height

This is one of the most important ideas to understand about continuous distributions.

For a continuous random variable:

$$
P(X=x)=0
$$

The probability of one exact value is zero.

Why?

Because an individual point has **no width**, so it has no area underneath the curve.

Therefore, you normally calculate probability over an **interval**.

For example:

$$
P(a<X<b)
$$

This represents the area under the density curve between $a$ and $b$.

Mathematically:

$$
P(a<X<b)=\int_a^b f_X(x)\,dx
$$

Therefore:

$$
\text{PDF height}=\text{density}
$$

while:

$$
\text{Area under the PDF}=\text{probability}
$$

### Important distinction

The height of the PDF at one point is **not** the probability of that exact value.

Instead:

**Density × interval width produces probability through area.**

---

# 9. The CDF gives accumulated probability

The **cumulative distribution function**, or CDF, is:

$$
F_X(x)=P(X\leq x)
$$

The CDF tells you the probability that $X$ is **less than or equal to** a particular value.

Therefore:

$$
F_X(x)=P(X\leq x)
$$

The normal PDF is **bell-shaped**.

The normal CDF is **S-shaped**.

---

## PDF versus CDF

### PDF

$$
f_X(x)
$$

The PDF shows where values are most densely concentrated.

### CDF

$$
F_X(x)
$$

The CDF shows how much total probability has accumulated from the far left of the distribution up to $x$.

---

## Important CDF properties

The CDF must always be between 0 and 1:

$$
0\leq F_X(x)\leq1
$$

As $x$ moves toward negative infinity:

$$
F_X(x)\rightarrow0 \quad\text{as }x\rightarrow-\infty
$$

As $x$ moves toward positive infinity:

$$
F_X(x)\rightarrow1 \quad\text{as }x\rightarrow\infty
$$

At the mean of a normal distribution:

$$
F_X(\mu)=0.50
$$

because half of the normal distribution lies below the mean.

---

## Finding probability between two values with the CDF

To calculate:

$$
P(a<X<b)
$$

using the CDF:

$$
P(a<X<b)=F_X(b)-F_X(a)
$$

In words:

$$
\text{Probability between two values} = \text{upper CDF} - \text{lower CDF}
$$

---

# 10. Standardization converts values into z-scores

A **z-score** tells you how many standard deviations a value is above or below the mean.

The standardization formula is:

$$
z=\frac{x-\mu}{\sigma}
$$

where:

- $z$: z-score
- $x$: observed value
- $\mu$: population mean
- $\sigma$: population standard deviation

---

## Interpreting z-scores

If:

$$
z=0
$$

the value is exactly at the mean.

If:

$$
z=1
$$

the value is **one standard deviation above the mean**.

If:

$$
z=-1
$$

the value is **one standard deviation below the mean**.

If:

$$
z=2
$$

the value is **two standard deviations above the mean**.

If:

$$
z=-2
$$

the value is **two standard deviations below the mean**.

---

## The standard normal distribution

After standardization:

$$
Z\sim N(0,1)
$$

The standard normal distribution has:

$$
\mu=0
$$

and:

$$
\sigma=1
$$

Therefore:

$$
Z\sim N(0,1)
$$

---

## Z-score example

Suppose test scores follow:

$$
X\sim N(70,10^2)
$$

Therefore:

$$
\mu=70
$$

and:

$$
\sigma=10
$$

Suppose a student scores:

$$
x=85
$$

Use:

$$
z=\frac{x-\mu}{\sigma}
$$

Substitute:

$$
z=\frac{85-70}{10}
$$

$$
=\frac{15}{10}
$$

$$
=1.5
$$

Therefore, the student's score is:

**1.5 standard deviations above the mean.**

Standardization makes it easier to compare values measured on different scales.

---

# 11. Remember the 68-95-99.7 rule

For an approximately normal distribution, most observations occur within a few standard deviations of the mean.

This is called the:

**68-95-99.7 Rule**

or:

**Empirical Rule**

---

## Within one standard deviation

Approximately:

$$
68\%
$$

of observations fall between:

$$
\mu-\sigma
$$

and:

$$
\mu+\sigma
$$

Therefore:

$$
P(\mu-\sigma<X<\mu+\sigma)\approx68\%
$$

---

## Within two standard deviations

Approximately:

$$
95\%
$$

of observations fall between:

$$
\mu-2\sigma
$$

and:

$$
\mu+2\sigma
$$

Therefore:

$$
P(\mu-2\sigma<X<\mu+2\sigma)\approx95\%
$$

---

## Within three standard deviations

Approximately:

$$
99.7\%
$$

of observations fall between:

$$
\mu-3\sigma
$$

and:

$$
\mu+3\sigma
$$

Therefore:

$$
P(\mu-3\sigma<X<\mu+3\sigma)\approx99.7\%
$$

---

## Example

Suppose:

$$
\mu=70
$$

and:

$$
\sigma=10
$$

### Within one standard deviation

$$
70-10=60
$$

$$
70+10=80
$$

Approximately:

$$
68\%
$$

of observations fall between:

$$
60\text{ and }80
$$

### Within two standard deviations

$$
70-20=50
$$

$$
70+20=90
$$

Approximately:

$$
95\%
$$

fall between:

$$
50\text{ and }90
$$

### Within three standard deviations

$$
70-30=40
$$

$$
70+30=100
$$

Approximately:

$$
99.7\%
$$

fall between:

$$
40\text{ and }100
$$

---

# 12. A large binomial distribution can resemble a normal distribution

A binomial distribution can sometimes be approximated using a normal distribution.

Suppose:

$$
X\sim\mathrm{Binomial}(100,0.5)
$$

This represents:

$$
n=100
$$

independent trials where:

$$
p=0.5
$$

For example, this could represent 100 independent fair coin flips.

---

## Binomial mean

The binomial mean is:

$$
\mu=np
$$

Substitute:

$$
\mu=100(0.5)
$$

$$
=50
$$

Therefore, the distribution is centered around 50.

---

## Binomial standard deviation

The binomial standard deviation is:

$$
\sigma=\sqrt{np(1-p)}
$$

Substitute:

$$
\sigma= \sqrt{100(0.5)(0.5)}
$$

$$
=\sqrt{25}
$$

$$
=5
$$

This is why a binomial distribution with:

$$
n=100,\qquad p=0.5
$$

has a bell-like shape centered around:

$$
50
$$

---

# 13. Conditions for a normal approximation to the binomial

A binomial distribution can usually be approximated by a normal distribution when both:

$$
np\geq10
$$

and:

$$
n(1-p)\geq10
$$

For:

$$
n=100
$$

and:

$$
p=0.5
$$

we have:

$$
np=100(0.5)=50
$$

and:

$$
n(1-p)=100(0.5)=50
$$

Both are greater than:

$$
10
$$

Therefore, the normal approximation works well.

---

# 14. Continuity correction

A binomial distribution is **discrete**, while a normal distribution is **continuous**.

Because of this difference, a **continuity correction** may be used when approximating a binomial probability with a normal distribution.

For example, suppose we want:

$$
P(X\leq55)
$$

Using a normal approximation, this becomes approximately:

$$
P(Y\leq55.5)
$$

The:

$$
0.5
$$

adjustment helps account for the difference between discrete bars and a continuous curve.

Therefore:

$$
P(X\leq55)\approx P(Y\leq55.5)
$$

---

# 15. Normal-distribution applications

Normal distributions may approximately describe measurements influenced by many small independent factors.

Examples include:

- Human height within a defined population
- Measurement errors
- Some standardized test scores
- Manufacturing variation
- Communication-system noise
- Sampling distributions

However, **not every bell-shaped dataset is exactly normal**.

You should not automatically assume that data are normally distributed simply because they appear approximately bell-shaped.

---

# 16. Normality in machine learning and statistics

Machine-learning models do **not** universally require every input variable to follow a normal distribution.

Some statistical models instead make assumptions about the distribution of their:

**Errors or residuals**

rather than requiring every original variable to be normally distributed.

Therefore:

$$
\text{Normality is not automatically required for every variable}
$$

---

# Most Important Definitions and Distinctions to Remember

## Normal distribution

A normal distribution is a:

**Continuous, symmetric, bell-shaped probability distribution.**

Its total area is:

$$
1
$$

For a perfectly normal distribution:

$$
\text{Mean}=\text{Median}=\text{Mode}
$$

---

## Mean

The mean determines the center of the distribution.

$$
\mu=\text{center}
$$

Changing $\mu$ moves the curve left or right.

---

## Standard deviation

Standard deviation determines the spread of the distribution.

$$
\sigma=\text{spread}
$$

A smaller $\sigma$ creates a narrower curve.

A larger $\sigma$ creates a wider curve.

---

## Variance

Variance is the square of the standard deviation.

$$
\sigma^2=\text{variance}
$$

Therefore:

$$
\sigma=\sqrt{\sigma^2}
$$

---

## Normal-distribution notation

$$
X\sim N(\mu,\sigma^2)
$$

where:

- $\mu$ = mean
- $\sigma^2$ = variance
- $\sigma$ = standard deviation

---

## PDF

The probability density function describes **density**.

$$
f_X(x)
$$

Remember:

$$
\text{PDF height}=\text{density}
$$

and:

$$
\text{Area under the PDF}=\text{probability}
$$

For a continuous random variable:

$$
P(X=x)=0
$$

---

## CDF

The cumulative distribution function gives accumulated probability.

$$
F_X(x)=P(X\leq x)
$$

To calculate probability between two values:

$$
P(a<X<b)=F_X(b)-F_X(a)
$$

---

## Z-score

The z-score tells you how many standard deviations a value is from the mean.

$$
z=\frac{x-\mu}{\sigma}
$$

The standard normal distribution is:

$$
Z\sim N(0,1)
$$

---

## 68-95-99.7 Rule

For an approximately normal distribution:

$$
P(\mu-\sigma<X<\mu+\sigma)\approx68\%
$$

$$
P(\mu-2\sigma<X<\mu+2\sigma)\approx95\%
$$

$$
P(\mu-3\sigma<X<\mu+3\sigma)\approx99.7\%
$$

---

## Binomial normal approximation

For a binomial distribution:

$$
\mu=np
$$

and:

$$
\sigma=\sqrt{np(1-p)}
$$

A normal approximation generally works well when:

$$
np\geq10
$$

and:

$$
n(1-p)\geq10
$$

---

# Main Rules to Put in Your Notebook

$$
X\sim N(\mu,\sigma^2)
$$

$$
\mu=\text{center}
$$

$$
\sigma=\text{spread}
$$

$$
\sigma^2=\text{variance}
$$

$$
\text{Total area under the PDF}=1
$$

$$
P(X=x)=0 \text{ for a continuous random variable}
$$

$$
\text{Probability}=\text{area under the PDF}
$$

$$
F_X(x)=P(X\leq x)
$$

$$
P(a<X<b)=F_X(b)-F_X(a)
$$

$$
z=\frac{x-\mu}{\sigma}
$$

$$
Z\sim N(0,1)
$$

$$
68\%-95\%-99.7\%
$$

For the binomial normal approximation:

$$
\mu=np
$$

$$
\sigma=\sqrt{np(1-p)}
$$

The biggest idea is:

**The PDF gives density, the area under the PDF gives probability, and the CDF gives accumulated probability. The mean controls the center, the standard deviation controls the spread, and z-scores measure how far a value is from the mean in standard-deviation units.**
