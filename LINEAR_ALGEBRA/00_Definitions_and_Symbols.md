# Definitions and Symbols — Master Reference

> One page for the two things worth having in front of you: **what every symbol means**, and **the definitions you should be able to state from memory**.
>
> Each entry names the file where the idea is developed in full. Numbers in the right-hand columns refer to files 01 through 06.

---

# Part 1 — Symbols

## Systems and equations

| Symbol | What it means | File |
|---|---|---|
| $a,b,c,\ldots$ | Variables in a system — prices, unknowns, coordinates | 02 |
| $a+b=10$ | A linear equation: variables scaled by numbers, then added | 02 |
| $(8,2)$ | A solution, written as an ordered pair or triple | 02 |
| $\infty$ | "Infinitely many solutions" — one of the three possible outcomes | 02, 03 |

## Geometry

| Symbol | What it means | File |
|---|---|---|
| $b=(\text{slope})\,a+(\text{intercept})$ | An equation rewritten to reveal its line | 03 |
| $(a,b)$ | A point in 2D; a solution of a 2-variable system | 03 |
| $(a,b,c)$ | A point in 3D; a solution of a 3-variable system | 03 |

## Matrices

| Symbol | What it means | File |
|---|---|---|
| A grid of numbers, e.g. rows $[1,1]$ and $[1,2]$ | The coefficient matrix — coefficients only, constants stripped away | 04 |
| $a,b,c,d$ | Generic labels for a 2×2 matrix: top-left, top-right, bottom-left, bottom-right | 04, 06 |
| $a,b,c,d,e,f,g,h,i$ | Generic labels for a 3×3 matrix, read row by row | 06 |

## Rows and dependence

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $R_1,R_2,R_3$ | "row 1", "row 2", "row 3" | A row of a matrix, referred to by number | 05 |
| $[a,b]$ | "the row a, b" | A row vector, written as a bracketed list | 05 |
| $k$ | "k" | The scalar multiplier in the row-multiple test | 05, 06 |
| $c_1,c_2,c_3,\ldots$ | — | The numbers scaling each row in a linear combination | 05 |
| $M_1,M_2,\ldots$ | "matrix 1", "matrix 2" | A matrix, referred to by number, in a worked example or quiz | 05, 06 |

