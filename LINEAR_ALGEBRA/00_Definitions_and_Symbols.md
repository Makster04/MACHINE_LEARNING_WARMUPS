# Definitions and Symbols — Master Reference

> One page for the two things worth having in front of you: **what every symbol means**, and **the definitions you should be able to state from memory**.
>
> Covers files **01–11**. Each entry names the file where the idea is developed in full.
>
> **Week 1 (01–06) diagnoses systems** — telling singular from non-singular, and knowing what to expect before solving. **Week 2 (07–11) solves them** — getting the actual numbers out. Section headings are tagged so you can skip to the week you need.

---

# Part 1 — Symbols

## Systems and equations · *Week 1*

| Symbol | What it means | File |
|---|---|---|
| $a,b,c,\ldots$ | Variables in a system — prices, unknowns, coordinates | 02 |
| $a+b=10$ | A linear equation: variables scaled by numbers, then added | 02 |
| $(8,2)$ | A solution, written as an ordered pair or triple | 02 |
| $\infty$ | "Infinitely many solutions" — one of the three possible outcomes | 02, 03 |

## Geometry · *Week 1*

| Symbol | What it means | File |
|---|---|---|
| $b=(\text{slope})\,a+(\text{intercept})$ | An equation rewritten to reveal its line | 03 |
| $(a,b)$ | A point in 2D; a solution of a 2-variable system | 03 |
| $(a,b,c)$ | A point in 3D; a solution of a 3-variable system | 03 |

## Matrices · *Weeks 1–2*

| Symbol | What it means | File |
|---|---|---|
| A grid of numbers, e.g. rows $[1,1]$ and $[1,2]$ | The coefficient matrix — coefficients only, constants stripped away | 04 |
| $a,b,c,d$ | Generic labels for a 2×2 matrix: top-left, top-right, bottom-left, bottom-right | 04, 06 |
| $a,b,c,d,e,f,g,h,i$ | Generic labels for a 3×3 matrix, read row by row | 06 |
| A grid with a final separated column | The **augmented matrix** — coefficients plus the constants | 08, 11 |
| $*$ | "any value" — an entry the form places no constraint on | 10, 11 |

## Rows and dependence · *Weeks 1–2*

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $R_1,R_2,R_3$ | "row 1", "row 2", "row 3" | A row of a matrix, referred to by number | 05, 08 |
| $[a,b]$ | "the row a, b" | A row vector, written as a bracketed list | 05 |
| $k$ | "k" | The scalar multiplier in the row-multiple test | 05, 06 |
| $c_1,c_2,c_3,\ldots$ | — | The numbers scaling each row in a linear combination | 05 |
| $M_1,M_2,\ldots$ | "matrix 1", "matrix 2" | A matrix, referred to by number, in a worked example | 05, 06 |
| $R_1 - 2R_2$ | "row 1 minus twice row 2" | A row operation written compactly | 08, 10, 11 |

