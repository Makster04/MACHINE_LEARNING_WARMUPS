# Week 1 Practice Quiz — Worked Solutions

> Scored **80/100**. All five questions are worked below; every answer has been checked against an exact computation.
>
> File numbers in the right-hand column refer to notes files 01 through 14.

---

## Index

| Q | Problem | Answer | Files it draws on |
|---|---|---|---|
| 1 | Ten dice, sum greater than 10 | $\dfrac{6^{10}-1}{6^{10}}$ | **01**, **02** |
| 2 | A/B test, version given a bug | $0.50$ | **03** |
| 3 | Two flips, one head and one tail | $\dfrac{1}{2}$ | **01**, **08** |
| 4 | Two dice, sum of 10 | $\dfrac{1}{12}$ | **01**, **03** |
| 5 | Headache or fever | Not determined | **01** |

---

# Q1 — Ten dice, sum greater than 10

**Given.** A six-sided die thrown 10 times, and the results summed.

**Find.** $P(\text{sum} > 10)$.

**Uses:** 01 §3 (complement rule), 02 §9 (repeated independent events).

## Step 1 — flip to the complement

"Sum greater than 10" covers a huge number of outcomes. Its opposite does not, so use the complement rule from 01:

$$
P(\text{sum} > 10) = 1 - P(\text{sum} \leq 10)
$$

## Step 2 — the key observation

Every die shows **at least 1**, so the smallest sum ten dice can possibly produce is:

$$
10 \times 1 = 10
$$

That means "sum $\leq 10$" can happen in exactly **one** way: every single die shows a 1.

$$
\boxed{\text{sum} \leq 10 \iff \text{all ten dice show 1}}
$$

## Step 3 — probability of that one outcome

Each throw is independent with $P(1) = \frac16$, so by the $p^n$ rule from 02:

$$
P(\text{all ones}) = \left(\frac16\right)^{10} = \frac{1}{6^{10}}
$$

## Step 4 — subtract

$$
P(\text{sum} > 10) = 1 - \frac{1}{6^{10}}
$$

$$
\boxed{P(\text{sum} > 10) = \frac{6^{10}-1}{6^{10}}}
$$

Numerically $6^{10} = 60{,}466{,}176$, so the answer is $\frac{60{,}466{,}175}{60{,}466{,}176} \approx 0.99999998$ — very nearly certain.

## Why the hint mattered

Counting the sums greater than 10 directly would mean enumerating almost all $6^{10}$ outcomes. Counting the opposite means enumerating **one**. That is the whole value of the complement rule: when the event you want is sprawling and its opposite is tiny, flip it.

---

# Q2 — A/B test, which version given a bug

**Given.**

| | Users | Bugs |
|---|---|---|
| Version A | 4,000 | 1,500 |
| Version B | 5,000 | 1,500 |
| **Total** | **9,000** | **3,000** |

The A row's bug count is not stated directly — it is $3000 - 1500 = 1500$.

**Find.** $P(B \mid \text{bug})$.

**Uses:** 03 §6 (conditional probability formula), 03 §2 (conditioning shrinks the sample space).

## Solve with the formula

$$
P(B \mid E) = \frac{P(B \cap E)}{P(E)}
$$

$$
P(B \cap E) = \frac{1500}{9000} = \frac16
\qquad
P(E) = \frac{3000}{9000} = \frac13
$$

$$
P(B \mid E) = \frac{1/6}{1/3} = \frac{1}{2}
$$

$$
\boxed{P(B \mid \text{bug}) = 0.50}
$$

## Solve by shrinking the sample space

Same answer, less algebra. From 03 §2, conditioning on "experienced a bug" throws away everyone else. That leaves **3,000 people**, of whom **1,500** were on version B:

$$
\frac{1500}{3000} = 0.50 \qquad\checkmark
$$

The 9,000 total never actually enters the calculation — it cancels. Once you condition on the bug, the only two numbers that matter are 1,500 and 3,000.

## Bonus — B is the better version

Worth noticing, because it is the opposite of what a 50 percent result sounds like:

| | Bug rate |
|---|---|
| Version A | $\dfrac{1500}{4000} = 0.375$ |
| Version B | $\dfrac{1500}{5000} = 0.300$ |
| Overall | $\dfrac{3000}{9000} \approx 0.333$ |

Version B has the **lower** bug rate. It only accounts for half the bugs because it had more users. And applying the independence test from 02 §12:

$$
P(B) = \frac{5000}{9000} \approx 0.556
\qquad\text{but}\qquad
P(B \mid \text{bug}) = 0.500
$$

Since these differ, version and bug are **dependent** — learning that someone hit a bug makes it slightly less likely they were on B.

---

# Q3 — Two flips, one head and one tail

**Given.** A fair coin flipped twice.

**Find.** $P(\text{one head and one tail, in any order})$.

**Uses:** 01 §1 (events and outcomes), 08 §6 (the binomial route).

## Solve by listing the sample space

Two flips give four equally likely outcomes:

$$
\{HH,\ HT,\ TH,\ TT\}
$$

Now ask which of them have exactly one head and one tail:

| Outcome | Heads | Counts? |
|---|---|---|
| $HH$ | 2 | no |
| $HT$ | 1 | **yes** |
| $TH$ | 1 | **yes** |
| $TT$ | 0 | no |

Two of the four qualify:

$$
\boxed{P = \frac{2}{4} = \frac{1}{2}}
$$

## The mistake to avoid

The trap is **"in any order."** Those three words mean $HT$ and $TH$ are two separate outcomes and **both** count.

Answering $\frac14$ means counting only one of them — the probability of a *specific* order, such as head-then-tail. Answering $\frac34$ means counting three outcomes when only two qualify.

$$
\boxed{\text{“in any order” means every arrangement counts, not just one}}
$$

## The binomial route

This is the same idea as the arrangements section in 08 §9. With $n=2$, $x=1$, $p=0.5$:

$$
P(X=1) = \binom{2}{1}(0.5)^1(0.5)^1 = 2 \times 0.25 = 0.5 \qquad\checkmark
$$

The $\binom{2}{1} = 2$ **is** the "in any order" factor. Drop it and you get $0.25$ — exactly the wrong answer. This is the same failure 08 §9 warns about: forgetting the coefficient gives the probability of one specific sequence rather than of the count.

---

# Q4 — Two dice, sum of 10

**Given.** Two dice thrown and summed.

**Find.** $P(\text{sum} = 10)$.

**Uses:** 01 §16 (the 36-outcome grid), 03 §13 (this exact example).

## Solve by counting

Two dice produce:

$$
6 \times 6 = 36
$$

equally likely ordered outcomes. The ones summing to 10 are:

$$
(4,6), \quad (5,5), \quad (6,4)
$$

$$
\boxed{P(\text{sum} = 10) = \frac{3}{36} = \frac{1}{12}}
$$

## Watch the ordering

$(4,6)$ and $(6,4)$ are **two** outcomes, not one — the same "in any order" point as Q3. But $(5,5)$ is only **one**, because swapping the dice changes nothing. Treating all three as pairs would give 6; treating them all as unordered would give 3 out of 21. Counting ordered outcomes consistently is what makes 36 the right denominator.

## You have already seen this

This is the exact example worked in 03 §13, where it becomes the starting point for conditioning. There:

$$
P(\text{sum}=10) = \frac{1}{12}
\qquad\text{but}\qquad
P(\text{sum}=10 \mid \text{first die is 6}) = \frac16
$$

Knowing the first die is a 6 doubles it. The dice grid figure in 03 shows all 36 cells with the sum-10 cells marked.

---

# Q5 — Headache or fever

**Given.** 100 patients. 50 had a headache, 50 had a fever.

**Find.** $P(\text{headache or fever})$.

**Uses:** 01 §10 (double counting), 01 §11 (the addition rule), 01 §15 (disjoint versus joint).

## The answer

$$
\boxed{\text{Not enough information.}}
$$

## Why

The addition rule from 01 §11 is:

$$
P(H \cup F) = P(H) + P(F) - P(H \cap F)
$$

You are given $P(H) = 0.5$ and $P(F) = 0.5$, but **nothing** about $P(H \cap F)$. Nothing in the problem says a patient cannot have both symptoms — and in fact people commonly do.

So the events are **joint**, not disjoint, and the overlap term cannot be dropped.

## How far apart the possible answers are

The overlap could be anything from 0 to 0.5, which puts the answer anywhere in a very wide range:

| If... | $P(H \cap F)$ | $P(H \cup F)$ |
|---|---|---|
| No patient has both (disjoint) | $0$ | $1.00$ |
| Symptoms are independent | $0.25$ | $0.75$ |
| Everyone with a fever also has a headache | $0.50$ | $0.50$ |

The answer could be **anywhere from 0.50 to 1.00**, and the data cannot narrow it down. That is what "not enough information" means here — not that the problem is unanswerable, but that one specific number is missing.

## Why the two distractors are wrong

**$P(H) + P(F) = 1$** assumes the events are **disjoint**. Nothing in the problem says that, and symptoms overlapping is the normal case.

**$P(H) \times P(F) = 0.25$** makes two errors at once: it assumes **independence**, which is also not stated, and it computes the **intersection** rather than the union. Even granting independence, $0.25$ would be $P(H \cap F)$, and the union would then be $0.75$.

$$
\boxed{\text{Do not assume disjoint. Do not assume independent. Both must be told to you.}}
$$

---

# What to review

| Missed | Why | Read |
|---|---|---|
| Q3 | "In any order" — counted one arrangement instead of both | **01** §1, then **08** §9 |

The habit to build is **listing the sample space before reaching for a formula**. Q3 has only four outcomes; writing $\{HH, HT, TH, TT\}$ and ticking the qualifying ones takes ten seconds and cannot go wrong.

Notice that three of the five questions on this quiz turn on the same skill:

| Q | What it tests |
|---|---|
| 3 | $HT$ and $TH$ both count |
| 4 | $(4,6)$ and $(6,4)$ both count, but $(5,5)$ counts once |
| 5 | Does the overlap get counted twice? |

All three are about **counting outcomes correctly** rather than about any formula. That is file 01's territory, and it is where the points on this quiz were actually won and lost.
