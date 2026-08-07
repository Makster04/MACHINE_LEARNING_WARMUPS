# What You Should Know About the Normal Distribution

These slides are mainly teaching **six important ideas**.

---

## 1. A normal distribution is a symmetric bell-shaped distribution

A normal distribution:

* Has most observations near the center
* Has fewer observations as you move farther from the center
* Is symmetric: the left and right sides mirror each other
* Extends across all real numbers
* Has a total area of **1**

Because the total area equals 1, areas under the curve represent probabilities.

[
\text{Total area under the curve}=1
]

For a perfectly normal distribution:

[
\text{Mean}=\text{Median}=\text{Mode}
]

All three are located at the center of the curve.

---

# 2. The mean controls the center

The population mean is written:

[
\mu
]

It determines where the center and peak of the distribution are located.

For example:

* If (\mu=0), the curve is centered at 0.
* If (\mu=2), the same curve shifts and becomes centered at 2.
* Changing (\mu) moves the curve left or right.
* Changing (\mu) does **not** change the width of the curve.

In the slides, the data are centered around:

[
\mu=2
]

---

# 3. Standard deviation controls the spread

The population standard deviation is written:

[
\sigma
]

It measures how spread out the values are around the mean.

### Small standard deviation

A small (\sigma) creates a:

* Narrower curve
* Taller peak
* More concentrated distribution

### Large standard deviation

A large (\sigma) creates a:

* Wider curve
* Shorter peak
* More spread-out distribution

For example:

[
\sigma=1
]

produces a narrow curve, while:

[
\sigma=3
]

produces a wider curve.

The total area remains 1 in both cases. The wider curve must therefore become shorter.

---

# 4. Know the normal-distribution notation

A normal random variable is written:

[
X\sim N(\mu,\sigma^2)
]

This means:

* (X): the random variable
* (\sim): “is distributed as”
* (N): normal distribution
* (\mu): population mean
* (\sigma^2): population variance

Be careful: the second number in the notation is usually the **variance**, not the standard deviation.

For example:

[
X\sim N(50,25)
]

means:

[
\mu=50
]

[
\sigma^2=25
]

Therefore:

[
\sigma=\sqrt{25}=5
]

Some software uses (N(\mu,\sigma)) instead, so always check the notation being used.

---

# 5. The normal PDF describes density

The probability density function is:

[
f_X(x)=
\frac{1}{\sigma\sqrt{2\pi}}
e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}
]

You should know what the pieces mean, but you usually will not calculate this entire formula by hand.

| Symbol     | Meaning                             |
| ---------- | ----------------------------------- |
| (f_X(x))   | Density of (X) at (x)               |
| (x)        | Particular value being evaluated    |
| (\mu)      | Population mean                     |
| (\sigma)   | Population standard deviation       |
| (\sigma^2) | Population variance                 |
| (e)        | Euler’s number, approximately 2.718 |
| (\pi)      | Pi, approximately 3.14159           |

### What each part does

The expression:

[
x-\mu
]

measures how far (x) is from the mean.

The expression:

[
\frac{x-\mu}{\sigma}
]

measures that distance in standard-deviation units.

The exponential portion creates the bell shape:

[
e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}
]

The part:

[
\frac{1}{\sigma\sqrt{2\pi}}
]

is a **scaling constant**. It adjusts the curve so that its total area equals 1.

Without that scaling constant, the area under:

[
e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2}
]

would be:

[
\sigma\sqrt{2\pi}
]

For example, when (\sigma=3), the unscaled area is:

[
3\sqrt{2\pi}
]

Multiplying by:

[
\frac{1}{3\sqrt{2\pi}}
]

changes the total area to 1.

---

# 6. Probability is area, not the curve’s height

For a continuous random variable:

[
P(X=x)=0
]

An exact value has zero probability because an individual point has no width.

You calculate probability over an interval:

[
P(a<X<b)
]

This is the area under the density curve between (a) and (b):

[
P(a<X<b)=\int_a^b f_X(x),dx
]

Therefore:

* **PDF height** = density
* **Area under the PDF** = probability

This is one of the most important distinctions to remember.

---

# 7. The CDF gives accumulated probability

The cumulative distribution function is:

[
F_X(x)=P(X\leq x)
]

It tells you the probability that (X) is less than or equal to a particular value.

The normal PDF is bell-shaped, but the normal CDF is S-shaped.

### PDF

[
f_X(x)
]

Shows where values are most densely concentrated.

### CDF

[
F_X(x)
]

