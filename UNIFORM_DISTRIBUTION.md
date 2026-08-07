# What You Should Know About the Uniform Distribution

These slides are mainly teaching five important ideas:

- What makes a distribution uniform
- What \(a\) and \(b\) represent
- Why the PDF has a constant height
- How probability is calculated from the uniform PDF
- How the uniform CDF is constructed

---

## 1. A uniform distribution gives equal density throughout an interval

A **continuous uniform distribution** models a continuous random variable when all possible values within a particular interval have the same density.

The slides use the example of calling a tech-support line.

The company can answer at any time between:

$$
0
$$

minutes and:

$$
15
$$

minutes.

The observed waiting times appear spread roughly evenly throughout the entire 0-to-15-minute interval.

### Main idea

**Uniform distribution = constant density across an interval**

---

## 2. The interval is controlled by \(a\) and \(b\)

A continuous uniform distribution has two parameters.

The lower endpoint is:

$$
a
$$

The upper endpoint is:

$$
b
$$

Therefore:

**\(a\) = lower endpoint**

**\(b\) = upper endpoint**

The total width of the interval is:

$$
b-a
$$

So the random variable can take values between \(a\) and \(b\).

---

## 3. The PDF is flat because the density is constant

For the uniform distribution, the PDF does not rise and fall like a normal distribution.

Instead, it is a horizontal line between \(a\) and \(b\).

Why?

Because every equal-sized portion of the interval has the same density.

Inside the interval:

$$
f_X(x)=\text{constant}
$$

Outside the interval:

$$
f_X(x)=0
$$

Therefore, the uniform PDF has the shape of a rectangle.

---

## 4. The height of the PDF is determined by the interval width

The total area underneath any probability density function must equal:

$$
1
$$

The uniform PDF is a rectangle.

Therefore:

**Area = width × height**

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

Divide both sides by \(b-a\):

$$
h=\frac{1}{b-a}
$$

### Main rule

The height of the uniform PDF is:

$$
\frac{1}{b-a}
$$

---

## 5. Uniform PDF formula

The PDF has two different rules depending on the value of \(x\).

### If \(x\) is between \(a\) and \(b\)

If:

$$
a<x<b
$$

then:

$$
f_X(x)=\frac{1}{b-a}
$$

### If \(x\) is outside the interval

If \(x\) is outside the interval from \(a\) to \(b\), then:

$$
f_X(x)=0
$$

So remember:

**Inside the interval → constant density**

**Outside the interval → density equals 0**

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

The total width is:

$$
b-a=15-0
$$

Therefore:

$$
b-a=15
$$

The PDF height is:

$$
\frac{1}{b-a}
$$

Substitute the values:

$$
\frac{1}{15-0}
$$

Therefore:

$$
f_X(x)=\frac{1}{15}
$$

Approximately:

$$
f_X(x)=0.0667
$$

So for waiting times between 0 and 15 minutes:

$$
f_X(x)=\frac{1}{15}
$$

---

## 7. Probability comes from area under the uniform PDF

Because the uniform distribution is continuous, probability corresponds to **area underneath the PDF**.

For a uniform distribution, this is especially easy because the PDF is a rectangle.

Suppose we want:

$$
P(c<X<d)
$$

where:

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

Probability equals width times height:

$$
P(c<X<d)=(d-c)\left(\frac{1}{b-a}\right)
$$

Therefore:

$$
P(c<X<d)=\frac{d-c}{b-a}
$$

### In words

**Probability = desired interval length / total interval length**

---

## 8. The easiest way to think about uniform probability

For a uniform distribution:

**Probability = width × height**

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
P(c<X<d)=(d-c)\left(\frac{1}{b-a}\right)
$$

which simplifies to:

$$
P(c<X<d)=\frac{d-c}{b-a}
$$

So another useful way to remember it is:

**Uniform probability = desired width / total width**

---

## 9. Uniform PDF versus normal PDF

This is an important visual distinction.

A normal PDF has changing density.

It goes approximately:

**low → high → low**

The result is a bell-shaped curve.

A uniform PDF has the same density everywhere inside the interval.

The result is a rectangle.

Therefore:

| Distribution | PDF Shape |
|---|---|
| Normal | Bell-shaped |
| Uniform | Flat rectangle |

---

## 10. The uniform CDF gives accumulated probability

The Cumulative Distribution Function is defined as:

$$
F_X(x)=P(X\leq x)
$$

The CDF tells us how much probability has accumulated by the time we reach \(x\).

For a uniform distribution, probability begins accumulating at \(a\).

It continues increasing until \(b\).

After \(b\), all probability has accumulated.

---

## 11. Before \(a\), the CDF equals 0

Suppose:

$$
x<a
$$

The random variable cannot take values below \(a\).

Therefore, no probability has accumulated yet.

So:

$$
F_X(x)=0
$$

### Rule

If:

$$
x<a
$$

then:

$$
F_X(x)=0
$$

---

## 12. Between \(a\) and \(b\), the CDF increases linearly

Suppose:

$$
a\leq x<b
$$

The amount of the interval covered so far is:

$$
x-a
$$

The entire interval has width:

$$
b-a
$$

Therefore:

