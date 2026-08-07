# What You Should Know About Independent Events

These slides are mainly teaching **eight important ideas**: what independence means, how independent events differ from dependent events, how to calculate the probability of independent events happening together, and how the product rule works for repeated events.

---

## 1. Independent events do not affect each other's probabilities

Two events are **independent** when the occurrence of one event does **not change the probability** of the other event occurring.

In simple terms:

**Knowing that Event A happened gives you no new information about whether Event B will happen.**

For independent events:

$$
\boxed{\text{A happening does not affect the probability of B}}
$$

and:

$$
\boxed{\text{B happening does not affect the probability of A}}
$$

### Example: Coin flips

Suppose you flip a fair coin twice.

The probability of heads on the first flip is:

$$
P(H_1)=\frac{1}{2}
$$

The probability of heads on the second flip is still:

$$
P(H_2)=\frac{1}{2}
$$

Even if the first flip was heads, the second flip still has:

$$
P(H_2)=\frac{1}{2}
$$

The first flip does not change the probability of the second flip.

Therefore, the flips are **independent**.

---

# 2. Dependent events do affect each other

Events are **dependent** when the occurrence of one event changes the probability of another event occurring.

In simple terms:

$$
\boxed{\text{A happening affects the probability of B}}
$$

### Example

The slides use chess as an intuitive example.

What happens on one move can affect what happens on the next move.

The later move depends on the earlier state of the game.

Therefore, those events are **not independent**.

Another common example is drawing cards **without replacement**.

Suppose a deck contains 52 cards.

The probability of drawing an ace first is:

$$
\frac{4}{52}
$$

If you draw an ace and do not replace it, there are now:

$$
3
$$

aces remaining out of:

$$
51
$$

cards.

So the probability of another ace becomes:

$$
\frac{3}{51}
$$

The first event changed the probability of the second event.

Therefore, the events are **dependent**.

---

# 3. Independent versus dependent events

This is the first major distinction to remember.

| | Independent Events | Dependent Events |
|---|---|---|
| Does A affect B? | No | Yes |
| Does B's probability change after A? | No | Yes |
| Example | Separate coin flips | Drawing cards without replacement |
| Probabilities stay the same? | Yes | Not necessarily |

Remember:

$$
\boxed{\text{Independent}=\text{probabilities do not affect each other}}
$$

