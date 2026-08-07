# What You Should Know About Naive Bayes

These slides are mainly teaching **six important ideas**:

1. How Bayes' theorem works when there are multiple pieces of evidence
2. Why calculating the joint probability of many features can become difficult
3. What the **naive assumption** is
4. How that assumption simplifies the calculation
5. How Naive Bayes works with many features
6. How to calculate a Naive Bayes posterior probability

The slides use **spam-email classification** throughout: deciding whether an email is spam based on words such as **"lottery"** and **"winning."**

---

# 1. Naive Bayes starts with Bayes' theorem

Suppose we want to determine:

$$
P(\text{spam}\mid\text{lottery})
$$

This means:

> What is the probability that an email is spam, **given that it contains the word "lottery"?**

The basic Bayes idea is:

$$
\boxed{\ \text{Posterior} = \frac{\text{Prior}\times\text{Likelihood}}{\text{Evidence}}\ }
$$

For spam classification:

* **Prior** = how common spam is before seeing the words
* **Evidence / features** = words contained in the email
* **Posterior** = updated probability that the email is spam

The first slide extends this idea from one word to an email containing both **"lottery" and "winning."**

---

# 2. With two features, we want the probability of spam given both

Instead of only $P(\text{spam}\mid\text{lottery})$ or $P(\text{spam}\mid\text{winning})$, we may want:

$$
\boxed{\ P(\text{spam}\mid\text{lottery}\cap\text{winning})\ }
$$

In words:

> What is the probability that the email is spam given that it contains **both "lottery" and "winning"?**

The ordinary Bayes expression shown in the slides is:

$$
P(\text{spam}\mid\text{lottery}\cap\text{winning}) = \frac{P(\text{spam})\,P(\text{lottery}\cap\text{winning}\mid\text{spam})}{P(\text{spam})\,P(\text{lottery}\cap\text{winning}\mid\text{spam}) + P(\text{ham})\,P(\text{lottery}\cap\text{winning}\mid\text{ham})}
$$

where **ham** means **not spam**.

---

# 3. The difficult part is the joint probability of the features

The challenging term is:

$$
P(\text{lottery}\cap\text{winning}\mid\text{spam})
$$

This means:

> Among spam emails, how often do **both words occur together?**

For two words, you might be able to estimate this directly. But when an email contains many words $w_1, w_2, \ldots, w_{100}$, you would need something like:

$$
P(w_1, w_2, \ldots, w_{100}\mid\text{spam})
$$

The slides show why this becomes a problem: there may be **zero training emails containing that exact combination of all the words**, making the direct joint estimate difficult or impossible.

So the problem is:

$$
\boxed{\ \text{Many features}\rightarrow\text{joint probabilities become difficult to estimate}\ }
$$

---

# 4. Naive Bayes makes the "naive assumption"

The quicker approach used in the slides is the **naive assumption**: within a given class, the features are treated as independent of one another. This is called **conditional independence**, because the independence is assumed *given the class*.

The basic independence rule is:

$$
\boxed{\ P(A\cap B) = P(A)\,P(B)\quad\text{when }A\text{ and }B\text{ are independent}\ }
$$

Applied *inside* the spam class, this gives:

$$
\boxed{\
P(\text{lottery}\cap\text{winning}\mid\text{spam}) \approx P(\text{lottery}\mid\text{spam})\,P(\text{winning}\mid\text{spam})
\ }
$$

Likewise for ham:

$$
\boxed{\
P(\text{lottery}\cap\text{winning}\mid\text{ham}) \approx P(\text{lottery}\mid\text{ham})\,P(\text{winning}\mid\text{ham})
\ }
$$

This is the key simplification shown on pages 2 and 4.

---

# 5. Why is it called "Naive" Bayes?

The **naive** part is the assumption that the features can be treated independently within each class. It is called naive because it is usually not literally true — words like "lottery" and "winning" really do tend to appear together — but the approximation still works well in practice.

For example, instead of worrying about how frequently "lottery" **and** "winning" appear together, Naive Bayes estimates them separately and multiplies:

$$
P(\text{lottery}\mid\text{spam}) \times P(\text{winning}\mid\text{spam})
$$

Therefore:

$$
\boxed{\ \text{Naive assumption} = \text{treat the features as independent within each class}\ }
$$

---

# 6. Two-feature Naive Bayes formula

Using the naive assumption, the slides rewrite the spam calculation as:

$$
\boxed{\ P(\text{spam}\mid\text{lottery}\cap\text{winning}) = \frac{P(\text{spam})\,P(\text{lottery}\mid\text{spam})\,P(\text{winning}\mid\text{spam})}{P(\text{spam})\,P(\text{lottery}\mid\text{spam})\,P(\text{winning}\mid\text{spam}) + P(\text{ham})\,P(\text{lottery}\mid\text{ham})\,P(\text{winning}\mid\text{ham})}\ }
$$

