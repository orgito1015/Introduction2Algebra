# 📘 Introduction to Algebra — Lecture Notes Guide
### Department of Mathematics | Prof. Rigena Sema

> **How to use this guide:** This document explains every topic covered in the lecture PDFs in this folder — in plain English, with examples and intuition. Think of it as sitting in the front row and having the professor explain everything *twice*, more slowly. Whether you are reviewing before an exam or seeing this material for the first time, read through each section in order — they build on each other.

---

## 📚 Table of Contents

1. [Sets (Bashkësitë)](#1-sets)
2. [Numbers & Number Theory (Numrat)](#2-numbers--number-theory)
3. [Relations (Relacionet)](#3-relations)
4. [Functions (Funksionet)](#4-functions)
5. [Congruences (Kongruencat)](#5-congruences-modular-arithmetic)
6. [Rings (Unazat)](#6-rings)
7. [Seminar & Practice Problems](#7-seminars--practice-problems)

---

## 1. Sets

> 📄 *Source: Bashkesite Leksion.pdf*

### What is a Set?

A **set** is simply a well-defined collection of objects. Those objects are called **elements** of the set.

- If `x` is an element of set `A`, we write: `x ∈ A` (read: "*x belongs to A*")
- If `x` is **not** in set `A`, we write: `x ∉ A`
- Elements are usually denoted with lowercase letters: `a, b, c, ...`
- Sets themselves are denoted with uppercase letters: `A, B, C, ...`

### How to Describe a Set

There are two ways to write a set:

**1. Roster Notation** — just list the elements inside curly braces:
```
A = {1, 2, 3, 4, 5, 6}
```

**2. Set-Builder Notation** — describe the rule that elements must satisfy:
```
A = { x | x is a positive integer less than or equal to 6 }
  = { x | x ∈ ℤ and 0 < x ≤ 6 }
```
Both of these describe the exact same set.

### Important Number Sets

| Symbol | Name | Contents |
|--------|------|----------|
| `ℕ` | Natural numbers | {1, 2, 3, 4, ...} |
| `ℤ` | Integers | {..., −2, −1, 0, 1, 2, ...} |
| `ℚ` | Rational numbers | Fractions p/q where p, q ∈ ℤ, q ≠ 0 |
| `ℝ` | Real numbers | All numbers on the number line |
| `ℂ` | Complex numbers | Numbers of the form a + bi |

### Cardinality (Size of a Set)

The **cardinality** of set `A`, written `|A|` or `car(A)`, is the number of elements in `A`.

- If a set has a finite number of elements → it's a **finite set**
- If a set has infinitely many elements → it's an **infinite set**
- The set with **no elements** is the **empty set**, written `∅` or `{}`

> 💡 **Key fact:** The empty set is unique. There is only one empty set. *(Proof: if ∅₁ and ∅₂ are both empty, then each is a subset of the other, so they are equal.)*

### Subsets

Set `B` is a **subset** of set `A` (written `B ⊆ A`) if every element of `B` is also in `A`.

```
B ⊆ A  means:  for all x, if x ∈ B then x ∈ A
```

**Example:**
- `{1, 3} ⊆ {1, 2, 3, 4}` ✓
- `{1, 5} ⊆ {1, 2, 3, 4}` ✗  (5 is not in the second set)

> 🔑 Two sets are **equal** (`A = B`) if and only if `A ⊆ B` and `B ⊆ A`. Every element of `A` is in `B`, and every element of `B` is in `A`.

### Set Operations

| Operation | Symbol | Meaning |
|-----------|--------|---------|
| Union | `A ∪ B` | Elements in `A` **or** `B` (or both) |
| Intersection | `A ∩ B` | Elements in both `A` **and** `B` |
| Difference | `A \ B` | Elements in `A` but **not** in `B` |
| Complement | `Aᶜ` | Elements **not** in `A` (relative to a universe) |

### Cartesian Product

The **Cartesian product** `A × B` is the set of all ordered pairs `(a, b)` where `a ∈ A` and `b ∈ B`:

```
A × B = { (a, b) | a ∈ A and b ∈ B }
```

**Example:** If `A = {1, 2}` and `B = {x, y}`, then:
```
A × B = { (1,x), (1,y), (2,x), (2,y) }
```

---

## 2. Numbers & Number Theory

> 📄 *Source: Numrat leksion.pdf*

### The Division Theorem

This is one of the most fundamental theorems in all of mathematics. It says:

> For any two natural numbers `a ≠ 0` and `b`, there exist **unique** integers `q ≥ 0` and `0 ≤ r < a` such that:
> ```
> b = a·q + r
> ```

Here, `q` is the **quotient** and `r` is the **remainder**.

**Example:** Divide 17 by 5:
```
17 = 5 · 3 + 2     →   q = 3,  r = 2
```

**Why it matters:** This theorem is the foundation of everything else in number theory — GCD, prime factorization, modular arithmetic — it all builds on this.

### Divisibility

We say `a` **divides** `b` (written `a | b`) if the remainder when dividing `b` by `a` is zero.

**Examples:**
- `3 | 12` ✓ (because 12 = 3 × 4, remainder 0)
- `4 | 10` ✗ (because 10 = 4 × 2 + 2, remainder is 2)

### Prime Numbers

A number `a > 1` is **prime** if it has no divisors other than `1` and itself.

**Examples of primes:** 2, 3, 5, 7, 11, 13, 17, 19, ...

A number greater than 1 that is **not** prime is called **composite**.

> 💡 Think of prime numbers as the "atoms" of arithmetic — every number can be broken down into primes.

### Greatest Common Divisor (GCD)

The **GCD** of `a` and `b` — written `gcd(a, b)` or `pmp(a, b)` in Albanian — is the largest integer that divides both `a` and `b`.

**Important property:** Two numbers `a` and `b` are called **coprime** (relatively prime) if `gcd(a, b) = 1`.

**Examples:**
- `gcd(12, 8) = 4`
- `gcd(9, 14) = 1` → these are coprime

### The Euclidean Algorithm

This is an efficient method for finding `gcd(a, b)`:

1. Divide the larger by the smaller, find the remainder
2. Replace the larger number with the smaller, and the smaller with the remainder
3. Repeat until the remainder is 0
4. The last non-zero remainder is the GCD

**Example:** Find `gcd(25, 18)`:
```
25 = 18 · 1 + 7
18 = 7  · 2 + 4
7  = 4  · 1 + 3
4  = 3  · 1 + 1
3  = 1  · 3 + 0   ← stop here
```
The last non-zero remainder is **1**, so `gcd(25, 18) = 1` (they are coprime!).

### Bézout's Identity

If `gcd(a, b) = d`, then there exist integers `u, v` (called **Bézout coefficients**) such that:
```
a·u + b·v = d
```

**Example:** Since `gcd(25, 18) = 1`, we can find u, v such that `25u + 18v = 1`:
```
Working backwards through the Euclidean Algorithm:
1 = 4 − 3·1
  = 4 − (7 − 4·1)·1     = 4·2 − 7
  = (18 − 7·2)·2 − 7    = 18·2 − 7·5
  = 18·2 − (25−18)·5    = 18·7 − 25·5
So: 25·(−5) + 18·7 = 1
```

This is also called the **extended Euclidean algorithm** and it's essential for solving congruences.

### Fundamental Theorem of Arithmetic

> Every integer greater than 1 can be written **uniquely** as a product of prime numbers (up to the order of factors).

**Examples:**
```
12 = 2² · 3
60 = 2² · 3 · 5
360 = 2³ · 3² · 5
```

---

## 3. Relations

> 📄 *Source: Relacionet Leksion.pdf, Seminar relacionet.pdf, Uhstrime relacionet dore.pdf*

### What is a Binary Relation?

A **binary relation** from set `X` to set `Y` is a triple `ρ = (X, Y, G)` where `G ⊆ X × Y` is the **graph** of the relation.

When `(x, y) ∈ G`, we write `xρy` and say "*x is related to y by ρ*."

- `X` is called the **source** (domain/starting set)
- `Y` is called the **target** (codomain/ending set)
- `G` is the **graph** (the actual set of pairs)

**Example:**
Let `A = {2, 4, 6, 8, 10}`, `B = {1, 2, 3, 4, 5}`, and `G = {(2,1), (4,2), (6,3), (8,4), (10,5)}`.

Then `ρ = (A, B, G)` is a relation that pairs each even number with half its value.

### Inverse Relation

If `ρ = (X, Y, G)` is a relation, its **inverse** `ρ⁻¹ = (Y, X, G⁻¹)` is defined by:
```
G⁻¹ = { (y, x) | (x, y) ∈ G }
```
Simply reverse all the pairs!

> 🔑 The inverse of the inverse gets you back: `(ρ⁻¹)⁻¹ = ρ`

### Types of Relations (on a single set X)

When `ρ` is a relation **on a set `X`** (meaning `X = Y`), it can have special properties:

| Property | Definition | In Words |
|----------|------------|----------|
| **Reflexive** | `∀x ∈ X: xρx` | Every element is related to itself |
| **Symmetric** | `∀x,y ∈ X: xρy ⟹ yρx` | If x relates to y, then y relates to x |
| **Antisymmetric** | `∀x,y: xρy and yρx ⟹ x = y` | Mutual relation only if they're equal |
| **Transitive** | `∀x,y,z: xρy and yρz ⟹ xρz` | Chains of relations connect the endpoints |

### Equivalence Relations

A relation is an **equivalence relation** if it is **reflexive, symmetric, and transitive** — all three at once.

**Classic example:** "has the same remainder when divided by 5"
- Reflexive: Every number has the same remainder as itself ✓
- Symmetric: If `x` has the same remainder as `y`, then `y` has the same as `x` ✓
- Transitive: If `x ≡ y` and `y ≡ z`, then `x ≡ z` ✓

### Equivalence Classes

When `ρ` is an equivalence relation, the **equivalence class** of an element `a` is:
```
[a] = { b ∈ X | a ρ b }
```
— the set of all elements equivalent to `a`.

Key facts:
- Every element belongs to exactly one equivalence class
- Two equivalence classes are either equal or completely disjoint
- The equivalence classes **partition** the set (they cover it with no overlaps)

The collection of all equivalence classes is the **quotient set** `X/ρ`.

### Order Relations

A relation is a **partial order** if it is **reflexive, antisymmetric, and transitive**.

**Example:** `≤` on real numbers is an order relation.

---

## 4. Functions

> 📄 *Source: Funksionet Leksion.pdf*

### What is a Function?

A **function** `f: X → Y` is a relation `(X, Y, G)` where **every element of `X` is paired with exactly one element of `Y`**.

- Each element `x ∈ X` has **one and only one** partner `y ∈ Y`
- We write `f(x) = y`, and call `y` the **image** (output) of `x`
- `x` is called the **pre-image** (input)
- `X` is the **domain**, `Y` is the **codomain**

**Not a function:** If some `x` maps to two different `y` values — that breaks the "exactly one" rule.

**Not a function:** If some `x` maps to nothing at all — that also breaks it.

### Image and Pre-Image

For a function `f: X → Y` and a subset `A ⊆ X`:

- **Direct image**: `f(A) = { y ∈ Y | ∃x ∈ A, y = f(x) }` — all outputs from inputs in `A`
- **Inverse image**: `f⁻¹(B) = { x ∈ X | f(x) ∈ B }` — all inputs whose outputs land in `B`
- **Image of f** (= range): `Im(f) = f(X)` — all possible outputs of `f`

### Types of Functions

#### Injective (One-to-One)
`f` is **injective** if different inputs always give different outputs:
```
f(x₁) = f(x₂)  ⟹  x₁ = x₂
```
> Think: no two `x` values share the same `y` value. Each output comes from at most one input.

#### Surjective (Onto)
`f` is **surjective** if every element of `Y` is hit by at least one `x`:
```
∀y ∈ Y, ∃x ∈ X such that f(x) = y
```
> Think: the image of `f` equals the entire codomain `Y`. Nothing in `Y` is "missed."

#### Bijective (One-to-One and Onto)
`f` is **bijective** if it is both injective AND surjective.

> 🏆 A bijection is a perfect pairing — every element of `X` maps to a unique element of `Y`, and every element of `Y` is hit. It's like a perfect seating arrangement where every seat is taken by exactly one person.

### Composition of Functions

If `f: X → Y` and `g: Y → Z`, the **composition** `g ∘ f: X → Z` is defined by:
```
(g ∘ f)(x) = g(f(x))
```
First apply `f`, then apply `g` to the result.

> ⚠️ Order matters! `g ∘ f ≠ f ∘ g` in general.

### Inverse Function

If `f: X → Y` is a **bijection**, then its **inverse function** `f⁻¹: Y → X` is the function that "undoes" `f`:
```
f⁻¹(y) = x  ⟺  f(x) = y
```

Properties:
- `f⁻¹ ∘ f = id_X` (the identity on X)
- `f ∘ f⁻¹ = id_Y` (the identity on Y)

---

## 5. Congruences (Modular Arithmetic)

> 📄 *Source: Kongruencat Lkesion.pdf, Ushtrime pë kongruencën.pdf*

### What Does "Congruent mod n" Mean?

Two integers `a` and `b` are **congruent modulo n** (written `a ≡ b (mod n)`) if `n` divides their difference:
```
a ≡ b (mod n)  ⟺  n | (a − b)
```

**Four equivalent ways to say the same thing:**
1. `n` divides `a − b`
2. `a` and `b` leave the **same remainder** when divided by `n`
3. `b` is in the arithmetic progression `{a + nk | k ∈ ℤ}`
4. `a` and `b` belong to the same equivalence class modulo `n`

**Examples:**
```
1325 ≡ 2  (mod 9)    because 1325 − 2 = 1323 = 9 × 147
3    ≡ −1 (mod 4)    because 3 − (−1) = 4 = 4 × 1
13   ≡ 0  (mod 13)   because 13 − 0 = 13 = 13 × 1
```

### Properties of Congruences

1. **Scaling:** If `a ≡ b (mod n)`, then `ka ≡ kb (mod n)` for any integer `k`
   - ⚠️ The reverse is NOT always true!

2. **Congruence is an equivalence relation** (reflexive, symmetric, transitive)

3. **Compatible with arithmetic:** If `a ≡ a' (mod n)` and `b ≡ b' (mod n)`, then:
   - `a + b ≡ a' + b' (mod n)` — you can add congruences
   - `a · b ≡ a' · b' (mod n)` — you can multiply congruences

### Congruence Classes and ℤₙ

The congruence class of `a` mod `n` is:
```
ā = { b ∈ ℤ | a ≡ b (mod n) } = { a + kn | k ∈ ℤ }
```

The quotient set `ℤ/ρₙ` has exactly `n` classes:
```
ℤₙ = { 0̄, 1̄, 2̄, ..., n̄−1 }
```

**Example with n = 4:**
```
ℤ₄ = { 0̄, 1̄, 2̄, 3̄ }
0̄ = {..., −4, 0, 4, 8, 12, ...}
1̄ = {..., −3, 1, 5, 9, 13, ...}
2̄ = {..., −2, 2, 6, 10, 14, ...}
3̄ = {..., −1, 3, 7, 11, 15, ...}
```

### Solving Linear Congruences

**Problem:** Solve `ax ≡ b (mod n)` for `x`.

**Theorem:** The congruence `ax ≡ b (mod n)` has a solution **if and only if** `gcd(a, n) | b`.

**Method (using Bézout's Identity):**

1. Use the Euclidean Algorithm to find `gcd(a, n)`
2. Check whether `gcd(a, n)` divides `b`
3. Use back-substitution (Bézout) to write `gcd(a, n) = au + nv`
4. Multiply through by `b / gcd(a, n)` to get a solution

**Worked Example:** Solve `18x ≡ 1 (mod 25)`

*Step 1 — Euclidean Algorithm:*
```
25 = 18·1 + 7
18 = 7·2  + 4
7  = 4·1  + 3
4  = 3·1  + 1    ← gcd(18, 25) = 1
3  = 1·3  + 0
```
`gcd(18, 25) = 1`, and `1 | 1`, so a solution exists.

*Step 2 — Bézout back-substitution:*
```
1 = 4 − 3·1
  = 4 − (7 − 4)·1         = 4·2 − 7
  = (18 − 7·2)·2 − 7      = 18·2 − 7·5
  = 18·2 − (25 − 18)·5    = 18·7 − 25·5
```
So: `18·7 + 25·(−5) = 1`, meaning `18·7 ≡ 1 (mod 25)`.

**Solution:** `x ≡ 7 (mod 25)`, i.e., all integers of the form `7 + 25k`.

---

## 6. Rings

> 📄 *Source: Unazat leksion.pdf, Seminare Unazat.pdf*

### What is a Ring?

A **ring** is a set `R` with two operations, addition (`+`) and multiplication (`·`), satisfying these axioms:

**Addition axioms (R forms an abelian group under +):**
1. **Associativity of addition:** `(a + b) + c = a + (b + c)`
2. **Zero element (additive identity):** `∃θ ∈ R` such that `θ + a = a + θ = a` for all `a`
3. **Additive inverse:** For every `a ∈ R`, `∃b ∈ R` such that `a + b = b + a = θ`
4. **Commutativity of addition:** `a + b = b + a`

**Multiplication axioms:**

5. **Associativity of multiplication:** `(a · b) · c = a · (b · c)`
6. **Distributivity (left and right):** `a(b + c) = ab + ac` and `(a + b)c = ac + bc`

> 🧠 **Think of it this way:** A ring is a system where you can add, subtract, and multiply — but you can't necessarily divide. The integers ℤ are the classic example of a ring.

### Special Types of Rings

| Type | Extra Condition |
|------|----------------|
| **Commutative ring** | `a · b = b · a` for all `a, b` |
| **Ring with unity (unital ring)** | `∃e ∈ R` (the "1") such that `e · a = a · e = a` |
| **Integral domain** | Commutative, unital, no zero divisors |
| **Field** | Commutative, unital, every non-zero element has a multiplicative inverse |

### Zero Divisors

An element `a ≠ 0` in ring `R` is a **zero divisor** if there exists `b ≠ 0` such that `a · b = 0`.

**Example in ℤ₈:** `2̄ · 4̄ = 8̄ = 0̄`, but `2̄ ≠ 0̄` and `4̄ ≠ 0̄` — so `2̄` (and `4̄`) are zero divisors in ℤ₈.

### Examples of Rings

| Ring | Commutative? | Has 1? | Integral Domain? | Field? |
|------|-------------|--------|-----------------|--------|
| `ℤ` (integers) | ✓ | ✓ | ✓ | ✗ (no inverse for 2) |
| `ℚ` (rationals) | ✓ | ✓ | ✓ | ✓ |
| `ℝ` (reals) | ✓ | ✓ | ✓ | ✓ |
| `ℤₙ` (n prime) | ✓ | ✓ | ✓ | ✓ |
| `ℤₙ` (n composite) | ✓ | ✓ | ✗ (has zero divisors) | ✗ |
| `M₂(ℤ)` (2×2 matrices) | ✗ | ✓ | ✗ | ✗ |
| `2ℤ` (even integers) | ✓ | ✗ | ✓ | ✗ |

### Properties that Follow from the Ring Axioms

These can all be **proved** from the axioms alone — you don't need to assume them:

- `a · 0 = 0 · a = 0` for all `a` (multiplying by zero gives zero)
- `(−a) · b = a · (−b) = −(a · b)` (negative × positive = negative)
- `(−a) · (−b) = a · b` (negative × negative = positive)
- Multiplication distributes over subtraction: `a(b − c) = ab − ac`

### Invertible Elements (Units)

In a **ring with unity**, element `b` is the **multiplicative inverse** of `a` if:
```
a · b = b · a = e  (where e is the multiplicative identity, "1")
```
We write `b = a⁻¹`.

**Examples:**
- In ℤ: only `1` and `−1` have inverses (since `1·1 = 1` and `(−1)·(−1) = 1`)
- In ℝ: every non-zero number `a` has inverse `1/a`
- In ℤₙ: element `ā` has an inverse **if and only if** `gcd(a, n) = 1`

### The Ring ℤₙ

The set `ℤₙ = {0̄, 1̄, 2̄, ..., n̄−1}` with addition and multiplication modulo `n` is a ring.

**Key theorem:**
> `ℤₙ` is a **field** if and only if `n` is a **prime number**.

**Why?** When `n` is prime, every non-zero element is coprime to `n`, so every non-zero element has a multiplicative inverse. When `n` is composite, there are zero divisors.

**Finding the inverse of `ā` in ℤₙ:**
Use the **Euclidean Algorithm + Bézout's Identity**:
1. Verify `gcd(a, n) = 1` (if not, no inverse exists)
2. Find `u, v` such that `au + nv = 1` (Bézout's identity)
3. Then `ā⁻¹ = ū` in ℤₙ

**Worked Example:** Find `10̄⁻¹` in ℤ₇₇:

```
Euclidean Algorithm:
77 = 10·7 + 7
10 = 7·1  + 3
7  = 3·2  + 1    ← gcd(10, 77) = 1
3  = 1·3  + 0

Bézout back-substitution:
1 = 7 − 3·2
  = 7 − (10 − 7)·2      = 7·3 − 10·2
  = (77 − 10·7)·3 − 10·2 = 77·3 − 10·23
```
So `10·(−23) + 77·3 = 1`, meaning `10·(−23) ≡ 1 (mod 77)`.
Since `−23 ≡ 54 (mod 77)`, the inverse is `10̄⁻¹ = 54̄`.

### Fields

A **field** is a commutative ring with unity in which every non-zero element has a multiplicative inverse.

**In a field, you can do all four arithmetic operations:** add, subtract, multiply, and divide (by non-zero elements).

Examples: `ℚ, ℝ, ℂ, ℤₚ` (for prime `p`)

---

## 7. Seminars & Practice Problems

> 📄 *Source: Seminar relacionet.pdf, Seminare Unazat.pdf, Ushtrime pë kongruencën.pdf*

The seminars and exercise sheets focus on applying the lecture material. Here is a summary of the key problem types you will encounter:

### Relations Practice

**Problem type:** Given a relation `ρ` on ℤ, prove or disprove it is an equivalence relation.

**Method:**
1. Check **reflexivity**: Is `xρx` true for all `x`?
2. Check **symmetry**: Does `xρy` always imply `yρx`?
3. Check **transitivity**: Does `xρy` and `yρz` always imply `xρz`?

**Example (from seminar):** Let `ρ` be defined on ℤ by: `xρy ⟺ 5 | (x − y)`

- **Reflexive:** `x − x = 0 = 5·0`, so `5 | 0` ✓
- **Symmetric:** If `5 | (x − y)`, then `x − y = 5k`, so `y − x = −5k = 5(−k)`, thus `5 | (y − x)` ✓
- **Transitive:** If `5 | (x−y)` and `5 | (y−z)`, then `x − z = (x − y) + (y − z)` is divisible by 5 ✓

This is an equivalence relation! (In fact, it's just congruence mod 5.)

### Rings Practice

**Problem type:** Verify that a given set with two operations forms a ring.

**Method:** Check each of the 6 ring axioms systematically.

**Problem type:** Show whether `ℤₙ` is a field.

**Method:** Check whether `n` is prime. If yes → field. If no → find zero divisors.

### Congruences Practice

**Problem type:** Find inverses in `ℤₙ`.

**Method:** Use the Euclidean Algorithm to check coprimality, then Bézout's identity to find the inverse.

**Problem type:** Find all zero divisors of `ℤₙ`.

**Key fact:** `ā ≠ 0̄` is a zero divisor in `ℤₙ` if and only if `gcd(a, n) > 1`.

**Example:** Find zero divisors of ℤ₄:
- `1̄`: gcd(1, 4) = 1 → has inverse, not a zero divisor
- `2̄`: gcd(2, 4) = 2 ≠ 1 → zero divisor (`2̄ · 2̄ = 4̄ = 0̄`)
- `3̄`: gcd(3, 4) = 1 → has inverse, not a zero divisor

So the only zero divisor in ℤ₄ is `2̄`.

---

## 🗂️ Files in This Folder

| File | Content |
|------|---------|
| `Bashkesite Leksion.pdf` | Set theory lecture (12 pages) |
| `Numrat leksion.pdf` | Number theory lecture (10 pages) |
| `Relacionet Leksion.pdf` | Relations lecture (10 pages) |
| `Funksionet Leksion.pdf` | Functions lecture (13 pages) |
| `Kongruencat Lkesion.pdf` | Congruences lecture (12 pages) |
| `Unazat leksion.pdf` | Rings lecture (15 pages) |
| `Seminare Unazat.pdf` | Rings seminar with exercises (15 pages) |
| `Seminar relacionet.pdf` | Relations seminar with exercises (3 pages) |
| `Ushtrime pë kongruencën.pdf` | Congruence exercises (3 pages) |
| `Ushtrime pë kongruencën (2).pdf` | More congruence exercises (3 pages) |
| `Uhstrime relacionet dore.pdf` | Handwritten relations exercises (11 pages) |
| `aglebra 1.pdf` | Main textbook (42 pages, scanned) |

---

## 🔗 How the Topics Connect

```
Sets
 └─► Relations  (a relation is a subset of a Cartesian product)
      └─► Functions  (a function is a special type of relation)
           └─► Rings  (rings use functions/operations on sets)
                └─► Fields  (a field is a special ring)

Numbers
 └─► GCD / Euclidean Algorithm
      └─► Bézout's Identity
           └─► Congruences  (modular arithmetic)
                └─► ℤₙ is a ring / field
```

> **Big picture:** Everything in this course is about taking a simple idea (a set of objects), adding structure to it (operations, relations, constraints), and studying the beautiful patterns that emerge. Sets are the raw material. Relations add connections. Functions are special relations. Rings formalize arithmetic. Congruences let you do arithmetic in finite systems. It all fits together.

---

*Notes compiled from lecture materials by Prof. Rigena Sema, Department of Mathematics, FSHN.*
