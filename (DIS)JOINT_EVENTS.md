# What You Should Know About Joint and Disjoint Events

These slides are mainly teaching **seven important ideas**: what union and intersection mean, how disjoint events differ from joint events, and when you need to subtract the overlap when adding probabilities.

---

## 1. Start with what an event is

An **event** is a set of possible outcomes.

Events are usually represented with capital letters:

$$
A,\quad B
$$

For example, when rolling one six-sided die:

$$
A=\text{rolling an even number}
$$

Therefore:

$$
A=\{2,4,6\}
$$

Suppose:

$$
B=\text{rolling a 5}
$$

Therefore:

$$
B=\{5\}
$$

---

# 2. Union means OR

The union symbol is:

$$
\cup
$$

Therefore:

$$
A\cup B
$$

means:

**A OR B**

The union includes outcomes that are:

- In $A$
- In $B$
- In both $A$ and $B$

Therefore:

$$
P(A\cup B)
$$

means:

$$
\boxed{\text{Probability that A or B occurs}}
$$

### Example

Suppose:

$$
A=\text{plays soccer}
$$

and:

$$
B=\text{plays basketball}
$$

Then:

$$
A\cup B
$$

means:

$$
\text{plays soccer OR basketball}
$$

This includes someone who plays:

- Only soccer
- Only basketball
- Both soccer and basketball

### Important

In probability, **OR includes both unless stated otherwise**.

---

# 3. Intersection means AND

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

It represents the outcomes that the two events share.

For example:

$$
A=\text{plays soccer}
$$

$$
B=\text{plays basketball}
$$

Then:

$$
A\cap B
$$

means:

$$
\text{plays soccer AND basketball}
$$

On a Venn diagram, this is the **overlapping section** between the two circles.

Therefore:

$$
P(A\cap B)
$$

means:

$$
\boxed{\text{Probability that both A and B occur}}
$$

---

# 4. Disjoint events cannot happen together

Two events are **disjoint** when they have **no outcomes in common**.

They cannot happen at the same time.

Disjoint events are also called:

**Mutually exclusive events**

For disjoint events:

$$
A\cap B=\varnothing
$$

where:

$$
\varnothing=\text{no outcomes}
$$

Therefore:

$$
\boxed{P(A\cap B)=0}
$$

### Example

Roll one six-sided die.

Let:

$$
A=\text{rolling an even number}
$$

Therefore:

$$
A=\{2,4,6\}
$$

Let:

$$
B=\text{rolling a 5}
$$

Therefore:

$$
B=\{5\}
$$

There are no outcomes shared by both events.

Therefore:

$$
A\cap B=\varnothing
$$

The events are **disjoint**.

---

# 5. For disjoint events, simply add the probabilities

Because disjoint events have no overlap:

$$
P(A\cap B)=0
$$

Therefore, the probability that $A$ OR $B$ occurs is:

$$
\boxed{P(A\cup B)=P(A)+P(B)}
$$

### Dice example

Let:

$$
A=\text{rolling an even number}
$$

There are three even numbers:

$$
\{2,4,6\}
$$

Therefore:

$$
P(A)=\frac{3}{6}
$$

Let:

$$
B=\text{rolling a 5}
$$

There is one outcome:

$$
P(B)=\frac{1}{6}
$$

Because these events are disjoint:

$$
P(A\cup B)=P(A)+P(B)
$$

Substitute:

$$
P(A\cup B)
=
\frac{3}{6}+\frac{1}{6}
$$

$$
=\frac{4}{6}
$$

$$
=\boxed{\frac{2}{3}}
$$

---

# 6. Joint events can happen together

**Joint events** are events that can occur at the same time.

This means the two events can have outcomes in common.

For example:

$$
A=\text{plays soccer}
$$

and:

$$
B=\text{plays basketball}
$$

A student may play both soccer and basketball.

Therefore:

$$
A\cap B\neq\varnothing
$$

The events overlap.

Joint events are therefore different from disjoint events.

### Disjoint

The circles do not overlap.

$$
A\cap B=\varnothing
$$

### Joint

The circles overlap.

$$
A\cap B\neq\varnothing
$$

---

# 7. You cannot always simply add probabilities

Suppose:

$$
P(S)=0.60
$$

for soccer and:

