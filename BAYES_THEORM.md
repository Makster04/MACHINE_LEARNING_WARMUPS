# What You Should Know About Bayes' Theorem

Bayes' theorem is mainly about **updating a probability after receiving new information**.

The most important ideas are:

- Conditional probability
- The direction of conditioning
- Prior probability
- Likelihood
- Total probability
- Bayes' theorem
- True positives versus false positives
- Why base rates matter
- How to recognize and solve a Bayes problem

---

# 1. Bayes' theorem answers a "given that" question

Bayes' theorem is used when you want a probability such as:

$$
P(A\mid B)
$$

This is read:

**The probability of A GIVEN B.**

The symbol:

$$
\mid
$$

means:

**given that**

For example:

$$
P(\text{sick}\mid\text{tested positive})
$$

means:

**What is the probability that a person is actually sick GIVEN that the person tested positive?**

Therefore:

$$
\boxed{
P(A\mid B)=\text{probability of A given that B occurred}
}
$$

---

# 2. Conditional probability changes the group you are looking at

The definition of conditional probability is:

$$
\boxed{
P(A\mid B)=\frac{P(A\cap B)}{P(B)}
}
$$

This means:

> Out of all cases where $B$ happened, what fraction also had $A$ happen?

The denominator:

$$
P(B)
$$

restricts your attention to cases where $B$ occurred.

The numerator:

$$
P(A\cap B)
$$

represents cases where **both A and B occurred**.

Therefore:

$$
\boxed{
P(A\mid B)
=
\frac{\text{A AND B}}{\text{all B}}
}
$$

### Medical example

If:

$$
A=\text{sick}
$$

and:

$$
B=\text{tested positive}
$$

then:

$$
P(A\mid B)
=
\frac{P(\text{sick AND positive})}
{P(\text{positive})}
$$

In words:

$$
\boxed{
\text{Actually sick among everyone who tested positive}
}
$$

---

# 3. The order in conditional probability matters

This is one of the **most important distinctions** in Bayes' theorem.

In general:

$$
P(A\mid B)\neq P(B\mid A)
$$

These probabilities answer different questions.

For example:

$$
P(\text{positive}\mid\text{sick})
$$

means:

**If someone is sick, what is the probability the test is positive?**

But:

$$
P(\text{sick}\mid\text{positive})
$$

means:

**If someone's test is positive, what is the probability the person is actually sick?**

These are **not the same probability**.

Bayes' theorem allows us to reverse the direction.

You may know:

$$
P(B\mid A)
$$

but want:

$$
P(A\mid B)
$$

Therefore:

$$
\boxed{
\text{Bayes' theorem reverses the conditioning direction}
}
$$

---

# 4. Prior probability is what you know before the new evidence

The **prior probability** is the original probability of an event before considering the new evidence.

It is written:

$$
P(A)
$$

In the medical example:

$$
P(\text{sick})=0.0001
$$

which is:

$$
0.01\%
$$

or:

$$
\frac{1}{10,000}
$$

This is the disease's **base rate**.

Therefore:

$$
\boxed{
P(A)=\text{prior probability}
}
$$

Think of the prior as:

**What did I believe about A before learning B?**

---

# 5. The complement represents the opposite event

If:

$$
A=\text{sick}
$$

then:

$$
A'
$$

means:

**not sick**

The probability of the complement is:

$$
P(A')=1-P(A)
$$

In the medical example:

$$
P(A)=0.0001
$$

Therefore:

$$
P(A')=1-0.0001
$$

$$
=0.9999
$$

So:

$$
P(\text{not sick})=99.99\%
$$

Remember:

$$
\boxed{
P(A')=1-P(A)
}
$$

---

# 6. Likelihood tells you how likely the evidence is if A is true

The slides use:

$$
P(B\mid A)
$$

as the **likelihood**.

In the medical example:

$$
P(\text{positive}\mid\text{sick})=0.99
$$

This means:

**If the person really is sick, there is a 99% probability that the test is positive.**

Therefore:

$$
\boxed{
P(B\mid A)=\text{likelihood}
}
$$

For a medical test, this is also the **true positive rate** or **sensitivity**.

---

# 7. False positive rate is different from the true positive rate

The medical example also gives:

$$
P(\text{positive}\mid\text{not sick})=0.01
$$

This is the **false positive rate**.

It means:

**Among healthy people, 1% will incorrectly receive a positive result.**

Do not confuse:

$$
P(\text{positive}\mid\text{sick})
$$

with:

$$
P(\text{positive}\mid\text{not sick})
$$

They describe two different groups.

### True positive rate

$$
\boxed{
P(\text{positive}\mid\text{sick})
}
$$

### False positive rate

$$
\boxed{
P(\text{positive}\mid\text{not sick})
}
$$

---

# 8. Know the four possible test outcomes

The slides divide medical-test outcomes into four categories.

| Actual Condition | Test Result | Name |
|---|---|---|
| Sick | Positive | True Positive |
| Sick | Negative | False Negative |
| Healthy | Positive | False Positive |
| Healthy | Negative | True Negative |

### True Positive

The person is sick and the test correctly says positive.

$$
\text{Sick}\cap\text{Positive}
$$

### False Negative

The person is sick but the test incorrectly says negative.

$$
\text{Sick}\cap\text{Negative}
$$

### False Positive

The person is healthy but the test incorrectly says positive.

$$
\text{Healthy}\cap\text{Positive}
$$

### True Negative

The person is healthy and the test correctly says negative.

$$
\text{Healthy}\cap\text{Negative}
$$

The most important distinction for the Bayes example is:

$$
\boxed{
\text{Positive test}
=
\text{True Positives}
+
\text{False Positives}
}
$$

---

# 9. Use the multiplication rule to calculate A AND B

The conditional-probability formula can be rearranged.

Starting with:

$$
P(B\mid A)
=
\frac{P(A\cap B)}{P(A)}
$$

Multiply both sides by:

$$
P(A)
$$

to get:

$$
\boxed{
P(A\cap B)
=
P(A)P(B\mid A)
}
$$

This calculates the probability that:

**A happens AND B happens.**

In the medical example:

$$
P(\text{sick AND positive})
=
P(\text{sick})
P(\text{positive}\mid\text{sick})
$$

$$
=
0.0001(0.99)
$$

$$
=
0.000099
$$

---

# 10. The denominator must include every way B can happen

This is one of the most important steps in Bayes' theorem.

Suppose:

$$
B=\text{positive test}
$$

A positive test can happen in **two different ways**:

1. The person is sick and correctly tests positive.
2. The person is healthy and incorrectly tests positive.

Therefore:

$$
P(B)
=
P(A\cap B)+P(A'\cap B)
$$

Using the multiplication rule:

$$
\boxed{
P(B)
=
P(A)P(B\mid A)
+
P(A')P(B\mid A')
}
$$

This is the **Law of Total Probability** for this two-case situation.

In the medical example:

$$
P(\text{positive})
=
P(\text{sick})P(\text{positive}\mid\text{sick})
+
P(\text{healthy})P(\text{positive}\mid\text{healthy})
$$

---

# 11. Bayes' theorem combines these ideas

The standard Bayes formula is:

$$
\boxed{
P(A\mid B)
=
\frac{P(A)P(B\mid A)}
{P(B)}
}
$$

The numerator is:

$$
P(A)P(B\mid A)
$$

which represents:

$$
P(A\cap B)
$$

The denominator:

$$
P(B)
$$

represents **all ways that B can happen**.

Therefore, in words:

$$
\boxed{
\text{Updated probability}
=
\frac{\text{Prior}\times\text{Likelihood}}
{\text{Overall probability of the evidence}}
}
$$

---

# 12. The expanded Bayes formula

When there are two possibilities:

$$
A
$$

and:

$$
A'
$$

the denominator can be expanded using total probability.

Therefore:

$$
\boxed{
P(A\mid B)
=
\frac{
P(A)P(B\mid A)
}{
P(A)P(B\mid A)
+
P(A')P(B\mid A')
}
}
$$

This is the main version used in the medical-test slides.

---

# 13. Medical-test example

Suppose:

$$
P(\text{sick})=0.0001
$$

$$
P(\text{not sick})=0.9999
$$

$$
P(\text{positive}\mid\text{sick})=0.99
$$

$$
P(\text{positive}\mid\text{not sick})=0.01
$$

We want:

$$
P(\text{sick}\mid\text{positive})
$$

Use Bayes' theorem:

$$
P(\text{sick}\mid\text{positive})
=
\frac{
P(\text{sick})P(\text{positive}\mid\text{sick})
}{
P(\text{sick})P(\text{positive}\mid\text{sick})
+
P(\text{not sick})P(\text{positive}\mid\text{not sick})
}
$$

Substitute:

$$
=
\frac{
0.0001(0.99)
}{
0.0001(0.99)+0.9999(0.01)
}
$$

Calculate the true-positive path:

$$
0.0001(0.99)=0.000099
$$

Calculate the false-positive path:

$$
0.9999(0.01)=0.009999
$$

Therefore:

$$
P(\text{positive})
=
0.000099+0.009999
$$

$$
=0.010098
$$

Now divide:

$$
P(\text{sick}\mid\text{positive})
=
\frac{0.000099}{0.010098}
$$

$$
\approx0.0098
$$

Therefore:

$$
\boxed{
P(\text{sick}\mid\text{positive})
\approx0.98\%
}
$$

So despite the test being 99% effective, a positive test corresponds to only about a **1% probability of actually being sick** in this example.

---

# 14. Natural frequencies make Bayes easier to understand

The slides also explain the problem using:

$$
1,000,000
$$

people.

The disease affects:

$$
1\text{ in }10,000
$$

people.

Therefore:

$$
100
$$

people are sick.

Of those 100 sick people:

$$
99\%
$$

test positive.

So:

$$
99
$$

are **true positives**.

There are:

$$
999,900
$$

healthy people.

Of those:

$$
1\%
$$

test positive incorrectly.

So:

$$
9,999
$$

are **false positives**.

Therefore, the total number of positive tests is:

$$
99+9,999=10,098
$$

Only:

$$
99
$$

of those positive tests belong to truly sick people.

Therefore:

$$
P(\text{sick}\mid\text{positive})
=
\frac{99}{10,098}
$$

$$
\approx0.0098
$$

$$
\approx0.98\%
$$

This produces the same answer as Bayes' formula.

---

# 15. Why the base rate matters

This example demonstrates an extremely important Bayes idea.

The disease is extremely rare:

$$
P(\text{sick})=0.01\%
$$

Almost everyone is healthy:

$$
P(\text{healthy})=99.99\%
$$

Even though only:

$$
1\%
$$

of healthy people receive a false positive, the healthy population is enormous.

That produces:

$$
9,999
$$

false positives compared with only:

$$
99
$$

true positives.

Therefore:

$$
\boxed{
\text{A small false-positive rate can still create many false positives when the base population is huge}
}
$$

This is why you cannot ignore the **prior probability or base rate**.

---

# 16. Bayes updates the prior using evidence

Before the test result, the probability of being sick is:

$$
P(\text{sick})=0.01\%
$$

This is the **prior**.

After observing a positive test, we calculate:

$$
P(\text{sick}\mid\text{positive})
\approx0.98\%
$$

The evidence changed our probability.

Therefore, the big idea behind Bayes' theorem is:

$$
\boxed{
\text{Start with a prior probability and update it using new evidence}
}
$$

---

# 17. A simple Bayes problem-solving recipe

When solving a Bayes problem, use this order.

### Step 1: Identify what you want

Find:

$$
P(A\mid B)
$$

Ask:

**What probability am I trying to find GIVEN what evidence?**

---

### Step 2: Identify the prior

Find:

$$
P(A)
$$

---

### Step 3: Find the complement

If needed:

$$
P(A')=1-P(A)
$$

---

### Step 4: Identify the likelihood

Find:

$$
P(B\mid A)
$$

---

### Step 5: Identify the alternative likelihood

Find:

$$
P(B\mid A')
$$

---

### Step 6: Calculate the numerator

$$
P(A)P(B\mid A)
$$

---

### Step 7: Calculate all ways B can happen

$$
P(B)
=
P(A)P(B\mid A)
+
P(A')P(B\mid A')
$$

---

### Step 8: Divide

$$
P(A\mid B)
=
\frac{
P(A)P(B\mid A)
}{
P(B)
}
$$

A useful shortcut to remember is:

$$
\boxed{
\text{Prior}\times\text{Likelihood}
\rightarrow
\text{sum all evidence paths}
\rightarrow
\text{divide}
}
$$

---

# 18. Bayes is not limited to medical testing

The slides also apply the same idea to the **Monty Hall problem**.

Suppose you choose Door 1 and the host opens Door 3.

Initially:

$$
P(E_1)=P(E_2)=P(E_3)=\frac13
$$

where each $E_i$ represents the car being behind that door.

After observing the host open Door 3, the probability changes.

The slides calculate:

$$
P(E_2\mid B)=\frac23
$$

while:

$$
P(E_1\mid B)=\frac13
$$

Therefore, switching to Door 2 gives the larger probability.

The important point is not memorizing the Monty Hall arithmetic.

The important point is that the **same Bayes structure applies**:

$$
\boxed{
\text{Prior}\times\text{Likelihood}
\rightarrow
\text{total probability}
\rightarrow
\text{divide}
}
$$

---

# Most Important Definitions and Distinctions to Remember

## Conditional probability

$$
\boxed{
P(A\mid B)
=
\text{probability of A given B}
}
$$

Definition:

$$
\boxed{
P(A\mid B)=\frac{P(A\cap B)}{P(B)}
}
$$

---

## Prior probability

The probability before considering the new evidence:

$$
\boxed{
P(A)=\text{prior}
}
$$

---

## Likelihood

The probability of observing the evidence if A is true:

$$
\boxed{
P(B\mid A)=\text{likelihood}
}
$$

---

## Complement

The probability that A does not occur:

$$
\boxed{
P(A')=1-P(A)
}
$$

---

## Multiplication rule

$$
\boxed{
P(A\cap B)=P(A)P(B\mid A)
}
$$

---

## Total probability

When B can happen through A or through $A'$:

$$
\boxed{
P(B)
=
P(A)P(B\mid A)
+
P(A')P(B\mid A')
}
$$

---

## Bayes' theorem

$$
\boxed{
P(A\mid B)
=
\frac{P(A)P(B\mid A)}
{P(B)}
}
$$

Expanded:

$$
\boxed{
P(A\mid B)
=
\frac{
P(A)P(B\mid A)
}{
P(A)P(B\mid A)
+
P(A')P(B\mid A')
}
}
$$

---

# The Most Important Distinction: P(A|B) versus P(B|A)

These are **not interchangeable**.

$$
P(A\mid B)
$$

means:

**Probability of A given B**

while:

$$
P(B\mid A)
$$

means:

**Probability of B given A**

Therefore:

$$
\boxed{
P(A\mid B)\neq P(B\mid A)
}
$$

in general.

For the medical example:

$$
P(\text{positive}\mid\text{sick})=99\%
$$

does **not** mean:

$$
P(\text{sick}\mid\text{positive})=99\%
$$

The latter must be calculated with Bayes' theorem.

---

# Main Rules to Put in Your Notebook

$$
\boxed{
\mid=\text{given that}
}
$$

$$
\boxed{
P(A\mid B)=\frac{P(A\cap B)}{P(B)}
}
$$

$$
\boxed{
P(A\cap B)=P(A)P(B\mid A)
}
$$

$$
\boxed{
P(A')=1-P(A)
}
$$

$$
\boxed{
P(B)
=
P(A)P(B\mid A)
+
P(A')P(B\mid A')
}
$$

$$
\boxed{
P(A\mid B)
=
\frac{P(A)P(B\mid A)}
{P(B)}
}
$$

or:

$$
\boxed{
P(A\mid B)
=
\frac{
P(A)P(B\mid A)
}{
P(A)P(B\mid A)
+
P(A')P(B\mid A')
}
}
$$

Remember:

$$
\boxed{
P(A\mid B)\neq P(B\mid A)
}
$$

And the easiest way to remember the Bayes process is:

$$
\boxed{
\text{Prior}\times\text{Likelihood}
\rightarrow
\text{find total probability of the evidence}
\rightarrow
\text{divide}
}
$$

The biggest idea is:

**Bayes' theorem updates what you believed before seeing the evidence. It starts with the prior probability, combines it with how likely the evidence would be under each possibility, and then asks what fraction of all cases producing that evidence came from the event you care about.**
