# Formal Logic Fundamentals: A 14-Lecture Audio Course

> **Source conversation:** https://claude.ai/chat/13aa4f73-9c4f-4fe5-9f67-00cf06857d5f  
> **Created:** February 5, 2026  
> **Format:** Spoken-word lecture scripts (DOCX)  
> **Scope:** ~30,000 words — complete 14-lecture graduate course  
> **Level:** Advanced undergraduate / beginning graduate

---

## Course Overview

This course covers mathematical logic from propositional logic through Gödel's incompleteness theorems, Cohen's forcing, and large cardinal axioms. It is designed for spoken delivery, with each lecture approximately 45–60 minutes of audio content. The course assumes basic mathematical maturity but no prior formal logic.

---

## Lecture 1: Propositional Logic

Welcome to Formal Logic Fundamentals. This first lecture introduces propositional logic — the simplest formal system, but the foundation for everything that follows.

**Syntax.** The language of propositional logic has atomic propositions — P, Q, R, and so on — and connectives: negation (not), conjunction (and), disjunction (or), and implication (if-then). A formula is built from atoms using connectives.

**Semantics.** A truth assignment gives each atomic proposition a truth value — true or false. A formula is true or false under each truth assignment. The connectives are defined by truth tables.

**Tautology.** A formula is a tautology if it is true under every truth assignment. The law of excluded middle — P or not-P — is a tautology. The law of non-contradiction — not both P and not-P — is a tautology.

**Logical equivalence.** Two formulas are logically equivalent if they have the same truth value under every truth assignment.

---

## Lecture 2: Propositional Proof Theory

A proof system gives rules for deriving formulas from other formulas. The goal: a proof system that is sound (only derives tautologies) and complete (derives every tautology).

**Natural deduction.** Proofs are derivations using introduction and elimination rules for each connective. The conjunction introduction rule: from A and B, derive A and B. The implication elimination rule (modus ponens): from A and A-implies-B, derive B.

**Soundness theorem.** If A is provable, then A is a tautology.

**Completeness theorem for propositional logic.** If A is a tautology, then A is provable. This means truth and provability coincide in propositional logic.

---

## Lecture 3: First-Order Logic — Syntax

First-order logic extends propositional logic with quantifiers over a domain of individuals.

**Signatures.** A signature specifies constant symbols, function symbols with arities, and relation symbols with arities. For groups: one constant (identity), one binary function (multiplication), one unary function (inverse).

**Terms.** Variables and constants are terms. If f is an n-ary function symbol and t_1,...,t_n are terms, then f(t_1,...,t_n) is a term.

**Formulas.** Atomic formulas are R(t_1,...,t_n) for a relation symbol R and terms t_i. Formulas are built from atomic formulas using negation, conjunction, disjunction, implication, and quantifiers: (∀x)φ and (∃x)φ.

**Free and bound variables.** A variable is free in a formula if it occurs outside any quantifier binding it. A sentence is a formula with no free variables.

---

## Lecture 4: First-Order Logic — Semantics

**Structures.** A structure M for a signature consists of a non-empty domain M, an interpretation of each constant as an element of M, each n-ary function symbol as an n-ary function on M, and each n-ary relation symbol as an n-ary relation on M.

**Satisfaction.** The satisfaction relation M ⊨ φ[a] (M satisfies φ under assignment a) is defined inductively on the structure of φ.

**Validity.** A sentence φ is valid (a logical truth) if M ⊨ φ for every structure M.

**Logical consequence.** φ is a logical consequence of a theory T if every model of T satisfies φ.

---

## Lecture 5: Proof Theory and Gödel's Completeness Theorem

**Natural deduction for FOL.** Extends propositional natural deduction with quantifier rules.

**Gödel's Completeness Theorem (1930).** A first-order sentence is provable from a theory T if and only if it holds in every model of T. Equivalently: a consistent theory has a model.

*Proof sketch.* Given a consistent theory T, we build a canonical model — the Henkin model — by adding witnesses for all existential statements and taking equivalence classes of terms. The key insight: add constants c_φ for each formula (∃x)φ and add the axioms φ(c_φ). The resulting extended theory is still consistent. Its term model satisfies T.

**Consequences.** The completeness theorem means first-order logic is exactly right: the proof system captures all semantic consequences. Every consistent first-order theory has a model.

---

## Lecture 6: Axiomatic Set Theory — ZFC

**Why axiomatize set theory?** Naive set theory leads to paradoxes. Russell's paradox: the set R = {x : x ∉ x} — if R ∈ R then R ∉ R, and vice versa.

