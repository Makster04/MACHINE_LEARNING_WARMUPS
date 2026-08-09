# Week 1 Quiz — Worked Solutions

> Only the **numerical** problems are worked here. Questions 3, 4 and 8 were concept-recognition questions with no calculation; they are listed in the appendix with the file that covers them.
>
> Every answer below has been checked against an exact computation.

---

## Index

| Q | Problem | Answer | Files it draws on |
|---|---|---|---|
| 1 | Union of disjoint events | $\dfrac{7}{12}$ | **01** |
| 2 | Bayes, medical test | $\approx 0.0876$ | **04**, **05**, **03**, **01** |
| 5 | Build a CDF from a PMF | see table | **06** |
| 6 | Ten coins, not all heads | $\dfrac{2^{10}-1}{2^{10}}$ | **01**, **02** |
| 7 | Binomial setup, die rolls | $\binom{20}{7}\left(\frac16\right)^7\left(\frac56\right)^{13}$ | **08** |
| 9 | Cumulative probability | $0.75$ | **06** |
| 10 | Conditional probability | $\dfrac{7}{10}$ | **03**, **01**, **02** |

---

# Q1 — Union of disjoint events

**Given.** A bag of marbles. $A$ is drawing red, $B$ is drawing blue.

$$
P(A)=\frac14 \qquad P(B)=\frac13
$$

**Find.** $P(A\cup B)$.

**Uses:** 01 §7 (disjoint events), 01 §8 (add the probabilities), 01 §15 (why this is the general rule in disguise).

## Solve

One marble cannot be both red and blue, so the events are **disjoint**:

$$
P(A\cap B)=0
$$

Start from the general addition rule and let the overlap term vanish:

$$
P(A\cup B)=P(A)+P(B)-P(A\cap B)=P(A)+P(B)
$$

Put both fractions over 12 and add:

$$
P(A\cup B)=\frac14+\frac13=\frac{3}{12}+\frac{4}{12}
$$

$$
\boxed{P(A\cup B)=\frac{7}{12}\approx0.583}
$$

## Watch out for

Only drop the intersection term when the events genuinely cannot co-occur. If the question had been *soccer or basketball*, a person could do both and you would have to subtract the overlap.

---

# Q2 — Bayes' theorem, medical test

**Given.**

$$
P(\text{sick})=0.01
$$

$$
P(\text{pos}\mid\text{sick})=0.95
$$

$$
P(\text{neg}\mid\text{not sick})=0.90
$$

**Find.** $P(\text{sick}\mid\text{pos})$.

**Uses:** 04 §12 (the nine-step recipe), 05 §4 (this quantity is precision / PPV), 03 §17 (the denominator is the Law of Total Probability), 01 §3 (complement rule).

## Step 1 — fill in the two missing pieces

The problem gives specificity, not the false positive rate. Use the complement rule from 01:

$$
P(\text{not sick})=1-0.01=0.99
$$

$$
P(\text{pos}\mid\text{not sick})=1-0.90=0.10
$$

## Step 2 — the two paths to a positive test

$$
\text{sick and positive} \rightarrow 0.01\times0.95=0.0095
$$

$$
\text{healthy and positive} \rightarrow 0.99\times0.10=0.0990
$$

## Step 3 — total probability of the evidence

$$
P(\text{pos})=0.0095+0.0990=0.1085
$$

## Step 4 — divide

$$
P(\text{sick}\mid\text{pos})=\frac{0.0095}{0.1085}
$$

$$
\boxed{P(\text{sick}\mid\text{pos})\approx0.0876}
$$

or about **8.76 percent**.

## The counting version

From 04 §11, the same answer by counting whole people. Take 10,000:

| | positive | negative | total |
|---|---|---|---|
| **sick** | 95 | 5 | 100 |
| **healthy** | 990 | 8,910 | 9,900 |
| **total** | 1,085 | 8,915 | 10,000 |

$$
\frac{95}{1{,}085}\approx0.0876
$$

Of the 1,085 positive tests, only 95 are real. **False positives outnumber true positives about 10 to 1.**

## Why the answer is so low

This is the base-rate effect from 05 §7. The disease affects 1 percent, but the test's false positive rate is 10 percent — **ten times larger than the thing being detected**. The 990 false alarms from the huge healthy group swamp the 95 true positives from the tiny sick group.

