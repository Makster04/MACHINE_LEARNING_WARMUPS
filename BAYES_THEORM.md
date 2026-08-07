# What You Should Know About Bayes' Theorem

Bayes' theorem is used to **update a probability after receiving new evidence**.

More specifically, it allows you to reverse the direction of a conditional probability.

You may know:

```math
P(B\mid A)
```

but want:

```math
P(A\mid B)
```

The most important ideas are:

- Prior probability
- Evidence
- Likelihood
- Posterior probability
- Complement
- Total probability
- True positives and false positives
- Base rates
- Reversing conditional probability
- The Bayes formula

---

## 1. Conditional probability reminder

Bayes' theorem is built from conditional probability.

Recall:

```math
P(A\mid B)
```

means:

**Probability of A GIVEN B.**

The vertical bar means:

```math
\boxed{\displaystyle \mid=\text{given that}}
```

The conditional-probability definition is:

```math
P(A\mid B) = \frac{P(A\cap B)}{P(B)}
```

For a complete explanation of this formula, see the **Conditional Probability** notes.

---

# 2. Bayes reverses the direction of conditioning

This is the main reason Bayes' theorem is useful.

Suppose you know:

```math
P(B\mid A)
```

but you want:

```math
P(A\mid B)
```

These are not normally equal:

```math
\boxed{\displaystyle P(A\mid B)\neq P(B\mid A)}
```

Bayes' theorem gives you a way to calculate one direction using information about the other.

Therefore:

```math
\boxed{\displaystyle \text{Bayes' theorem reverses conditional probability}}
```

---

# 3. Medical-test example

Let:

```math
A=\text{sick}
```

and:

```math
B=\text{diagnosed sick}
```

Suppose the question asks:

**What is the probability that you are actually sick GIVEN that you tested positive?**

We want:

```math
P(A\mid B)
```

or:

```math
P(\text{sick}\mid\text{diagnosed sick})
```

But the test information usually gives us something like:

```math
P(\text{diagnosed sick}\mid\text{sick})
```

That is the opposite direction.

Bayes' theorem allows us to reverse it.

---

# 4. Prior probability

The **prior probability** is the probability of A before considering the new evidence.

It is written:

```math
P(A)
```

In the medical example:

```math
P(\text{sick})=\frac{1}{10,000}
```

which equals:

```math
0.0001
```

or:

```math
0.01\%
```

Therefore:

```math
\boxed{\displaystyle P(A)=\text{prior probability}}
```

Think of the prior as:

**What was the probability before seeing the new evidence?**

---

# 5. Base rate

The prior probability is also often called the **base rate**.

In the medical example:

```math
P(\text{sick})=0.01\%
```

The disease is therefore extremely rare.

This matters because Bayes' theorem considers not only how accurate the evidence is, but also how common the event was before the evidence appeared.

Therefore:

```math
\boxed{\displaystyle \text{Base rate}=\text{how common A is before observing B}}
```

---

# 6. Complement

The complement of A is written:

```math
A'
```

and means:

**A does not happen.**

If:

```math
A=\text{sick}
```

then:

```math
A'=\text{not sick}
```

The complement rule is:

```math
\boxed{\displaystyle P(A')=1-P(A)}
```

For the medical example:

```math
P(A')=1-0.0001
```

```math
=0.9999
```

Therefore:

```math
P(\text{not sick})=99.99\%
```

---

# 7. Likelihood

The **likelihood** describes how likely the evidence B is if A is true.

It is:

```math
P(B\mid A)
```

In the medical example:

```math
P(\text{diagnosed sick}\mid\text{sick})=0.99
```

This means:

**If someone is actually sick, there is a 99% probability that the test says positive.**

Therefore:

```math
\boxed{\displaystyle P(B\mid A)=\text{likelihood}}
```

---

# 8. True positive rate

For a medical test:

```math
P(\text{positive}\mid\text{sick})
```

is the **true positive rate**.

It is also called the test's:

**Sensitivity**

In the example:

```math
P(\text{positive}\mid\text{sick})=0.99
```

Therefore:

```math
\boxed{\displaystyle \text{True Positive Rate} = P(\text{positive}\mid\text{sick})}
```

---

# 9. False positive rate

The false positive rate is:

```math
P(\text{positive}\mid\text{not sick})
```

It represents healthy people who incorrectly receive a positive test result.

In the example:

```math
P(\text{positive}\mid\text{not sick})=0.01
```

Therefore:

```math
\boxed{\displaystyle \text{False Positive Rate} = P(\text{positive}\mid\text{not sick})}
```

Do not confuse this with the true positive rate.

---

# 10. Know the four possible test outcomes

A medical-test example can produce four possible combinations.

| Actual Condition | Test Result | Name |
|---|---|---|
| Sick | Positive | True Positive |
| Sick | Negative | False Negative |
| Healthy | Positive | False Positive |
| Healthy | Negative | True Negative |

### True Positive

Actually sick and correctly tests positive.

### False Negative

Actually sick but incorrectly tests negative.

### False Positive

Actually healthy but incorrectly tests positive.

### True Negative

Actually healthy and correctly tests negative.

The two groups most important for the Bayes example are:

```math
\boxed{\displaystyle \text{True Positives}}
```

and:

```math
\boxed{\displaystyle \text{False Positives}}
```

because both groups appear among people who tested positive.

---

# 11. The numerator represents A AND B

Bayes' theorem needs:

```math
P(A\cap B)
```

The general product rule gives:

```math
P(A\cap B) = P(A)P(B\mid A)
```

In the medical example:

```math
P(\text{sick AND positive}) = P(\text{sick}) P(\text{positive}\mid\text{sick})
```

Substitute:

```math
= 0.0001(0.99)
```

```math
= 0.000099
```

Therefore:

```math
\boxed{\displaystyle P(\text{sick AND positive})=0.000099}
```

---

# 12. The evidence can happen in more than one way

Suppose:

```math
B=\text{positive test}
```

A positive test can occur through two different paths.

### Path 1

The person is sick and tests positive.

```math
A\cap B
```

### Path 2

The person is healthy and tests positive.

```math
A'\cap B
```

Therefore:

```math
P(B) = P(A\cap B)+P(A'\cap B)
```

Using the product rule:

```math
\boxed{\displaystyle P(B) = P(A)P(B\mid A) + P(A')P(B\mid A')}
```

This is the **Law of Total Probability** for this two-case situation.

---

# 13. Why the denominator is so important

The denominator:

```math
P(B)
```

must include **every way the evidence B can occur**.

In the medical example:

```math
P(\text{positive})
```

includes:

- Sick people who correctly test positive
- Healthy people who incorrectly test positive

Therefore:

```math
\boxed{\displaystyle \text{All positive tests} = \text{true positives} + \text{false positives}}
```

Ignoring false positives would produce the wrong answer.

---

# 14. Bayes' theorem

The standard Bayes formula is:

```math
\boxed{\displaystyle P(A\mid B) = \frac{P(A)P(B\mid A)} {P(B)}}
```

In words:

```math
\boxed{\displaystyle \text{Posterior} = \frac{\text{Prior}\times\text{Likelihood}} {\text{Probability of the Evidence}}}
```

This is the central Bayes formula.

---

# 15. Expanded Bayes formula

If A and its complement $A'$ are the two possible underlying cases, then:

```math
P(B) = P(A)P(B\mid A) + P(A')P(B\mid A')
```

Therefore:

```math
\boxed{\displaystyle P(A\mid B) = \frac{ P(A)P(B\mid A) }{ P(A)P(B\mid A) + P(A')P(B\mid A') }}
```

This is the main version used in the medical-test example.

---

# 16. Posterior probability

The answer produced by Bayes' theorem is called the **posterior probability**.

The prior is:

```math
P(A)
```

The posterior is:

```math
P(A\mid B)
```

Therefore:

```math
\boxed{\displaystyle \text{Prior} \xrightarrow{\text{new evidence}} \text{Posterior}}
```

In words:

**Start with what you believed before the evidence and update it after observing the evidence.**

---

# 17. Solve the medical-test example

Suppose:

```math
P(\text{sick})=0.0001
```

```math
P(\text{not sick})=0.9999
```

```math
P(\text{positive}\mid\text{sick})=0.99
```

```math
P(\text{positive}\mid\text{not sick})=0.01
```

We want:

```math
P(\text{sick}\mid\text{positive})
```

