Yep — I’d organize the **PMF, PDF, and CDF material the same way as the Normal Distribution notes**: focus on the definitions, the distinctions that are easiest to confuse, the equations, and the rules worth memorizing. That matches the structure of your Normal Distribution sheet. 

# What You Should Know About PMF, PDF, and CDF

These slides are mainly teaching the difference between **discrete and continuous random variables**, how **PMFs and PDFs represent probability**, and how the **CDF accumulates probability**.

---

# 1. Discrete versus continuous random variables

Before PMF, PDF, and CDF make sense, you need to know whether the random variable is **discrete** or **continuous**.

## Discrete random variable

A discrete random variable can take a **finite or countable number of separate values**.

Examples:

* Number of heads in 5 coin flips
* Number rolled on a die
* Number of customers
* Number of goals scored

For example:

$$
X=\text{number of heads in 5 coin flips}
$$

can only take:

$$
X=0,1,2,3,4,5
$$

You cannot get:

$$
X=2.4
$$

heads.

Discrete random variables use a:

$$
\boxed{\text{PMF}}
$$

The slides use the five-coin example to show separate probabilities at (X=0,1,2,3,4,5). 

---

## Continuous random variable

A continuous random variable can take **any value within an interval**.

Examples:

* Waiting time
* Height
* Weight
* Temperature
* Distance

For waiting time, values could include:

$$
1,\quad1.01,\quad1.274,\quad2,\quad2.43,\ldots
$$

There are infinitely many possible values between any two measurements.

Continuous random variables use a:

$$
\boxed{\text{PDF}}
$$

The waiting-time slides emphasize that a continuous variable can take infinitely many possible values. 

---

# 2. PMF — Probability Mass Function

A **Probability Mass Function (PMF)** is used for:

$$
\boxed{\text{Discrete random variables}}
$$

The PMF is written:

$$
p_X(x)
$$

and means:

$$
\boxed{p_X(x)=P(X=x)}
$$

In words:

> **The PMF gives the probability that a discrete random variable equals exactly (x).**

---

## Example

Suppose:

$$
X=\text{number of heads in 5 fair coin flips}
$$

The slides give:

$$
P(X=2)=\frac{10}{32}
$$

Therefore:

$$
p_X(2)=P(X=2)=\frac{10}{32}
$$

So there is a:

$$
\frac{10}{32}=0.3125
$$

or:

$$
31.25%
$$

probability of getting exactly 2 heads.

The slide also shows that the probabilities across all six possible outcomes add to 1. 

---

# 3. The two main PMF rules

A valid PMF must satisfy two conditions.

## Rule 1: Probabilities cannot be negative

$$
\boxed{p_X(x)\geq0}
$$

Every probability must be zero or positive.

---

## Rule 2: All probabilities must add to 1

$$
\boxed{\sum_x p_X(x)=1}
$$

For the five-coin example:

$$
\frac{1}{32}
+\frac{5}{32}
+\frac{10}{32}
+\frac{10}{32}
+\frac{5}{32}
+\frac{1}{32}
=1
$$

Therefore:

$$
\boxed{\text{Discrete: sum of all probability masses}=1}
$$



---

# 4. Probability with a PMF comes from adding probabilities

Suppose you want:

$$
P(1\leq X\leq3)
$$

For a discrete variable, add the probabilities:

$$
P(1\leq X\leq3)
===============

P(X=1)+P(X=2)+P(X=3)
$$

Using PMF notation:

$$
P(1\leq X\leq3)
===============

p_X(1)+p_X(2)+p_X(3)
$$

Or more generally:

$$
\boxed{
P(a\leq X\leq b)
================

\sum_{x=a}^{b}p_X(x)
}
$$

So remember:

$$
\boxed{\text{PMF probability}=\text{sum of probability masses}}
$$

---

# 5. PDF — Probability Density Function

A **Probability Density Function (PDF)** is used for:

$$
\boxed{\text{Continuous random variables}}
$$

The PDF is written:

$$
f_X(x)
$$

The important distinction is that:

$$
\boxed{f_X(x)=\text{density}}
$$

It is **not** the probability that (X=x).

The slides describe the PDF as the rate at which probability accumulates around each point and emphasize that it is defined for continuous variables. 

---

# 6. Probability for a continuous variable comes from area

For a PDF:

$$
\boxed{\text{Area under the curve}=\text{probability}}
$$

Therefore:

$$
P(a<X<b)
$$

is the area underneath the PDF between (a) and (b).

Mathematically:

$$
\boxed{
P(a<X<b)=\int_a^b f_X(x),dx
}
$$

The slides illustrate this by shading the region between (a) and (b) underneath (f_X(x)). 

---

# 7. PDF height is NOT probability

This is probably the **most important PDF distinction**.

Suppose the PDF has some height at:

$$
x=2
$$

That height:

