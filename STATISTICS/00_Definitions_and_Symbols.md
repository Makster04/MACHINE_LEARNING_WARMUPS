# Definitions and Symbols — Master Reference

> One page for the two things worth having in front of you: **what every symbol means**, and **the definitions you should be able to state from memory**.
>
> Each entry names the file where the idea is developed in full. Numbers in the right-hand columns refer to files 01 through 14.

---

# Part 1 — Symbols

## Events and sets

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $S$ | "the sample space" | Every possible outcome. $P(S)=1$ | 01 |
| $A$, $B$ | "event A", "event B" | A set of outcomes | 01 |
| $A\cup B$ | "A **or** B" | Union: in A, in B, or in both | 01 |
| $A\cap B$ | "A **and** B" | Intersection: in both at once | 01 |
| $A^c$ | "**not** A" | Complement. Also written $A'$ or $\bar{A}$ | 01 |
| $\varnothing$ | "the empty set" | No outcomes at all | 01 |
| $\lvert A\rvert$ | "the size of A" | How many outcomes are in A | 01 |
| $A_1,\ldots,A_k$ | "a partition" | Pieces with no overlap and no gaps | 01 |

## Probability

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $P(A)$ | "the probability of A" | A number between 0 and 1 | 01 |
| $\mid$ | "**given that**" | Everything after the bar has already happened | 03 |
| $P(A\mid B)$ | "probability of A given B" | A measured only within B | 03 |
| $\propto$ | "is proportional to" | Equal up to a constant that does not affect the comparison | 04, 13 |
| $\perp$ | "is independent of" | Written out as $P(A\cap B)=P(A)P(B)$ in these notes | 02 |

## Random variables

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $X$ | "the random variable X" | The **rule** assigning a number to each outcome | 06 |
| $x$ | "a value x" | One particular number $X$ can take | 06 |
| $p_X(x)$ | "the PMF of X at x" | $P(X=x)$, for **discrete** variables | 06 |
| $f_X(x)$ | "the PDF of X at x" | **Density** at $x$, for **continuous** variables | 06 |
| $F_X(x)$ | "the CDF of X at x" | $P(X\leq x)$, accumulated probability | 06 |
| $\sim$ | "is distributed as" | $X\sim N(0,1)$ means X follows that distribution | 08 |

Note the case: lowercase $f$ is the density, capital $F$ is the cumulative function. That is the only thing telling them apart.

## Summary numbers

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $E[X]$ | "the expected value of X" | The long-run average; the balance point | 07 |
| $\mu$ | "mu" | Population **mean**. Same thing as $E[X]$ | 07 |
| $\sigma$ | "sigma" | Population **standard deviation** | 07 |
| $\sigma^2$ | "sigma squared" | Population **variance** | 07 |
| $\text{Var}(X)$ | "the variance of X" | $E[(X-\mu)^2]$ | 07 |
| $\bar{x}$ | "x-bar" | **Sample** mean | 07 |
| $s$, $s^2$ | "s", "s squared" | **Sample** standard deviation and variance | 07 |

Greek letters describe a **population**. Roman letters describe a **sample**.

## Distribution names

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $\text{Bernoulli}(p)$ | — | One success/failure trial | 08 |
| $\text{Binomial}(n,p)$ | — | Successes across $n$ independent trials | 08 |
| $U(a,b)$ | "uniform on a to b" | Constant density between $a$ and $b$ | 09 |
| $N(\mu,\sigma^2)$ | "normal mu, sigma squared" | The bell. **Second argument is the variance** | 10 |
| $Z$ | "Z" | A variable that is $N(0,1)$ | 11 |
| $\Phi(z)$ | "capital phi of z" | The standard normal **CDF** — what a z-table holds | 11 |
| $\varphi(z)$ | "phi of z" | The standard normal **PDF** | 14 |
| $\chi^2(k)$ | "chi-square with k df" | Sum of $k$ independent squared standard normals | 14 |

## Distribution parameters

| Symbol | What it means | File |
|---|---|---|
| $n$ | Number of trials | 08 |
| $p$ | Probability of success on one trial | 08 |
| $1-p$ | Probability of failure | 08 |
| $x$ | Number of successes you are asking about | 08 |
| $n-x$ | Number of failures | 08 |
| $a$, $b$ | Lower and upper endpoints of a uniform | 09 |
| $k$ | Degrees of freedom | 14 |
| $\hat{p}$ | "p-hat" — a **sample** proportion, $X/n$ | 12 |