Use:

```math
P(A\mid B) = \frac{ P(A)P(B\mid A) }{ P(A)P(B\mid A) + P(A')P(B\mid A') }
```

Substitute:

```math
P(\text{sick}\mid\text{positive}) = \frac{ 0.0001(0.99) }{ 0.0001(0.99)+0.9999(0.01) }
```

Calculate the true-positive path:

```math
0.0001(0.99)=0.000099
```

Calculate the false-positive path:

```math
0.9999(0.01)=0.009999
```

Calculate all positive tests:

```math
0.000099+0.009999 = 0.010098
```

Now divide:

```math
P(\text{sick}\mid\text{positive}) = \frac{0.000099}{0.010098}
```

```math
\approx0.0098
```

Therefore:

```math
\boxed{\displaystyle P(\text{sick}\mid\text{positive}) \approx0.98\%}
```

---

# 18. Why a 99% effective test does not mean a 99% chance of being sick

This is one of the most important distinctions in the entire topic.

The statement:

```math
P(\text{positive}\mid\text{sick})=99\%
```

does **not** mean:

```math
P(\text{sick}\mid\text{positive})=99\%
```

These are reversed conditional probabilities.

In this example:

```math
P(\text{positive}\mid\text{sick})=99\%
```

but:

```math
P(\text{sick}\mid\text{positive})\approx0.98\%
```

Therefore:

```math
\boxed{\displaystyle P(A\mid B)\neq P(B\mid A)}
```

in general.

---

# 19. Natural-frequency interpretation

The Bayes result becomes easier to understand if we imagine:

```math
1,000,000
```

people.

Since the disease occurs in:

```math
1\text{ out of }10,000
```

people:

```math
100
```

people are sick.

Of those 100 sick people, 99% test positive:

```math
100(0.99)=99
```

So there are:

```math
99
```

true positives.

There are:

```math
999,900
```

healthy people.

Of those, 1% test positive incorrectly:

```math
999,900(0.01)=9,999
```

So there are:

```math
9,999
```

false positives.

Therefore, total positive tests equal:

```math
99+9,999=10,098
```

Only:

```math
99
```

of those people are actually sick.

Therefore:

```math
P(\text{sick}\mid\text{positive}) = \frac{99}{10,098}
```

```math
\approx0.98\%
```

---

# 20. Why base rates matter

The disease is extremely rare:

```math
P(\text{sick})=0.01\%
```

while:

```math
P(\text{healthy})=99.99\%
```

So even though only:

```math
1\%
```

of healthy people produce false positives, there are so many healthy people that the false-positive count becomes very large.

The example produces:

```math
99
```

true positives but:

```math
9,999
```

false positives.

Therefore:

```math
\boxed{\displaystyle \text{A very large population can make a small false-positive rate produce many false positives}}
```

This is why Bayes' theorem must consider the **base rate**.

---

# 21. Base-rate neglect

A common mistake is to focus only on the accuracy of the evidence and ignore how common the original event was.

For example, someone might think:

> The test is 99% accurate, so a positive result must mean there is a 99% chance of disease.

That ignores:

```math
P(\text{sick})
```

the prior or base rate.

Bayes' theorem prevents this mistake by combining:

- The prior
- The likelihood
- The false-positive path

Therefore:

```math
\boxed{\displaystyle \text{Do not ignore the prior when interpreting evidence}}
```

---

# 22. Bayes problem-solving recipe

Most Bayes problems of this type can be solved using the same process.

### Step 1: Identify what you want

Find:

```math
P(A\mid B)
```

---

### Step 2: Identify the prior

Find:

```math
P(A)
```

---

### Step 3: Find the complement

```math
P(A')=1-P(A)
```

---

### Step 4: Identify the likelihood

Find:

```math
P(B\mid A)
```

---

### Step 5: Identify the alternative likelihood

Find:

```math
P(B\mid A')
```

---

### Step 6: Calculate the A path

```math
P(A)P(B\mid A)
```

---

### Step 7: Calculate the alternative path

```math
P(A')P(B\mid A')
```

---

### Step 8: Add the paths

```math
P(B) = P(A)P(B\mid A) + P(A')P(B\mid A')
```

---

### Step 9: Divide

