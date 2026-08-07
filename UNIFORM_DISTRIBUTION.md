# What You Should Know About the Uniform Distribution

These slides are mainly teaching five important ideas:

- What makes a distribution uniform
- What \(a\) and \(b\) represent
- Why the PDF has a constant height
- How probability is calculated from the uniform PDF
- How the uniform CDF is constructed

---

## 1. A uniform distribution gives equal density throughout an interval

A **continuous uniform distribution** models a continuous random variable when all possible values within a particular interval have the same density of occurrence.

The slides use the example of calling a tech-support line.

The company can answer at any time between:

$$
0\text{ minutes}
$$

and:

$$
15\text{ minutes}
$$

The observed waiting times appear spread roughly evenly throughout the entire \(0\)-to-\(15\)-minute interval.

Therefore, the basic idea is:

$$
\boxed{\text{Uniform distribution}=\text{constant density across an interval}}
$$

---

## 2. The interval is controlled by \(a\) and \(b\)

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

Therefore:

$$
\boxed{a=\text{lower endpoint}}
$$

$$
\boxed{b=\text{upper endpoint}}
$$

The total width of the interval is:

$$
\boxed{b-a}
$$

---

## 3. The PDF is flat because the density is constant

For the uniform distribution, the PDF does not rise and fall like a normal distribution.

Instead, it is a horizontal line between \(a\) and \(b\).

Why?

Because every portion of the interval has the same density.

Therefore:

$$
\boxed{f_X(x)=\text{constant between }a\text{ and }b}
$$

Outside the interval:

$$
\boxed{f_X(x)=0}
$$

The uniform PDF therefore has a rectangular shape.

---

## 4. The height of the PDF is \(\frac{1}{b-a}\)

The total area underneath any PDF must equal:

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

Solving for \(h\):

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

The complete uniform PDF is:

$$
f_X(x)=
\begin{cases}
\dfrac{1}{b-a}, & a<x<b \\
0, & \text{otherwise}
\end{cases}
$$

The important idea is:

- **Inside the interval** → constant density
- **Outside the interval** → density equals \(0\)

So:

$$
\boxed{a<x<b\Rightarrow f_X(x)=\frac{1}{b-a}}
$$

and:

$$
\boxed{x\text{ outside the interval}\Rightarrow f_X(x)=0}
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

The PDF height is:

$$
f_X(x)=\frac{1}{15}
$$

which is approximately:

$$
0.0667
$$

This can also be derived using:

$$
15h=1
$$

Therefore:

$$
h=\frac{1}{15}\approx0.0667
$$

So:

$$
\boxed{f_X(x)=\frac{1}{15}}
$$

for waiting times between \(0\) and \(15\) minutes.

---

## 7. Probability comes from area under the uniform PDF

Because this is a continuous distribution, probability corresponds to **area underneath the PDF**.

For a uniform distribution, this is especially easy because the PDF is a rectangle.

Suppose we want the probability that \(X\) falls between \(c\) and \(d\), where:

$$
a\leq c<d\leq b
$$

The width of the desired interval is:

$$
d-c
$$

The height of the PDF is:

$$
\frac{1}{b-a}
$$

Therefore:

$$
P(c<X<d)=(d-c)\left(\frac{1}{b-a}\right)
$$

So:

$$
\boxed{P(c<X<d)=\frac{d-c}{b-a}}
$$

In words:

$$
\boxed{
\text{Probability}
=
\frac{\text{desired interval length}}{\text{total interval length}}
}
$$

---

## 8. The easiest way to think about uniform probability

For a uniform distribution:

$$
\boxed{\text{Probability}=\text{width}\times\text{height}}
$$

The width is:

$$
d-c
$$

The height is:

$$
\frac{1}{b-a}
$$

Therefore:

$$
\text{Probability}
=
(d-c)\left(\frac{1}{b-a}\right)
$$

which becomes:

$$
\boxed{P(c<X<d)=\frac{d-c}{b-a}}
$$

This is easier than dealing with a curved PDF because the density never changes.

---

## 9. Uniform PDF versus normal PDF

This is an important visual distinction.

A normal PDF has changing density:

$$
\text{low}\rightarrow\text{high}\rightarrow\text{low}
$$

A uniform PDF has the same density everywhere inside the interval:

$$
\boxed{\text{constant height}}
$$

Therefore:

- **Normal distribution** → bell-shaped PDF
- **Uniform distribution** → rectangular PDF

---

## 10. The uniform CDF gives accumulated probability

The **Cumulative Distribution Function** is defined as:

$$
\boxed{F_X(x)=P(X\leq x)}
$$

For the uniform distribution, the CDF tells us how much probability has accumulated from the beginning of the interval \(a\) up to \(x\).

As \(x\) moves from left to right, more area underneath the PDF accumulates.

---

## 11. Before \(a\), the CDF equals 0

If:

$$
x<a
$$

then \(x\) occurs before the interval where the random variable can take values.