$$
F_X(x)=\frac{x-a}{b-a}
$$

The CDF increases at a constant rate because the PDF has constant density.

This produces a straight diagonal line on the CDF graph.

---

## 13. At and beyond \(b\), the CDF equals 1

Suppose:

$$
x\geq b
$$

At this point, the entire possible interval has already been included.

Therefore, all probability has accumulated.

So:

$$
F_X(x)=1
$$

### Rule

If:

$$
x\geq b
$$

then:

$$
F_X(x)=1
$$

---

## 14. Uniform CDF formula

Instead of writing the CDF as one large piecewise equation, it can be remembered as three separate rules.

### Rule 1: Before the interval

If:

$$
x<a
$$

then:

$$
F_X(x)=0
$$

### Rule 2: Inside the interval

If:

$$
a\leq x<b
$$

then:

$$
F_X(x)=\frac{x-a}{b-a}
$$

### Rule 3: At or beyond the end of the interval

If:

$$
x\geq b
$$

then:

$$
F_X(x)=1
$$

These three rules together form the complete CDF of a continuous uniform distribution.

---

## 15. Why the CDF is a straight line inside the interval

The uniform PDF has constant height:

$$
\frac{1}{b-a}
$$

This means every equal-sized interval adds the same amount of probability.

For example, moving \(x\) another 1 unit always adds the same amount of area.

Therefore:

**Constant PDF → linear CDF**

This is the main relationship between the uniform PDF and CDF.

---

## 16. Special example: Uniform distribution from 0 to 1

Suppose:

$$
X\sim U(0,1)
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
\frac{1}{b-a}
$$

Substitute \(a=0\) and \(b=1\):

$$
\frac{1}{1-0}=1
$$

Therefore:

$$
f_X(x)=1
$$

for values between 0 and 1.

For the CDF, use:

$$
F_X(x)=\frac{x-a}{b-a}
$$

Substitute \(a=0\) and \(b=1\):

$$
F_X(x)=\frac{x-0}{1-0}
$$

Therefore:

$$
F_X(x)=x
$$

for:

$$
0\leq x<1
$$

---

## 17. Example of reading the CDF

Suppose:

$$
X\sim U(0,1)
$$

and we want:

$$
F_X(0.25)
$$

Use:

$$
F_X(x)=\frac{x-a}{b-a}
$$

Substitute:

$$
F_X(0.25)=\frac{0.25-0}{1-0}
$$

Simplify:

$$
F_X(0.25)=0.25
$$

Because:

$$
F_X(x)=P(X\leq x)
$$

we know:

$$
P(X\leq0.25)=0.25
$$

Therefore, 25% of the total probability has accumulated by:

$$
x=0.25
$$

---

# Most Important Definitions and Distinctions to Remember

## Uniform distribution

A continuous uniform distribution has **constant density between \(a\) and \(b\)**.

Equal-length portions of the interval have equal probabilities.

---

## Parameters

Lower endpoint:

$$
a
$$

Upper endpoint:

$$
b
$$

Total interval width:

$$
b-a
$$

Remember:

**\(a\) = lower endpoint**

**\(b\) = upper endpoint**

**Width = \(b-a\)**

---

## Uniform PDF

The PDF height is:

$$
\frac{1}{b-a}
$$

If:

$$
a<x<b
$$

then:

$$
f_X(x)=\frac{1}{b-a}
$$

Otherwise:

$$
f_X(x)=0
$$

---

## Uniform probability

For an interval between \(c\) and \(d\):

$$
P(c<X<d)=\frac{d-c}{b-a}
$$

Remember:

**Probability = desired interval width / total interval width**

You can also think of it as:

**Probability = width × height**

---

## Uniform CDF

The CDF is defined as:

$$
F_X(x)=P(X\leq x)
$$

Before the interval:

$$
F_X(x)=0
$$

Inside the interval:

$$
F_X(x)=\frac{x-a}{b-a}
$$

After the interval:

$$
F_X(x)=1
$$

The CDF:

- Equals 0 before \(a\)
- Increases linearly between \(a\) and \(b\)
- Equals 1 at and after \(b\)

---

# Main Rules to Put in Your Notebook

### Uniform distribution

**Equal density across an interval**

### Lower endpoint

$$
a
$$

### Upper endpoint

$$
b
$$

### Total width

$$
b-a
$$

### PDF height

$$
\frac{1}{b-a}
$$

### PDF inside the interval

$$
f_X(x)=\frac{1}{b-a}
$$

### PDF outside the interval

$$
f_X(x)=0
$$

### Probability between \(c\) and \(d\)

$$
P(c<X<d)=\frac{d-c}{b-a}
$$

### CDF inside the interval

$$
F_X(x)=\frac{x-a}{b-a}
$$

### CDF definition

$$
F_X(x)=P(X\leq x)
$$

---

# Biggest Ideas to Remember

**Uniform PDF = constant density**

**Uniform probability = desired interval length / total interval length**

**Constant PDF → straight-line CDF**

So in plain English:

**If every part of an interval has the same density, the PDF is a flat rectangle. Probability depends only on how much of the interval you select, and the CDF rises evenly from 0 to 1.**# What You Should Know About the Uniform Distribution

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
