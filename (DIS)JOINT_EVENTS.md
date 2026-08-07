# What You Should Know About Joint and Disjoint Events

These slides are mainly teaching **seven important ideas**: what union and intersection mean, how disjoint events differ from overlapping events, and when you need to subtract the overlap when adding probabilities.  

---

## 1. Start with what an event is

An **event** is simply a set of possible outcomes.

We usually name events with capital letters:

[
A,\quad B
]

For example, when rolling one six-sided die:

[
A=\text{rolling an even number}
]

So:

[
A={2,4,6}
]

and:

[
B=\text{rolling a 5}
]

So:

[
B={5}
]

Your slides use this exact even-number-or-5 setup as a disjoint-events example. 

---

# 2. Union means **OR**

The union symbol is:

[
\cup
]

Therefore:

[
A\cup B
]

means:

> **A OR B**

More precisely, it includes outcomes that are:

* In (A)
* In (B)
* Or in **both**

So:

[
P(A\cup B)
]

means:

[
\boxed{\text{Probability that A or B occurs}}
]

### Example

Suppose:

[
A=\text{plays soccer}
]

[
B=\text{plays basketball}
]

Then:

[
A\cup B
]

means:

[
\text{plays soccer OR basketball}
]

This includes someone who plays:

* Only soccer
* Only basketball
* **Both soccer and basketball**

### Important

In probability, **OR usually includes both**.

It does **not** normally mean "one or the other but not both."

---

# 3. Intersection means **AND**

The intersection symbol is:

[
\cap
]

Therefore:

[
A\cap B
]

means:

> **A AND B**

It represents the outcomes shared by both events.

Your joint-event slides describe the intersection as the situation where both events happen together. 

For example:

[
A=\text{plays soccer}
]

[
B=\text{plays basketball}
]

Then:

[
A\cap B
]

means:

[
\text{plays soccer AND basketball}
]

On a Venn diagram, this is the **overlapping middle section**.

So:

[
P(A\cap B)
]

means:

[
\boxed{\text{Probability that both A and B happen}}
]

---

# 4. Disjoint events cannot happen together

Two events are **disjoint** when they have **no outcomes in common**.

They cannot happen simultaneously. This is also called **mutually exclusive**. Your slides use even versus odd on one die as an example: a single roll cannot be both even and odd. 

Therefore:

[
A\cap B=\varnothing
]

where:

[
\varnothing=\text{no outcomes}
]

And consequently:

[
\boxed{P(A\cap B)=0}
]

### Example

Roll one die.

Let:

[
A=\text{even number}={2,4,6}
]

and:

[
B=\text{roll a 5}={5}
]

There is nothing appearing in both sets:

[
A\cap B=\varnothing
]

Therefore they are disjoint.

---

# 5. For disjoint events, simply add the probabilities

Because there is no overlap, the probability of:

[
A\text{ OR }B
]

is:

[
\boxed{P(A\cup B)=P(A)+P(B)}
]

### Dice example

Let:

[
A=\text{roll an even number}
]

There are 3 even values:

[
{2,4,6}
]

Therefore:

[
P(A)=\frac{3}{6}
]

Let:

[
B=\text{roll a 5}
]

There is one 5:

[
P(B)=\frac{1}{6}
]

Because these events cannot overlap:

[
P(A\cup B)=P(A)+P(B)
]

[
=\frac{3}{6}+\frac{1}{6}
]

[
=\frac{4}{6}
]

[
=\boxed{\frac23}
]

That matches the dice example in your slides. 

---

# 6. Joint / overlapping events can happen together

In your slides, **joint events** are events that can occur together, meaning their circles can overlap. 

For example:

[
A=\text{plays soccer}
]

[
B=\text{plays basketball}
]

A student could play **both** sports.

Therefore:

[
A\cap B\neq\varnothing
]

and potentially:

[
P(A\cap B)>0
]

These are also called **non-mutually-exclusive events**.

### Visually

Disjoint:

[
\text{○}\qquad\text{○}
]

No overlap.

Joint / overlapping:

[
\text{○ overlapping ○}
]

There is an intersection.

---

# 7. Why you cannot simply add probabilities for overlapping events

Suppose:

[
P(S)=0.60
]

for soccer and:

[
P(B)=0.50
]

for basketball.

If you simply added:

[
0.60+0.50=1.10
]

you would get:

[
110%
]

which cannot be the probability of the union.

Your slides specifically point out that this happens because the students who play **both sports are being counted twice**. 

Imagine one student plays both.

