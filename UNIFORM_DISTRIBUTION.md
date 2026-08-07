# What You Should Know About the Uniform Distribution

These slides are mainly teaching five important ideas:

* What makes a distribution uniform
* What (a) and (b) represent
* Why the PDF has a constant height
* How probability is calculated from the uniform PDF
* How the uniform CDF is constructed

---

## 1. A uniform distribution gives equal density throughout an interval

A **continuous uniform distribution** models a continuous random variable when all possible values within a particular interval have the same frequency/density of occurrence.

The slides use the example of calling a tech-support line.

The company can answer at any time between:

$$
0\text{ minutes}
$$

and:

$$
15\text{ minutes}
$$

The observed waiting times appear spread roughly evenly throughout the entire (0)-to-(15)-minute interval.

Therefore, the basic idea is:

$$
\boxed{\text{Uniform distribution}=\text{constant density across an interval}}
$$

---

## 2. The interval is controlled by (a) and (b)

A continuous uniform distribution has two parameters:

$$
a=\text{beginning of the interval}
$$

and:

$$
b=\text{end of the interval}
$$

So the possible values occur between:

$$
a\text{ and }b
$$

The model shown on page 3 labels these directly as the beginning and end of the interval.

Therefore:

$$
\boxed{a=\text{lower endpoint}}
$$

$$
\boxed{b=\text{upper endpoint}}
$$

---

## 3. The PDF is flat because the density is constant

For the uniform distribution, the PDF does not rise and fall like a normal distribution.

Instead, it is a horizontal line between (a) and (b).

Why?

Because every portion of the interval has the same density.

Therefore:

$$
\boxed{f_X(x)=\text{constant between }a\text{ and }b}
$$

and outside the interval:

$$
\boxed{f_X(x)=0}
$$

The graph on page 3 shows exactly this rectangular PDF.

---

## 4. The height of the PDF is (\frac{1}{b-a})

The PDF must have total area:

$$
1
$$

Since the uniform PDF is a rectangle:

$$
\text{Area}=\text{width}\times\text{height}
$$

The width is:

$$
b-a
$$

Let the height be:

$$
h
$$

Then:

$$
(b-a)h=1
$$

Solving:

$$
h=\frac{1}{b-a}
$$

Therefore:

$$
\boxed{\text{Uniform PDF height}=\frac{1}{b-a}}
$$

This is the main PDF rule for the uniform distribution.

---

## 5. Uniform PDF formula

The slides give the PDF as:

$$
\boxed{
f_X(x)=
\begin{cases}
\dfrac{1}{b-a}, & a<x<b [6pt]
0, & x\notin(a,b)
\end{cases}
}
$$

The important idea is:

* **Inside the interval** → constant density
* **Outside the interval** → density (0)

So:

$$
\boxed{a<x<b\quad\Rightarrow\quad f_X(x)=\frac{1}{b-a}}
$$

and:

$$
\boxed{x\text{ outside the interval}\quad\Rightarrow\quad f_X(x)=0}
$$

---

## 6. Example: waiting time from 0 to 15 minutes

In the tech-support example:

$$
a=0
$$

and:

$$
b=15
$$

Therefore, the width is:

$$
b-a=15-0=15
$$

The PDF height must therefore be:

$$
f_X(x)=\frac{1}{15}
$$

which is approximately:

$$
0.0667
$$

The slides derive this using:

$$
15h=1
$$

so:

$$
h=\frac{1}{15}\approx0.0667
$$

Therefore:

$$
\boxed{f_X(x)=\frac{1}{15}\text{ for waiting times between 0 and 15 minutes}}
$$

---

## 7. Probability comes from area under the uniform PDF

Because this is a continuous distribution, probability corresponds to **area underneath the PDF**.

For a uniform distribution, that is especially easy because the PDF is a rectangle.

Suppose you want the probability of being between two values:

$$
c\text{ and }d
$$

where:

$$
a\leq c<d\leq b
$$

The width of this region is:

$$
d-c
$$

The PDF height is:

$$
\frac{1}{b-a}
$$

Therefore:

$$
P(c<X<d)=(d-c)\frac{1}{b-a}
$$

So:

$$
\boxed{P(c<X<d)=\frac{d-c}{b-a}}
$$

In words:

$$
\boxed{
\text{Probability}
==================

\frac{\text{desired interval length}}{\text{total interval length}}
}
$$

This follows directly from the rectangular uniform PDF shown in the slides.

---

## 8. The easiest way to think about uniform probability

For a uniform distribution:

$$
\boxed{\text{Probability}=\text{width}\times\text{height}}
$$

Since:

$$
\text{height}=\frac{1}{b-a}
$$

then:

$$
\text{Probability}
==================

(d-c)\left(\frac{1}{b-a}\right)
$$

which becomes:

$$
\boxed{P(c<X<d)=\frac{d-c}{b-a}}
$$

This is much easier than dealing with a curved PDF because the density is constant.

---

## 9. Uniform PDF versus a normal PDF

This is an important visual distinction.

A normal PDF has a changing density:

$$
\text{low}\rightarrow\text{high}\rightarrow\text{low}
$$

A uniform PDF has the same density everywhere inside the interval:

$$
\boxed{\text{constant height}}
$$

So the uniform PDF looks like a **rectangle** rather than a bell curve.

The PDF graphs on pages 3–4 show this flat rectangular shape.

---

## 10. The uniform CDF gives accumulated probability

The **Cumulative Distribution Function** still means:

$$
\boxed{F_X(x)=P(X\leq x)}
$$

For the uniform distribution, the CDF tells us how much area under the rectangular PDF has accumulated from the beginning of the interval (a) up to (x).