Shows how much total probability has accumulated from the far left up to (x).

Important CDF properties:

[
0\leq F_X(x)\leq1
]

[
F_X(x)\rightarrow0
\quad\text{as }x\rightarrow-\infty
]

[
F_X(x)\rightarrow1
\quad\text{as }x\rightarrow\infty
]

At the mean of a normal distribution:

[
F_X(\mu)=0.50
]

because half of the distribution is below the mean.

To find probability between two values:

[
P(a<X<b)=F_X(b)-F_X(a)
]

---

# 8. Standardization converts values into z-scores

The standardization formula is:

[
z=\frac{x-\mu}{\sigma}
]

A z-score tells you how many standard deviations a value is above or below the mean.

* (z=0): exactly at the mean
* (z=1): one standard deviation above the mean
* (z=-1): one standard deviation below the mean
* (z=2): two standard deviations above the mean

After standardization:

[
Z\sim N(0,1)
]

The standard normal distribution has:

[
\mu=0
]

[
\sigma=1
]

### Example

Suppose test scores follow:

[
X\sim N(70,10^2)
]

A student receives 85.

[
z=\frac{85-70}{10}
]

[
z=\frac{15}{10}=1.5
]

The score is therefore **1.5 standard deviations above the mean**.

Standardization allows values measured on different scales to be compared.

---

# 9. Remember the 68–95–99.7 rule

For an approximately normal distribution:

[
P(\mu-\sigma<X<\mu+\sigma)\approx68%
]

About 68% of observations fall within one standard deviation of the mean.

[
P(\mu-2\sigma<X<\mu+2\sigma)\approx95%
]

About 95% fall within two standard deviations.

[
P(\mu-3\sigma<X<\mu+3\sigma)\approx99.7%
]

About 99.7% fall within three standard deviations.

For example, with:

[
\mu=70,\qquad \sigma=10
]

approximately:

* 68% fall between 60 and 80
* 95% fall between 50 and 90
* 99.7% fall between 40 and 100

---

# 10. A large binomial distribution can resemble a normal distribution

The first slide shows:

[
X\sim\operatorname{Binomial}(100,0.5)
]

This represents 100 independent coin flips where:

[
n=100,\qquad p=0.5
]

The binomial mean is:

[
\mu=np
]

[
\mu=100(0.5)=50
]

The binomial standard deviation is:

[
\sigma=\sqrt{np(1-p)}
]

[
\sigma=\sqrt{100(0.5)(0.5)}
]

[
\sigma=\sqrt{25}=5
]

That is why the graph is centered around 50 and has a bell-like shape.

A binomial distribution can usually be approximated by a normal distribution when both:

[
np\geq10
]

and:

[
n(1-p)\geq10
]

Here:

[
np=50
]

[
n(1-p)=50
]

so the approximation works well.

Because a binomial variable is discrete and a normal variable is continuous, a **continuity correction** may be used. For example:

[
P(X\leq55)
]

is approximated using:

[
P(Y\leq55.5)
]

---

# 11. Normal-distribution applications

Normal distributions may approximately describe measurements influenced by many small independent factors, such as:

* Human height within a defined population
* Measurement errors
* Some standardized test scores
* Manufacturing variation
* Communication-system noise
* Sampling distributions

However, not every bell-shaped dataset is exactly normal.

Also, machine-learning models do not universally require every input variable to be normal. Some statistical models assume that **errors or residuals** are approximately normal rather than requiring all original variables to be normal.

---

# Main Rules to Put in Your Notebook

[
\boxed{X\sim N(\mu,\sigma^2)}
]

[
\boxed{\mu=\text{center}}
]

[
\boxed{\sigma=\text{spread}}
]

[
\boxed{\text{Total area under the PDF}=1}
]

[
\boxed{P(X=x)=0\text{ for a continuous variable}}
]

[
\boxed{\text{Probability}=\text{area under the PDF}}
]

[
\boxed{F_X(x)=P(X\leq x)}
]

[
\boxed{P(a<X<b)=F_X(b)-F_X(a)}
]

[
\boxed{z=\frac{x-\mu}{\sigma}}
]

[
\boxed{Z\sim N(0,1)}
]

[
\boxed{68%-95%-99.7%\text{ rule}}
]

For the binomial normal approximation:

[
\boxed{\mu=np}
]

[
\boxed{\sigma=\sqrt{np(1-p)}}
]

The biggest idea is this: **the PDF gives density, the area under it gives probability, and the CDF gives accumulated probability.**
