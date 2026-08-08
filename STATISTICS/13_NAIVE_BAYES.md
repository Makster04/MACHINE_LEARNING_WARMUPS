# What You Should Know About Naive Bayes

> **Prerequisites:** Bayes' theorem, priors, likelihoods, and posteriors are in 04. Conditional independence is introduced in 02. Precision and recall are in 05.
>
> This is the only **algorithm** in these notes. Everything before it was probability theory; this is what you build with it.

These notes cover:

1. How Bayes' theorem works when there are multiple pieces of evidence
2. Why calculating the joint probability of many features becomes impossible
3. What the **naive assumption** actually claims
4. How that assumption simplifies the calculation
5. How to compute a Naive Bayes posterior
6. The three practical problems — decisions, zeros, and underflow — and their fixes

The running example is **spam-email classification**: deciding whether an email is spam based on words such as **"lottery"** and **"winning."**

---

# 1. Naive Bayes starts with Bayes' theorem

Suppose we want:

$$
P(\text{spam}\mid\text{lottery})
$$

meaning:

> What is the probability that an email is spam, **given that it contains the word "lottery"?**

From 04, the structure is:

$$
\boxed{\text{Posterior} = \frac{\text{Prior}\times\text{Likelihood}}{\text{Evidence}}}
$$

Mapped onto spam classification:

| Bayes term | Here it means |
|---|---|
| **Prior** $P(\text{spam})$ | How common spam is before looking at any words |
| **Likelihood** $P(\text{word}\mid\text{spam})$ | How often that word shows up in spam |
| **Evidence** $P(\text{word})$ | How often that word shows up at all |
| **Posterior** $P(\text{spam}\mid\text{word})$ | Updated probability after seeing the word |

Nothing here is new. Naive Bayes is what happens when you try to apply this to **many words at once**.

Throughout, **ham** means **not spam**.

---

# 2. With two features, we want the probability given both

Instead of only $P(\text{spam}\mid\text{lottery})$ or $P(\text{spam}\mid\text{winning})$, we want:

$$
\boxed{P(\text{spam}\mid\text{lottery}\cap\text{winning})}
$$

In words:

> What is the probability that the email is spam given that it contains **both "lottery" and "winning"?**

Writing out ordinary Bayes with the expanded denominator from 04:

$$
P(\text{spam}\mid\text{lottery}\cap\text{winning}) = \frac{P(\text{spam})\, P(\text{lottery}\cap\text{winning}\mid\text{spam})}{P(\text{spam})\, P(\text{lottery}\cap\text{winning}\mid\text{spam}) + P(\text{ham})\, P(\text{lottery}\cap\text{winning}\mid\text{ham})}
$$

This is exact. No approximation has been made yet.

---

# 3. The problem: joint probabilities of many features

The difficult term is:

$$
P(\text{lottery}\cap\text{winning}\mid\text{spam})
$$

meaning:

> Among spam emails, how often do **both words occur together?**

For two words you could count this directly. But a real email contains many words, and then you would need:

$$
P(w_1, w_2, \ldots, w_{100}\mid\text{spam})
$$

## Why this cannot be estimated

To measure that directly you would need training emails containing **that exact combination** of all 100 words. There will almost certainly be **zero** such emails — the specific combination has probably never occurred in human history.

The number of possible combinations explodes. With 100 binary features there are $2^{100}$ possible patterns, which is vastly more than any dataset could ever cover.

$$
\boxed{\text{Many features} \rightarrow \text{joint probabilities become impossible to estimate}}
$$

---

# 4. The naive assumption

Naive Bayes cuts through this by assuming that, **within a given class**, the features are independent of one another.

Recall the product rule from 02: for independent events,

$$
P(A\cap B) = P(A)\,P(B)
$$

Applied *inside* the spam class:

$$
\boxed{P(\text{lottery}\cap\text{winning}\mid\text{spam}) \approx P(\text{lottery}\mid\text{spam})\, P(\text{winning}\mid\text{spam})}
$$

Likewise for ham:

