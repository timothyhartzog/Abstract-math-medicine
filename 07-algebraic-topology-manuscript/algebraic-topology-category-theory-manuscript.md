# Algebraic Topology and Category Theory: A Graduate Manuscript

> **Source conversation:** https://claude.ai/chat/d781a287-036f-4491-819a-6d2fb8dbaa60  
> **Created:** January 11, 2026  
> **Format:** Textbook-length educational manuscript  
> **Scope:** ~40,000 words — balanced graduate treatment  
> **Level:** Advanced undergraduate / graduate (assumes point-set topology and abstract algebra)

---

## Preface

This manuscript develops algebraic topology and category theory in parallel, showing how categorical methods provide the natural organizing framework for algebraic topology and how topological problems motivated key categorical constructions. The two subjects are inseparable: every major theorem in algebraic topology has a categorical formulation, and many categorical concepts were invented specifically to state and prove topological results.

We assume familiarity with point-set topology (metric spaces, compactness, connectedness, quotient topology, product topology) and abstract algebra (groups, rings, modules, homomorphisms). The treatment is self-contained beyond these prerequisites.

---

## Historical Introduction

### The Foundational Context

The early twentieth century saw mathematics grappling with questions of rigor and foundation. The same decades that produced the foundational crisis in set theory also witnessed the emergence of algebraic methods in topology. Poincaré had introduced homology and the fundamental group at the turn of the century, but the full algebraic machinery — the toolkit of exact sequences, functors, and natural transformations — took decades to crystallize.

### The Emergence of Category Theory

Eilenberg and Mac Lane's 1945 paper "General Theory of Natural Equivalences" is the founding document of category theory. But it was not written as an exercise in abstraction — it was written to solve a specific problem: to make precise what it means for a construction to be "natural" in algebra and topology.

The canonical example motivating the paper: for any vector space V over a field k, there is an isomorphism V ≅ V** (the double dual), while there is also an isomorphism V ≅ V* (the single dual) — but the first is "natural" (works for all linear maps, no choice required) while the second requires choosing a basis. Category theory was created to make this distinction precise.

Grothendieck's revolutionary reformulation of algebraic geometry in categorical terms (1950s–60s) demonstrated that the categorical perspective could solve problems inaccessible to classical methods. His introduction of sheaves, schemes, and toposes showed that the categorical language was not merely descriptive but constitutively necessary.

Lawvere showed in the 1960s that category theory could serve as an alternative foundation for all of mathematics, with profound philosophical implications. The subject has continued to grow, touching every area of mathematics.

---

## Part I: The Fundamental Group

### Chapter 1: Homotopy

**Definition 1.1.** Two continuous maps f, g: X → Y are **homotopic** (f ≃ g) if there is a continuous map H: X × [0,1] → Y with H(-,0) = f and H(-,1) = g. The map H is a **homotopy** from f to g.

Homotopy is an equivalence relation on the set of continuous maps X → Y. The set of homotopy classes is [X, Y].

**Definition 1.2.** A continuous map f: X → Y is a **homotopy equivalence** if there exists g: Y → X with g∘f ≃ id_X and f∘g ≃ id_Y. We write X ≃ Y and say X and Y have the same **homotopy type**.

**Examples:**
- Any convex subset of ℝ^n is contractible (homotopy equivalent to a point)
- S^n is not contractible (proved using homology or homotopy groups)
- The Möbius band is homotopy equivalent to S^1

### Chapter 2: The Fundamental Group

**Definition 2.1.** A **path** in X is a continuous map γ: [0,1] → X. The path is a **loop** based at x₀ if γ(0) = γ(1) = x₀.

**Definition 2.2.** The **fundamental group** π₁(X, x₀) has:
- Elements: homotopy classes of loops based at x₀ (relative to endpoints)
- Multiplication: concatenation of loops

**Theorem 2.3.** π₁(X, x₀) is indeed a group.

**Categorical formulation.** The fundamental groupoid Π₁(X) is the category with:
- Objects: points of X
- Morphisms: homotopy classes of paths (relative to endpoints)
- Composition: concatenation

π₁(X, x₀) = Aut_{Π₁(X)}(x₀): the automorphism group of x₀ in the fundamental groupoid.

### Chapter 3: Computing Fundamental Groups

