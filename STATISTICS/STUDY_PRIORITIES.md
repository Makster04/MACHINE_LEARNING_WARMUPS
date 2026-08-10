# Study Priorities — What Actually Matters

> The notes run to fourteen files. The **load-bearing ideas** are far fewer than that.
>
> This file is the triage list: what to understand deeply, what to memorize, what to practise, and what you can safely look up. Read it before an exam rather than re-reading everything.

---

# Part 1 — The five ideas everything rests on

If these five are solid, most of the rest can be reconstructed. If any is shaky, the files above it will keep feeling arbitrary.

## 1. Probability is counting, done carefully

Every answer in 01 comes from:

$$
\frac{\text{favourable outcomes}}{\text{total outcomes}}
$$

The division is never the hard part. The hard part is deciding **what counts as one outcome**. Is $(4,6)$ the same as $(6,4)$? Does $HT$ count separately from $TH$? Settle that and the arithmetic is trivial.

$$
\boxed{\text{Write the sample space down before reaching for a formula.}}
$$

*Files: 01, and it never stops mattering.*

## 2. Conditioning shrinks the sample space

Once you are told $B$ happened, every outcome inconsistent with $B$ is gone, and you measure against what remains.

That one sentence generates conditional probability, independence, Bayes' theorem, and Naive Bayes. If you remember nothing else from 03, remember this.

$$
\boxed{P(A\mid B) = \frac{\text{favourable outcomes inside } B}{\text{all outcomes inside } B}}
$$

*Files: 03, and it powers 04, 05, 13.*

## 3. Direction matters

$$
\boxed{P(A\mid B) \neq P(B\mid A)}
$$

This is the most consequential mistake in the subject, and it has a name in every field that uses it — **base-rate neglect** in 04, the **precision/recall confusion** in 05.

Bayes' theorem is nothing but the machine for reversing the arrow correctly.

*Files: 03, 04, 05.*

## 4. A random variable turns outcomes into numbers

"Heads, heads, tails" cannot be averaged. The value $2$ can.

That conversion is what makes expectation, variance, and every distribution possible. Before random variables you can only talk about events; after them you can do arithmetic.

*Files: 06, and everything from 07 onward.*

## 5. A distribution is a model, not a fact

Every distribution arrives with assumptions attached — fixed $n$, constant $p$, independence, normality. The formula is only correct **if the assumptions hold**, and checking them is part of the work, not an optional extra.

$$
\boxed{\text{Naming the distribution is a claim. Verify it.}}
$$

*Files: 08 through 14.*

---

# Part 2 — One non-negotiable per file

The single thing from each file you should be able to state without looking.

| File | The thing |
|---|---|
| **01** | Add for OR and subtract the overlap. Use the complement when the opposite is simpler |
| **02** | Multiply for AND, but only after confirming independence. **Disjoint events are always dependent** |
| **03** | The general product rule always works; independence is the shortcut. The Law of Total Probability breaks a problem into cases |
| **04** | Bayes is the product rule divided by the Law of Total Probability. It is not a new rule |
| **05** | Sensitivity describes **the test**. Precision describes **your result**, and depends on the base rate |
| **06** | PMF is mass, so add. PDF is density, so take area. CDF is the running total. The PDF is the CDF's slope |
| **07** | $E[X]$ is the balance point; variance is the average squared distance. **Variance adds only for independent variables** |
| **08** | A binomial counts successes across $n$ independent trials with constant $p$. The coefficient counts arrangements |
| **09** | Constant density means probability is simply the fraction of the interval you selected |
| **10** | The normal is fixed by $\mu$ and $\sigma$ alone, and its area has **no closed form** |
| **11** | Standardizing puts every normal onto one curve, but it **never changes the shape** |
| **12** | A large binomial is nearly normal, but discrete bars need a half-unit boundary correction |
| **13** | Naive Bayes is Bayes plus conditional independence, with smoothing and logs to survive real data |
| **14** | Squaring a standard normal gives chi-square. Adding $k$ independent ones gives $k$ degrees of freedom |

---

# Part 3 — The five skills

Facts can be looked up. These cannot.

## 1. Decide OR or AND before touching a formula

$$
\text{OR} \rightarrow \text{add} \qquad \text{AND} \rightarrow \text{multiply, if independent}
$$

Reading the question for this one word first prevents a whole class of error.

## 2. Ask whether the complement is easier

Whenever the event is sprawling and its opposite is compact, flip it:

$$
P(\text{at least one}) = 1 - P(\text{none})
$$

"At least one" almost always signals this.

## 3. Count with a consistent notion of "same"

Ordered or unordered — pick one and hold it for the whole problem. Two dice have **36 ordered outcomes**; switching to unordered mid-problem is what produces wrong denominators.

## 4. Verify assumptions before using a shortcut

| About to use | First check |
|---|---|
| $P(A)P(B)$ | Are they independent? |
| $P(A)+P(B)$ | Are they disjoint? |
| $\binom{n}{x}p^x(1-p)^{n-x}$ | Fixed $n$, constant $p$, independent trials? |
| A z-table | Is the data actually normal? |
| $N(np, np(1-p))$ | Is $np \geq 10$ and $n(1-p) \geq 10$? |
| $\text{Var}(X+Y)=\text{Var}(X)+\text{Var}(Y)$ | Are they independent? |

## 5. Sanity-check the answer

- Is it between 0 and 1?
- Did the evidence move the probability in the direction it should have?
- Does the complement come out sensible?
- Do the pieces sum to 1 where they should?

A probability above 1 is wrong before you check anything else.

---

# Part 4 — Where the points actually go

Across both quizzes taken so far, **every** miss traces to one of three things. None of them is a formula.

| Failure mode | What it looked like | Fix |
|---|---|---|
| Counting the wrong thing | "In any order" — $HT$ and $TH$ both count | Write out the sample space |
| Grabbing the wrong number | Used *only-soccer* (30) instead of *all soccer* (100) | Draw the Venn and label every region |
| Assuming an unstated property | Treated events as disjoint or independent when nothing said so | If it was not stated, you cannot use it |

$$
\boxed{\text{The formulas were never the problem.}}
$$

The distinctions table in **00** drills the third failure. The first two are a habit, not a fact — write the outcomes down before computing.

---

# Part 5 — Triage

## Understand deeply

These are the ideas that generate other ideas. Time spent here pays compound interest.

- Conditioning shrinks the sample space *(03)*
- $P(A\mid B)\neq P(B\mid A)$ *(03, 04, 05)*
- Independent is not disjoint *(02)*
- Density is not probability *(06, 09)*
- The PDF is the slope of the CDF *(06)*
- Sensitivity versus precision *(05)*

## Memorize

Short, high-frequency, no derivation needed.

- $P(A^c)=1-P(A)$
- $P(A\cup B)=P(A)+P(B)-P(A\cap B)$
- $P(A\mid B)=\dfrac{P(A\cap B)}{P(B)}$
- $P(X=x)=\binom{n}{x}p^x(1-p)^{n-x}$
- $z=\dfrac{x-\mu}{\sigma}$
- 68-95-99.7, and that exactly 95 percent needs $1.96$
- Mean and variance for Bernoulli, binomial, uniform, normal, chi-square

The table in **00** has all of these with a worked instance beside each.

## Practise

Skills, not facts. They only come from repetition.

- Counting outcomes, ordered and unordered
- Choosing the complement
- Building a tree and reading the Law of Total Probability off it
- Filling a confusion matrix from counts
- Running the nine-step Bayes recipe *(04 §12)*
- Applying the continuity correction in the right direction *(12 §6)*

## Look up

No reason to carry these in your head.

- The full normal PDF formula
- The general chi-square PDF with the gamma function
- Exact z-table values beyond the common few
- Laplace smoothing constants and Naive Bayes variant names

---

# The one-paragraph version

**Probability is careful counting. Conditioning narrows what you are counting over, and the direction of that conditioning changes the answer — which is what Bayes' theorem exists to handle. Random variables turn outcomes into numbers so you can average them and measure their spread. A distribution is a named model with assumptions attached, and the assumptions have to be checked before the formula is allowed. Almost every mistake comes from counting the wrong thing, grabbing the wrong number, or assuming a property nobody stated.**

---

# Where to go next

| If this feels shaky | Read |
|---|---|
| Counting, OR versus AND | **01** §4, §5, §16, §17 |
| Independent versus disjoint | **02** §12 |
| Conditioning | **03** §2, §6 |
| Bayes mechanics | **04** §12 (the nine steps) |
| Which rate is which | **05** §5 |
| Density versus probability | **06** §8, then **09** §4 |
| Why variance squares things | **07** §4 |
| When the binomial does not apply | **08** §3 |
| Reading a z-table | **11** §8, §9 |
| The continuity correction | **12** §6 |