$$
\boxed{P(\text{lottery}\cap\text{winning}\mid\text{ham}) \approx P(\text{lottery}\mid\text{ham})\, P(\text{winning}\mid\text{ham})}
$$

## What this buys you

One impossible quantity is replaced by several easy ones:

$$
\boxed{\text{One complicated joint probability} \rightarrow \text{many simple individual probabilities}}
$$

Instead of hunting for emails containing an exact 100-word combination, you count each word separately. Every one of those counts is easy to obtain.

$$
\boxed{\text{Naive assumption} = \text{treat the features as independent within each class}}
$$

---

# 5. Conditional independence is not ordinary independence

This is the sharpest idea in the file, and it is what "naive" actually refers to.

The assumption is **conditional** independence, written:

$$
\boxed{P(A\cap B\mid C) = P(A\mid C)\, P(B\mid C)}
$$

This is a claim about what happens **once the class is known**. It is *not* the claim that:

$$
P(A\cap B) = P(A)\, P(B)
$$

As 02 warns, conditional independence does not imply independence, and independence does not imply conditional independence. They are separate statements.

## Seeing the difference in the actual data

Using the counts from section 10 — 100 emails, with "lottery" in 24 of them and "winning" in 23:

$$
P(\text{lottery}) = \frac{24}{100} = 0.24 \qquad P(\text{winning}) = \frac{23}{100} = 0.23
$$

If the two words were genuinely independent overall, they would co-occur with probability:

$$
P(\text{lottery})\,P(\text{winning}) = 0.24(0.23) = 0.0552
$$

But the model's own estimate of how often they co-occur is $0.115$ — about **twice** as often as independence would predict.

$$
\boxed{\text{The two words are strongly DEPENDENT overall, yet treated as independent within each class}}
$$

The dependence is real: both words are common in spam and rare in ham, so seeing one makes the other more likely. But once you have already *conditioned on the class*, that shared cause has been accounted for, and the leftover dependence is smaller.

That is the whole intuition. The class is the reason the words travel together. Fix the class, and much of the connection disappears — though not all of it, which is why the assumption is naive rather than true.

---

# 6. The two-feature Naive Bayes formula

Substituting the naive assumption into the exact Bayes expression from section 2:

$$
\boxed{P(\text{spam}\mid\text{lottery}\cap\text{winning}) = \frac{P(\text{spam})\, P(\text{lottery}\mid\text{spam})\, P(\text{winning}\mid\text{spam})}{P(\text{spam})\, P(\text{lottery}\mid\text{spam})\, P(\text{winning}\mid\text{spam}) + P(\text{ham})\, P(\text{lottery}\mid\text{ham})\, P(\text{winning}\mid\text{ham})}}
$$

This is the central equation. Every joint term has become a product of separate terms.

---

# 7. What each part of the formula means

Consider the numerator:

$$
P(\text{spam})\, P(\text{lottery}\mid\text{spam})\, P(\text{winning}\mid\text{spam})
$$

### $P(\text{spam})$

The probability that an email is spam **before looking at the words**. This is the **prior**, or in machine-learning terms the **class prior** — the same quantity called a base rate in 05.

### $P(\text{lottery}\mid\text{spam})$

The probability that the word **lottery** appears, given that the email is spam. This is a **likelihood**.

### $P(\text{winning}\mid\text{spam})$

The probability that the word **winning** appears, given that the email is spam.

### $P(\text{spam}\mid\text{lottery}\cap\text{winning})$

The updated probability that the email is spam after observing both words. This is the **posterior**.

---

# 8. The denominator compares spam against ham

The denominator contains the spam term:

$$
P(\text{spam})\, P(\text{lottery}\mid\text{spam})\, P(\text{winning}\mid\text{spam})
$$

plus the ham term:

$$
P(\text{ham})\, P(\text{lottery}\mid\text{ham})\, P(\text{winning}\mid\text{ham})
$$

So the model considers how well the evidence fits **both** possibilities, and the denominator adds them together. This is the Law of Total Probability from 03, applied over the two classes, and it is what makes the posterior a proper probability between 0 and 1.

---

