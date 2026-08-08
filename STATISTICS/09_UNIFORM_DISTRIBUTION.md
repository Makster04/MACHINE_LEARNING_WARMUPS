# What You Should Know About the Uniform Distribution

> **Prerequisites:** PDF, CDF, and the relationship between them are in 06. Mean and variance are in 07. This file gives only the uniform's *specific* formulas and relies on 06 for the general rules that apply to every PDF and CDF.

These notes cover:

- What makes a distribution uniform
- What $a$ and $b$ represent
- Why the PDF has a constant height
- How probability is calculated from the uniform PDF
- The mean and variance
- How the uniform CDF is constructed

---

# 1. A uniform distribution gives equal density throughout an interval

A **continuous uniform distribution** models a continuous random variable when all possible values within a particular interval have the same density.

The standard example is calling a tech-support line. The company can answer at any time between $0$ minutes and $15$ minutes, and the observed waiting times appear spread roughly evenly throughout the entire interval.

### Main idea

$$
\boxed{\text{Uniform distribution} = \text{constant density across an interval}}
$$

## A note on the discrete version

There is also a **discrete** uniform distribution, where finitely many separate values are equally likely — a fair die is the standard case, with $p_X(x)=\frac16$ for each face.

Everything in this file concerns the **continuous** version, where the values form an unbroken interval rather than a list.

---

# 2. The interval is controlled by $a$ and $b$

A continuous uniform distribution has two parameters:

$$
a = \text{lower endpoint} \qquad b = \text{upper endpoint}
$$

The total width of the interval is:

$$
b - a
$$

So the random variable can take values between $a$ and $b$. The notation is:

$$
\boxed{X \sim U(a,b)}
$$

---

# 3. The PDF is flat because the density is constant

For the uniform distribution, the PDF does not rise and fall like a normal distribution. Instead, it is a horizontal line between $a$ and $b$.

Why? Because the density is the same at every point of the interval, which means equal-sized portions of the interval carry equal probability.

Inside the interval:

$$
f_X(x) = \text{constant}
$$

Outside the interval:

$$
f_X(x) = 0
$$

Therefore, the uniform PDF has the shape of a **rectangle**.

---

# 4. The height of the PDF is determined by the interval width

From 06, the total area underneath any probability density function must equal $1$.

The uniform PDF is a rectangle, so:

$$
\text{Area} = \text{width} \times \text{height}
$$

The width is $b-a$. Let the height be $h$. Then:

$$
(b-a)h = 1
$$

Dividing both sides by $b-a$:

$$
h = \frac{1}{b-a}
$$

### Main rule

$$
\boxed{\text{The height of the uniform PDF is } \frac{1}{b-a}}
$$

Notice that the height is **not** a probability — it is a density, exactly as 06 warns. For a narrow interval it can easily exceed 1. With $a=0$ and $b=0.5$ the height is $2$, and the total area is still exactly 1.

---

# 5. Uniform PDF formula

The PDF has two different rules depending on the value of $x$:

$$
f_X(x) =
\begin{cases}
\dfrac{1}{b-a}, & a < x < b \cr
0, & \text{otherwise}
\end{cases}
$$

So remember:

$$
\boxed{\text{Inside the interval} \rightarrow \text{constant density}}
$$

$$
\boxed{\text{Outside the interval} \rightarrow \text{density equals } 0}
$$

---

# 6. Example: waiting time from 0 to 15 minutes

In the tech-support example:

$$
a = 0 \qquad b = 15
$$

The total width is:

$$
b - a = 15 - 0 = 15
$$

The PDF height is:

$$
f_X(x) = \frac{1}{b-a} = \frac{1}{15 - 0} = \frac{1}{15} \approx 0.0667
$$

So for waiting times between $0$ and $15$ minutes:

$$
f_X(x) = \frac{1}{15}
$$

---

# 7. Probability is width times height

Because the uniform PDF is a rectangle, finding the area under it requires no integration at all. Area is just width times height.

Suppose we want $P(c < X < d)$, where:

$$
a \leq c < d \leq b
$$

The width of the desired interval is $d-c$, and the height of the PDF is $\dfrac{1}{b-a}$. Therefore:

$$
\boxed{P(c < X < d) = (d-c)\left(\frac{1}{b-a}\right) = \frac{d-c}{b-a}}
$$

### In words

$$
\boxed{\text{Probability} = \frac{\text{desired interval length}}{\text{total interval length}}}
$$

This is the easiest probability calculation of any continuous distribution, because the density never changes. Nothing depends on *where* in the interval you look, only on *how much* of it you selected.

## Example

What is the probability the tech-support call is answered between 5 and 10 minutes?

$$
P(5 < X < 10) = \frac{10-5}{15-0} = \frac{5}{15} = \frac13
$$

The window is one third of the total interval, so it carries one third of the probability.

## A reminder from 06

Because this is a continuous distribution, a single exact value carries no probability:

$$
P(X = 7) = 0
$$

and it makes no difference whether the endpoints are included:

$$
P(5 < X < 10) = P(5 \leq X \leq 10)
$$

---

# 8. Mean and variance

Using the definitions from 07:

$$
\boxed{\mu = \frac{a+b}{2}}
$$

$$
\boxed{\sigma^2 = \frac{(b-a)^2}{12} \qquad \sigma = \frac{b-a}{\sqrt{12}}}
$$

## Why the mean is obvious and the variance is not

The mean is simply the **midpoint** of the interval. The distribution is flat and symmetric, so its balance point — the interpretation from 07 — must be dead centre. No calculation is needed.

The $12$ in the variance has no intuitive explanation. It comes out of the integral and simply has to be memorized.

## What the variance formula tells you

The variance depends only on the **width** $b-a$, not on where the interval sits. So $U(0,10)$ and $U(100,110)$ have identical spread and completely different means.

That is the shifting rule from 07 in action: adding a constant to a random variable moves the mean but leaves the variance untouched.

## Example: the tech-support call

With $a=0$ and $b=15$:

$$
\mu = \frac{0+15}{2} = 7.5 \text{ minutes}
$$

$$
\sigma^2 = \frac{(15-0)^2}{12} = \frac{225}{12} = 18.75 \qquad \sigma = \sqrt{18.75} \approx 4.33 \text{ minutes}
$$

So the average wait is 7.5 minutes, give or take about 4.3.

---

# 9. Uniform PDF versus normal PDF

This is an important visual distinction.

A normal PDF has changing density. It goes approximately **low → high → low**, producing a bell-shaped curve.

A uniform PDF has the same density everywhere inside the interval, producing a rectangle.

| Distribution | PDF Shape | Density | Finding probability |
|---|---|---|---|
| Normal | Bell-shaped | Changes with $x$ | Needs a table or software |
| Uniform | Flat rectangle | Constant | Width × height |

---

# 10. The uniform CDF has three regions

Recall from 06 that the CDF is defined as:

$$
F_X(x) = P(X \leq x)
$$

and measures how much probability has accumulated by the time you reach $x$. All the general CDF properties — running from 0 to 1, never decreasing — are in 06 and apply here without restatement.

For a uniform distribution, probability begins accumulating at $a$, increases steadily until $b$, and after $b$ everything has accumulated. That gives three regions.

## Region 1: before $a$, the CDF equals 0

Suppose $x < a$. The random variable cannot take values below $a$, so no probability has accumulated yet:

$$
F_X(x) = 0 \quad \text{for } x < a
$$

## Region 2: between $a$ and $b$, the CDF increases linearly

Suppose $a \leq x < b$. The amount of the interval covered so far is $x-a$, and the entire interval has width $b-a$. Therefore:

$$
F_X(x) = \frac{x-a}{b-a}
$$

This is the same "desired length over total length" idea from section 7, measured from the left endpoint.

## Region 3: at and beyond $b$, the CDF equals 1

Suppose $x \geq b$. The entire possible interval has already been included, so all probability has accumulated:

$$
F_X(x) = 1 \quad \text{for } x \geq b
$$

---

# 11. Uniform CDF formula

Putting the three regions together:

$$
F_X(x) =
\begin{cases}
0, & x < a \cr
\dfrac{x-a}{b-a}, & a \leq x < b \cr
1, & x \geq b
\end{cases}
$$

These three rules together form the complete CDF of a continuous uniform distribution.

---

# 12. Why the CDF is a straight line inside the interval

The uniform PDF has constant height $\dfrac{1}{b-a}$. While $x$ is inside the interval, every equal-sized step adds the same amount of probability — moving $x$ another unit always adds the same amount of area.

Therefore:

$$
\boxed{\text{Constant PDF} \rightarrow \text{linear CDF}}
$$

## Confirming it with the rule from 06

File 06 states that the PDF is the **slope** of the CDF:

$$
f_X(x) = \frac{d}{dx}F_X(x)
$$

Differentiate the middle region of the uniform CDF:

$$
\frac{d}{dx}\left(\frac{x-a}{b-a}\right) = \frac{1}{b-a}
$$

which is exactly the PDF height from section 4. The two formulas agree, and this is the cleanest possible illustration of the PDF/CDF relationship: a constant rate of accumulation produces a constant slope, and a constant slope is a straight line.

---

# 13. The standard uniform: $U(0,1)$

Suppose $X \sim U(0,1)$, so $a = 0$ and $b = 1$. This special case is worth knowing on its own.

The PDF height is:

$$
\frac{1}{b-a} = \frac{1}{1-0} = 1
$$

Therefore:

$$
f_X(x) = 1 \quad \text{for } 0 < x < 1
$$

For the CDF, substitute $a=0$ and $b=1$:

$$
F_X(x) = \frac{x-0}{1-0} = x \quad \text{for } 0 \leq x < 1
$$

So the CDF of $U(0,1)$ is simply $x$ itself, which is why it appears so often in derivations.

Its mean and variance:

$$
\mu = \frac{0+1}{2} = 0.5 \qquad \sigma^2 = \frac{(1-0)^2}{12} = \frac{1}{12} \approx 0.0833
$$

