# What You Should Know About the Uniform Distribution

These notes cover five main ideas:

- What makes a distribution uniform
- What $a$ and $b$ represent
- Why the PDF has a constant height
- How probability is calculated from the uniform PDF
- How the uniform CDF is constructed

---

## 1. A uniform distribution gives equal density throughout an interval

A **continuous uniform distribution** models a continuous random variable when all possible values within a particular interval have the same density.

The slides use the example of calling a tech-support line. The company can answer at any time between $0$ minutes and $15$ minutes, and the observed waiting times appear spread roughly evenly throughout the entire interval.

### Main idea

**Uniform distribution = constant density across an interval**

---

## 2. The interval is controlled by $a$ and $b$

A continuous uniform distribution has two parameters:

$$
a = \text{lower endpoint} \qquad b = \text{upper endpoint}
$$

The total width of the interval is:

$$
b - a
$$

So the random variable can take values between $a$ and $b$.

---

## 3. The PDF is flat because the density is constant

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

Therefore, the uniform PDF has the shape of a rectangle.

---

## 4. The height of the PDF is determined by the interval width

The total area underneath any probability density function must equal $1$.

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

The height of the uniform PDF is:

$$
\frac{1}{b-a}
$$

---

## 5. Uniform PDF formula

The PDF has two different rules depending on the value of $x$:

$$
f_X(x) =
\begin{cases}
\dfrac{1}{b-a}, & a < x < b \\[6pt]
0, & \text{otherwise}
\end{cases}
$$

So remember:

**Inside the interval → constant density**

**Outside the interval → density equals 0**

---

## 6. Example: waiting time from 0 to 15 minutes

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

## 7. Probability comes from area under the uniform PDF

Because the uniform distribution is continuous, probability corresponds to **area underneath the PDF**. For a uniform distribution this is especially easy, because the PDF is a rectangle.

Suppose we want $P(c < X < d)$, where:

$$
a \leq c < d \leq b
$$

The width of the desired interval is $d-c$, and the height of the PDF is $\dfrac{1}{b-a}$. Probability equals width times height:

$$
P(c < X < d) = (d-c)\left(\frac{1}{b-a}\right) = \frac{d-c}{b-a}
$$

### In words

**Probability = desired interval length / total interval length**

---

## 8. The easiest way to think about uniform probability

For a uniform distribution:

**Probability = width × height**

where the width is $d-c$ and the height is $\dfrac{1}{b-a}$. This is easier than working with a curved PDF, because the density never changes:

$$
P(c < X < d) = \frac{d-c}{b-a}
$$

---

## 9. Uniform PDF versus normal PDF

This is an important visual distinction.

A normal PDF has changing density. It goes approximately **low → high → low**, producing a bell-shaped curve.

A uniform PDF has the same density everywhere inside the interval, producing a rectangle.

| Distribution | PDF Shape |
|---|---|
| Normal | Bell-shaped |
| Uniform | Flat rectangle |

---

## 10. The uniform CDF gives accumulated probability

The Cumulative Distribution Function is defined as:

$$
F_X(x) = P(X \leq x)
$$

The CDF tells us how much probability has accumulated by the time we reach $x$.

For a uniform distribution, probability begins accumulating at $a$, continues increasing until $b$, and after $b$ all probability has accumulated.

---

## 11. Before $a$, the CDF equals 0

Suppose $x < a$. The random variable cannot take values below $a$, so no probability has accumulated yet:

$$
F_X(x) = 0 \quad \text{for } x < a
$$

---

## 12. Between $a$ and $b$, the CDF increases linearly

Suppose $a \leq x < b$. The amount of the interval covered so far is $x-a$, and the entire interval has width $b-a$. Therefore:

$$
F_X(x) = \frac{x-a}{b-a}
$$

The CDF increases at a constant rate because the PDF has constant density. This produces a straight diagonal line on the CDF graph.

---

## 13. At and beyond $b$, the CDF equals 1

Suppose $x \geq b$. At this point the entire possible interval has already been included, so all probability has accumulated:

$$
F_X(x) = 1 \quad \text{for } x \geq b
$$

---

## 14. Uniform CDF formula

Putting the three regions together:

$$
F_X(x) =
\begin{cases}
0, & x < a \\[6pt]
\dfrac{x-a}{b-a}, & a \leq x < b \\[6pt]
1, & x \geq b
\end{cases}
$$

These three rules together form the complete CDF of a continuous uniform distribution.

---

## 15. Why the CDF is a straight line inside the interval

The uniform PDF has constant height $\dfrac{1}{b-a}$. This means that, while $x$ is inside the interval, every equal-sized step adds the same amount of probability — moving $x$ another 1 unit always adds the same amount of area.

Therefore:

**Constant PDF → linear CDF**

This is the main relationship between the uniform PDF and CDF.

---

## 16. Special example: Uniform distribution from 0 to 1

Suppose $X \sim U(0,1)$, so $a = 0$ and $b = 1$.

The PDF height is:

$$
\frac{1}{b-a} = \frac{1}{1-0} = 1
$$

Therefore:

$$
f_X(x) = 1 \quad \text{for } 0 < x < 1
$$

For the CDF, use $F_X(x) = \dfrac{x-a}{b-a}$ and substitute $a=0$ and $b=1$:

$$
F_X(x) = \frac{x-0}{1-0} = x \quad \text{for } 0 \leq x < 1
$$

---

## 17. Example of reading the CDF

Suppose $X \sim U(0,1)$ and we want $F_X(0.25)$.

$$
F_X(0.25) = \frac{0.25 - 0}{1 - 0} = 0.25
$$

Because $F_X(x) = P(X \leq x)$, we know:

$$
P(X \leq 0.25) = 0.25
$$

Therefore, 25% of the total probability has accumulated by $x = 0.25$.

---

# Most Important Definitions and Distinctions to Remember

## Uniform distribution

A continuous uniform distribution has **constant density between $a$ and $b$**. Equal-length portions of the interval have equal probabilities.

## Parameters

**$a$ = lower endpoint**

**$b$ = upper endpoint**

**Width = $b-a$**

## Uniform PDF

The PDF height is $\dfrac{1}{b-a}$, and:

$$
f_X(x) =
\begin{cases}
\dfrac{1}{b-a}, & a < x < b \\[6pt]
0, & \text{otherwise}
\end{cases}
$$

## Uniform probability

For an interval between $c$ and $d$ contained inside $[a,b]$:

$$
P(c < X < d) = \frac{d-c}{b-a}
$$

Remember:

**Probability = desired interval width / total interval width**

**Probability = width × height**

## Uniform CDF

$$
F_X(x) =
\begin{cases}
0, & x < a \\[6pt]
\dfrac{x-a}{b-a}, & a \leq x < b \\[6pt]
1, & x \geq b
\end{cases}
$$

The CDF:

- Equals $0$ before $a$
- Increases linearly between $a$ and $b$
- Equals $1$ at and after $b$

---

# Main Rules to Put in Your Notebook

| Concept | Rule |
|---|---|
| Uniform distribution | Equal density across an interval |
| Lower endpoint | $a$ |
| Upper endpoint | $b$ |
| Total width | $b-a$ |
| PDF height | $\dfrac{1}{b-a}$ |
| PDF inside the interval | $f_X(x) = \dfrac{1}{b-a}$ |
| PDF outside the interval | $f_X(x) = 0$ |
| Probability between $c$ and $d$ | $P(c<X<d) = \dfrac{d-c}{b-a}$ |
| CDF definition | $F_X(x) = P(X \leq x)$ |
| CDF inside the interval | $F_X(x) = \dfrac{x-a}{b-a}$ |

---

# Biggest Ideas to Remember

**Uniform PDF = constant density**

**Uniform probability = desired interval length / total interval length**

**Constant PDF → straight-line CDF**

So in plain English:

**If every part of an interval has the same density, the PDF is a flat rectangle. Probability depends only on how much of the interval you select, and the CDF rises evenly from 0 to 1.**