The slides build the CDF visually by increasing the shaded area underneath the uniform PDF as (x) moves from left to right.

---

## 11. Before (a), the CDF is 0

If:

$$
x<a
$$

then we have not reached the interval where the random variable can occur.

Therefore:

$$
\boxed{F_X(x)=0}
$$

for:

$$
x<a
$$

---

## 12. Between (a) and (b), the CDF increases linearly

Suppose:

$$
a\leq x<b
$$

The amount of the interval accumulated so far is:

$$
x-a
$$

The total interval width is:

$$
b-a
$$

Therefore:

$$
\boxed{F_X(x)=\frac{x-a}{b-a}}
$$

This means the uniform CDF rises at a constant rate between (a) and (b).

That is why its graph is a **straight diagonal line** rather than an S-shaped curve.

---

## 13. At and beyond (b), the CDF equals 1

Once we reach the end of the interval:

$$
x\geq b
$$

all of the probability has accumulated.

Therefore:

$$
\boxed{F_X(x)=1}
$$

---

## 14. Uniform CDF formula

Putting the three regions together:

$$
\boxed{
F_X(x)=
\begin{cases}
0, & x<a [6pt]
\dfrac{x-a}{b-a}, & a\leq x<b [8pt]
1, & x\geq b
\end{cases}
}
$$

This is the full general CDF shown on the final slide.

---

## 15. Why the CDF is a straight line inside the interval

The PDF has constant height:

$$
\frac{1}{b-a}
$$

So every equal-sized interval adds the same amount of probability.

For example, moving (x) by another 1 unit always adds the same amount of area.

Therefore, the CDF increases evenly:

$$
\boxed{\text{constant PDF}\rightarrow\text{linear CDF}}
$$

This is the main relationship between the uniform PDF and CDF.

---

## 16. Special example: Uniform distribution from 0 to 1

The slides also illustrate a uniform distribution whose endpoints are:

$$
a=0
$$

and:

$$
b=1
$$

The PDF height is:

$$
\frac{1}{1-0}=1
$$

Therefore:

$$
f_X(x)=1
$$

between:

$$
0\text{ and }1
$$

The CDF becomes:

$$
F_X(x)=\frac{x-0}{1-0}
$$

so:

$$
F_X(x)=x
$$

for:

$$
0\leq x<1
$$

The graph on pages 4–5 shows the rectangular PDF alongside this straight-line CDF.

---

## 17. Example of reading the CDF

Suppose:

$$
X\sim\text{Uniform}(0,1)
$$

and we want:

$$
F_X(0.25)
$$

Using:

$$
F_X(x)=\frac{x-a}{b-a}
$$

we substitute:

$$
F_X(0.25)=\frac{0.25-0}{1-0}
$$

Therefore:

$$
F_X(0.25)=0.25
$$

This means:

$$
\boxed{P(X\leq0.25)=0.25}
$$

So **25%** of the total probability has accumulated by (x=0.25).

The page 5 diagram illustrates this exact idea by matching accumulated area under the PDF to the corresponding CDF height.

---

# Most Important Definitions and Distinctions to Remember

## Uniform distribution

A continuous uniform distribution has:

$$
\boxed{\text{constant density between }a\text{ and }b}
$$

All parts of the interval are treated equally.

---

## Parameters

$$
\boxed{a=\text{beginning/lower endpoint}}
$$

$$
\boxed{b=\text{end/upper endpoint}}
$$

The total interval width is:

$$
\boxed{b-a}
$$

---

## Uniform PDF

The PDF height is:

$$
\boxed{\frac{1}{b-a}}
$$

Therefore:

$$
\boxed{
f_X(x)=
\begin{cases}
\dfrac{1}{b-a}, & a<x<b [6pt]
0, & \text{otherwise}
\end{cases}
}
$$

---

## Probability

For an interval contained inside ([a,b]):

$$
\boxed{P(c<X<d)=\frac{d-c}{b-a}}
$$

So remember:

$$
\boxed{
\text{Probability}
==================

\frac{\text{desired interval width}}{\text{total interval width}}
}
$$

---

## Uniform CDF

$$
\boxed{
F_X(x)=
\begin{cases}
0, & x<a [6pt]
\dfrac{x-a}{b-a}, & a\leq x<b [8pt]
1, & x\geq b
\end{cases}
}
$$

The CDF:

* Is (0) before (a)
* Increases linearly between (a) and (b)
* Equals (1) after (b)

---

# Main Rules to Put in Your Notebook

$$
\boxed{\text{Uniform distribution}=\text{equal density across an interval}}
$$

$$
\boxed{a=\text{lower endpoint}}
$$

$$
\boxed{b=\text{upper endpoint}}
$$

$$
\boxed{\text{Width}=b-a}
$$

$$
\boxed{\text{PDF height}=\frac{1}{b-a}}
$$

$$
\boxed{f_X(x)=\frac{1}{b-a}\quad\text{between }a\text{ and }b}
$$

$$
\boxed{f_X(x)=0\quad\text{outside }[a,b]}
$$

$$
\boxed{P(c<X<d)=\frac{d-c}{b-a}}
$$

$$
\boxed{F_X(x)=\frac{x-a}{b-a}\quad\text{between }a\text{ and }b}
$$

And the biggest ideas to remember are:

$$
\boxed{\text{Uniform PDF}=\text{constant density}}
$$

$$
\boxed{
\text{Uniform probability}
==========================

\frac{\text{desired interval length}}{\text{total interval length}}
}
$$

$$
\boxed{\text{Constant PDF}\rightarrow\text{straight-line CDF}}
$$

So in plain English: **if every part of an interval is equally likely, the PDF is a flat rectangle; probability depends only on how much of the interval you select; and the CDF rises evenly from 0 to 1.**