## The determinant · *Week 1*

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $\det$ | "the determinant of" | One number computed from a matrix that tests singularity | 06 |
| $ad-bc$ | — | The 2×2 determinant formula | 06 |
| $aei+bfg+cdh-ceg-afh-bdi$ | — | The 3×3 determinant formula (Sarrus' rule) | 06 |

## Solving and reduction · *Week 2*

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $0=0$ | "zero equals zero" | An equation that dissolved — true but empty; signals redundancy | 07 |
| $0=2$ | "zero equals two" | An impossible statement — signals contradiction | 07 |
| A boxed leading entry | "pivot" | The leftmost nonzero entry of a row | 10, 11 |
| A staircase of pivots | — | Row echelon form: each pivot strictly right of the one above | 10 |
| $\mathbf{1}$ on the diagonal, $0$ elsewhere | — | The identity matrix — the RREF of any non-singular square matrix | 11 |

## Operators and relations

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $\times$ | "times" | Ordinary multiplication, or "row scaled by" in $[a,b]\times k$ | 05, 06 |
| $\iff$, $\Longleftrightarrow$ | "if and only if" | Each side implies the other — a genuine two-way rule | 02, 04, 06 |
| $\Rightarrow$ | "implies" | The left side forces the right side | throughout |
| $\neq$ | "does not equal" | — | throughout |
| $\rightarrow$ | "becomes" | One step of a transformation | 08, 10, 11 |
| $\infty$ | "infinity" | Infinitely many solutions | 02, 03 |

---

# Part 2 — Definitions

## 01 · Systems of sentences · *Week 1*

**System.** Several statements considered together, as one package — judged jointly, never one at a time.

**Complete.** Every sentence adds new information, and everything gets determined.

**Redundant.** At least one sentence repeats information the others already gave. True, but wasteful.

**Contradictory.** The sentences cannot all be true at once — the package is broken, not just inefficient.

**Singular.** Redundant or contradictory. A system that fails to deliver full, unique information.

**Non-singular.** Complete. A system where every sentence pulls its weight.

> Singular and non-singular describe the **whole system**, never a single sentence — the same sentence can sit inside a non-singular system in one context and a singular one in another.

---

## 02 · Systems of equations · *Week 1*

**Equation.** A sentence about numbers. Translating a sentence into an equation loses nothing.

**Linear equation.** Variables multiplied by numbers and added — nothing squared, nothing multiplied together, nothing inside a function, no variable in an exponent.

**Solution.** Values that satisfy **every** equation of the system simultaneously. Satisfying some of them counts for nothing.

**The trichotomy.** A linear system has exactly one solution, infinitely many, or none — never any other count, and in particular never exactly two.

> Singular does **not** mean unsolvable. It means "no unique solution" — which includes both infinitely many solutions and none at all.

---

## 03 · Geometry: lines and planes · *Week 1*

**Line.** The complete solution set of one linear equation in two variables.

**Slope.** How steeply a line runs, set entirely by the equation's **coefficients**.

**Intercept.** Where a line crosses the axis, set entirely by the equation's **constant**.

**Plane.** The complete solution set of one linear equation in three variables. A hyperplane is the same idea in more variables than can be drawn.

**Solution as intersection.** Solving a system means finding the point(s) lying on every one of its lines or planes at once.

**Why only three outcomes.** Two distinct straight lines share at most one point — if they shared two, they would be the same line. That single fact is the whole proof of 02's trichotomy.

---

## 04 · Matrices and singularity · *Week 1*

**Coefficient.** A number multiplying a variable. Coefficients set an equation's slope.

**Constant.** The number alone on the right of an equation. Constants set an equation's intercept, and nothing else.

**Matrix.** The grid formed from a system's coefficients alone — one row per equation, one column per variable, with variable names and constants both stripped away.

**System singular ⟺ matrix singular.** Singularity is entirely a property of the coefficients. Constants can never flip it — they only decide, among already-singular systems, redundant versus contradictory.

**Homogeneous system.** Every constant on the right equals zero.

**Trivial solution.** The all-zero point — always a solution of a homogeneous system, since $0=0$ regardless of the coefficients. So a homogeneous system is never contradictory: only non-singular (trivial solution alone) or singular (infinitely many).

---

## 05 · Linear dependence and independence · *Week 1*

**Linear combination.** Any sum of rows, each first scaled by some number: $c_1R_1+c_2R_2+c_3R_3+\cdots$

**Linearly dependent.** Some row equals a linear combination of the others. With only two rows this simplifies to "one row is a scalar multiple of the other."

**Linearly independent.** No row can be written as a combination of the rest.

**Rows dependent ⟺ matrix singular.** Dependence among rows is exactly what makes a matrix singular — redundancy, relocated one level deeper than the system.

> The scalar-multiple test only fully covers two rows. With three or more, check every combination — a row can depend on several others at once.

> One dependency anywhere makes the **whole** matrix singular. The other rows don't get a vote.

---

## 06 · The determinant · *Week 1*

**Determinant (2×2).** $ad-bc$ — the product of the main diagonal, minus the product of the other diagonal.

**Determinant (3×3).** $aei+bfg+cdh-ceg-afh-bdi$ — three diagonal products added, three subtracted (the diagonal method, Sarrus' rule).

**Determinant ⟺ singularity.** A genuine if-and-only-if: zero exactly when the matrix is singular, nonzero exactly when it isn't.

**Triangular matrix.** Every entry below the main diagonal is zero. Its determinant is just the product of the diagonal entries.

**All-zero row.** Forces the determinant to zero automatically — the most extreme dependent row, carrying no information at all.

---

## 07 · Solving by elimination · *Week 2*

**Solved system.** The same system rewritten so each variable stands alone: $a=3$, $b=2$. Solving means transforming into this form without changing the solution set.

**The three legal manipulations.** Swap two equations; multiply an equation by a **nonzero** constant; add two equations. Safe because each is **reversible** — reversible moves cannot lose or invent solutions.

**Elimination.** Normalize (divide each equation by its coefficient of the target variable), subtract to cancel that variable, repeat on the smaller system, then **back-substitute** upward.

**Back-substitution.** Once the last variable is known, plug it into the equation above, solve, and keep climbing.

**Degree of freedom.** A variable you may choose freely, with the others determined by that choice. Each $0=0$ that appears leaves one more.

> A zero coefficient is not a failure — it means that elimination step is already done.

---

## 08 · Matrix row reduction · *Week 2*

**Augmented matrix.** The coefficient matrix with the constants carried along in an extra final column.

**Row operations.** The same three legal moves from 07, applied to matrix rows: switch two rows; multiply a row by a nonzero scalar; add one row to another.

**Effect on the determinant.** Switching rows flips its **sign**; scaling a row by $k$ **multiplies** it by $k$; adding one row to another leaves it **unchanged**.

**Preserves singularity.** None of the three can turn a zero determinant nonzero or vice versa — so singularity and rank survive any amount of row reduction. This is the permission slip for everything in 09–11.

**Upper diagonal matrix.** Zeros below the diagonal — what 10 calls row echelon form.

**Diagonal matrix.** Zeros above *and* below — what 11 calls reduced row echelon form.

> "Preserves singularity" is **not** "preserves the determinant." Two of the three operations genuinely change its value; they just can't change whether it's zero.

---

## 09 · Rank · *Week 2*

**Rank.** The number of independent pieces of information a system carries — equivalently, the number of **linearly independent rows** of its matrix.

**Full rank.** Rank equal to the number of rows. Full rank ⟺ non-singular.

**Solution space.** The set of all solutions of the homogeneous system, with a dimension: a point (0), a line (1), a plane (2), and so on.

**Rank-nullity.** $\text{rank} + \text{dimension of solution space} = \text{number of variables}$. Every independent equation removes one degree of freedom. The dimension of the solution space is the **nullity**.

> Rank counts **independent** rows, not rows. A matrix with two rows and no zeros anywhere can still have rank 1.

---

## 10 · Row echelon form · *Week 2*

**Pivot.** The leftmost nonzero entry of a row. An all-zero row has no pivot.

**Row echelon form.** Each pivot sits strictly to the right of the pivot in the row above; all-zero rows sit at the bottom. The result is a descending staircase.

**The algorithm.** Divide each row by its leftmost nonzero entry, subtract to clear beneath that pivot, then move down and repeat.

**Gaussian elimination.** Row-reduce to echelon form, then back-substitute. The standard algorithm for solving linear systems.

**Rank from the form.** $\text{rank} = \text{the number of pivots} = \text{the number of nonzero rows}$.

> Count **pivots**, not diagonal entries. The staircase may skip a column, and then the two counts disagree.

> Pivots need not be 1 in row echelon form — only the staircase is required. The usual algorithm normalizes them to 1 as a side effect.

---

## 11 · Reduced row echelon form · *Week 2*

**Reduced row echelon form (RREF).** In row echelon form, **and** every pivot is a 1, **and** every entry above a pivot is 0.

**The algorithm.** Divide each row by its pivot, then clear upward — working from the rightmost pivot leftward, subtract multiples of each pivot row from the rows above it.

**Gauss-Jordan elimination.** Reducing all the way to RREF, so no back-substitution is needed at all.

**Reading the solution.** With constants carried in an augmented matrix, the final column of the RREF **is** the solution.

**Uniqueness.** Every matrix has exactly one RREF, however you get there. (Row echelon form is *not* unique.)

> RREF does not mean "everything but the pivots is zero." Only entries **above a pivot** must vanish; columns containing no pivot are unconstrained.

---

# The master dictionary

The same fact, traced through every file. Each row is a different vocabulary for identical territory.

| File | Level | Non-singular | Singular |
|---|---|---|---|
| 01 | Sentences | Complete | Redundant or contradictory |
| 02 | Equations | Unique solution | Infinitely many, or none |
| 03 | Geometry | Lines/planes cross at a point | They coincide, or never meet |
| 04 | Matrix | Non-singular matrix | Singular matrix |
| 05 | Rows | Linearly independent | Linearly dependent |
| 06 | A number | Determinant $\neq 0$ | Determinant $= 0$ |
| 07 | Elimination | Every variable pinned down | Ends in $0=0$ or $0=\text{nonzero}$ |
| 09 | Rank | Full rank | Rank $<$ number of rows |
| 10 | Echelon form | A pivot in every row | At least one zero row |

$$
\boxed{\text{Nine levels, one fact: does every row carry a genuinely new piece of information?}}
$$

---

# Four ways to test for singularity

By the end of the series there are four independent checks. They always agree — pick whichever is cheapest for the matrix in front of you.

| Test | How | Best when | File |
|---|---|---|---|
| **Inspection** | Is one row a combination of the others? | Small matrices with obvious patterns | 05 |
| **Determinant** | Compute it; zero means singular | 2×2 and 3×3 | 06 |
| **Rank** | Is the rank less than the number of rows? | When you also want the solution-set size | 09 |
| **Row reduction** | Reduce; does a zero row appear? | Large matrices, and anything a computer does | 10 |

$$
\boxed{\text{det}=0 \iff \text{rank} < \text{full} \iff \text{a zero row appears} \iff \text{rows dependent} \iff \text{singular}}
$$

---

# The distinctions most often confused

| These look alike | But | File |
|---|---|---|
| Singular vs. "no solutions" | Singular includes infinitely many solutions too — it means *no unique solution* | 02 |
| Redundant vs. contradictory | Both singular; opposite failures — too little information vs. conflicting information | 01, 02 |
| Coefficients vs. constants | Only coefficients decide singular vs. non-singular; constants only decide redundant vs. contradictory | 04 |
| $a,b,c$ as variables vs. as matrix entries | Prices/coordinates in 02–03, generic grid positions in 04 and 06 | 02–03 vs. 04, 06 |
| The row-multiple test vs. the full combination test | The multiple test only covers 2 rows; 3+ rows need every combination checked | 05 |
| "Preserves singularity" vs. "preserves the determinant" | Row operations do the first, not the second — two of three change the value | 08 |
| Rank vs. number of rows | Rank counts *independent* rows; they differ exactly when there's redundancy | 09 |
| Pivots vs. diagonal entries | Rank is the pivot count; the diagonal count is wrong whenever the staircase skips a column | 10, 11 |
| Row echelon vs. **reduced** row echelon | REF clears below pivots only; RREF clears above too, forces pivots to 1, and is unique | 10, 11 |
| Gaussian vs. Gauss-Jordan | Gaussian stops at REF and back-substitutes; Gauss-Jordan goes to RREF and reads off | 10, 11 |

---

# Formulas and procedures to know cold

Each line is shown twice: once in symbols, once with a real case from the notes.

## Week 1 — diagnosing

| Formula | The same thing, with real numbers | File |
|---|---|---|
| Linear equation: number·variable $+\cdots=$ number | $3.4a-48.99b+2c=122.5$ | 02 |
| Checking a solution | $a=8,b=2$: $8+2=10$ ✓ and $8+2(2)=12$ ✓ | 02 |
| $b=(\text{slope})\,a+(\text{intercept})$ | $a+b=10 \Rightarrow b=10-a$: slope $-1$, intercept $10$ | 03 |
| System → matrix | $a+b=10,\ a+2b=12$ → rows $[1,1]$ and $[1,2]$ | 04 |
| Row-multiple test | $[1,1]\times 2=[2,2]$ — dependent, singular | 05 |
| Linear combination | $3R_1+2R_2=R_3$ for rows $[1,0,1],[0,1,0],[3,2,3]$ | 05 |
| $\det=ad-bc$ | $1\cdot2-1\cdot1=1$ — non-singular | 06 |
| $\det=ad-bc$ | $2\cdot3-(-1)\cdot(-6)=6-6=0$ — singular | 06 |
| $\det=aei+bfg+cdh-ceg-afh-bdi$ | $[1,1,1],[1,2,1],[1,1,2]$: $(4+1+1)-(2+1+2)=1$ | 06 |
| Triangular shortcut | $[1,1,1],[0,2,2],[0,0,3]$: $\det=1\times2\times3=6$ | 06 |

## Week 2 — solving

| Formula | The same thing, with real numbers | File |
|---|---|---|
| Normalize a row | $5a+b=17 \;\div 5\; \Rightarrow\; a+0.2b=3.4$ | 07 |
| Eliminate by subtracting | $(a-0.75b=1.5)-(a+0.2b=3.4) \Rightarrow -0.95b=-1.9$ | 07 |
| Back-substitute | $b=2$ into $a+0.2b=3.4 \Rightarrow a=3$ | 07 |
| Redundant tell | $(a+b=10)-(a+b=10) \Rightarrow 0=0$ | 07 |
| Contradictory tell | $(a+b=12)-(a+b=10) \Rightarrow 0=2$ | 07 |
| Row swap on the determinant | $\det[5,1;4,3]=11 \Rightarrow \det[4,3;5,1]=-11$ | 08 |
| Row scaling on the determinant | Row 1 $\times 10$: $\det = 110 = 10\times 11$ | 08 |
| Row addition on the determinant | $R_1+R_2$: $\det[9,4;4,3]=11$, unchanged | 08 |
| Rank-nullity | Rank 1 with 2 variables ⟹ solution space is a line (dimension 1) | 09 |
| Reduce to echelon form | $[5,1],[4,-3] \rightarrow [1,0.2],[0,1]$ — 2 pivots, rank 2 | 10 |
| Singular echelon form | $[5,1],[10,2] \rightarrow [1,0.2],[0,0]$ — 1 pivot, rank 1 | 10 |
| Clear above a pivot | $[1,0.2]-0.2[0,1]=[1,0]$ | 11 |
| Read off the solution | Augmented RREF $[1,0\mid 3],[0,1\mid 2] \Rightarrow a=3,\ b=2$ | 11 |

## The full pipeline

$$
\boxed{\text{System} \rightarrow \text{Matrix} \rightarrow \text{Echelon form} \rightarrow \text{Reduced echelon form} \rightarrow \text{Solution}}
$$

## Reading the table

The left column is what you write down; the right column is what it actually **means**. If you can rebuild the right column from the left, you know the formula rather than just recognizing it. When one stops making sense, go back to its concrete case and re-derive from there.