$$
P(B)=0.50
$$

for basketball.

If we simply added them:

$$
0.60+0.50=1.10
$$

we would get:

$$
110\%
$$

But a probability cannot be greater than:

$$
100\%
$$

The problem is **double-counting**.

Students who play both soccer and basketball were counted once in the soccer group and again in the basketball group.

Therefore, the overlap must be subtracted.

---

# 8. For joint events, subtract the intersection

The general addition rule is:

$$
\boxed{
P(A\cup B)
=
P(A)+P(B)-P(A\cap B)
}
$$

In words:

$$
\boxed{
\text{OR probability}
=
A+B-\text{both}
}
$$

The reason we subtract:

$$
P(A\cap B)
$$

is because the intersection was counted **twice** when we added:

$$
P(A)+P(B)
$$

Subtracting the intersection removes the duplicate count.

---

# 9. School example: Soccer and basketball

Suppose:

$$
P(S)=0.60
$$

$$
P(B)=0.50
$$

and:

$$
P(S\cap B)=0.30
$$

The question is:

**What is the probability that a child plays soccer OR basketball?**

Use:

$$
P(S\cup B)
=
P(S)+P(B)-P(S\cap B)
$$

Substitute:

$$
P(S\cup B)
=
0.60+0.50-0.30
$$

$$
=1.10-0.30
$$

$$
=\boxed{0.80}
$$

Therefore:

$$
\boxed{P(S\cup B)=80\%}
$$

---

# 10. The same rule works with counts

Sometimes a problem gives you the **number of outcomes or people** instead of probabilities.

Use:

$$
\boxed{
|A\cup B|
=
|A|+|B|-|A\cap B|
}
$$

The vertical bars mean the **number of outcomes in the event**.

For example:

$$
|S|=6
$$

means six students play soccer.

Suppose:

$$
|S|=6
$$

$$
|B|=5
$$

$$
|S\cap B|=3
$$

Then:

$$
|S\cup B|
=
6+5-3
$$

$$
=\boxed{8}
$$

Therefore, **8 students play soccer or basketball**.

---

# 11. Disjoint events are a special case of the general addition rule

The general rule is:

$$
P(A\cup B)
=
P(A)+P(B)-P(A\cap B)
$$

For disjoint events:

$$
P(A\cap B)=0
$$

Therefore:

$$
P(A\cup B)
=
P(A)+P(B)-0
$$

which becomes:

$$
\boxed{
P(A\cup B)=P(A)+P(B)
}
$$

So the general formula works for both situations.

### Joint events

$$
\boxed{
P(A\cup B)
=
P(A)+P(B)-P(A\cap B)
}
$$

### Disjoint events

Because:

$$
P(A\cap B)=0
$$

the formula simplifies to:

$$
\boxed{
P(A\cup B)=P(A)+P(B)
}
$$

---

# 12. Two-dice example: Disjoint events

Suppose the question asks:

**What is the probability of obtaining a sum of 7 OR a sum of 10?**

Let:

$$
A=\text{sum of 7}
$$

and:

$$
B=\text{sum of 10}
$$

Rolling two dice produces:

$$
6\times6=36
$$

possible ordered outcomes.

There are six ways to obtain a sum of 7:

$$
(1,6),(2,5),(3,4),(4,3),(5,2),(6,1)
$$

Therefore:

$$
P(A)=\frac{6}{36}
$$

There are three ways to obtain a sum of 10:

$$
(4,6),(5,5),(6,4)
$$

Therefore:

$$
P(B)=\frac{3}{36}
$$

A single roll of two dice cannot have a sum of both 7 and 10.

Therefore:

$$
P(A\cap B)=0
$$

The events are disjoint.

So:

$$
P(A\cup B)
=
\frac{6}{36}+\frac{3}{36}
$$

$$
=\frac{9}{36}
$$

$$
=\boxed{\frac{1}{4}}
$$

---

# 13. Two-dice example: Joint events

Now suppose:

$$
A=\text{sum of 7}
$$

and:

$$
B=\text{difference of 1}
$$

Some dice outcomes satisfy **both conditions**.

Therefore, the events are joint.

Suppose:

$$
P(A)=\frac{6}{36}
$$

$$
P(B)=\frac{10}{36}
$$

