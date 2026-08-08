# What You Should Know About Events and Set Notation

> **This file is the home for probability set notation.**
> Union, intersection, complement, the empty set, disjoint vs. joint events, and the addition rule are all defined here. Later files reference this one instead of redefining these symbols.

These notes cover **eight important ideas**: what an event is, what the sample space and complement are, what union and intersection mean, how disjoint events differ from joint events, what a partition is, and when you need to subtract the overlap before adding probabilities.

---

# 1. Start with what an event is

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

# 2. The sample space is everything that could happen

The **sample space** is the set of all possible outcomes. It is written:

$$
S
$$

For one six-sided die:

$$
S=\{1,2,3,4,5,6\}
$$

Because the sample space contains every possible outcome, something in it must happen. Therefore:

$$
P(S)=1
$$

Every event is a subset of the sample space.

---

# 3. The complement means NOT

The **complement** of an event is everything in the sample space that is **not** in that event.

It is written:

$$
A^c
$$

You may also see:

$$
A'\qquad\text{or}\qquad \bar{A}
$$

All three mean the same thing.

### Example

Roll one die. Let:

$$
A=\text{rolling an even number}=\{2,4,6\}
$$

Then:

$$
A^c=\text{rolling an odd number}=\{1,3,5\}
$$

### The complement rule

An event either happens or it does not. There is no third possibility. Therefore:

$$
P(A)+P(A^c)=1
$$

Rearranging gives the rule you will actually use:

$$
P(A^c)=1-P(A)
$$

Check it with the die:

$$
P(A)=\frac{3}{6}\qquad P(A^c)=1-\frac{3}{6}=\frac{3}{6}
$$

### Why the complement is useful

Sometimes the event you want is complicated, but its opposite is simple. Instead of calculating the event directly, calculate the opposite and subtract from 1.

The most common case is an **"at least one"** question:

$$
P(\text{at least one})=1-P(\text{none})
$$

Counting all the ways to get "at least one" is tedious. Counting the single way to get "none" is easy.

---

# 4. Union means OR

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
\text{Probability that A or B occurs}
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

# 5. Intersection means AND

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
\text{Probability that both A and B occur}
$$

---

# 6. Notation reference

These are the symbols this file defines. Every later topic uses them.

| Symbol | Name | Read as | Meaning |
|---|---|---|---|
| $S$ | Sample space | "everything" | All possible outcomes |
| $A\cup B$ | Union | A **OR** B | In A, in B, or in both |
| $A\cap B$ | Intersection | A **AND** B | In both A and B |
| $A^c$ | Complement | **NOT** A | Everything not in A |
| $\varnothing$ | Empty set | "nothing" | No outcomes |
| $\lvert A\rvert$ | Cardinality | "size of A" | Number of outcomes in A |

The two you will confuse most often:

$$
\cup=\text{OR}
$$

$$
\cap=\text{AND}
$$

A memory hook: $\cup$ looks like a **cup** that collects everything from both events. $\cap$ is the **cap** where the two events touch.

---

# 7. Disjoint events cannot happen together

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
P(A\cap B)=0
$$

### Example

Roll one six-sided die.

Let:

$$
A=\text{rolling an even number}=\{2,4,6\}
$$

Let:

$$
B=\text{rolling a 5}=\{5\}
$$

There are no outcomes shared by both events.

Therefore:

$$
A\cap B=\varnothing
$$

The events are **disjoint**.

---

# 8. For disjoint events, simply add the probabilities

Because disjoint events have no overlap:

$$
P(A\cap B)=0
$$

Therefore, the probability that $A$ OR $B$ occurs is:

$$
P(A\cup B)=P(A)+P(B)
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
P(A\cup B) = \frac{3}{6}+\frac{1}{6}
$$

$$
=\frac{4}{6}
$$

$$
=\frac{2}{3}
$$

---

# 9. Joint events can happen together

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

### On a Venn diagram

**Disjoint** — the circles do not overlap:

$$
A\cap B=\varnothing
$$

**Joint** — the circles overlap:

$$
A\cap B\neq\varnothing
$$

---

# 10. You cannot always simply add probabilities

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

# 11. For joint events, subtract the intersection

The **general addition rule** is:

$$
P(A\cup B) = P(A)+P(B)-P(A\cap B)
$$

In words:

$$
\text{OR probability} = A+B-\text{both}
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

# 12. School example: Soccer and basketball

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
P(S\cup B) = P(S)+P(B)-P(S\cap B)
$$

Substitute:

$$
P(S\cup B) = 0.60+0.50-0.30
$$

$$
=1.10-0.30
$$

$$
=0.80
$$

Therefore:

$$
P(S\cup B)=80\%
$$

---

# 13. The same rule works with counts

Sometimes a problem gives you the **number of outcomes or people** instead of probabilities.

Use:

$$
|A\cup B| = |A|+|B|-|A\cap B|
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
|S\cup B| = 6+5-3
$$

$$
=8
$$

Therefore, **8 students play soccer or basketball**.

---

# 14. Exhaustive events and partitions

Two ideas often appear together, and they are not the same thing.

### Mutually exclusive

The events do not overlap:

$$
A\cap B=\varnothing
$$

### Exhaustive

The events cover the entire sample space, leaving nothing out:

$$
A\cup B\cup\cdots = S
$$

### Partition

A group of events that is **both** mutually exclusive **and** exhaustive is called a **partition** of the sample space.

A partition slices the sample space into pieces that do not overlap and leave no gaps. Because every outcome lands in exactly one piece:

$$
P(A_1)+P(A_2)+\cdots+P(A_k)=1
$$

### The simplest partition

Any event and its complement always form a partition:

$$
A\cup A^c=S \qquad\text{and}\qquad A\cap A^c=\varnothing
$$

which is exactly why:

$$
P(A)+P(A^c)=1
$$

### Example

Roll one die. These three events form a partition:

$$
\{1,2\},\quad\{3,4\},\quad\{5,6\}
$$

They do not overlap, and together they cover all six outcomes.

But these two events do **not** form a partition:

$$
A=\{2,4,6\}\qquad B=\{5\}
$$

They are disjoint, but they are **not exhaustive** — the outcomes $1$ and $3$ are missing.

### Why this matters later

Partitions are what make the Law of Total Probability and the denominator of Bayes' theorem work. When you break an outcome into "all the separate ways it could have happened," you are using a partition.

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

### Disjoint events are a special case of the general rule

You only need to memorize **one** addition formula. The general rule is:

$$
P(A\cup B) = P(A)+P(B)-P(A\cap B)
$$

For disjoint events:

$$
P(A\cap B)=0
$$

Therefore:

$$
P(A\cup B) = P(A)+P(B)-0
$$

which becomes:

$$
P(A\cup B)=P(A)+P(B)
$$

So the disjoint formula is not a separate rule. It is the general rule with the overlap term equal to zero.

---

# 16. Two-dice example: Disjoint events

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
P(A\cup B) = \frac{6}{36}+\frac{3}{36}
$$

$$
=\frac{9}{36}
$$

$$
=\frac{1}{4}
$$

All 36 ordered outcomes, with each cell showing the **sum**. Rows are die 1, columns are die 2.

|  | **1** | **2** | **3** | **4** | **5** | **6** |
|---|---|---|---|---|---|---|
| **1** | 2 | 3 | 4 | 5 | 6 | **7** |
| **2** | 3 | 4 | 5 | 6 | **7** | 8 |
| **3** | 4 | 5 | 6 | **7** | 8 | 9 |
| **4** | 5 | 6 | **7** | 8 | 9 | `10` |
| **5** | 6 | **7** | 8 | 9 | `10` | 11 |
| **6** | **7** | 8 | 9 | `10` | 11 | 12 |

**Bold** marks the six ways to make 7. `Code` marks the three ways to make 10. **No cell carries both marks** — that is what disjoint looks like. Because the marked cells never coincide, the two counts can simply be added: $6 + 3 = 9$ cells out of 36.

---

# 17. Two-dice example: Joint events

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
P(A\cup B) = P(A)+P(B)-P(A\cap B)
$$

Substitute:

$$
P(A\cup B) = \frac{6}{36} + \frac{10}{36} - \frac{2}{36}
$$

$$
= \frac{14}{36}
$$

$$
=\frac{7}{18}
$$

The same 36 outcomes, now marked for two events that **can** overlap.

|  | **1** | **2** | **3** | **4** | **5** | **6** |
|---|---|---|---|---|---|---|
| **1** | 2 | `3` | 4 | 5 | 6 | **7** |
| **2** | `3` | 4 | `5` | 6 | **7** | 8 |
| **3** | 4 | `5` | 6 | **`7`** | 8 | 9 |
| **4** | 5 | 6 | **`7`** | 8 | `9` | 10 |
| **5** | 6 | **7** | 8 | `9` | 10 | `11` |
| **6** | **7** | 8 | 9 | 10 | `11` | 12 |