Therefore:

$$
\boxed{F_X(x)=0}
$$

for:

$$
x<a
$$

No probability has accumulated yet.

---

## 12. Between \(a\) and \(b\), the CDF increases linearly

Suppose:

$$
a\leq x<b
$$

The amount of the interval accumulated so far is:

$$
x-a
$$

The total width of the interval is:

$$
b-a
$$

Therefore:

$$
\boxed{F_X(x)=\frac{x-a}{b-a}}
$$

This means the uniform CDF rises at a constant rate between \(a\) and \(b\).

That is why the graph is a straight diagonal line.

---

## 13. At and beyond \(b\), the CDF equals 1

If:

$$
x\geq b
$$

then the entire interval has already been included.

Therefore all probability has accumulated:

$$
\boxed{F_X(x)=1}
$$

---

## 14. Uniform CDF formula

Putting the three regions together:

$$
F_X(x)=
\begin{cases}
0, & x<a \\
\dfrac{x-a}{b-a}, & a\leq x<b \\
1, & x\geq b
\end{cases}
$$

This is the complete CDF for the continuous uniform distribution.

---

## 15. Why the CDF is a straight line inside the interval

The PDF has constant height:

$$
\frac{1}{b-a}
$$

Therefore, every equal-sized interval adds the same amount of probability.

For example, moving \(x\) another 1 unit always adds the same amount of area.

Therefore:

$$
\boxed{\text{constant PDF}\rightarrow\text{linear CDF}}
$$

This is the main relationship between the uniform PDF and CDF.

---

## 16. Special example: Uniform distribution from 0 to 1

Suppose:

$$
X\sim\mathrm{Uniform}(0,1)
$$

Then:

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

for:

$$
0<x<1
$$

The CDF is:

$$
F_X(x)=\frac{x-a}{b-a}
$$

Substituting \(a=0\) and \(b=1\):

$$
F_X(x)=\frac{x-0}{1-0}
$$

Therefore:

$$
\boxed{F_X(x)=x}
$$

for:

$$
0\leq x<1
$$

---

## 17. Example of reading the CDF

Suppose:

$$
X\sim\mathrm{Uniform}(0,1)
$$

and we want:

$$
F_X(0.25)
$$

Using:

$$
F_X(x)=\frac{x-a}{b-a}
$$

substitute:

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

So \(25\%\) of the total probability has accumulated by:

$$
x=0.25
$$

---

# Most Important Definitions and Distinctions to Remember

## Uniform distribution

A continuous uniform distribution has:

$$
\boxed{\text{constant density between }a\text{ and }b}
$$

All equal-length parts of the interval have equal probabilities.

---

## Parameters

The lower endpoint is:

$$
\boxed{a=\text{lower endpoint}}
$$

The upper endpoint is:

$$
\boxed{b=\text{upper endpoint}}
$$

The total interval width is:

$$
\boxed{\text{Width}=b-a}
$$

---

## Uniform PDF

The PDF height is:

$$
\boxed{\frac{1}{b-a}}
$$

The complete PDF is:

$$
f_X(x)=
\begin{cases}
\dfrac{1}{b-a}, & a<x<b \\
0, & \text{otherwise}
\end{cases}
$$

---

## Probability

For an interval contained inside \([a,b]\):

$$
\boxed{P(c<X<d)=\frac{d-c}{b-a}}
$$

In words:

$$
\boxed{
\text{Probability}
=
\frac{\text{desired interval width}}{\text{total interval width}}
}
$$

Another way to remember it is:

$$
\boxed{\text{Probability}=\text{width}\times\text{height}}
$$

---

## Uniform CDF

The full CDF is:

$$
F_X(x)=
\begin{cases}
0, & x<a \\
\dfrac{x-a}{b-a}, & a\leq x<b \\
1, & x\geq b
\end{cases}
$$

The CDF:

- Equals \(0\) before \(a\)
- Increases linearly between \(a\) and \(b\)
- Equals \(1\) at and after \(b\)

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
\boxed{f_X(x)=\frac{1}{b-a}\text{ between }a\text{ and }b}
$$

$$
\boxed{f_X(x)=0\text{ outside }[a,b]}
$$

$$
\boxed{P(c<X<d)=\frac{d-c}{b-a}}
$$

$$
\boxed{F_X(x)=\frac{x-a}{b-a}\text{ between }a\text{ and }b}
$$

---

# Biggest Ideas to Remember

$$
\boxed{\text{Uniform PDF}=\text{constant density}}
$$

$$
\boxed{
\text{Uniform probability}
=
\frac{\text{desired interval length}}{\text{total interval length}}
}
$$

$$
\boxed{\text{Constant PDF}\rightarrow\text{straight-line CDF}}
$$

So in plain English:

**If every part of an interval is equally likely, the PDF is a flat rectangle, probability depends only on how much of the interval you select, and the CDF rises evenly from 0 to 1.**