```math
P(A\mid B) = \frac{ P(A)P(B\mid A) }{ P(B) }
```

A useful memory shortcut is:

```math
\boxed{\displaystyle \text{Prior}\times\text{Likelihood} \rightarrow \text{sum all evidence paths} \rightarrow \text{divide}}
```

---

# 23. Bayes is not only for medical tests

Bayes' theorem applies whenever new evidence changes what we should believe about an event.

The slides also use the **Monty Hall problem**.

Suppose you initially choose Door 1.

Before seeing any new information:

```math
P(E_1)=P(E_2)=P(E_3)=\frac13
```

where:

```math
E_i=\text{car is behind Door }i
```

Then the host opens Door 3.

That new information changes the probabilities.

The Bayes calculation gives:

```math
P(E_2\mid B)=\frac23
```

while:

```math
P(E_1\mid B)=\frac13
```

Therefore, switching to Door 2 gives the larger probability.

The important lesson is that the same Bayes structure applies:

```math
\boxed{\displaystyle \text{Prior}\times\text{Likelihood} \rightarrow \text{Total Probability} \rightarrow \text{Posterior}}
```

---

# Most Important Definitions and Distinctions to Remember

## Prior

Probability before observing the evidence:

```math
\boxed{\displaystyle P(A)=\text{prior}}
```

---

## Likelihood

Probability of observing the evidence if A is true:

```math
\boxed{\displaystyle P(B\mid A)=\text{likelihood}}
```

---

## Evidence

The event that was observed:

```math
\boxed{\displaystyle B=\text{evidence}}
```

---

## Posterior

Updated probability after observing the evidence:

```math
\boxed{\displaystyle P(A\mid B)=\text{posterior}}
```

---

## Complement

```math
\boxed{\displaystyle P(A')=1-P(A)}
```

---

## Total probability

```math
\boxed{\displaystyle P(B) = P(A)P(B\mid A) + P(A')P(B\mid A')}
```

---

## Bayes' theorem

```math
\boxed{\displaystyle P(A\mid B) = \frac{P(A)P(B\mid A)} {P(B)}}
```

Expanded:

```math
\boxed{\displaystyle P(A\mid B) = \frac{ P(A)P(B\mid A) }{ P(A)P(B\mid A) + P(A')P(B\mid A') }}
```

---

# Most Important Distinctions

| Concept | Meaning |
|---|---|
| $P(A)$ | Prior probability |
| $P(B\mid A)$ | Likelihood |
| $P(B)$ | Overall probability of the evidence |
| $P(A\mid B)$ | Posterior probability |
| $A'$ | Opposite or complement of A |

Most importantly:

```math
\boxed{\displaystyle P(A\mid B)\neq P(B\mid A)}
```

For medical testing:

```math
\boxed{\displaystyle P(\text{positive}\mid\text{sick}) \neq P(\text{sick}\mid\text{positive})}
```

---

# Main Rules to Put in Your Notebook

```math
\boxed{\displaystyle P(A')=1-P(A)}
```

```math
\boxed{\displaystyle P(A\cap B)=P(A)P(B\mid A)}
```

```math
\boxed{\displaystyle P(B) = P(A)P(B\mid A) + P(A')P(B\mid A')}
```

```math
\boxed{\displaystyle P(A\mid B) = \frac{P(A)P(B\mid A)} {P(B)}}
```

or:

```math
\boxed{\displaystyle P(A\mid B) = \frac{ P(A)P(B\mid A) }{ P(A)P(B\mid A) + P(A')P(B\mid A') }}
```

Remember:

```math
\boxed{\displaystyle \text{Prior} \xrightarrow{\text{Evidence}} \text{Posterior}}
```

```math
\boxed{\displaystyle P(A\mid B)\neq P(B\mid A)}
```

And the easiest Bayes recipe to remember is:

```math
\boxed{\displaystyle \text{Prior}\times\text{Likelihood} \rightarrow \text{add all ways the evidence can happen} \rightarrow \text{divide}}
```

The biggest idea is:

**Bayes' theorem updates a prior probability after new evidence is observed. It uses how common the event was beforehand, how likely the evidence is under each possible explanation, and then determines what proportion of all cases producing that evidence came from the event you care about.**