and:

$$
P(A\cap B)=\frac{2}{36}
$$

Use:

$$
P(A\cup B)
=
P(A)+P(B)-P(A\cap B)
$$

Substitute:

$$
P(A\cup B)
=
\frac{6}{36}
+
\frac{10}{36}
-
\frac{2}{36}
$$

$$
=
\frac{14}{36}
$$

$$
=\boxed{\frac{7}{18}}
$$

The intersection is subtracted because those outcomes were counted in both events.

---

# 14. OR versus AND

This is one of the most important distinctions to remember.

| Meaning | Symbol | Read as |
|---|---|---|
| Union | $A\cup B$ | A **OR** B |
| Intersection | $A\cap B$ | A **AND** B |

Remember:

$$
\boxed{\cup=\text{OR}}
$$

$$
\boxed{\cap=\text{AND}}
$$

### Union

$$
A\cup B
$$

means combine the outcomes belonging to either event.

### Intersection

$$
A\cap B
$$

means look only at the outcomes shared by both events.

---

# 15. Disjoint versus joint events

| | Disjoint Events | Joint Events |
|---|---|---|
| Can both happen? | No | Yes |
| Venn circles overlap? | No | Yes |
| Intersection | No shared outcomes | Shared outcomes can exist |
| $P(A\cap B)$ | $0$ | Can be greater than $0$ |
| Other name | Mutually exclusive | Non-mutually exclusive |
| OR formula | Add probabilities | Add and subtract overlap |

### Disjoint events

$$
\boxed{P(A\cap B)=0}
$$

Therefore:

$$
\boxed{
P(A\cup B)=P(A)+P(B)
}
$$

### Joint events

The events overlap.

Therefore:

$$
\boxed{
P(A\cup B)
=
P(A)+P(B)-P(A\cap B)
}
$$

---

# 16. How to know which formula to use

When you see an **OR** probability problem, ask:

> **Can A and B happen at the same time?**

### If NO

The events are **disjoint**.

Use:

$$
\boxed{
P(A\cup B)=P(A)+P(B)
}
$$

### If YES

The events are **joint**.

Use:

$$
\boxed{
P(A\cup B)
=
P(A)+P(B)-P(A\cap B)
}
$$

The key is determining whether an **overlap exists**.

---

# Most Important Definitions and Distinctions to Remember

## Event

An event is a set of possible outcomes.

$$
\boxed{A,B=\text{events}}
$$

---

## Union

Union means **OR**.

$$
\boxed{A\cup B=\text{A OR B}}
$$

It includes:

- A only
- B only
- Both A and B

---

## Intersection

Intersection means **AND**.

$$
\boxed{A\cap B=\text{A AND B}}
$$

It represents the overlap between the events.

---

## Disjoint Events

Disjoint events cannot happen at the same time.

$$
\boxed{A\cap B=\varnothing}
$$

Therefore:

$$
\boxed{P(A\cap B)=0}
$$

For disjoint events:

$$
\boxed{
P(A\cup B)=P(A)+P(B)
}
$$

---

## Joint Events

Joint events can happen at the same time.

Their outcomes may overlap:

$$
A\cap B\neq\varnothing
$$

Use:

$$
\boxed{
P(A\cup B)
=
P(A)+P(B)-P(A\cap B)
}
$$

The intersection is subtracted because otherwise it would be counted twice.

---

# Main Rules to Put in Your Notebook

$$
\boxed{\cup=\text{OR}}
$$

$$
\boxed{\cap=\text{AND}}
$$

$$
\boxed{\text{Disjoint}=\text{cannot happen together}}
$$

$$
\boxed{\text{Joint}=\text{can happen together}}
$$

For disjoint events:

$$
\boxed{P(A\cap B)=0}
$$

$$
\boxed{
P(A\cup B)=P(A)+P(B)
}
$$

For joint events:

$$
\boxed{
P(A\cup B)
=
P(A)+P(B)-P(A\cap B)
}
$$

For counts:

$$
\boxed{
|A\cup B|
=
|A|+|B|-|A\cap B|
}
$$

The most important idea is:

**Union means OR and intersection means AND. If two events cannot overlap, simply add their probabilities. If they can overlap, add the probabilities and subtract the intersection once so that you do not double-count it.**