$$
f_X(2)
$$

does **not** mean:

$$
P(X=2)
$$

Instead:

$$
\boxed{\text{PDF height}=\text{density}}
$$

while:

$$
\boxed{\text{Area under the PDF}=\text{probability}}
$$

---

# 8. For a continuous variable, an exact value has probability 0

The waiting-time slides specifically ask:

> What is the probability that you wait **exactly** one minute?

The answer is:

$$
\boxed{0}
$$

For every continuous random variable:

$$
\boxed{P(X=x)=0}
$$

Why?

A single point has:

$$
\text{width}=0
$$

so the area underneath that individual point is:

$$
0
$$

The slides reinforce this again with the example (P(\text{exactly 2 minutes})=0).  

---

# 9. Intervals DO have probability for continuous variables

Although:

$$
P(X=2)=0
$$

an interval such as:

$$
P(2<X<3)
$$

can have a positive probability because the interval has width.

The slides give a waiting-time example where:

$$
P(2<X<3)=\frac15
$$

and a smaller interval:

$$
P(2<X<2.5)=0.1
$$



For a **constant density**, this can be thought of as:

$$
\boxed{
\text{Probability}
==================

\text{density}\times\text{interval width}
}
$$

For a curved PDF, the more general rule is:

$$
\boxed{
\text{Probability}
==================

\text{area under the PDF}
}
$$

---

# 10. The three main PDF rules

A valid PDF must satisfy:

## Rule 1: Density cannot be negative

$$
\boxed{f_X(x)\geq0}
$$

---

## Rule 2: Total area equals 1

$$
\boxed{
\int_{-\infty}^{\infty}f_X(x),dx=1
}
$$

The slides contrast this with the discrete case: **discrete probabilities sum to 1, while continuous probability is represented by total area equal to 1.** 

---

## Rule 3: Probability comes from area over an interval

$$
\boxed{
P(a<X<b)=\int_a^b f_X(x),dx
}
$$

---

# 11. PMF versus PDF

This is one of the biggest distinctions to memorize.

| Feature     | PMF                       | PDF                          |
| ----------- | ------------------------- | ---------------------------- |
| Full name   | Probability Mass Function | Probability Density Function |
| Used for    | Discrete variables        | Continuous variables         |
| Notation    | (p_X(x))                  | (f_X(x))                     |
| Exact value | (P(X=x)=p_X(x))           | (P(X=x)=0)                   |
| Probability | Add probabilities         | Find area                    |
| Total       | Sum = 1                   | Area = 1                     |
| Graph       | Separate bars/points      | Continuous curve             |

The slides directly contrast discrete PMFs with continuous PDFs. 

The easiest rule to remember is:

$$
\boxed{
\text{Discrete}\rightarrow\text{PMF}\rightarrow\text{ADD}
}
$$

$$
\boxed{
\text{Continuous}\rightarrow\text{PDF}\rightarrow\text{AREA}
}
$$

---

# 12. CDF — Cumulative Distribution Function

The **Cumulative Distribution Function (CDF)** tells you how much probability has accumulated **up to a particular value**.

It is written:

$$
F_X(x)
$$

and defined as:

$$
\boxed{
F_X(x)=P(X\leq x)
}
$$

In words:

> **The CDF gives the probability that (X) is less than or equal to (x).**

The slides describe cumulative probability as the probability that the event has occurred before a chosen reference point. 

---

# 13. The CDF works for BOTH discrete and continuous variables

This is an important distinction.

A CDF is **not another version of the PDF**.

It can be used for:

$$
\boxed{\text{Discrete AND continuous random variables}}
$$

So:

| Variable   | Probability function | CDF? |
| ---------- | -------------------- | ---- |
| Discrete   | PMF                  | Yes  |
| Continuous | PDF                  | Yes  |

Therefore:

$$
\boxed{
\text{PMF = discrete only}
}
$$

$$
\boxed{
\text{PDF = continuous only}
}
$$

$$
\boxed{
\text{CDF = both}
}
$$

---

# 14. CDF means accumulated probability

Suppose:

$$
F_X(2)=0.50
$$

This means:

$$
P(X\leq2)=0.50
$$

Therefore:

> There is a **50% probability that (X) is 2 or less**.

The CDF slides show exactly this relationship by matching the area to the left of (x=2) underneath the density curve with a CDF value of (0.5). 

---

# 15. A CDF always goes from 0 toward 1

The CDF represents accumulated probability.

Before any possible outcomes have occurred:

$$
F_X(x)=0
$$

After all possible probability has accumulated:

$$
F_X(x)=1
$$

Therefore:

$$
\boxed{
0\leq F_X(x)\leq1
}
$$

The slides explicitly state that the CDF starts at 0 and ends at 1. 

---

# 16. A CDF never decreases

Because probability is being **accumulated**, moving farther to the right can:

* Add probability
* Leave probability unchanged