## Operators and relations

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $\sum$ | "sum over" | Add the terms up (discrete) | 06 |
| $\prod$ | "product over" | Multiply the terms together | 13 |
| $\int$ | "the integral of" | Area under a curve (continuous) | 06 |
| $\binom{n}{x}$ | "n choose x" | $\dfrac{n!}{x!(n-x)!}$, the number of arrangements | 08 |
| $!$ | "factorial" | $5! = 5\cdot4\cdot3\cdot2\cdot1$ | 08 |
| $\Gamma$ | "gamma" | A function generalizing the factorial | 14 |
| $\arg\max$ | "the argument that maximizes" | Which option scores highest, not the score itself | 13 |
| $\lvert z\rvert$ | "the absolute value of z" | Size, ignoring the sign | 11 |
| $\min$, $\max$ | "min", "max" | The smallest and largest value in the data | 11 |
| $\approx$ | "approximately equals" | | — |
| $\neq$ | "does not equal" | | — |
| $\leq$, $\geq$ | "at most", "at least" | | — |
| $\Rightarrow$ | "implies" | | 03 |
| $\Longleftrightarrow$ | "if and only if" | Each statement implies the other | 03 |
| $\infty$ | "infinity" | | 06 |

## Constants

| Symbol | Value | File |
|---|---|---|
| $e$ | $\approx 2.71828$ | 10 |
| $\pi$ | $\approx 3.14159$ | 10 |
| $\alpha$ | The smoothing constant, usually 1 | 13 |

## Classification shorthand

| Symbol | What it means | File |
|---|---|---|
| TP | True positive — sick, tested positive | 05 |
| FN | False negative — sick, tested negative | 05 |
| FP | False positive — healthy, tested positive | 05 |
| TN | True negative — healthy, tested negative | 05 |
| $\hat{y}$ | "y-hat" — the **predicted** label | 13 |
| $w_i$ | The $i$-th feature, or word | 13 |
| $F_1$ | The harmonic mean of precision and recall | 05 |

---

# Part 2 — Definitions

## Events and set language

**Event.** A set of possible outcomes. *(01)*

**Sample space.** The set of all possible outcomes, written $S$, with $P(S)=1$. *(01)*

**Complement.** Everything not in the event. $P(A^c)=1-P(A)$. *(01)*

**Disjoint** (or **mutually exclusive**). The events cannot happen together: $A\cap B=\varnothing$, so $P(A\cap B)=0$. *(01)*

**Joint.** The events can happen together, so the intersection may be non-zero. *(01)*

**Exhaustive.** The events cover the whole sample space, leaving no gaps. *(01)*

**Partition.** A group of events that is **both** disjoint and exhaustive — no overlap, no gaps. Their probabilities add to 1. *(01)*

> Disjoint asks *do they overlap?* Exhaustive asks *do they cover everything?* A partition needs both.

---

## Probability rules

**Addition rule.** $P(A\cup B)=P(A)+P(B)-P(A\cap B)$. Subtract the overlap so it is not counted twice. For disjoint events the last term is 0. *(01)*

**Independence.** One event happening does not change the probability of the other. Three equivalent statements: *(02, 03)*

$$
P(A\cap B)=P(A)P(B)
\quad\Longleftrightarrow\quad
P(A\mid B)=P(A)
\quad\Longleftrightarrow\quad
P(B\mid A)=P(B)
$$

**Conditional independence.** Independence **within** a group: $P(A\cap B\mid C)=P(A\mid C)P(B\mid C)$. This does **not** imply ordinary independence, and is not implied by it. *(02, 13)*

**Conditional probability.** $P(A\mid B)=\dfrac{P(A\cap B)}{P(B)}$, requiring $P(B)>0$. Conditioning shrinks the sample space to B. *(03)*

**General product rule.** $P(A\cap B)=P(A)P(B\mid A)=P(B)P(A\mid B)$. Always valid. Collapses to $P(A)P(B)$ when independent. *(03)*

**Law of Total Probability.** For a partition $A_1,\ldots,A_k$: *(03)*

$$
P(B)=\sum_{i=1}^{k}P(A_i)P(B\mid A_i)
$$

Multiply along each branch, add across the branches.

**Bayes' theorem.** Reverses the direction of a conditional: *(04)*

$$
P(A\mid B)=\frac{P(A)P(B\mid A)}{P(A)P(B\mid A)+P(A^c)P(B\mid A^c)}
$$

**Prior.** $P(A)$ — the probability before seeing evidence. Also called the **base rate**. *(04, 05)*

**Likelihood.** $P(B\mid A)$ — how likely the evidence is if A is true. *(04)*

**Evidence.** $P(B)$ — how likely the evidence is overall, from any cause. It is the denominator, and it normalizes the result. *(04)*