**The ZFC axioms.**

*Extensionality:* Two sets are equal iff they have the same elements. A set is completely determined by its members.

*Empty Set:* There exists a set with no elements — the empty set.

*Pairing:* For any a and b, the set {a, b} exists.

*Union:* For any set a, the union ∪a — the set of all elements of elements of a — exists.

*Power Set:* For any set a, the power set P(a) — all subsets of a — exists.

*Infinity:* There exists an infinite set. Specifically: there is a set containing ∅ and closed under the successor operation a ↦ a ∪ {a}.

*Replacement:* If F is a definable function (given by a formula) and a is a set, then {F(x) : x ∈ a} is a set.

*Foundation (Regularity):* Every non-empty set has an element disjoint from it. This prevents infinite descending ∈-chains.

*Separation schema:* For any set a and formula φ, {x ∈ a : φ(x)} is a set.

**The Axiom of Choice.** For any collection of non-empty sets, there exists a function choosing one element from each. Equivalent to Zorn's Lemma and the Well-Ordering Theorem. Independent of ZF.

---

## Lecture 7: Ordinals and Cardinals

**Well-ordering.** A total order where every non-empty subset has a least element. The natural numbers under their usual order are well-ordered. The integers are not.

**Ordinal numbers.** Von Neumann ordinals: 0 = ∅, 1 = {0}, 2 = {0,1}, 3 = {0,1,2}, ω = {0,1,2,...}, ω+1 = {0,1,...,ω}, ...

Every well-ordered set is order-isomorphic to a unique ordinal.

**Transfinite induction.** To prove a property P holds for all ordinals, prove: P(0); if P(α) then P(α+1); if P(β) for all β < λ (limit ordinal λ), then P(λ).

**Cardinal numbers.** Cardinals measure size. Two sets have the same cardinality iff there is a bijection between them. A cardinal is an ordinal not in bijection with any smaller ordinal.

**Cantor's theorem.** |P(X)| > |X| for any set X. The power set is strictly larger. Proof: the diagonal argument — the function mapping x to {x} cannot be surjective.

**The continuum hypothesis (CH).** There is no cardinal strictly between ℵ_0 (the cardinality of ℕ) and 2^{ℵ_0} (the cardinality of ℝ). Equivalently: 2^{ℵ_0} = ℵ_1.

---

## Lecture 8: Introduction to Model Theory

**Models of a theory.** A model of first-order theory T is a structure satisfying all axioms of T.

**Elementary equivalence.** Structures M and N are elementarily equivalent (M ≡ N) if they satisfy the same first-order sentences.

**Complete theory.** A theory T is complete if for every sentence φ, either T ⊨ φ or T ⊨ ¬φ. The theory of an individual structure M (all sentences true in M) is always complete.

**Compactness theorem.** A set Σ of sentences has a model iff every finite subset has a model.

*Proof:* By the completeness theorem, if every finite subset is consistent, so is Σ. Hence Σ has a model.

**Löwenheim-Skolem theorem (downward).** If a countable theory has an infinite model, it has a countable model.

**Löwenheim-Skolem theorem (upward).** If a theory has an infinite model, it has models of every infinite cardinality.

**Skolem's paradox.** ZFC has a countable model (by downward L-S), yet ZFC proves the uncountable set ℝ exists. Resolution: "uncountable" is relative to the model — inside the countable model, there is no bijection with ℕ, but from outside there is.

---

## Lecture 9: Computability Theory

**Turing machines.** A Turing machine has a tape (infinite in one direction), a read/write head, a finite set of states, and a transition function. It computes by reading a symbol, possibly writing a new symbol, moving left or right, and transitioning to a new state.

**Computable functions.** A function is computable (recursive) if some Turing machine computes it.

**The halting problem.** Does a given Turing machine M halt on input w? There is no algorithm to decide this for all M, w.

*Proof:* Suppose algorithm H decides the halting problem. Construct machine D: on input M, run H on (M, M). If H says M halts on M, loop forever. If H says M doesn't halt on M, halt. Now run D on D. If D halts on D, D loops — contradiction. If D doesn't halt on D, D halts — contradiction.

**Church-Turing thesis.** Every effectively computable function is computable by a Turing machine. This is not provable — it is a thesis about the nature of computation.

**Undecidability of first-order logic.** The set of valid first-order sentences is not decidable. (It is computably enumerable — we can enumerate all proofs — but its complement is not.)

---

## Lecture 10: Recursion Theory and Arithmetic