**Theorem 3.1 (Van Kampen's theorem).** If X = U ∪ V with U, V open, path-connected, and U∩V path-connected, then:

π₁(X) ≅ π₁(U) *_{π₁(U∩V)} π₁(V)

(the amalgamated free product, pushed out over π₁(U∩V))

**Categorical statement.** Van Kampen's theorem says that π₁ sends the pushout of spaces U ← U∩V → V to a pushout of groups — it preserves certain colimits. More precisely, for the fundamental groupoid, the result is a pushout in the category of groupoids.

**Computations:**
- π₁(S¹) = ℤ (the winding number)
- π₁(S^n) = 0 for n ≥ 2 (proved by covering space theory or transversality)
- π₁(torus) = ℤ × ℤ
- π₁(Klein bottle) = ⟨a, b | abab⁻¹ = 1⟩
- π₁(RP²) = ℤ/2ℤ

### Chapter 4: Covering Spaces

**Definition 4.1.** A continuous surjection p: X̃ → X is a **covering map** if every x ∈ X has an open neighborhood U such that p⁻¹(U) is a disjoint union of open sets each mapped homeomorphically to U.

**Theorem 4.2 (Lifting theorem).** Given a covering p: X̃ → X, a map f: Y → X with f(y₀) = x₀, and a lift ỹ₀ ∈ p⁻¹(x₀):
1. If Y is path-connected, the lift is unique if it exists
2. If Y is simply connected, a lift exists

**The Galois correspondence.** For a path-connected, locally path-connected, semi-locally simply connected space X with basepoint x₀, there is an equivalence of categories:

{connected covering spaces of X} ≅ {π₁(X, x₀)-sets}

Subgroups H ≤ π₁(X) correspond to connected covering spaces p: X_H → X.

This is the topological analogue of the fundamental theorem of Galois theory — and category theory makes the analogy precise.

---

## Part II: Homology Theory

### Chapter 5: Simplicial Homology

**Definition 5.1.** A **simplicial complex** K consists of a vertex set V and a collection of finite subsets (simplices) of V, closed under taking subsets.

An n-simplex is an (n+1)-element subset of V. The **boundary** of the standard n-simplex Δ^n = [v₀,...,v_n] is ∂Δ^n = Σᵢ (-1)^i [v₀,...,v̂ᵢ,...,v_n] (alternating sum of faces).

**Chain groups:** C_n(K) = free abelian group on n-simplices.

**Boundary maps:** ∂_n: C_n → C_{n-1} defined by the boundary formula, satisfying ∂_{n-1} ∘ ∂_n = 0.

**Homology groups:** H_n(K) = ker(∂_n) / im(∂_{n+1}) = Z_n / B_n.

### Chapter 6: Singular Homology

**Definition 6.1.** A **singular n-simplex** in X is a continuous map σ: Δ^n → X.

**Singular chain groups:** C_n(X) = free abelian group on singular n-simplices.

**Boundary:** ∂σ = Σᵢ (-1)^i σ|_{[v₀,...,v̂ᵢ,...,v_n]}.

**Singular homology:** H_n(X) = ker(∂_n) / im(∂_{n+1}).

**Functoriality.** A continuous map f: X → Y induces homomorphisms f_*: H_n(X) → H_n(Y) by f_*(σ) = f∘σ. This makes H_n a functor Top → Ab.

**Homotopy invariance.** If f ≃ g, then f_* = g_*: H_n(X) → H_n(Y). Thus H_n is a functor on the homotopy category.

### Chapter 7: Long Exact Sequences

**The long exact sequence of a pair.** For a pair (X, A) with A ⊆ X:

⋯ → H_n(A) →^{i_*} H_n(X) →^{j_*} H_n(X,A) →^∂ H_{n-1}(A) → ⋯

**The Mayer-Vietoris sequence.** For X = U ∪ V:

⋯ → H_n(U∩V) → H_n(U)⊕H_n(V) → H_n(X) →^∂ H_{n-1}(U∩V) → ⋯

**Categorical perspective.** Long exact sequences arise from the Snake Lemma in abelian categories. Given a short exact sequence of chain complexes 0 → A• → B• → C• → 0, there is a long exact sequence on homology — a theorem that holds in any abelian category.

### Chapter 8: Computations

- H_n(point) = ℤ if n=0, 0 otherwise
- H_n(S^k) = ℤ if n=0 or n=k, 0 otherwise (k ≥ 1)
- H_n(T²) = ℤ (n=0), ℤ² (n=1), ℤ (n=2), 0 (n>2)
- H_n(RP²) = ℤ (n=0), ℤ/2ℤ (n=1), 0 (n>1)
- H_n(RP^{2k}) has ℤ/2ℤ in degrees 1, 3, ..., 2k-1

### Chapter 9: Cellular Homology

For a CW complex X, the cellular chain groups C_n^{CW}(X) = H_n(X^n, X^{n-1}) are free abelian with basis the n-cells. The cellular boundary maps are computed via degrees of attaching maps. Cellular homology equals singular homology — and is far easier to compute.

---

## Part III: Cohomology Theory

### Chapter 10: Cohomology Groups

**Cohomology:** C^n(X; G) = Hom(C_n(X), G) (cochains). The coboundary δ: C^n → C^{n+1} is the dual of ∂.

**H^n(X; G)** = ker(δ^n) / im(δ^{n-1}).

**Universal Coefficient Theorem:**

0 → Ext¹(H_{n-1}(X), G) → H^n(X; G) → Hom(H_n(X), G) → 0

This splits (unnaturally), expressing cohomology in terms of homology.

### Chapter 11: Cup Product

**Definition.** For cochains φ ∈ C^p, ψ ∈ C^q:

(φ ⌣ ψ)(σ) = φ(σ|_{[v₀,...,v_p]}) · ψ(σ|_{[v_p,...,v_{p+q}]})

This passes to cohomology, making H*(X; R) a graded ring — the **cohomology ring**.

**Applications:**
- H*(CP^n; ℤ) = ℤ[x]/(x^{n+1}) with |x| = 2
- H*(T^n; ℤ) = Λ[x₁,...,x_n] (exterior algebra, |xᵢ| = 1)
- Cup products distinguish spaces with the same homology groups

### Chapter 12: Poincaré Duality

For a closed oriented n-manifold M:

H^k(M; ℤ) ≅ H_{n-k}(M; ℤ)

The isomorphism is given by cap product with the fundamental class [M] ∈ H_n(M). This is not merely a group isomorphism but preserves algebraic structure in a precise sense (Poincaré duality as a statement about derived categories).

---

## Part IV: Homotopy Theory

### Chapter 13: Higher Homotopy Groups

**Definition:** π_n(X, x₀) = [(S^n, s₀), (X, x₀)] — homotopy classes of based maps.

**Theorem.** π_n(X) is abelian for n ≥ 2 (Eckmann-Hilton argument).

**Long exact sequence of a fibration.** For p: E → B a fibration with fiber F = p⁻¹(b₀):

⋯ → π_n(F) → π_n(E) → π_n(B) →^∂ π_{n-1}(F) → ⋯

### Chapter 14: Fibrations and Cofibrations

**Fibration** (Hurewicz). A map p: E → B satisfying the homotopy lifting property for all spaces.

**Cofibration.** A map i: A → X satisfying the homotopy extension property.

**The Puppe sequence.** For a cofibration i: A → X, there is an exact sequence of pointed spaces:

A → X → X/A → ΣA → ΣX → Σ(X/A) → ⋯

(Σ = suspension). This is the cofiber sequence.

**Adjunction.** Suspension Σ ⊣ Loop space Ω. This adjunction underlies the long exact sequence and the relationship between homotopy groups: π_n(X) = π_{n-1}(ΩX).

### Chapter 15: CW Complexes and Whitehead's Theorem

**CW complex.** Built by attaching cells: start with X^0 (discrete set of 0-cells), attach 1-cells along their boundary points (getting X^1), attach 2-cells along their boundary circles (getting X^2), and so on.

**Whitehead's theorem.** A map f: X → Y between CW complexes that induces isomorphisms on all homotopy groups is a homotopy equivalence.

**Cellular approximation theorem.** Every continuous map between CW complexes is homotopic to a cellular map (sending n-skeleton to n-skeleton).

---

## Part V: Homological Algebra

### Chapter 16: Exact Functors and Derived Functors

**Left-exact functor.** Hom(A, -): Ab → Ab is left-exact: it sends 0 → M' → M → M'' → 0 to 0 → Hom(A,M') → Hom(A,M) → Hom(A,M'') (not necessarily exact on the right).