This is the central equation in the slides.

---

# 7. What each part of the formula means

Consider the numerator:

$$
P(\text{spam})\,P(\text{lottery}\mid\text{spam})\,P(\text{winning}\mid\text{spam})
$$

### $P(\text{spam})$

The probability that an email is spam **before looking at the words**. This is the **prior**.

### $P(\text{lottery}\mid\text{spam})$

The probability that the word **lottery** appears, given that the email is spam.

### $P(\text{winning}\mid\text{spam})$

The probability that the word **winning** appears, given that the email is spam.

These are the feature probabilities used to evaluate how compatible the observed words are with the spam class.

### $P(\text{spam}\mid\text{lottery}\cap\text{winning})$

The updated probability that the email is spam after observing both words. This is the **posterior**.

---

# 8. The denominator compares spam against ham

The denominator contains the spam term:

$$
P(\text{spam})\,P(\text{lottery}\mid\text{spam})\,P(\text{winning}\mid\text{spam})
$$

plus the ham term:

$$
P(\text{ham})\,P(\text{lottery}\mid\text{ham})\,P(\text{winning}\mid\text{ham})
$$

So the model considers how well the evidence fits **both possibilities**, spam and ham, and the denominator adds these two together. This is what makes the posterior a proper probability between 0 and 1.

---

# 9. The same idea extends to many features

Suppose an email contains $w_1, w_2, \ldots, w_n$. The naive assumption treats those word appearances as independent within each class.

Instead of estimating $P(w_1, w_2, \ldots, w_n\mid\text{spam})$ directly, use:

$$
\boxed{\
P(w_1\mid\text{spam})\,P(w_2\mid\text{spam})\cdots P(w_n\mid\text{spam})
\ }
$$

The same is done for ham:

$$
P(w_1\mid\text{ham})\,P(w_2\mid\text{ham})\cdots P(w_n\mid\text{ham})
$$

---

# 10. General Naive Bayes form from the slides

For many words:

$$
\boxed{\ P(\text{spam}\mid w_1,\ldots,w_n) = \frac{P(\text{spam})\,P(w_1\mid\text{spam})\cdots P(w_n\mid\text{spam})}{P(\text{spam})\,P(w_1\mid\text{spam})\cdots P(w_n\mid\text{spam}) + P(\text{ham})\,P(w_1\mid\text{ham})\cdots P(w_n\mid\text{ham})}\ }
$$

So the overall pattern is:

$$
\boxed{\ \text{Prior}\times\text{feature 1 probability}\times\text{feature 2 probability}\times\cdots\ }
$$

for each possible class.

---

# 11. Spam example: calculate the prior probabilities

The slides use $100$ total emails: $20$ are spam and $80$ are ham. Therefore:

$$
P(\text{spam}) = \frac{20}{100} = 0.2
\qquad
P(\text{ham}) = \frac{80}{100} = 0.8
$$

So:

$$
\boxed{\ P(\text{spam}) = 0.2 \qquad P(\text{ham}) = 0.8\ }
$$

---

# 12. Calculate the probability of "lottery"

Among the $20$ spam emails, $14$ contain **lottery**. Among the $80$ ham emails, $10$ contain **lottery**. Therefore:

$$
P(\text{lottery}\mid\text{spam}) = \frac{14}{20} = 0.7
\qquad
P(\text{lottery}\mid\text{ham}) = \frac{10}{80} = 0.125
$$

So:

$$
\boxed{\ P(\text{lottery}\mid\text{spam}) = 0.7 \qquad P(\text{lottery}\mid\text{ham}) = 0.125\ }
$$

---

# 13. Calculate the probability of "winning"

Among the $20$ spam emails, $15$ contain **winning**. Among the $80$ ham emails, $8$ contain **winning**. Therefore:

$$
P(\text{winning}\mid\text{spam}) = \frac{15}{20} = 0.75
\qquad
P(\text{winning}\mid\text{ham}) = \frac{8}{80} = 0.1
$$

So:

$$
\boxed{\ P(\text{winning}\mid\text{spam}) = 0.75 \qquad P(\text{winning}\mid\text{ham}) = 0.1\ }
$$

---

# 14. Put all the probabilities into Naive Bayes

We now have:

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

---

# 15. Calculate the spam side

$$
0.2 \times 0.7 \times 0.75 = 0.105
$$

So the spam side contributes $\boxed{0.105}$.

---

# 16. Calculate the ham side

$$
0.8 \times 0.125 \times 0.1 = 0.01
$$