**Primitive recursive functions.** Built from zero, successor, and projection by composition and primitive recursion. Include all common arithmetic functions.

**Recursive functions.** Extend primitive recursive functions with minimization (unbounded search). Equivalent to Turing computability.

**Peano arithmetic (PA).** The standard axioms for arithmetic: zero and successor axioms, plus induction schema. PA is strong enough to formalize much of mathematics.

**Gödel numbering.** Assign natural numbers to symbols, formulas, and proofs in a systematic way. The number of a formula φ is written ⌈φ⌉. This allows arithmetic to talk about its own syntax.

**Representability.** A relation R is representable in PA if there is a formula φ(x_1,...,x_n) such that PA proves φ(n_1,...,n_k) iff R(n_1,...,n_k) holds.

**Diagonal lemma (fixed-point lemma).** For any formula φ(x) with one free variable, there is a sentence G such that PA proves: G ↔ φ(⌈G⌉). A sentence can assert something about its own Gödel number.

---

## Lecture 11: Gödel's First Incompleteness Theorem

**Setup.** Let T be a consistent, recursively axiomatized extension of PA. (Recursively axiomatized means we can mechanically check whether something is an axiom.)

**The Gödel sentence.** By the diagonal lemma, there is a sentence G such that T proves: G ↔ "G is not provable in T."

**The theorem.** If T is consistent, then T neither proves nor disproves G.

*Proof that T ⊬ G:* Suppose T proves G. Since G says "I am not provable," and T proves G, G is provable, which G says is false — a contradiction. So T is inconsistent. Contrapositive: if T is consistent, T ⊬ G.

*Proof that T ⊬ ¬G:* (Assuming T is ω-consistent, or using the Rosser trick for simple consistency.) If T proves ¬G, then T proves "G is provable." But if we ever produce an actual proof of G, T proves a contradiction. More carefully: ¬G says "G is provable," meaning some natural number codes a proof of G. If T ⊢ ¬G, then T says some number codes a proof of G — but we showed T ⊬ G, so no such proof exists. Under ω-consistency, T cannot prove false existential arithmetic statements.

**The true Gödel sentence.** G is in fact true (in the standard model ℕ), since it correctly says it is not provable in T. So T is incomplete: there are true arithmetical statements T cannot prove.

---

## Lecture 12: Gödel's Second Incompleteness Theorem

**Con(T).** The consistency statement Con(T) is the arithmetic sentence asserting that T has no proof of a contradiction. It is an arithmetic statement that can be formalized using Gödel numbering.

**The theorem.** If T is consistent, then T does not prove Con(T).

*Proof idea:* From the first incompleteness theorem, T proves: "Con(T) → G is not provable" (where G is the Gödel sentence). This argument uses only arithmetic reasoning, so T can formalize it. Thus T proves: Con(T) → G. If T also proved Con(T), then by modus ponens T would prove G — contradicting the first theorem (if T is consistent). So T cannot prove Con(T).

**The derivability conditions.** The proof requires that the provability predicate Prov(⌈φ⌉) satisfies the Hilbert-Bernays conditions:
1. If T ⊢ φ, then T ⊢ Prov(⌈φ⌉)
2. T ⊢ Prov(⌈φ⌉) → Prov(⌈Prov(⌈φ⌉)⌉)
3. T ⊢ Prov(⌈φ→ψ⌉) ∧ Prov(⌈φ⌉) → Prov(⌈ψ⌉)

**Philosophical implications.** We cannot have absolute certainty about the consistency of mathematics from within mathematics itself. Any formal system strong enough to be interesting cannot guarantee its own coherence. This does not mean mathematics is likely inconsistent — we have centuries of evidence otherwise — but absolute proof is unattainable.

**Gentzen's consistency proof.** Gerhard Gentzen proved the consistency of PA using transfinite induction up to ε_0 (the first ordinal satisfying ω^α = α). This goes beyond finitary methods but uses entirely natural and well-understood tools.

---

## Lecture 13: Advanced Set Theory — Independence Results and Large Cardinals

**Independence from ZFC.** Some natural mathematical questions can neither be proved nor disproved from ZFC.

**The continuum hypothesis.** Gödel proved in 1938 that CH is consistent with ZFC, using the constructible universe L. Cohen proved in 1963 that ¬CH is also consistent with ZFC, using the technique of forcing.

**Forcing.** Cohen's technique for building new models of ZFC by adding "generic" sets.

The basic setup: start with a ground model V ⊨ ZFC. Choose a forcing poset (P, ≤) — a partially ordered set of conditions. A generic filter G ⊆ P is a filter meeting every dense subset of P (with "dense" defined in V). The generic extension V[G] is a new model of ZFC containing G.