**Derived functors.** Take an injective resolution 0 → M → I^0 → I^1 → ⋯, apply Hom(A,-), take cohomology: Ext^n(A,M) = H^n(Hom(A, I•)).

**Tensor product** is right-exact. Its left-derived functor is Tor_n(A,M).

**Applications:**
- Ext^1(A,B) classifies extensions 0 → B → E → A → 0
- Tor_1(A,B) = 0 iff A is flat

### Chapter 17: Spectral Sequences

A **spectral sequence** {E_r^{p,q}, d_r} is a sequence of bigraded abelian groups with differentials d_r: E_r^{p,q} → E_r^{p+r, q-r+1} satisfying d_r² = 0, and E_{r+1} = H(E_r, d_r).

**Serre spectral sequence.** For a fibration F → E → B with π₁(B) acting trivially on H*(F):

E₂^{p,q} = H^p(B; H^q(F)) ⟹ H^{p+q}(E)

This powerful tool computes cohomology of total spaces from fiber and base cohomology.

**Applications:**
- Compute H*(ΩS^n)
- Prove the Hurewicz theorem
- Compute cohomology of Eilenberg-Mac Lane spaces K(G,n)

---

## Part VI: Sheaves and Sheaf Cohomology

### Chapter 18: Presheaves and Sheaves