## The determinant

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $\det$ | "the determinant of" | One number computed from a matrix that tests singularity | 06 |
| $ad-bc$ | — | The 2×2 determinant formula | 06 |
| $aei+bfg+cdh-ceg-afh-bdi$ | — | The 3×3 determinant formula (Sarrus' rule) | 06 |

## Operators and relations

| Symbol | Read as | What it means | File |
|---|---|---|---|
| $\times$ | "times" | Ordinary multiplication, or "row scaled by" in $[a,b]\times k$ | 05, 06 |
| $\iff$, $\Longleftrightarrow$ | "if and only if" | Each side implies the other — a genuine two-way rule | 02, 04, 06 |
| $\Rightarrow$ | "implies" | The left side forces the right side | throughout |
| $\neq$ | "does not equal" | — | throughout |
| $\approx$ | "is approximately" | — | 01 |
| $\infty$ | "infinity" | Infinitely many solutions | 02, 03 |

---

# Part 2 — Definitions

## Systems of sentences

**System.** Several statements considered together, as one package — judged jointly, never one at a time. *(01)*

**Complete.** Every sentence in the system adds new information, and everything gets determined. *(01)*

**Redundant.** At least one sentence repeats information the others already gave. True, but wasteful. *(01)*

**Contradictory.** The sentences cannot all be true at once — the package is broken, not just inefficient. *(01)*

**Singular.** Redundant or contradictory. A system that fails to deliver full, unique information. *(01)*

**Non-singular.** Complete. A system where every sentence pulls its weight. *(01)*

> Singular and non-singular describe the **whole system**, never a single sentence — the same sentence can sit inside a non-singular system in one context and a singular one in another.

---

## Systems of equations

**Equation.** A sentence about numbers. Translating a sentence into an equation loses nothing. *(02)*

**Linear equation.** Variables multiplied by numbers and added — nothing squared, nothing multiplied together, nothing inside a function. *(02)*

**Solution.** Values that satisfy **every** equation in the system simultaneously. Satisfying only some of them counts for nothing. *(02)*

**The trichotomy.** A linear system has exactly one solution, infinitely many, or none — never any other count, and in particular never exactly two. *(02, 03)*

> Singular does **not** mean unsolvable. It means "no unique solution" — which includes both infinitely many solutions and none at all.

---

## Geometry: lines and planes

**Line.** The complete solution set of one linear equation in two variables. *(03)*

**Slope.** How steeply a line runs, set entirely by the equation's **coefficients**. *(03, 04)*

**Intercept.** Where a line crosses the axis, set entirely by the equation's **constant**. *(03, 04)*

**Plane.** The complete solution set of one linear equation in three variables. A hyperplane is the same idea in more variables than can be drawn. *(03)*

**Solution as intersection.** Solving a system means finding the point(s) lying on every one of its lines or planes at once. *(03)*

**Why only three outcomes.** Two distinct straight lines can share at most one point — if they shared two, they would be the same line. That single fact rules out any solution count except one, infinitely many, or zero. *(03)*

---

## Matrices

**Coefficient.** A number multiplying a variable. Coefficients set an equation's slope. *(04)*

**Constant.** The number alone on the right of an equation. Constants set an equation's intercept, and nothing else. *(04)*

**Matrix.** The grid formed from a system's coefficients alone — one row per equation, one column per variable, with variable names and constants both stripped away. *(04)*

**System singular ⟺ matrix singular.** Singularity is entirely a property of the coefficients. Constants can never turn a singular system non-singular, or the reverse — they can only decide, among already-singular systems, whether the result is redundant or contradictory. *(04)*

**Homogeneous system.** Every constant on the right equals zero. *(04)*

**Trivial solution.** The all-zero point — always a solution of a homogeneous system, since $0=0$ regardless of the coefficients. Because of this, a homogeneous system can never be contradictory: only non-singular (the trivial solution alone) or singular (infinitely many, including the trivial one). *(04)*

---

## Linear dependence and independence

**Linear combination.** Any sum of rows, each first scaled by some number: $c_1R_1+c_2R_2+c_3R_3+\cdots$ *(05)*

**Linearly dependent.** Some row equals a linear combination of the others. With only two rows, this simplifies to "one row is a scalar multiple of the other." *(05)*

**Linearly independent.** No row can be written as a combination of the rest. *(05)*

**Rows dependent ⟺ matrix singular.** Dependence among the rows is exactly what makes a matrix singular — redundancy, relocated one level deeper than the system itself. *(04, 05)*

> The scalar-multiple test ("is row 2 just row 1 times some $k$?") only fully covers two rows. With three or more, check every combination — a row can depend on several others at once, not just one.

> It only takes **one** dependent row to make the whole matrix singular. The other rows don't get a vote back to non-singular.

---

## The determinant

**Determinant (2×2).** $ad-bc$ — the product of the main diagonal, minus the product of the other diagonal. *(06)*

**Determinant (3×3).** $aei+bfg+cdh-ceg-afh-bdi$ — three diagonal products added, three subtracted, using the diagonal method (Sarrus' rule). *(06)*

**Determinant ⟺ singularity.** A genuine if-and-only-if: the determinant is zero exactly when the matrix is singular, and nonzero exactly when it's non-singular. *(06)*

**Triangular matrix.** Every entry below the main diagonal is zero. Its determinant is just the product of the diagonal entries, because every other diagonal product in the formula is forced to include a zero. *(06)*

**All-zero row.** A row of nothing but zeros forces the determinant to zero automatically — every diagonal product touching that row vanishes. It's the most extreme case of a dependent row: a row carrying no information at all. *(06)*

---

## Techniques

**Extracting a matrix from a system.** Strip every equation down to its coefficients only, keeping variable order consistent, one row per equation. *(04)*

**The row-multiple test (2 rows).** Ask whether $[a,b]\times k=[c,d]$ has a solution for $k$ — check if the same $k$ satisfies both entries at once. *(05)*

**The linear-combination test (3+ rows).** Try to build one row from a scaled sum of the others; if any combination works, the rows are dependent. *(05)*

**The diagonal method.** Multiply along each diagonal of the matrix — add the ones leaning one way, subtract the ones leaning the other — to get the determinant directly, without solving anything. *(06)*

**The triangular shortcut.** If a matrix is triangular, skip the diagonal method entirely and just multiply the diagonal. *(06)*

**Sliding a system to the origin.** Set every constant to zero. This never changes whether the system is singular, but it does rule out "no solutions" as an outcome — useful for seeing a system's pure geometric shape. *(04)*

---

# The master dictionary

The same fact, traced through every file in the series. Each row is a different vocabulary for identical territory — non-singular on the left, singular on the right.

| File | Level | Non-singular | Singular |
|---|---|---|---|
| 01 | Sentences | Complete | Redundant or contradictory |
| 02 | Equations | Unique solution | Infinitely many, or none |
| 03 | Geometry | Lines/planes cross at one point | Lines/planes coincide, or never meet |
| 04 | Matrix | Non-singular matrix | Singular matrix |
| 05 | Rows | Linearly independent | Linearly dependent |
| 06 | Number | Determinant $\neq 0$ | Determinant $=0$ |

$$
\boxed{\text{Six files, one fact: does the system carry a genuinely new piece of information in every row, or not?}}
$$

---

# The distinctions most often confused

| These look alike | But | File |
|---|---|---|
| Singular vs. "no solutions" | Singular includes infinitely many solutions too — it means *no unique solution* | 02 |
| Redundant vs. contradictory | Both are singular; they're opposite failures — too little information vs. conflicting information | 01, 02 |
| $a,b,c$ as variables vs. $a,b,c$ as matrix entries | Same letters, different jobs: prices/coordinates in 02–03, generic grid positions in 04 and 06 | 02–03 vs. 04, 06 |
| Coefficients vs. constants | Only coefficients decide singular vs. non-singular; constants only decide redundant vs. contradictory | 04 |
| The row-multiple test vs. the full combination test | The multiple test (row 2 = row 1 × k) only covers 2 rows; 3+ rows need every combination checked | 05 |
| A matrix's singularity vs. its determinant | Logically identical (an *iff*), but computed completely differently — one by inspection, one by formula | 04, 06 |
| Slope vs. intercept | Slope comes from coefficients (orientation); intercept comes from constants (position) | 03, 04 |

---

# Formulas to know cold

Each formula is shown twice: once in symbols, and once with the symbols replaced by a real case from the notes.

| Formula | The same thing, with real numbers | File |
|---|---|---|
| Linear equation: number·variable + number·variable + $\cdots$ = number | $3.4a-48.99b+2c=122.5$ | 02 |
| Checking a solution | $a=8,b=2$: $8+2=10$ ✓ and $8+2(2)=12$ ✓ | 02 |
| $b=(\text{slope})\,a+(\text{intercept})$ | $a+b=10 \Rightarrow b=10-a$: slope $-1$, intercept $10$ | 03 |
| System → matrix | $a+b=10,\ a+2b=12$ → rows $[1,1]$ and $[1,2]$ | 04 |
| Row-multiple test | $[1,1]\times 2=[2,2]$ — dependent, singular | 05 |
| Linear combination | $3R_1+2R_2=R_3$ for rows $[1,0,1],[0,1,0],[3,2,3]$ | 05 |
| $\det=ad-bc$ | $1\cdot2-1\cdot1=1$ — non-singular | 06 |
| $\det=ad-bc$ | $2\cdot3-(-1)\cdot(-6)=6-6=0$ — singular | 06 |
| $\det=aei+bfg+cdh-ceg-afh-bdi$ | $[1,1,1],[1,2,1],[1,1,2]$: $(4+1+1)-(2+1+2)=1$ | 06 |
| Triangular shortcut | $[1,1,1],[0,2,2],[0,0,3]$: $\det=1\times2\times3=6$ | 06 |
| All-zero row | $[1,1,1],[0,2,2],[0,0,0]$: $\det=0$ automatically | 06 |
| Homogeneous system | $a+b=0,\ a+2b=0$: the trivial solution $(0,0)$ always works | 04 |

## Reading the table

The left column is what you write down. The right column is what it actually **means** — and if you can rebuild the right column from the left, you know the formula rather than just recognizing it.

When a formula stops making sense, go back to its concrete case and re-derive it from there.