**Posterior.** $P(A\mid B)$ — the updated probability after seeing the evidence. *(04)*

> The order matters: $P(A\mid B)\neq P(B\mid A)$. Reversing them is the single most common probability error.

---

## Test accuracy

**Sensitivity**, also **recall**, also **TPR**. Of the people who are sick, how many does the test catch? $\dfrac{TP}{TP+FN}=P(\text{pos}\mid\text{sick})$. *(05)*

**Specificity**, also **TNR**. Of the healthy people, how many does the test clear? $\dfrac{TN}{TN+FP}$. *(05)*

**False positive rate.** $\dfrac{FP}{FP+TN}=1-\text{specificity}$. *(05)*

**Precision**, also **PPV**. If the test says positive, how often is it right? $\dfrac{TP}{TP+FP}=P(\text{sick}\mid\text{pos})$. *(05)*

**Accuracy.** $\dfrac{TP+TN}{\text{total}}$. Misleading whenever one class is rare. *(05)*

**Prevalence**, also **base rate**, also **class prior.** How common the condition is before testing. *(05)*

> Sensitivity and specificity condition on the **truth** and describe the test. Precision conditions on the **prediction** and depends on the base rate too. Bayes is what converts between them.

---

## Random variables

**Random variable.** A rule assigning a number to every outcome of an experiment. Capital $X$ is the rule; lowercase $x$ is one value it takes. *(06)*

**Discrete.** Takes separate, countable values. Uses a **PMF**. *(06)*

**Continuous.** Takes any value in an interval. Uses a **PDF**. *(06)*

**PMF — Probability Mass Function.** $p_X(x)=P(X=x)$ for discrete variables. Probability comes from **adding** masses, and $\sum_x p_X(x)=1$. *(06)*

**PDF — Probability Density Function.** $f_X(x)$ is **density**, not probability, for continuous variables. Probability comes from **area**, and the total area is 1. For any single point, $P(X=x)=0$. *(06)*

**CDF — Cumulative Distribution Function.** $F_X(x)=P(X\leq x)$. Works for both discrete and continuous. Runs from 0 to 1 and never decreases. *(06)*

**The link between them.** The PDF is the slope of the CDF; the CDF is the accumulated area under the PDF: *(06)*

$$
F_X(x)=\int_{-\infty}^{x}f_X(t)\,dt
\qquad
f_X(x)=F_X'(x)
$$

> A **density** can exceed 1. A **probability** never can. Only the area is capped.

---

## Summary numbers

**Expected value.** The weighted average, and the balance point of the distribution. It need not be a value the variable can actually take. *(07)*

$$
E[X]=\sum_x x\,p_X(x)
\qquad\text{or}\qquad
\int_{-\infty}^{\infty}x f_X(x)\,dx
$$

**Variance.** The average **squared** distance from the mean. Squared so that positive and negative deviations do not cancel. *(07)*

$$
\text{Var}(X)=E\left[(X-\mu)^2\right]=E[X^2]-\left(E[X]\right)^2
$$

**Standard deviation.** $\sigma=\sqrt{\text{Var}(X)}$, back in the original units. *(07)*

**Linear transformations.** $E[aX+b]=aE[X]+b$ and $\text{Var}(aX+b)=a^2\text{Var}(X)$. Shifting does not change spread; scaling changes variance by the **square** of the factor. *(07)*

**Additivity.** For **independent** variables, $\text{Var}(X+Y)=\text{Var}(X)+\text{Var}(Y)$. Variance adds; standard deviation does not. *(07)*

> Use $\sigma^2$ to calculate, $\sigma$ to interpret. Sample variance divides by $n-1$, not $n$.

---

## Distributions

| Distribution | Models | Mean | Variance | File |
|---|---|---|---|---|
| $\text{Bernoulli}(p)$ | One yes/no trial | $p$ | $p(1-p)$ | 08 |
| $\text{Binomial}(n,p)$ | Successes in $n$ independent trials | $np$ | $np(1-p)$ | 08 |
| $U(a,b)$ | Equal density across an interval | $\dfrac{a+b}{2}$ | $\dfrac{(b-a)^2}{12}$ | 09 |
| $N(\mu,\sigma^2)$ | A symmetric bell | $\mu$ | $\sigma^2$ | 10 |
| $\chi^2(k)$ | Sum of $k$ squared standard normals | $k$ | $2k$ | 14 |

**Bernoulli.** A single trial with two outcomes. Success has probability $p$. *(08)*

**Binomial.** Counts successes across $n$ trials that are **fixed in number, independent, and share the same $p$**. PMF: *(08)*

$$
P(X=x)=\binom{n}{x}p^x(1-p)^{n-x}
$$