Note also that this answer *is* **precision**, the quantity from 05 §4. Sensitivity is 95 percent and specificity is 90 percent, yet precision is under 9 percent, because precision depends on prevalence and the other two do not.

---

# Q5 — Building a CDF from a PMF

**Given.** Number of passengers $X$ in a taxi:

| $x$ | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
|---|---|---|---|---|---|---|---|
| $p_X(x)$ | 0.10 | 0.25 | 0.25 | 0.15 | 0.15 | 0.05 | 0.05 |

**Find.** The CDF.

**Uses:** 06 §13 (definition of the CDF), 06 §14 (properties), 06 §16 (the discrete CDF is the running sum of the PMF).

## Solve

First check the PMF is valid — the masses must total 1 (06 §4):

$$
0.10+0.25+0.25+0.15+0.15+0.05+0.05=1.00
$$

The CDF is defined as $F_X(x)=P(X\leq x)$, which for a discrete variable is the **running sum**:

$$
F_X(x)=\sum_{t\leq x}p_X(t)
$$

Accumulate left to right:

| $x$ | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
|---|---|---|---|---|---|---|---|
| $p_X(x)$ | 0.10 | 0.25 | 0.25 | 0.15 | 0.15 | 0.05 | 0.05 |
| $F_X(x)$ | **0.10** | **0.35** | **0.60** | **0.75** | **0.90** | **0.95** | **1.00** |

$$
\boxed{F_X = (0.10,\ 0.35,\ 0.60,\ 0.75,\ 0.90,\ 0.95,\ 1.00)}
$$

## How to rule out the wrong options fast

From 06 §14, every CDF must:

- **never decrease** — kills any option that goes down
- **end at 1** — kills any option whose last value is not 1
- **start at $p_X(0)$** — the first CDF value always equals the first PMF value

You can eliminate three of the four choices without adding anything up.

---

# Q6 — Ten coins, not all heads

**Given.** 10 fair coins.

**Find.** $P(\text{not all heads})$.

**Uses:** 01 §3 (complement rule), 02 §9 (repeated independent events give $p^n$).

## Solve

The event "not all heads" is messy — it covers 1,023 different outcomes. Its **opposite** is a single outcome, so use the complement rule.

Each flip is independent with $P(H)=\frac12$, so from 02 §9:

$$
P(\text{all heads})=\left(\frac12\right)^{10}=\frac{1}{1024}
$$

Now subtract from 1:

$$
P(\text{not all heads})=1-\frac{1}{2^{10}}
$$

$$
\boxed{P(\text{not all heads})=\frac{2^{10}-1}{2^{10}}=\frac{1023}{1024}\approx0.9990}
$$

## Watch out for

This is the classic **"at least one"** pattern from 01 §3. Whenever the event you want is complicated and its opposite is simple, flip it:

$$
P(\text{at least one})=1-P(\text{none})
$$

---

# Q7 — Binomial setup

**Given.** A six-sided die rolled 20 times.

**Find.** The expression for the probability that a 4 appears exactly 7 times.

**Uses:** 08 §6 (the binomial PMF), 08 §7 (what every symbol means), 08 §10 (the three factors).

## Step 1 — identify the parameters

Define **success** as rolling a 4. The die becomes a biased coin (08 §15):

$$
n=20 \qquad x=7 \qquad p=\frac16 \qquad 1-p=\frac56
$$

## Step 2 — apply the PMF

$$
P(X=x)=\binom{n}{x}p^x(1-p)^{n-x}
$$

$$
\boxed{P(X=7)=\binom{20}{7}\left(\frac16\right)^{7}\left(\frac56\right)^{13}}
$$

Numerically, $\binom{20}{7}=77{,}520$ and the result is $\approx0.0259$, about **2.6 percent**.

## The check that catches the wrong options

From 08 §10, the two exponents must add back to the number of trials:

$$
7+13=20 \qquad\checkmark
$$

The distractors fail exactly here — one has exponents $13$ and $7$ attached to the wrong probabilities, and another uses $7$ and $7$, which sums to 14 rather than 20. Checking the exponents is faster than checking anything else.

The success probability $\frac16$ must carry the exponent $7$ (the number of successes), and $\frac56$ must carry $13$ (the number of failures).

---

# Q9 — Cumulative probability

**Given.** The same taxi PMF as Q5.

**Find.** $P(X\leq3)$.