When you count soccer, you count that person once.

When you count basketball, you count that same person again.

So adding:

[
P(A)+P(B)
]

counts the intersection twice.

---

# 8. For joint events, subtract the overlap once

The general addition rule is:

[
\boxed{
P(A\cup B)
==========

P(A)+P(B)-P(A\cap B)
}
]

In words:

[
\boxed{
\text{OR}
=========

A+B-\text{both}
}
]

Why subtract?

Because:

[
P(A)+P(B)
]

counts the intersection **twice**.

Subtracting:

[
P(A\cap B)
]

removes one of those duplicate counts.

---

# 9. School example: soccer and basketball

Your slides give:

[
P(S)=0.60
]

[
P(B)=0.50
]

and:

[
P(S\cap B)=0.30
]

The question is:

> What is the probability that a child plays soccer **or** basketball?

Use:

[
P(S\cup B)
==========

P(S)+P(B)-P(S\cap B)
]

Substitute:

[
P(S\cup B)
==========

0.60+0.50-0.30
]

[
=1.10-0.30
]

[
=\boxed{0.80}
]

Therefore:

[
\boxed{P(S\cup B)=80%}
]

The slide's Venn diagram shows the same structure: 60% soccer, 50% basketball, with 30% in the overlap. 

---

# 10. The exact same rule works with counts

You do not always have probabilities.

Sometimes you are given the **number of people or outcomes**.

Then use:

[
\boxed{
|A\cup B|
=========

|A|+|B|-|A\cap B|
}
]

The vertical bars mean:

[
|A|=\text{number of outcomes in A}
]

Your school example gives:

[
|S|=6
]

[
|B|=5
]

[
|S\cap B|=3
]

So:

[
|S\cup B|
=========

6+5-3
]

[
=\boxed{8}
]

So **8 children** play soccer or basketball. The slides explicitly identify the overlap of three children as the information needed to solve the problem. 

---

# 11. Disjoint events are really a special case of the general formula

Remember the general formula:

[
P(A\cup B)
==========

P(A)+P(B)-P(A\cap B)
]

For disjoint events:

[
P(A\cap B)=0
]

Therefore:

[
P(A\cup B)
==========

P(A)+P(B)-0
]

which becomes:

[
\boxed{P(A\cup B)=P(A)+P(B)}
]

So you really only need to understand **one big rule**.

### General rule

[
\boxed{
P(A\cup B)
==========

P(A)+P(B)-P(A\cap B)
}
]

### If disjoint

The intersection is zero:

[
\boxed{
P(A\cup B)=P(A)+P(B)
}
]

---

# 12. Two-dice example: disjoint events

Your slides ask for:

> Probability of getting a sum of 7 **or** a sum of 10.

Let:

[
A=\text{sum of 7}
]

[
B=\text{sum of 10}
]

With two dice there are:

[
6\times6=36
]

possible ordered outcomes.

There are 6 ways to get a sum of 7:

[
(1,6),(2,5),(3,4),(4,3),(5,2),(6,1)
]

Therefore:

[
P(A)=\frac6{36}
]

There are 3 ways to get a sum of 10:

[
(4,6),(5,5),(6,4)
]

Therefore:

[
P(B)=\frac3{36}
]

A single pair of dice cannot simultaneously have a sum of both 7 and 10.

Therefore the events are disjoint:

[
P(A\cap B)=0
]

So:

[
P(A\cup B)
==========

\frac6{36}+\frac3{36}
]

[
=\frac9{36}
]

[
=\boxed{\frac14}
]

This is the disjoint two-dice example shown on page 3 of your slides. 

---

# 13. Two-dice example: overlapping events

Your joint-event slides give a more important example:

[
A=\text{sum of 7}
]

and:

[
B=\text{difference of 1}
]

Some dice outcomes satisfy **both conditions**.

So these are not disjoint.

The slides count:

[
P(A)=\frac6{36}
]

[
P(B)=\frac{10}{36}
]

and:

[
P(A\cap B)=\frac2{36}
]

Therefore:

[
P(A\cup B)
==========

P(A)+P(B)-P(A\cap B)
]

# [

\frac6{36}
+
\frac{10}{36}
-------------

\frac2{36}
]

# [

\frac{14}{36}
]

[
=\boxed{\frac7{18}}
]

The page 6–7 dice diagrams visually highlight the outcomes shared by both conditions, which is exactly why the intersection must be subtracted.

---

# 14. The biggest distinction: **OR versus AND**