but it cannot remove probability.

Therefore:

$$
\boxed{
F_X(x)\text{ never decreases}
}
$$

The final CDF slide lists this as one of its defining properties. 

---

# 17. Discrete CDF versus continuous CDF

A discrete and continuous CDF follow the same definition:

$$
F_X(x)=P(X\leq x)
$$

but their graphs look different.

## Discrete CDF

A discrete CDF looks like a:

$$
\boxed{\text{step function}}
$$

Each possible outcome causes the accumulated probability to jump upward.

---

## Continuous CDF

A continuous CDF usually looks like a:

$$
\boxed{\text{smooth increasing curve}}
$$

because probability accumulates continuously.

The slides display these side-by-side: the discrete version rises in steps, whereas the continuous version rises smoothly. 

---

# 18. PDF versus CDF

Do not confuse these two.

## PDF

$$
f_X(x)
$$

tells you:

$$
\boxed{\text{density around }x}
$$

Probability comes from **area underneath it**.

---

## CDF

$$
F_X(x)
$$

tells you:

$$
\boxed{\text{total probability accumulated up to }x}
$$

Therefore:

$$
F_X(x)=P(X\leq x)
$$

The slides summarize the PDF as a density curve with total area 1 and the CDF as an increasing cumulative curve approaching 1. 

---

# 19. Finding probability between two values using the CDF

Because:

$$
F_X(b)=P(X\leq b)
$$

and:

$$
F_X(a)=P(X\leq a)
$$

the probability between two points can be obtained by subtracting cumulative probabilities:

$$
\boxed{
P(a<X\leq b)=F_X(b)-F_X(a)
}
$$

In words:

$$
\boxed{
\text{Probability between}
==========================

## \text{upper CDF}

\text{lower CDF}
}
$$

---

# 20. PMF, PDF, and CDF answer different questions

This is probably the simplest way to distinguish all three.

### PMF

Question:

> What is the probability of **exactly this discrete value**?

$$
\boxed{p_X(x)=P(X=x)}
$$

---

### PDF

Question:

> Where is probability **densely concentrated**, and what is the probability over an interval?

$$
\boxed{
P(a<X<b)=\text{area under }f_X(x)
}
$$

---

### CDF

Question:

> What is the probability of being **at or below this value**?

$$
\boxed{
F_X(x)=P(X\leq x)
}
$$

---

# Most Important Definitions and Distinctions to Remember

## PMF

A **Probability Mass Function** is used for discrete random variables.

$$
\boxed{
p_X(x)=P(X=x)
}
$$

Probability is obtained by **adding probability masses**.

$$
\boxed{
\sum_xp_X(x)=1
}
$$

---

## PDF

A **Probability Density Function** is used for continuous random variables.

$$
\boxed{
f_X(x)=\text{density at }x
}
$$

Probability is represented by:

$$
\boxed{
\text{area under the PDF}
}
$$

For an interval:

$$
\boxed{
P(a<X<b)=\int_a^b f_X(x),dx
}
$$

For an exact continuous value:

$$
\boxed{
P(X=x)=0
}
$$

---

## CDF

A **Cumulative Distribution Function** works for both discrete and continuous variables.

$$
\boxed{
F_X(x)=P(X\leq x)
}
$$

It measures:

$$
\boxed{\text{accumulated probability}}
$$

and always satisfies:

$$
\boxed{
0\leq F_X(x)\leq1
}
$$

The CDF never decreases.

---

# Main Rules to Put in Your Notebook

$$
\boxed{\text{Discrete}\rightarrow\text{PMF}}
$$

$$
\boxed{\text{Continuous}\rightarrow\text{PDF}}
$$

$$
\boxed{\text{Discrete AND Continuous}\rightarrow\text{CDF}}
$$

$$
\boxed{p_X(x)=P(X=x)}
$$

$$
\boxed{\sum_xp_X(x)=1}
$$

$$
\boxed{f_X(x)\geq0}
$$

$$
\boxed{\text{Total area under a PDF}=1}
$$

$$
\boxed{P(X=x)=0\quad\text{for continuous }X}
$$

$$
\boxed{
P(a<X<b)=\int_a^b f_X(x),dx
}
$$

$$
\boxed{
F_X(x)=P(X\leq x)
}
$$

$$
\boxed{
0\leq F_X(x)\leq1
}
$$

$$
\boxed{
P(a<X\leq b)=F_X(b)-F_X(a)
}
$$

And the **single biggest idea** to remember is:

$$
\boxed{
\begin{aligned}
\text{PMF} &= \text{probability at discrete values}\
\text{PDF} &= \text{density; area gives probability}\
\text{CDF} &= \text{probability accumulated up to }x
\end{aligned}
}
$$

So in plain English:

**PMF = exact discrete probability, PDF = continuous density/area, CDF = running total of probability.**