# 9. Extending to many features

Suppose an email contains $w_1, w_2, \ldots, w_n$. The naive assumption treats those word appearances as independent within each class:

$$
\boxed{P(w_1,\ldots,w_n\mid\text{spam}) \approx P(w_1\mid\text{spam})\, P(w_2\mid\text{spam})\cdots P(w_n\mid\text{spam})}
$$

and the same for ham. The full formula becomes:

$$
\boxed{P(\text{spam}\mid w_1,\ldots,w_n) = \frac{P(\text{spam})\prod_{i=1}^{n} P(w_i\mid\text{spam})}{P(\text{spam})\prod_{i=1}^{n} P(w_i\mid\text{spam}) + P(\text{ham})\prod_{i=1}^{n} P(w_i\mid\text{ham})}}
$$

The overall pattern for each class is always:

$$
\boxed{\text{Prior}\times\text{feature 1 probability}\times\text{feature 2 probability}\times\cdots}
$$

Notice that this scales effortlessly. Going from 2 features to 10,000 adds more multiplications but nothing conceptually harder — which is exactly why Naive Bayes handles text so well.

---

# 10. Spam example: the priors

Take $100$ total emails, of which $20$ are spam and $80$ are ham. Therefore:

$$
P(\text{spam}) = \frac{20}{100} = 0.2
\qquad
P(\text{ham}) = \frac{80}{100} = 0.8
$$

$$
\boxed{P(\text{spam}) = 0.2 \qquad P(\text{ham}) = 0.8}
$$

---

# 11. Spam example: the feature probabilities

Among the $20$ spam emails, $14$ contain **lottery**. Among the $80$ ham emails, $10$ contain **lottery**:

$$
P(\text{lottery}\mid\text{spam}) = \frac{14}{20} = 0.7
\qquad
P(\text{lottery}\mid\text{ham}) = \frac{10}{80} = 0.125
$$

Among the $20$ spam emails, $15$ contain **winning**. Among the $80$ ham emails, $8$ contain **winning**:

$$
P(\text{winning}\mid\text{spam}) = \frac{15}{20} = 0.75
\qquad
P(\text{winning}\mid\text{ham}) = \frac{8}{80} = 0.1
$$

Note that each denominator is the **class size**, not the total. These are conditional probabilities, so the sample space has already been restricted to one class, exactly as 03 describes.

---

# 12. Spam example: the calculation

Collecting everything:

| Quantity | Value |
|---|---|
| $P(\text{spam})$ | $0.2$ |
| $P(\text{ham})$ | $0.8$ |
| $P(\text{lottery}\mid\text{spam})$ | $0.7$ |
| $P(\text{lottery}\mid\text{ham})$ | $0.125$ |
| $P(\text{winning}\mid\text{spam})$ | $0.75$ |
| $P(\text{winning}\mid\text{ham})$ | $0.1$ |

Substituting into the two-feature formula:

$$
P(\text{spam}\mid\text{lottery}\cap\text{winning}) = \frac{0.2(0.7)(0.75)}{0.2(0.7)(0.75) + 0.8(0.125)(0.1)}
$$

**Spam side:**

$$
0.2 \times 0.7 \times 0.75 = 0.105
$$

**Ham side:**

$$
0.8 \times 0.125 \times 0.1 = 0.01
$$

**Denominator:**

$$
0.105 + 0.01 = 0.115
$$

**Divide:**

$$
P(\text{spam}\mid\text{lottery}\cap\text{winning}) = \frac{0.105}{0.115} \approx 0.913
$$

$$
\boxed{P(\text{spam}\mid\text{lottery}\cap\text{winning}) \approx 91.3\%}
$$

As a check, the ham posterior is $\frac{0.01}{0.115}\approx0.087$, and the two sum to exactly 1 as any posterior pair must.

---

# 13. What the result means

> Given the Naive Bayes assumptions and the probabilities in this example, an email containing **"lottery" and "winning"** has roughly a **91.3 percent posterior probability of being spam**.