**Uses:** 06 §5 (discrete probability is a sum of masses), 06 §13 (the CDF).

## Solve

For a discrete variable you add the masses (06 §5):

$$
P(X\leq3)=p_X(0)+p_X(1)+p_X(2)+p_X(3)
$$

$$
P(X\leq3)=0.10+0.25+0.25+0.15
$$

$$
\boxed{P(X\leq3)=0.75}
$$

## Shortcut

This is just $F_X(3)$ from the CDF you already built in Q5. Once the CDF exists, every "less than or equal to" question is a single lookup, and every "between" question is one subtraction (06 §17):

$$
P(a<X\leq b)=F_X(b)-F_X(a)
$$

Also note the endpoint matters here. For a **discrete** variable, $P(X\leq3)=0.75$ but $P(X<3)=0.60$ — the bar at 3 carries real mass. For a continuous variable the two would be equal (06 §9).

---

# Q10 — Conditional probability

**Given.** 200 people in a room:

- 30 like **only** soccer
- 100 like **only** basketball
- 70 like **both**

**Find.** $P(B\mid S)$, the probability someone likes basketball given they like soccer.

**Uses:** 03 §6 (the conditional probability formula), 03 §2 (conditioning shrinks the sample space), 01 §5 (intersection), 02 §12 (testing independence).

## Step 1 — convert "only" counts into event totals

This is where the question is won or lost. **"30 like only soccer" is not $|S|$.** Everyone who likes both also likes soccer:

$$
|S| = 30 + 70 = 100
$$

$$
|B| = 100 + 70 = 170
$$

$$
|B\cap S| = 70
$$

Check the total: $30+100+70=200 \checkmark$

## Step 2 — apply the formula

$$
P(B\mid S)=\frac{P(B\cap S)}{P(S)}
$$

$$
P(B\mid S)=\frac{70/200}{100/200}=\frac{70}{100}
$$

$$
\boxed{P(B\mid S)=\frac{7}{10}=0.70}
$$

## Step 3 — sanity-check with the sample space idea

From 03 §2, conditioning on $S$ throws away everyone who does not like soccer. That leaves **100 soccer fans**, of whom **70** also like basketball:

$$
\frac{70}{100}=0.70 \qquad\checkmark
$$

## The mistake to avoid

Answering $\frac{7}{3}$ means dividing $\frac{70}{30}$ — using the **only-soccer** count as the denominator instead of the **total** soccer count.

$$
\frac{70}{30}=\frac{7}{3}\approx2.33
$$

There is a free alarm bell here: **a probability can never exceed 1.** Any answer above 1 is wrong before you check anything else.

$$
\boxed{\text{“only X” is a piece of the event, not the event}}
$$

Draw the Venn diagram (01 §5) and label all three regions before computing anything. The 70 who like both belong in the soccer circle *and* the basketball circle.

## Bonus — are the two independent?

Apply the test from 02 §12:

$$
P(B)=\frac{170}{200}=0.85 \qquad P(B\mid S)=0.70
$$

Since $P(B\mid S)\neq P(B)$, liking soccer and liking basketball are **dependent** in this room — knowing someone likes soccer makes them *less* likely to like basketball.

---

# What to review

| Missed | Why | Read |
|---|---|---|
| Q10 | Used the "only" count as the event total | **03** §6 and §2, then **01** §5 |
| Q3 | Distribution choice (conceptual) | **10** §10, **08** §3 |

Both misses are the same underlying habit: matching a formula before checking what the pieces actually refer to. In Q10 that meant grabbing 30 instead of 100; in Q3 it meant reaching for a distribution without checking whether the variable was a count or a measurement.

---

# Appendix — the non-numerical questions

Excluded from the worked solutions above, listed here for reference.

| Q | Topic | Answer | Covered in |
|---|---|---|---|
| 3 | Which distribution models heights | Normal | **10** §10, and **06** §2 for discrete versus continuous |
| 4 | Reading $\mu$ and $\sigma$ off a graph | $\mu$ sets the centre, $\sigma$ sets the width | **10** §2, §3, §4 |
| 8 | Which variables are continuous | height, time, temperature, weight | **06** §2 |

For Q3, the deciding question from 06 §2 is: *can I list the possible values, or must I describe a range?* Height is measured, not counted, so it is continuous — which rules out the binomial immediately, since a binomial counts successes in a fixed number of trials (08 §3).