**Uniform.** Constant density $\dfrac{1}{b-a}$ between $a$ and $b$. Probability is the fraction of the interval you select. *(09)*

**Normal.** Symmetric, bell-shaped, defined entirely by $\mu$ and $\sigma$. Its integral has **no closed form**, which is why z-tables exist. *(10)*

**Standard normal.** The special case $Z\sim N(0,1)$. Its CDF is $\Phi(z)$. *(11)*

**Chi-square.** $W=\sum_{i=1}^{k}Z_i^2$ for independent standard normals. Never negative. *(14)*

**Degrees of freedom.** $k$ — how many independent squared normals were added. It sets the whole shape: the peak sits at $k-2$. *(14)*

---

## Techniques

**Standardization (z-score).** Converts any value into the number of standard deviations it sits from the mean: *(11)*

$$
z=\frac{x-\mu}{\sigma}
\qquad\text{and back:}\qquad
x=\mu+z\sigma
$$

Always produces mean 0 and standard deviation 1. It **does not** change the shape, so it cannot make skewed data normal.

**Empirical rule (68-95-99.7).** For a normal distribution, roughly 68, 95 and 99.7 percent of values lie within 1, 2 and 3 standard deviations of the mean. These are the $z=\pm1,\pm2,\pm3$ tiers. For **exactly** 95 percent, use $1.96$. *(10, 11)*

**Normal approximation to the binomial.** Valid when $np\geq10$ and $n(1-p)\geq10$. Use $N\!\left(np,\ np(1-p)\right)$. *(12)*

**Continuity correction.** A discrete bar is one unit wide, so shift each boundary by $0.5$ before using a continuous curve. Expand by $0.5$ to **include** a value, shrink by $0.5$ to **exclude** it. *(12)*

**Naive assumption.** Treat features as **conditionally independent given the class**, turning one impossible joint probability into many easy individual ones. Usually false, but it rarely changes which class wins. *(13)*

**Laplace smoothing.** Add $\alpha$ to every count so no probability is ever exactly zero: $\dfrac{\text{count}+\alpha}{\text{total}+\alpha k}$. Without it, one unseen feature zeroes an entire class score. *(13)*

**Log probabilities.** Multiplying hundreds of small numbers underflows to zero, so work with $\log P$ and add instead. $\log$ is monotonic, so the winner never changes. Requires smoothing first, since $\log 0=-\infty$. *(13)*

**Min-max normalization.** A different rescaling: $x'=\dfrac{x-\min}{\max-\min}$, which forces every value into $[0,1]$. Standardization fixes the **mean and spread**; min-max fixes the **range**. Both get called "normalization," so check which is meant. *(11)*

---

# The distinctions most often confused

| These look alike | But | File |
|---|---|---|
| Independent vs disjoint | Disjoint events are always **dependent** | 02 |
| $P(A\mid B)$ vs $P(B\mid A)$ | Different questions, different answers | 03 |
| $P(A\cap B)$ vs $P(A\mid B)$ | The first is against all outcomes, the second only against B | 03 |
| Sensitivity vs precision | One conditions on truth, the other on the prediction | 05 |
| PMF vs PDF | Mass at a point vs density over an interval | 06 |
| Density vs probability | A density may exceed 1 | 06, 09 |
| $\sigma$ vs $\sigma^2$ | Original units vs squared units | 07 |
| $E[X^2]$ vs $(E[X])^2$ | The gap between them **is** the variance | 07 |
| $X$ vs $x$ | The rule vs one of its values | 06 |
| $N(\mu,\sigma^2)$ vs $N(\mu,\sigma)$ | Check whether the second argument is variance or SD | 10 |
| Conditional vs ordinary independence | Neither one implies the other | 02, 13 |

---

# Ten formulas to know cold

$$
P(A^c)=1-P(A)
$$

$$
P(A\cup B)=P(A)+P(B)-P(A\cap B)
$$

$$
P(A\mid B)=\frac{P(A\cap B)}{P(B)}
$$

$$
P(A\cap B)=P(A)P(B\mid A)
$$

$$
P(B)=\sum_i P(A_i)P(B\mid A_i)
$$

$$
P(A\mid B)=\frac{P(A)P(B\mid A)}{P(B)}
$$

$$
P(X=x)=\binom{n}{x}p^x(1-p)^{n-x}
$$

$$
E[X]=\sum_x x\,p_X(x)
\qquad
\text{Var}(X)=E[X^2]-\left(E[X]\right)^2
$$

$$
z=\frac{x-\mu}{\sigma}
$$

$$
F_X(x)=P(X\leq x)
\qquad
f_X(x)=F_X'(x)
$$