Notice the movement. The prior probability of spam was only **20 percent**, and after seeing those two words it became about **91.3 percent**. That is Bayes' theorem updating a belief on the strength of evidence, exactly as in 04.

$$
\boxed{20\% \xrightarrow{\text{two words}} 91.3\%}
$$

---

# 14. From posterior to prediction: the decision rule

A posterior is a probability, not a decision. To actually classify the email you need a **threshold**:

$$
\boxed{\text{Predict spam if } P(\text{spam}\mid\text{features}) > t}
$$

The default is $t=0.5$. Since $0.913 > 0.5$, this email is classified as **spam**.

## Choosing the threshold

From 05, the threshold trades precision against recall:

| Threshold | Effect |
|---|---|
| Lower $t$ | Catches more spam (higher recall), junks more real email (lower precision) |
| Higher $t$ | Fewer real emails lost (higher precision), more spam gets through (lower recall) |

For spam filtering, a **false positive is worse than a false negative** — a missed spam is an annoyance, but a real email lost to the junk folder can be serious. So production spam filters typically use a threshold well above 0.5.

## The shortcut: skip the denominator

From 04, the denominator is the same for every class, so it cannot change which class wins. For **classification only**, compare the numerators directly:

$$
\text{spam score} = 0.105 \qquad \text{ham score} = 0.01
$$

Since $0.105 > 0.01$, predict spam — no division needed. Formally:

$$
\boxed{\hat{y} = \arg\max_{c} \; P(c)\prod_{i=1}^{n} P(w_i\mid c)}
$$

Compute the full posterior only when you actually need a probability. If you just need a label, the numerators are enough.

---

# 15. The zero-probability problem and Laplace smoothing

Here is a failure that will bite you immediately in practice.

Suppose an email contains the word **"crypto"**, and no spam email in the training data ever contained it. Then:

$$
P(\text{crypto}\mid\text{spam}) = \frac{0}{20} = 0
$$

Now look at what happens to the product:

$$
P(\text{spam})\times P(\text{lottery}\mid\text{spam})\times P(\text{winning}\mid\text{spam})\times \underbrace{0}_{\text{crypto}}\times\cdots = 0
$$

$$
\boxed{\text{A single unseen word makes the entire class probability exactly zero}}
$$

The email could contain fifty other overwhelming spam indicators and it would not matter. One zero vetoes all other evidence. This is a direct consequence of multiplying — anything times zero is zero.

## The fix: Laplace smoothing

Add a small constant to every count so nothing is ever exactly zero:

$$
\boxed{P(w\mid c) = \frac{\text{count}(w, c) + \alpha}{\text{count}(c) + \alpha k}}
$$

where $k$ is the number of possible values for the feature and $\alpha$ is the smoothing constant. Setting $\alpha = 1$ is **Laplace smoothing**, also called add-one smoothing. Values of $\alpha < 1$ are called **Lidstone smoothing**.

## Applied to the example

For present/absent features, $k=2$. With $\alpha=1$:

| Word | Raw estimate | Smoothed |
|---|---|---|
| lottery in spam | $\dfrac{14}{20}=0.700$ | $\dfrac{14+1}{20+2}=\dfrac{15}{22}\approx0.682$ |
| winning in spam | $\dfrac{15}{20}=0.750$ | $\dfrac{15+1}{20+2}=\dfrac{16}{22}\approx0.727$ |
| **crypto in spam** | $\dfrac{0}{20}=\mathbf{0}$ | $\dfrac{0+1}{20+2}=\dfrac{1}{22}\approx\mathbf{0.045}$ |

The unseen word now contributes a small probability instead of a fatal zero. The other estimates barely move — smoothing pulls everything gently toward uniform, and the effect shrinks as the counts grow.

In scikit-learn this is the `alpha` parameter, and it defaults to $1.0$. Smoothing is on by default because the problem is so common.

---

# 16. Underflow and log probabilities

A second practical failure appears once you have many features.

Multiplying hundreds of numbers, each less than 1, produces an extremely small result:

| Product | Value | Status |
|---|---|---|
| $0.01^{100}$ | $10^{-200}$ | Representable |
| $0.01^{150}$ | $10^{-300}$ | Barely representable |
| $0.01^{200}$ | $10^{-400}$ | **Underflows to exactly 0** |

Standard double-precision floating point cannot hold values below about $10^{-308}$. So on a long document, both class scores collapse to zero and the comparison becomes meaningless.

## The fix: work in logs

Because $\log$ is **monotonically increasing**, it preserves ordering. Whichever score is larger stays larger after taking logs, so the $\arg\max$ is unchanged. And logarithms turn products into sums:

$$
\boxed{\log\!\left(P(c)\prod_{i} P(w_i\mid c)\right) = \log P(c) + \sum_{i} \log P(w_i\mid c)}
$$

So in practice every implementation computes:

$$
\boxed{\hat{y} = \arg\max_{c}\left[\log P(c) + \sum_{i=1}^{n} \log P(w_i\mid c)\right]}
$$

Adding a few hundred numbers around $-5$ each gives roughly $-500$, which is perfectly representable.

## Applied to the example

$$
\log(\text{spam score}) = \log 0.2 + \log 0.7 + \log 0.75 \approx -2.25
$$

$$
\log(\text{ham score}) = \log 0.8 + \log 0.125 + \log 0.1 \approx -4.61
$$

Since $-2.25 > -4.61$, predict spam — the same conclusion as $0.105 > 0.01$. The log scores are negative and are not probabilities, but you only ever need to compare them.

## Why smoothing must come first

$$
\boxed{\log(0) = -\infty}
$$

An unsmoothed zero does not merely produce a bad answer in log space; it produces negative infinity and breaks the arithmetic entirely. **Sections 15 and 16 are a package** — you cannot safely take logs without smoothing first.

---

# 17. The three Naive Bayes variants

"Naive Bayes" is a family, not a single algorithm. The naive assumption is always the same; what changes is how each feature probability $P(w_i\mid c)$ is modelled.

| Variant | Feature type | Models each feature as | Typical use |
|---|---|---|---|
| **Bernoulli NB** | Binary | Word present or absent | Short texts; **this file's example** |
| **Multinomial NB** | Counts | How many times a word appears | Standard for text classification |
| **Gaussian NB** | Continuous | A normal distribution per class | Numeric features |

## Gaussian Naive Bayes

For continuous features you cannot count occurrences, so instead you estimate a mean and standard deviation for **each feature within each class** from the training data, then use the normal PDF from 10:

$$
P(x_i\mid c) = \frac{1}{\sigma_{i,c}\sqrt{2\pi}}\, e^{-\frac{1}{2}\left(\frac{x_i-\mu_{i,c}}{\sigma_{i,c}}\right)^2}
$$

This is where files 07 and 10 are cashed in: $\mu$ and $\sigma$ are computed per feature per class, and the normal density supplies the likelihood.

The worked example in this file uses **Bernoulli NB**, since we only asked whether each word was present, not how often.

---

# 18. Why the naive assumption works anyway

Section 5 demonstrated that the assumption is **false** in this very dataset — the two words co-occur about twice as often as independence predicts. So why is Naive Bayes still a useful classifier?

## Classification needs the ranking, not the number

To predict a label you only need to know **which class scores highest**. You do not need the posterior to be numerically correct.

Correlated features effectively count the same evidence twice. Since "lottery" and "winning" both point at spam and travel together, the model treats them as two independent pieces of evidence when they are closer to one and a half. That inflates the winning score — but it inflates it in a direction that was already correct, so the ranking usually survives.

## The honest caveat

$$
\boxed{\text{Naive Bayes is a good classifier but a poorly calibrated probability estimator}}
$$

Double-counted evidence pushes posteriors toward the extremes, so Naive Bayes tends to report values very close to 0 or 1. The $91.3\%$ figure is best read as **"confidently spam"** rather than as a literal 91.3 percent chance. If you need trustworthy probabilities rather than labels, the outputs need to be recalibrated.

## What you get in exchange

- Trains in a single pass over the data
- Handles tens of thousands of features without difficulty
- Works well even on small training sets
- Fast enough to run on every incoming email