$$
\boxed{\text{Dependent}=\text{one event changes another's probability}}
$$

---

# 4. AND means intersection

When a question asks for the probability that **A AND B** occur, this is an intersection.

The intersection symbol is:

$$
\cap
$$

Therefore:

$$
A\cap B
$$

means:

**A AND B**

and:

$$
P(A\cap B)
$$

means:

$$
\boxed{\text{Probability that A and B both occur}}
$$

For example:

$$
P(\text{Soccer AND Room 1})
$$

means the probability that a randomly selected student:

- Likes soccer
- AND
- Is in Room 1

Both conditions must be true.

---

# 5. For independent events, multiply probabilities

The main formula in these slides is the **Product Rule for Independent Events**.

If A and B are independent:

$$
\boxed{
P(A\cap B)=P(A)\cdot P(B)
}
$$

In words:

$$
\boxed{
\text{Probability of A AND B}
=
P(A)\times P(B)
}
$$

This is one of the most important formulas to remember.

### Key word

When the events are independent and the question asks for:

**A AND B**

you usually **multiply**.

---

# 6. Soccer and Room 1 example

Suppose:

$$
P(S)=0.40
$$

where:

$$
S=\text{student likes soccer}
$$

and:

$$
P(R_1)=0.30
$$

where:

$$
R_1=\text{student is in Room 1}
$$

Suppose soccer preference and room assignment are independent.

We want:

$$
P(S\cap R_1)
$$

This means:

**Probability that a student likes soccer AND is in Room 1.**

Use the independent-event product rule:

$$
P(S\cap R_1)
=
P(S)\cdot P(R_1)
$$

Substitute:

$$
P(S\cap R_1)
=
0.40(0.30)
$$

$$
=\boxed{0.12}
$$

Therefore:

$$
\boxed{P(S\cap R_1)=12\%}
$$

---

# 7. Independence means the same proportion appears in each group

The school examples in the slides help visualize what independence means.

Suppose:

$$
40\%
$$

of all students like soccer.

If room assignment is independent of whether students like soccer, then we would expect approximately:

$$
40\%
$$

of students in each room to like soccer as well.

### Example

Suppose Room 1 contains:

$$
30
$$

students.

If:

$$
40\%
$$

like soccer, then:

$$
30(0.40)=12
$$

students in Room 1 would like soccer.

Therefore:

$$
\boxed{12\text{ students}}
$$

This matches the idea of independence:

**Being assigned to Room 1 does not change the proportion of students who like soccer.**

---

# 8. Independent events can happen together

Do not confuse **independent** with **unable to happen together**.

Independent events can absolutely occur at the same time.

For example:

$$
A=\text{first coin flip is heads}
$$

$$
B=\text{second coin flip is heads}
$$

The events are independent.

But both can happen:

$$
A\cap B=\text{Heads, Heads}
$$

Therefore:

$$
P(A\cap B)>0
$$

In fact:

$$
P(A\cap B)
=
\frac12\cdot\frac12
$$

$$
=\boxed{\frac14}
$$

So:

**Independent does NOT mean the events cannot happen together.**

---

# 9. Coin-flip example: Heads five times

Suppose you flip a fair coin five times.

The probability of heads on one flip is:

$$
P(H)=\frac12
$$

Each flip is independent.

To get heads five times, you need:

$$
H\cap H\cap H\cap H\cap H
$$

Therefore:

$$
P(\text{5 heads})
=
\frac12
\cdot
\frac12
\cdot
\frac12
\cdot
\frac12
\cdot
\frac12
$$

This can be written more simply as:

$$
P(\text{5 heads})
=
\left(\frac12\right)^5
$$

Calculate:

$$
\left(\frac12\right)^5
=
\frac{1}{32}
$$

Therefore:

$$
\boxed{
P(\text{5 heads})=\frac{1}{32}
}
$$

or approximately:

$$
\boxed{3.125\%}
$$

---

# 10. Repeated independent events can be written with exponents

If the same independent event occurs repeatedly and has the same probability each time, you can use an exponent.

Suppose one event has probability:

$$
p
$$

and you want it to occur:

$$
n
$$

times in a row.

Then:

$$
\boxed{
P(\text{event occurs every time})=p^n
}
$$

This is just a shortcut for multiplying:

$$
p\cdot p\cdot p\cdots p
$$

a total of $n$ times.

### Example

Five heads:

$$
\left(\frac12\right)^5
$$

instead of writing:

$$
\frac12
\cdot
\frac12
\cdot
\frac12
\cdot
\frac12
\cdot
\frac12
$$

---

# 11. Dice example: Rolling two sixes

For one fair six-sided die:

$$
P(6)=\frac16
$$

Suppose we roll two independent dice.

We want:

**Die 1 = 6 AND Die 2 = 6**

Use the product rule:

$$
P(6,6)
=
\frac16\cdot\frac16
$$

$$
=
\frac{1}{36}
$$

Therefore:

$$
\boxed{
P(6,6)=\frac{1}{36}
}
$$

This makes sense because rolling two dice creates:

$$
6\times6=36
$$

equally likely ordered outcomes.

Only one outcome is:

$$
(6,6)
$$

Therefore:

$$
P(6,6)=\frac1{36}
$$

---

# 12. Dice example: Rolling ten sixes

Suppose you roll a fair die ten independent times.

The probability of rolling a 6 once is:

$$
\frac16
$$

To obtain a 6 on **all ten rolls**:

$$
P(\text{10 sixes})
=
\left(\frac16\right)^{10}
$$

Therefore:

$$
\boxed{
P(\text{10 sixes})=
\left(\frac16\right)^{10}
}
$$

The probability becomes extremely small because you are requiring the same event to occur repeatedly.

---

# 13. Why multiplication makes probabilities smaller

When multiplying probabilities between 0 and 1, the result generally becomes smaller.

For example:

$$
\frac12\cdot\frac12
=
\frac14
$$

and:

$$
\frac12\cdot\frac12\cdot\frac12
=
\frac18
$$

This makes intuitive sense.

Getting one head is easier than getting:

- Two heads in a row
- Three heads in a row
- Five heads in a row

The more independent conditions that must **all** happen, the less likely the combined event becomes.

---

# 14. AND versus OR

This distinction is extremely important because it determines whether you are generally thinking about **multiplication** or **addition**.

### AND

AND means intersection:

$$
A\cap B
$$

For independent events:

$$
\boxed{
P(A\cap B)=P(A)P(B)
}
$$

So independent **AND** problems usually involve multiplication.

### OR

OR means union:

$$
A\cup B
$$

For OR problems, use the addition rule:

$$
P(A\cup B)
=
P(A)+P(B)-P(A\cap B)
$$

Therefore:

$$
\boxed{\text{AND}\rightarrow\text{intersection}}
$$

$$
\boxed{\text{OR}\rightarrow\text{union}}
$$

Do not automatically multiply just because two events appear in the same problem.

First determine whether the question is asking for **AND** or **OR**.

---

# 15. Independence versus disjoint events

This is one of the easiest probability concepts to confuse.

**Independent events and disjoint events are NOT the same thing.**

### Independent events

One event does not affect the probability of the other.

For independent events:

$$
\boxed{
P(A\cap B)=P(A)P(B)
}
$$

They **can happen together**.

### Disjoint events

Disjoint events cannot happen together.

For disjoint events:

$$
\boxed{
P(A\cap B)=0
}
$$

### Example of independent events

Flip a coin twice.

Let:

$$
A=\text{first flip is heads}
$$

$$
B=\text{second flip is heads}
$$

A and B are independent.

They can both happen.

### Example of disjoint events

Roll one die.

Let:

$$
A=\text{roll a 2}
$$

$$
B=\text{roll a 5}
$$

The same die roll cannot be both 2 and 5.

Therefore, they are disjoint.

### Remember

$$
\boxed{\text{Independent}\neq\text{Disjoint}}
$$

---

# 16. A mathematical way to test independence

Two events A and B are independent when:

$$
\boxed{
P(A\cap B)=P(A)P(B)
}
$$

So if a problem gives you all three probabilities, you can check independence.

### Example

Suppose:

$$
P(A)=0.50
$$

$$
P(B)=0.40
$$

and:

$$
P(A\cap B)=0.20
$$

Calculate:

$$
P(A)P(B)
=
0.50(0.40)
$$

$$
=0.20
$$

Since:

$$
P(A\cap B)=P(A)P(B)
$$

the events are independent.

---

# Most Important Definitions and Distinctions to Remember

## Independent events

Independent events are events where one event occurring does not change the probability of the other.

$$
\boxed{\text{Independent}=\text{one event does not affect the other}}
$$

For independent events:

$$
\boxed{
P(A\cap B)=P(A)P(B)
}
$$

---

## Dependent events

Dependent events are events where one event occurring changes the probability of another event.

$$
\boxed{
\text{Dependent}=\text{one event affects the probability of another}
}
$$

---

## Intersection

Intersection means **AND**.

$$
\boxed{
A\cap B=\text{A AND B}
}
$$

For independent events:

$$
\boxed{
P(A\cap B)=P(A)\cdot P(B)
}
$$

---

## Repeated independent events

If an event with probability $p$ must occur independently $n$ times:

$$
\boxed{
P(\text{event every time})=p^n
}
$$

For example:

$$
P(\text{5 heads})
=
\left(\frac12\right)^5
$$

and:

$$
P(\text{10 sixes})
=
\left(\frac16\right)^{10}
$$

---

## Independent versus dependent

| | Independent | Dependent |
|---|---|---|
| Does one affect the other? | No | Yes |
| Probability changes after first event? | No | Usually yes |
| Example | Separate coin flips | Cards without replacement |
| Basic idea | Probabilities stay unchanged | Probabilities can change |

---

## Independent versus disjoint

| | Independent | Disjoint |
|---|---|---|
| Can both events happen? | Yes | No |
| Does one affect the other? | No | If one happens, the other cannot |
| Intersection probability | $P(A)P(B)$ | $0$ |
| Example | Heads on two separate flips | Roll 2 or 5 on one die |

Remember:

$$
\boxed{\text{Independent}\neq\text{Disjoint}}
$$

---

# Main Rules to Put in Your Notebook

$$
\boxed{
\text{Independent}=
\text{one event does not change another's probability}
}
$$

$$
\boxed{
\text{Dependent}=
\text{one event changes another's probability}
}
$$

$$
\boxed{
\cap=\text{AND}
}
$$

For independent events:

$$
\boxed{
P(A\cap B)=P(A)\cdot P(B)
}
$$

For repeated independent events:

$$
\boxed{
P(\text{same event }n\text{ times})=p^n
}
$$

For five heads:

$$
\boxed{
P(\text{5 heads})
=
\left(\frac12\right)^5
=
\frac1{32}
}
$$

For two sixes:

$$
\boxed{
P(6,6)
=
\frac16\cdot\frac16
=
\frac1{36}
}
$$

For ten sixes:

$$
\boxed{
P(\text{10 sixes})
=
\left(\frac16\right)^{10}
}
$$

And most importantly:

$$
\boxed{
\text{Independent}\neq\text{Disjoint}
}
$$

The biggest idea is:

**Independent events do not change each other's probabilities. When independent events must happen together, multiply their probabilities. If the same independent event must happen repeatedly, multiply the probability by itself, which can be written using an exponent.**
