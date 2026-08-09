# Comprehensive Review Quiz — Files 01 through 14

> **30 questions, 1 point each.** Covers everything in the notes: probability rules, conditional probability and Bayes, random variables, expectation and variance, and the five distributions.
>
> Write your answers in the sheet at the bottom, then ask for the solutions. Each question has exactly one correct answer unless it says **select all that apply**.
>
> No calculator needed for most of them. Where a number is awkward, the options are far enough apart that an estimate will do.

---

# Part 1 — Probability rules

## Question 1

A standard 52-card deck contains 12 face cards. One card is drawn at random. What is the probability that it is **not** a face card?

- **A.** $\dfrac{3}{13}$
- **B.** $\dfrac{10}{13}$
- **C.** $\dfrac{1}{4}$
- **D.** $\dfrac{12}{52}$

## Question 2

You roll a fair six-sided die three times. What is the probability of getting **at least one** 6?

*Hint: what is the opposite of "at least one"?*

- **A.** $\dfrac{1}{2}$
- **B.** $\dfrac{3}{6}$
- **C.** $\dfrac{91}{216}$
- **D.** $\dfrac{125}{216}$

## Question 3

You flip a fair coin three times. What is the probability of getting **exactly two heads**, in any order?

- **A.** $\dfrac{1}{8}$
- **B.** $\dfrac{3}{8}$
- **C.** $\dfrac{1}{2}$
- **D.** $\dfrac{2}{3}$

## Question 4

For two events $A$ and $B$ with $P(A) = 0.6$ and $P(B) = 0.5$, which statement is true?

- **A.** $P(A\cup B) = 1.1$
- **B.** $P(A\cup B) = 0.30$ because the events are independent
- **C.** $P(A\cup B)$ cannot be determined without $P(A\cap B)$
- **D.** $P(A\cup B) = 0.8$

## Question 5

**Select all that apply.** Which of the following are true of two **disjoint** events $A$ and $B$, both with non-zero probability?

- **A.** $P(A\cap B) = 0$
- **B.** $A$ and $B$ are independent
- **C.** $A$ and $B$ are dependent
- **D.** $P(A\cup B) = P(A) + P(B)$
- **E.** Knowing that $A$ occurred tells you nothing about $B$

## Question 6

Rolling one die, let $A = \{2,4,6\}$ and $B = \{5\}$. Which describes these two events?

- **A.** They form a partition of the sample space
- **B.** They are disjoint but not exhaustive
- **C.** They are exhaustive but not disjoint
- **D.** They are independent

---

# Part 2 — Conditional probability and Bayes

## Question 7

In a school of 200 students: 60 take **only** chemistry, 80 take **only** physics, 40 take **both**, and 20 take neither.

A student is chosen at random from those taking chemistry. What is the probability they also take physics?

- **A.** $0.20$
- **B.** $0.40$
- **C.** $0.50$
- **D.** $0.67$

## Question 8

A factory buys parts from two suppliers. Supplier A provides 80 percent of parts, of which 5 percent are defective. Supplier B provides 20 percent, of which 20 percent are defective.

What proportion of all parts are defective?

- **A.** $0.05$
- **B.** $0.08$
- **C.** $0.125$
- **D.** $0.25$

## Question 9

Using the same factory as Question 8: a part is found to be **defective**. What is the probability it came from supplier A?

- **A.** $0.05$
- **B.** $0.20$
- **C.** $0.50$
- **D.** $0.80$

## Question 10

Which statement is correct?

- **A.** $P(A\mid B) = P(B\mid A)$ always
- **B.** $P(A\mid B) = P(B\mid A)$ only when $A$ and $B$ are disjoint
- **C.** $P(A\mid B)$ and $P(B\mid A)$ answer different questions and need not be equal
- **D.** $P(A\mid B) = P(A\cap B)$

## Question 11

Two cards are drawn from a deck **without replacement**. Which expression gives the probability that both are aces?

- **A.** $\dfrac{4}{52}\times\dfrac{4}{52}$
- **B.** $\dfrac{4}{52}\times\dfrac{3}{51}$
- **C.** $\dfrac{4}{52}+\dfrac{3}{51}$
- **D.** $\dfrac{4}{52}\times\dfrac{3}{52}$

## Question 12

In Bayes' theorem, what does the **denominator** represent?

- **A.** The prior probability of the hypothesis
- **B.** The likelihood of the evidence under the hypothesis
- **C.** The total probability of the evidence, across every way it could arise
- **D.** The complement of the posterior

---

# Part 3 — Test accuracy

A diagnostic test is run on 1,000 people. The results:

| | Test positive | Test negative |
|---|---|---|
| **Actually sick** | 40 | 10 |
| **Actually healthy** | 60 | 890 |

Use this table for Questions 13 to 16.

## Question 13

What is the **sensitivity** (recall) of the test?

- **A.** $0.40$
- **B.** $0.80$
- **C.** $0.93$
- **D.** $0.94$

## Question 14

What is the **precision** (positive predictive value)?

- **A.** $0.40$
- **B.** $0.80$
- **C.** $0.93$
- **D.** $0.94$

## Question 15

A second test is proposed that simply reports **negative for everyone**. What is its accuracy on this same population, and what does that tell you?

- **A.** $0.50$ — worse than the real test, so accuracy is a fine metric
- **B.** $0.93$ — identical to the real test, so the two are equally useful
- **C.** $0.95$ — higher than the real test, even though it catches nobody
- **D.** $0.05$ — accuracy correctly identifies it as useless

## Question 16

**Select all that apply.** Which of these quantities would **change** if the same test were used on a population where the disease is far more common?

- **A.** Sensitivity
- **B.** Specificity
- **C.** Precision
- **D.** Negative predictive value
- **E.** Prevalence

---