$$
\boxed{\text{A false assumption that makes the problem tractable and usually preserves the answer}}
$$

---

# Most Important Definitions and Distinctions to Remember

## Prior

The probability of a class before considering the features. Example: $P(\text{spam}) = 0.2$. Also called the **class prior**.

## Likelihood

A conditional probability such as $P(\text{lottery}\mid\text{spam})$:

> Probability that **lottery appears**, given that the email is spam.

## Posterior

The updated probability after observing the evidence: $P(\text{spam}\mid\text{lottery}\cap\text{winning})$.

## The naive assumption

Features are treated as independent **within each class**:

$$
\boxed{P(A\cap B\mid C) = P(A\mid C)\, P(B\mid C)}
$$

This is **conditional** independence, which is not the same as ordinary independence.

## Naive Bayes

$$
\boxed{\text{Naive Bayes} = \text{Bayes' theorem} + \text{conditional independence of the features}}
$$

## The three practical fixes

| Problem | Fix |
|---|---|
| A posterior is not a decision | Threshold, default $0.5$ |
| An unseen feature zeroes the product | Laplace smoothing, $\alpha=1$ |
| Long products underflow to zero | Work with logs |

---

# Main Rules to Put in Your Notebook

$$
\boxed{\text{Posterior} = \frac{\text{Prior}\times\text{Likelihood}}{\text{Evidence}}}
$$

$$
\boxed{\text{Naive Bayes} = \text{Bayes} + \text{conditional independence}}
$$

For many features:

$$
\boxed{P(w_1,\ldots,w_n\mid c) \approx \prod_{i=1}^{n} P(w_i\mid c)}
$$

Full posterior:

$$
\boxed{P(c\mid w_1,\ldots,w_n) = \frac{P(c)\prod_i P(w_i\mid c)}{\sum_{c'} P(c')\prod_i P(w_i\mid c')}}
$$

For classification only:

$$
\boxed{\hat{y} = \arg\max_{c}\left[\log P(c) + \sum_i \log P(w_i\mid c)\right]}
$$

Laplace smoothing:

$$
\boxed{P(w\mid c) = \frac{\text{count}(w,c)+\alpha}{\text{count}(c)+\alpha k}}
$$

For the worked example:

| Quantity | Value |
|---|---|
| $P(\text{spam})$ | $0.2$ |
| $P(\text{ham})$ | $0.8$ |
| $P(\text{lottery}\mid\text{spam})$ | $0.7$ |
| $P(\text{lottery}\mid\text{ham})$ | $0.125$ |
| $P(\text{winning}\mid\text{spam})$ | $0.75$ |
| $P(\text{winning}\mid\text{ham})$ | $0.1$ |
| Spam score | $0.105$ |
| Ham score | $0.01$ |
| $P(\text{spam}\mid\text{lottery}\cap\text{winning})$ | $\approx 0.913$ |

The **biggest idea** is:

$$
\boxed{\text{Naive Bayes computes a posterior using Bayes' theorem while treating the features as independent within each class.}}
$$

So in plain English: **start with how common each class is, look at how common each observed feature is within each class, multiply those feature probabilities under the naive assumption, and use Bayes' theorem to update the probability of the class. The assumption is usually false, but it turns an impossible calculation into an easy one and rarely changes which class wins.**

---

# Where This Came From

| Idea | Source file |
|---|---|
| Prior, likelihood, posterior | **04 — Bayes' Theorem** |
| $P(A\mid B)\propto P(A)P(B\mid A)$, skipping the denominator | **04** |
| Summing over classes in the denominator | **03 — Law of Total Probability** |
| $P(A\cap B)=P(A)P(B)$ for independent events | **02 — Independence** |
| Conditional independence | **02** |
| Class prior as a base rate | **05 — Test Accuracy and Base Rates** |
| Precision, recall, thresholds | **05** |
| Normal PDF for Gaussian NB | **10 — Normal Distribution** |
| $\mu$ and $\sigma$ per feature per class | **07 — Expectation and Variance** |