So the ham side contributes $\boxed{0.01}$.

---

# 17. Add both possibilities in the denominator

$$
0.105 + 0.01 = 0.115
$$

Therefore:

$$
P(\text{spam}\mid\text{lottery}\cap\text{winning}) = \frac{0.105}{0.115} \approx 0.913
$$

So the probability is approximately:

$$
\boxed{\ 91.3\%\ }
$$

---

# 18. What the final result means

The result means:

> Given the Naive Bayes assumptions and the probabilities in this example, an email containing **"lottery" and "winning"** has roughly a **91.3% posterior probability of being spam**.

Notice how the prior probability of spam was only $20\%$, but after seeing those two words it becomes about $91.3\%$. That is Bayes' theorem updating the probability based on the observed evidence.

---

# 19. Bayes' theorem versus Naive Bayes

These should not be confused.

## Bayes' theorem

Bayes' theorem provides the general rule for updating probability using evidence:

$$
\boxed{\ \text{Posterior} = \frac{\text{Prior}\times\text{Likelihood}}{\text{Evidence}}\ }
$$

It is exact — no extra assumptions required.

## Naive Bayes

Naive Bayes uses Bayes' theorem **plus the naive independence assumption** to handle multiple features:

$$
\boxed{\ \text{Naive Bayes} = \text{Bayes' theorem} + \text{naive feature-independence assumption}\ }
$$

This distinction is the central development across pages 1–4 of the slides.

---

# 20. Why the naive assumption is useful

Without the assumption, we need probabilities such as $P(w_1, w_2, \ldots, w_{100}\mid\text{spam})$, and the slides show that the exact combination might not occur in the data at all.

With the naive assumption, we instead calculate:

$$
P(w_1\mid\text{spam})\,P(w_2\mid\text{spam})\cdots P(w_{100}\mid\text{spam})
$$

Therefore:

$$
\boxed{\ \text{One complicated joint probability}\rightarrow\text{many simpler individual probabilities}\ }
$$

That is the main reason the naive assumption simplifies the calculation.

---

# Most Important Definitions and Distinctions to Remember

## Prior

The **prior** is the probability of a class before considering the new features. Example: $P(\text{spam}) = 0.2$.

## Feature probability

A conditional probability such as $P(\text{lottery}\mid\text{spam})$, meaning:

> Probability that **lottery appears**, given that the email is spam.

## Posterior

The **posterior** is the updated probability after observing the evidence. Example: $P(\text{spam}\mid\text{lottery}\cap\text{winning})$.

## Naive assumption

The features are treated as independent **within each class**. For two features:

$$
\boxed{\
P(\text{lottery}\cap\text{winning}\mid\text{spam}) \approx P(\text{lottery}\mid\text{spam})\,P(\text{winning}\mid\text{spam})
\ }
$$

## Naive Bayes

Naive Bayes combines Bayes' theorem with the independence assumption to estimate a posterior using multiple features.

---

# Main Rules to Put in Your Notebook

$$
\boxed{\ \text{Posterior} = \frac{\text{Prior}\times\text{Likelihood}}{\text{Evidence}}\ }
$$

$$
\boxed{\ \text{Naive Bayes} = \text{Bayes} + \text{naive independence assumption}\ }
$$

$$
\boxed{\ P(A\cap B) = P(A)\,P(B)\quad\text{under the independence assumption}\ }
$$

For two spam features:

$$
\boxed{\
P(\text{lottery}\cap\text{winning}\mid\text{spam}) \approx P(\text{lottery}\mid\text{spam})\,P(\text{winning}\mid\text{spam})
\ }
$$

For many features:

$$
\boxed{\
P(w_1,\ldots,w_n\mid\text{spam}) \approx P(w_1\mid\text{spam})\cdots P(w_n\mid\text{spam})
\ }
$$

For the example:

| Quantity | Value |
|---|---|
| $P(\text{spam})$ | $0.2$ |
| $P(\text{ham})$ | $0.8$ |
| $P(\text{lottery}\mid\text{spam})$ | $0.7$ |
| $P(\text{lottery}\mid\text{ham})$ | $0.125$ |
| $P(\text{winning}\mid\text{spam})$ | $0.75$ |
| $P(\text{winning}\mid\text{ham})$ | $0.1$ |
| $P(\text{spam}\mid\text{lottery}\cap\text{winning})$ | $\approx 0.913$ |

The **biggest idea** to remember is:

$$
\boxed{\ \text{Naive Bayes calculates a posterior using Bayes' theorem while treating the features independently.}\ }
$$

So in plain English: **start with how common each class is, look at how common each observed feature is within each class, multiply those feature probabilities under the naive assumption, and use Bayes' theorem to update the probability of the class.**