**Presheaf.** F: Open(X)^op → Ab. Assigns abelian groups to open sets with restriction maps.

**Sheaf.** A presheaf satisfying:
1. Locality: if s|_U = t|_U for all U in a cover, then s = t
2. Gluing: sections agreeing on overlaps glue to a global section

**Categorical formulation.** Sheaves on X form a Grothendieck topos Sh(X). The inclusion Sh(X) → Pre(X) has a left adjoint (sheafification).

### Chapter 19: Sheaf Cohomology

**Derived global sections.** The global sections functor Γ: Sh(X) → Ab is left-exact. Its derived functors are the sheaf cohomology groups H^n(X; F).

**Comparison theorem.** For "nice" spaces, sheaf cohomology = singular cohomology = de Rham cohomology (with appropriate coefficients).

**De Rham's theorem.** H^n_{dR}(M) ≅ H^n(M; ℝ) for smooth manifolds. The isomorphism sends a closed form ω to the cochain σ ↦ ∫_σ ω.

### Chapter 20: The Leray Spectral Sequence

For a continuous map f: X → Y and sheaf F on X:

E₂^{p,q} = H^p(Y; R^q f_* F) ⟹ H^{p+q}(X; F)

Here R^q f_* is the q-th derived pushforward sheaf. This generalizes the Serre spectral sequence.

---

## Part VII: Monoidal and Symmetric Monoidal Structure

### Chapter 21: Monoidal Structure in Topology

**Smash product.** For pointed spaces: X ∧ Y = X × Y / (X ∨ Y). The smash product is the tensor product in the category of pointed spaces.

**(Ab, ⊗, ℤ)** is symmetric monoidal. The tensor product of chain complexes: (A⊗B)_n = ⊕_{p+q=n} A_p ⊗ B_q.

**Künneth formula.** H_*(X×Y) ≅ H_*(X) ⊗ H_*(Y) (with a correction term from Tor) for spaces with free homology.

**Spectra and stable homotopy.** The stable homotopy category is symmetric monoidal under the smash product. The sphere spectrum S is the unit.

---

## Categorical Themes Throughout

**Homotopy category.** The homotopy category hTop has spaces as objects and homotopy classes of maps as morphisms. Homology and homotopy-invariant constructions are functors on hTop.

**Model categories.** Quillen's model categories axiomatize homotopy theory. A model category has three classes of maps — weak equivalences, fibrations, cofibrations — satisfying lifting and factorization axioms. The homotopy category is obtained by inverting weak equivalences.

**Derived categories.** The derived category D(A) of an abelian category A is the model-category-theoretic home for homological algebra. Sheaf cohomology and derived functors live naturally here.

**∞-categories.** The correct setting for homotopy-coherent constructions is ∞-categories. The ∞-category of spaces (∞-groupoids), of chain complexes, of spectra — these replace the classical homotopy category and make coherent composition available.

---

## Selected Bibliography

- Hatcher, A. (2002). *Algebraic Topology*. Cambridge University Press.
- May, J. P. (1999). *A Concise Course in Algebraic Topology*. University of Chicago Press.
- Bott, R. & Tu, L. (1982). *Differential Forms in Algebraic Topology*. Springer.
- Weibel, C. (1994). *An Introduction to Homological Algebra*. Cambridge University Press.
- Mac Lane, S. (1998). *Categories for the Working Mathematician*, 2nd ed. Springer.
- Lurie, J. (2009). *Higher Topos Theory*. Princeton University Press.
- Bredon, G. (1997). *Sheaf Theory*, 2nd ed. Springer.

---

*This artifact is a reconstruction from the original Claude conversation. Full 40,000-word manuscript available at the source conversation link above.*