Forcing conditions are partial specifications of the new generic object. The forcing relation p ⊩ φ (condition p forces φ) determines truth in V[G]: φ is true in V[G] iff some p ∈ G forces φ.

To prove ¬CH: use a forcing poset whose conditions are finite partial functions from ω_2 × ω to {0,1}. The generic object is a function f: ω_2 × ω → {0,1}, which codes ω_2 distinct reals — giving 2^{ℵ_0} ≥ ℵ_2, refuting CH.

**Large cardinals.** Axioms asserting the existence of very large infinite sets with special properties.

*Inaccessible cardinals:* A cardinal κ is inaccessible if κ > ω, κ is regular (not a union of fewer than κ smaller sets), and κ is a strong limit (2^λ < κ for all λ < κ). If an inaccessible cardinal exists, then V_κ is a model of ZFC — so the existence of an inaccessible cardinal implies Con(ZFC).

*Measurable cardinals:* A cardinal κ is measurable if there is a non-principal κ-complete ultrafilter on κ. Measurable cardinals are inaccessible and much larger.

*Woodin cardinals:* Technical large cardinal axioms central to the study of sets of reals. If κ is a Woodin cardinal, many statements about projective sets of reals can be decided.

*Supercompact cardinals:* For any ordinal λ, there is an elementary embedding j: V → M with critical point κ and j(κ) > λ. Supercompact cardinals imply the consistency of all smaller large cardinal axioms.

**Large cardinals and determinacy.** The Axiom of Determinacy (AD) states that all infinite two-player games on natural numbers are determined (one player has a winning strategy). AD contradicts Choice but is consistent with ZF. Large cardinal axioms (Woodin cardinals) imply restricted forms of determinacy compatible with Choice — specifically, projective determinacy.

**The inner model program.** Seeks canonical inner models (subclasses of V satisfying ZFC) containing large cardinals. Gödel's constructible universe L is the minimal inner model. For larger cardinals, more complex inner models (L[U], L[E]) are required. The inner model program provides exact calibrations of consistency strength.

---

## Lecture 14: Applications and Philosophical Perspectives

**Tarski's undefinability theorem.** Truth in a model cannot be defined within that model. More precisely: there is no arithmetic formula True(x) such that PA proves True(⌈φ⌉) ↔ φ for all arithmetic sentences φ. Proof: if such True existed, we could use the diagonal lemma to produce a "liar sentence" — G such that G ↔ ¬True(⌈G⌉) — generating a contradiction.

**Löb's theorem.** For any sentence φ: if T proves "Prov(⌈φ⌉) → φ", then T proves φ. In other words, the only sentences T can prove by proving "I can prove φ therefore φ" are those T already proves directly.

**Logic in mathematics.** Mathematical logic now permeates mathematics:
- Model theory: algebraic geometry (Hrushovski), o-minimality (Wilkie)
- Descriptive set theory: Borel, analytic, projective sets and their combinatorial properties
- Combinatorial set theory: partition calculus, pcf theory
- Category theory and logic: categorical semantics, topos theory

**Philosophical implications.** The incompleteness theorems have implications for mathematical Platonism (do mathematical truths exist independently of our proofs?), formalism (is mathematics just symbol manipulation?), and intuitionism (can we trust classical logic?). These questions remain open and actively debated.

---

## Appendix: Key Theorems Summary

**Gödel's Completeness Theorem.** A first-order sentence is valid iff it is provable. Semantic validity coincides with syntactic provability.

**Compactness Theorem.** A set of sentences has a model iff every finite subset does. Satisfiability of infinite theories reduces to finite parts.

**Löwenheim-Skolem Theorems.** Countable theories with infinite models have countable models; theories with infinite models have models of every infinite cardinality.

**Church-Turing Theorem.** The validity problem for first-order logic is undecidable.

**Gödel's First Incompleteness Theorem.** Any consistent, recursively axiomatized extension of PA is incomplete — there are true sentences it cannot prove.

**Gödel's Second Incompleteness Theorem.** Any consistent, recursively axiomatized extension of PA cannot prove its own consistency.

**Independence of CH.** The continuum hypothesis is independent of ZFC — it can be neither proved nor disproved from the standard axioms.

**Tarski's Undefinability Theorem.** Arithmetic truth is not definable in arithmetic.

---

*This artifact reconstructs the 14-lecture audio course from the original Claude conversation. Full 30,000-word DOCX with complete spoken scripts available at the source conversation link above.*