This is probably the most important notation distinction.

| Meaning   | Symbol | Read as     |
| --------- | ------ | ----------- |
| (A\cup B) | (\cup) | **A OR B**  |
| (A\cap B) | (\cap) | **A AND B** |

Remember:

[
\boxed{\cup=\text{OR}}
]

[
\boxed{\cap=\text{AND}}
]

A helpful way to remember it:

### Union = combine

[
A\cup B
]

Collect everything belonging to either event.

### Intersection = overlap

[
A\cap B
]

Keep only what belongs to **both** events.

---

# 15. Disjoint versus joint / overlapping

This is the other distinction you absolutely want to know.

|                       | Disjoint events    | Joint / overlapping events |
| --------------------- | ------------------ | -------------------------- |
| Can both happen?      | No                 | Yes                        |
| Venn circles overlap? | No                 | Yes                        |
| (A\cap B)             | Empty              | May contain outcomes       |
| (P(A\cap B))          | (0)                | May be (>0)                |
| Addition rule         | Add                | Add then subtract overlap  |
| Also called           | Mutually exclusive | Non-mutually exclusive     |

### Disjoint

[
\boxed{P(A\cap B)=0}
]

Therefore:

[
\boxed{P(A\cup B)=P(A)+P(B)}
]

### Joint / overlapping

[
P(A\cap B)>0
]

Therefore:

[
\boxed{
P(A\cup B)
==========

P(A)+P(B)-P(A\cap B)
}
]

---

# 16. How to recognize which formula to use

When you see a probability problem involving **OR**, ask:

> **Can A and B happen at the same time?**

### If NO

The events are disjoint.

Use:

[
\boxed{P(A\cup B)=P(A)+P(B)}
]

### If YES

The events overlap.

Use:

[
\boxed{
P(A\cup B)
==========

P(A)+P(B)-P(A\cap B)
}
]

That one question usually tells you which formula you need.

---

# 17. Do not confuse "disjoint" with "independent"

One additional distinction worth knowing, although it is **not the main focus of these slides**, is:

**Disjoint** and **independent** do not mean the same thing.

### Disjoint

If one happens, the other **cannot** happen:

[
P(A\cap B)=0
]

Example:

[
\text{roll a 2}
]

and:

[
\text{roll a 5}
]

on the same die roll.

### Independent

One event happening does **not change the probability** of the other.

For independent events:

[
P(A\cap B)=P(A)P(B)
]

For example:

* First coin flip is heads
* Second coin flip is heads

Those can happen together and are independent.

So remember:

[
\boxed{\text{Disjoint}\neq\text{Independent}}
]

---

# Most Important Definitions and Distinctions to Remember

### Event

[
\boxed{A,B=\text{events}}
]

---

### Union

[
\boxed{A\cup B=\text{A OR B}}
]

Includes A, B, **and both**.

---

### Intersection

[
\boxed{A\cap B=\text{A AND B}}
]

Represents the overlap.

---

### Disjoint events

Cannot happen together:

[
\boxed{A\cap B=\varnothing}
]

Therefore:

[
\boxed{P(A\cap B)=0}
]

and:

[
\boxed{P(A\cup B)=P(A)+P(B)}
]

---

### Joint / overlapping events

Can happen together:

[
\boxed{A\cap B\neq\varnothing}
]

Use:

[
\boxed{
P(A\cup B)=P(A)+P(B)-P(A\cap B)
}
]

---

### For counts

[
\boxed{
|A\cup B|
=========

|A|+|B|-|A\cap B|
}
]

---

# Main Rules to Put in Your Notebook

[
\boxed{\cup=\text{OR}}
]

[
\boxed{\cap=\text{AND}}
]

[
\boxed{\text{Disjoint}=\text{cannot happen together}}
]

[
\boxed{\text{Joint/overlapping}=\text{can happen together}}
]

[
\boxed{P(A\cap B)=0\text{ if A and B are disjoint}}
]

[
\boxed{P(A\cup B)=P(A)+P(B)\quad\text{if disjoint}}
]

[
\boxed{
P(A\cup B)
==========

P(A)+P(B)-P(A\cap B)
}
]

[
\boxed{\text{Subtract the intersection because it was counted twice}}
]

[
\boxed{
|A\cup B|
=========

|A|+|B|-|A\cap B|
}
]

The **biggest idea** is this: **Union means OR, intersection means AND. If two events cannot overlap, just add their probabilities. If they can overlap, add the probabilities and subtract the intersection once so you don't double-count it.**