# Part 4 — Random variables

## Question 17

**Select all that apply.** Which of the following are **continuous** random variables?

- **A.** The number of emails received in an hour
- **B.** The time until a lightbulb fails
- **C.** The number of heads in 20 coin flips
- **D.** The exact weight of a randomly chosen apple
- **E.** The shoe size sold at a store

## Question 18

Which statement about a probability **density** function $f_X(x)$ is true?

- **A.** $f_X(x)$ is the probability that $X$ equals $x$
- **B.** $f_X(x)$ can never exceed 1
- **C.** $f_X(x)$ can exceed 1, but the total area underneath must equal 1
- **D.** $f_X(x)$ must sum to 1 across all values of $x$

## Question 19

For a **continuous** random variable, what is $P(X = 3)$?

- **A.** It depends on the distribution
- **B.** $0$
- **C.** $f_X(3)$
- **D.** $F_X(3)$

## Question 20

Which of these could be a valid CDF for a discrete random variable taking values $0,1,2,3$?

- **A.** $0.2,\ 0.5,\ 0.4,\ 1.0$
- **B.** $0.2,\ 0.5,\ 0.8,\ 1.0$
- **C.** $0.2,\ 0.5,\ 0.8,\ 1.2$
- **D.** $1.0,\ 0.8,\ 0.5,\ 0.2$

## Question 21

A random variable $X$ has this distribution:

| $x$ | 0 | 1 | 2 | 3 |
|---|---|---|---|---|
| $p_X(x)$ | 0.1 | 0.3 | 0.4 | 0.2 |

What is $E[X]$?

- **A.** $1.5$
- **B.** $1.7$
- **C.** $2.0$
- **D.** $3.7$

## Question 22

Using the same distribution as Question 21, what is $\text{Var}(X)$?

*Hint: you will need $E[X^2]$ as well.*

- **A.** $0.81$
- **B.** $0.90$
- **C.** $2.89$
- **D.** $3.70$

## Question 23

If $\text{Var}(X) = 4$, what is $\text{Var}(3X + 5)$?

- **A.** $12$
- **B.** $17$
- **C.** $36$
- **D.** $41$

---

# Part 5 — Distributions

## Question 24

A fair coin is flipped 8 times. Which is the correct expression for the probability of getting exactly 3 heads if the coin is **biased** with $P(\text{heads}) = 0.25$?

- **A.** $\binom{8}{3}(0.25)^3(0.75)^5$
- **B.** $\binom{8}{3}(0.25)^5(0.75)^3$
- **C.** $(0.25)^3(0.75)^5$
- **D.** $\binom{8}{3}(0.25)^3(0.75)^3$

## Question 25

**Select all that apply.** Which of the following would **violate** the conditions for a binomial distribution?

- **A.** The number of trials is decided in advance
- **B.** Cards are drawn without replacement
- **C.** The probability of success changes from trial to trial
- **D.** Each trial has exactly two outcomes
- **E.** The trials influence one another

## Question 26

$X$ follows a continuous uniform distribution on the interval $[2, 10]$. What is $P(4 < X < 7)$?

- **A.** $0.125$
- **B.** $0.300$
- **C.** $0.375$
- **D.** $0.500$

## Question 27

A variable is described as $X \sim N(50, 16)$. What is its **standard deviation**?

- **A.** $4$
- **B.** $16$
- **C.** $50$
- **D.** $256$

## Question 28

Exam scores are approximately normal with $\mu = 100$ and $\sigma = 15$. Roughly what percentage of scores fall between **70 and 130**?

- **A.** $50$ percent
- **B.** $68$ percent
- **C.** $95$ percent
- **D.** $99.7$ percent

## Question 29

A dataset is strongly right-skewed. You apply standardization, converting every value to $z = \dfrac{x-\mu}{\sigma}$. What is the result?

- **A.** The data becomes normally distributed with mean 0 and SD 1
- **B.** The data has mean 0 and SD 1, but is still right-skewed
- **C.** The data is rescaled to the range $[0, 1]$
- **D.** The skew is reduced but the mean and SD are unchanged

## Question 30

$X \sim \text{Binomial}(100, 0.4)$ and you want to approximate $P(X \leq 45)$ with a normal distribution. Which setup is correct?

- **A.** $\mu = 40$, $\sigma = 24$, boundary at $45$
- **B.** $\mu = 40$, $\sigma \approx 4.9$, boundary at $44.5$
- **C.** $\mu = 40$, $\sigma \approx 4.9$, boundary at $45.5$
- **D.** $\mu = 45$, $\sigma \approx 4.9$, boundary at $45$

---

# Answer sheet

Fill this in and send it back for grading.

| Q | Answer | | Q | Answer | | Q | Answer |
|---|---|---|---|---|---|---|---|
| 1 | | | 11 | | | 21 | |
| 2 | | | 12 | | | 22 | |
| 3 | | | 13 | | | 23 | |
| 4 | | | 14 | | | 24 | |
| 5 | | | 15 | | | 25 | |
| 6 | | | 16 | | | 26 | |
| 7 | | | 17 | | | 27 | |
| 8 | | | 18 | | | 28 | |
| 9 | | | 19 | | | 29 | |
| 10 | | | 20 | | | 30 | |

Questions 5, 16, 17 and 25 are **select all that apply** — list every letter you choose.

---

# Notes before you start

- Nothing here needs a z-table. Question 28 uses a rule you should know by heart.
- Four questions are select-all. Partial credit applies: you lose the point if you miss a correct option or include a wrong one.
- Questions 8 and 9 are linked, as are 13 through 16 and 21 through 22. Getting the first one wrong will usually cost you the second, so check your work on those before moving on.
- If a question seems to have two defensible answers, re-read it — one of them is answering a slightly different question than the one asked.