**Bold** marks sum 7 (six cells). `Code` marks difference 1 (ten cells). **`Bold code`** marks the two cells that satisfy **both**: $(3,4)$ and $(4,3)$.

Counting naively gives $6 + 10 = 16$, but only $14$ distinct cells are marked — the two overlapping cells were counted twice. Subtracting them once gives $\frac{14}{36} = \frac{7}{18}$, which is exactly the addition rule at work.

The intersection is subtracted because those outcomes were counted in both events.

---

# 18. How to know which formula to use

When you see an **OR** probability problem, ask:

> **Can A and B happen at the same time?**

### If NO

The events are **disjoint**.

Use:

$$
P(A\cup B)=P(A)+P(B)
$$

### If YES

The events are **joint**.

Use:

$$
P(A\cup B) = P(A)+P(B)-P(A\cap B)
$$

The key is determining whether an **overlap exists**.

### If the event is complicated

Ask whether the **opposite** is easier to count. If so:

$$
P(A)=1-P(A^c)
$$

---

# Most Important Definitions and Distinctions to Remember

## Event

An event is a set of possible outcomes.

$$
A,B=\text{events}
$$

---

## Sample space

The set of all possible outcomes.

$$
S \qquad\text{and}\qquad P(S)=1
$$

---

## Complement

The complement means **NOT**.

$$
A^c=\text{everything not in }A
$$

$$
P(A^c)=1-P(A)
$$

---

## Union

Union means **OR**.

$$
A\cup B=\text{A OR B}
$$

It includes:

- A only
- B only
- Both A and B

---

## Intersection

Intersection means **AND**.

$$
A\cap B=\text{A AND B}
$$

It represents the overlap between the events.

---

## Disjoint Events

Disjoint events cannot happen at the same time.

$$
A\cap B=\varnothing
$$

Therefore:

$$
P(A\cap B)=0
$$

For disjoint events:

$$
P(A\cup B)=P(A)+P(B)
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
P(A\cup B) = P(A)+P(B)-P(A\cap B)
$$

The intersection is subtracted because otherwise it would be counted twice.

---

## Partition

A partition is a group of events that is **mutually exclusive** and **exhaustive**.

$$
\text{No overlap} \qquad+\qquad \text{no gaps}
$$

Therefore the probabilities across a partition add to 1:

$$
P(A_1)+P(A_2)+\cdots+P(A_k)=1
$$

The simplest partition is $A$ and $A^c$.

---

## Disjoint versus exhaustive

This distinction is easy to miss.

| | Mutually exclusive | Exhaustive |
|---|---|---|
| Question it answers | Do they overlap? | Do they cover everything? |
| Requirement | $A\cap B=\varnothing$ | $A\cup B=S$ |
| If both are true | A partition | A partition |

Events can be disjoint without being exhaustive. Rolling an even number and rolling a 5 do not overlap, but they leave out 1 and 3.

---

# Main Rules to Put in Your Notebook

$$
\cup=\text{OR}
$$

$$
\cap=\text{AND}
$$

$$
A^c=\text{NOT}
$$

$$
P(S)=1
$$

$$
P(A^c)=1-P(A)
$$

$$
P(\text{at least one})=1-P(\text{none})
$$

$$
\text{Disjoint}=\text{cannot happen together}
$$

$$
\text{Joint}=\text{can happen together}
$$

For disjoint events:

$$
P(A\cap B)=0
$$

$$
P(A\cup B)=P(A)+P(B)
$$

For joint events:

$$
P(A\cup B) = P(A)+P(B)-P(A\cap B)
$$

For counts:

$$
|A\cup B| = |A|+|B|-|A\cap B|
$$

For a partition:

$$
P(A_1)+P(A_2)+\cdots+P(A_k)=1
$$

The most important idea is:

**Union means OR and intersection means AND. If two events cannot overlap, simply add their probabilities. If they can overlap, add the probabilities and subtract the intersection once so that you do not double-count it. If the event itself is hard to count, count its complement and subtract from 1.**

---

# Where This Goes Next

| Idea from this file | Where it is used |
|---|---|
| $P(A\cap B)$ | **02 — Independence**: when events are independent, $P(A\cap B)=P(A)P(B)$ |
| Disjoint events | **02 — Independence**: disjoint and independent are **not** the same thing |
| $A^c$ and partitions | **03 — Conditional Probability**: the Law of Total Probability |
| Partitions | **04 — Bayes' Theorem**: the denominator sums over a partition |