## Why this one matters in practice

$U(0,1)$ is what a computer's random number generator actually produces. Calls like `random.random()` in Python or `np.random.rand()` return a draw from exactly this distribution.

Every other random variable is then built from it. The technique is called **inverse transform sampling**: if $U \sim U(0,1)$ and $F$ is the CDF of some target distribution, then:

$$
\boxed{F^{-1}(U) \text{ has the distribution described by } F}
$$

So drawing a uniform random number and pushing it backwards through a CDF produces a sample from that distribution. This is why $U(0,1)$ sits underneath train/test splits, weight initialization, dropout masks, shuffling, and bootstrap resampling.

$$
\boxed{U(0,1) \text{ is the raw material for all other randomness}}
$$

---

# 14. Example of reading the CDF

## With $U(0,1)$

Suppose we want $F_X(0.25)$:

$$
F_X(0.25) = \frac{0.25 - 0}{1 - 0} = 0.25
$$

Because $F_X(x) = P(X \leq x)$, this means:

$$
P(X \leq 0.25) = 0.25
$$

Therefore, 25 percent of the total probability has accumulated by $x = 0.25$.

## With the tech-support example

For $U(0,15)$:

$$
F_X(5) = \frac{5-0}{15-0} = \frac13
$$

So one third of calls are answered within the first 5 minutes.

Now use the subtraction rule from 06 to recover the earlier answer:

$$
P(5 < X \leq 10) = F_X(10) - F_X(5) = \frac{10}{15} - \frac{5}{15} = \frac{5}{15} = \frac13
$$

This matches the width-times-height calculation in section 7 exactly, confirming that the two approaches are the same.

---

# Most Important Definitions and Distinctions to Remember

## Uniform distribution

A continuous uniform distribution has **constant density between $a$ and $b$**. Equal-length portions of the interval have equal probabilities.

$$
\boxed{X \sim U(a,b)}
$$

## Parameters

$$
\boxed{a = \text{lower endpoint} \qquad b = \text{upper endpoint} \qquad \text{Width} = b-a}
$$

## Uniform PDF

$$
f_X(x) =
\begin{cases}
\dfrac{1}{b-a}, & a < x < b \cr
0, & \text{otherwise}
\end{cases}
$$

## Uniform probability

For an interval between $c$ and $d$ contained inside $[a,b]$:

$$
\boxed{P(c < X < d) = \frac{d-c}{b-a}}
$$

Remember:

$$
\boxed{\text{Probability} = \frac{\text{desired width}}{\text{total width}} = \text{width} \times \text{height}}
$$

## Mean and variance

$$
\boxed{\mu = \frac{a+b}{2} \qquad \sigma^2 = \frac{(b-a)^2}{12}}
$$

## Uniform CDF

$$
F_X(x) =
\begin{cases}
0, & x < a \cr
\dfrac{x-a}{b-a}, & a \leq x < b \cr
1, & x \geq b
\end{cases}
$$

The CDF equals $0$ before $a$, increases linearly between $a$ and $b$, and equals $1$ at and after $b$.

---

# Main Rules to Put in Your Notebook

| Concept | Rule |
|---|---|
| Uniform distribution | Equal density across an interval |
| Notation | $X \sim U(a,b)$ |
| Lower endpoint | $a$ |
| Upper endpoint | $b$ |
| Total width | $b-a$ |
| PDF height | $\dfrac{1}{b-a}$ |
| PDF inside the interval | $f_X(x) = \dfrac{1}{b-a}$ |
| PDF outside the interval | $f_X(x) = 0$ |
| Probability between $c$ and $d$ | $P(c<X<d) = \dfrac{d-c}{b-a}$ |
| Mean | $\mu = \dfrac{a+b}{2}$ |
| Variance | $\sigma^2 = \dfrac{(b-a)^2}{12}$ |
| CDF inside the interval | $F_X(x) = \dfrac{x-a}{b-a}$ |

# Biggest Ideas to Remember

$$
\boxed{\text{Uniform PDF} = \text{constant density}}
$$

$$
\boxed{\text{Uniform probability} = \frac{\text{desired interval length}}{\text{total interval length}}}
$$

$$
\boxed{\text{Constant PDF} \rightarrow \text{straight-line CDF}}
$$

So in plain English:

**If every part of an interval has the same density, the PDF is a flat rectangle. Probability depends only on how much of the interval you select, not on where you select it. The mean is the midpoint, the variance depends only on the width, and the CDF rises evenly from 0 to 1.**

---

# Where This Goes Next

| Idea from this file | Where it is used |
|---|---|
| Constant PDF, linear CDF | **10 — Normal Distribution**: the contrast case, where density varies |
| $\mu$ and $\sigma$ of a continuous distribution | **10**: the normal is defined directly by these two |
| Reading probability off a CDF | **11 — Z-Scores**: the same idea, but the CDF needs a table |
| $U(0,1)$ and inverse transform sampling | Random number generation, resampling, and simulation |
