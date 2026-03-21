# MatrixCore™ Architectural Space Framework

Version: 1.0  
Status: Stable 
Date: 2026-03-20  

Author: Jan Zdráhal  
ORCID: https://orcid.org/0009-0005-2012-1234  
Web: https://matrixcore.org

License: CC BY-ND 4.0  

---

## 1. Scope

This specification defines the MatrixCore™ Architectural Space Framework, a formal, architecture-neutral model for representing system architectures as structured configurations of artifacts within a multidimensional architectural space.

The framework introduces a mathematical model based on Cartesian product spaces, artifact embeddings, relational structures, invariant constraints, and projection mechanisms.

The framework is static and does not define temporal evolution, execution semantics, or state transitions.

---

## 2. Notation

- D - finite set of architectural dimensions  
- d ∈ D - individual dimension  
- V_d - value set of dimension d  
- S - architectural space  
- 𝒜 - set of architectural artifacts  
- A_i - individual artifact  
- R - architectural relation between artifacts (R ⊆ 𝒜 × 𝒜)  
- 𝓘 - set of invariants  
- ℛ - representation space
- π_L - projection over artifacts (π_L : 𝒜 → L)
- ℘(X) - power set of X

---

## 3. Core Model

### 3.1 Architectural Dimensions

Let D be a finite set of architectural dimensions.

For each dimension d ∈ D, there exists a set of admissible values V_d.

### 3.2 Architectural Space

The architectural space S is defined as:

S = ∏_{d ∈ D} V_d

Each point in S represents a configuration across all dimensions.

### 3.3 Architectural Artifacts

An architectural artifact is an abstract architectural entity represented as a subset of the architectural space:

A ∈ 𝒜, A ⊆ S

Artifacts do not denote physical, implementation-level, or runtime objects.
They represent structural regions within the architectural space defined by the framework.

Artifacts may represent:

- individual components (points in S)
- subsystems (regions in S)
- architectural domains (subspaces of S)

The framework does not impose a fixed granularity on artifacts.
The framework does not impose constraints on overlap between artifacts.

### 3.4 Architecture

An architecture is a finite set of artifacts:

𝒜 = {A_1, A_2, ..., A_n}  

where each A_i ∈ 𝒜 and A_i ⊆ S

### 3.5 Architectural Relations

The architectural relation defines connections between artifacts:

R ⊆ 𝒜 × 𝒜

Examples include:

- dependency
- communication
- containment

The framework does not prescribe specific relation types. Relation semantics may be defined by profiles.

### 3.6 Architectural Projections

A projection over the architectural space is a function:

π_S : S → ℛ

where ℛ is a representation space.

For an artifact A ⊆ S, the induced projection is defined as:

π_S[A] = { π_S(x) | x ∈ A }

Projections provide views of the architecture.

---

## 4. Core Axioms

### Axiom 1 — Artifact Localization

∀ A ∈ 𝒜 : A ⊆ S

### Axiom 2 — Dimensional Independence

Dimensions are independent unless explicitly constrained by relations.

### Axiom 3 — Projection Consistency

Projections must preserve architectural relations via homomorphic mapping.

∀ (A_i, A_j) ∈ R :

π_S[A_i] and π_S[A_j] preserve the relation between A_i and A_j in the representation space.

### Axiom 4 — Architectural Closure

∀ (A_i, A_j) ∈ R ⇒ A_i, A_j ∈ 𝒜

---

## 5. Invariants

𝓘_framework ⊆ 𝓘 - set of framework invariants

An invariant is a predicate:

I ∈ 𝓘, I : ℘(𝒜) → {0,1}

An architecture satisfies invariants if:

∀ I ∈ 𝓘_framework : I(𝒜) = 1

---

## 6. Profiles

A profile is defined as:

P = (D_p, I_p)

where:

- D_p defines dimensions
- I_p defines additional invariants

Profiles specialize the framework.

Each profile induces a specialized architectural space:

S_P = ∏_{d ∈ D_p} V_d

where D_p ⊆ D or extends D with additional dimensions.

Profiles must not alter the semantic interpretation of existing dimensions.

---

## 7. Conformance

An architecture conforms if:

1. Dimensions are defined  
2. Artifacts are subsets of S  
3. All invariants hold  

---

## 8. Extension Principles

### Profile Completeness Principle

∀ architecture 𝒜 : ∃ profile P : ∀ A ∈ 𝒜 : A ⊆ S_P

### Core Stability Invariant

Profiles must not modify core axioms.

### Extension Rule

Extensions must be defined via profiles.

### Architectural Space Extension

The architectural space may be extended by introducing additional dimensions.

Such extensions must preserve existing artifacts via a defined embedding into the extended space.

### Embedding Requirement

Let:

e : S → S_P

be an embedding function from the architectural space S to the extended architectural space S_P.

For every artifact A ⊆ S:

e[A] = { e(x) | x ∈ A }

e[A] ⊆ S_P

The embedding must preserve structural relations:

∀ (A_i, A_j) ∈ R :

e[A_i] and e[A_j] preserve the relation between A_i and A_j in the extended architectural space.

---

## 9. Projection Extensions

L - set of licenses  
λ - licensing function  
C ⊆ L × L - license compatibility relation  
R_impl ⊆ 𝒜 × 𝒜 - implementation relation between artifacts  

### 9.1 Licensing Projection

λ : 𝒜 → L

π_L : 𝒜 → L  
π_L(A) = λ(A)

### 9.2 Compatibility Constraint

∀ (A_i, A_j) ∈ R_impl :
(λ(A_i), λ(A_j)) ∈ C

---

## 10. Interpretation

The framework models architecture as:

- spatial configuration (S)
- structured artifacts (𝒜)
- relational structure (R)
- constraints (𝓘)
- projections (π_S, π_L)
- extensibility (profiles)

### Validation Model

The MatrixCore™ system is self-contained with respect to validation.

All structural, semantic, and compositional correctness conditions are defined within the system itself and can be evaluated without external rules.

---

## Trademark Notice

MatrixCore™ is an unregistered trademark of Jan Zdráhal.

The mark is used in connection with architectural modeling frameworks and related technologies.

---

## Appendix A — Minimal Core Definitions (Normative)

This appendix defines the minimal mathematical core of the MatrixCore framework.

The definitions and axioms specified in this appendix constitute a minimal, sufficient, and complete formal basis from which the rest of the framework can be derived.

### Definition 1 - Architectural Dimensions

Let:

D be a finite set of architectural dimensions.

For each dimension d ∈ D there exists a set of admissible values:

V_d

These represent possible positions of artifacts in the given dimension.

### Definition 2 - Architectural Space

The architectural space is the Cartesian product of all dimensions:

S = ∏_{d ∈ D} V_d

Each point in the space represents one architectural configuration across dimensions.

### Definition 3 - Architectural Artifact

An artifact is a subset of the architectural space.

A ⊆ S

Examples:

- point artifact: A = {a}, where a ∈ S
- subsystem: A ⊆ S
- architectural region: A ⊆ S

### Definition 4 - Architecture

An architecture is a finite set of artifacts.

𝒜 = {A_i}_{i=1}^k

where:

A_i ⊆ S

### Definition 5 — Architectural Projection

A projection is a function mapping the architectural space to a representation.

π_S : S → ℛ

where:

ℛ is a representation space (e.g. diagram, model).

Projections provide views of the architecture from different perspectives.

### Definition 6 - Architectural Relation

An architectural relation is a relation between artifacts.

R ⊆ 𝒜 × 𝒜

Examples:

- dependency
- communication
- containment.

Relations define structural connections within the architecture.


### Definition 7 — Architectural Invariant

An invariant is a predicate over architectures.

I : ℘(𝒜) → {0,1}

An invariant holds if:

I(𝒜) = 1

Invariants express structural or modeling constraints over the architecture.

### MatrixCore - Core Axioms

#### Axiom 1 — Artifact Localization

Each artifact must be localizable within the architectural space.

∀ A_i ∈ 𝒜 : A_i ⊆ S

#### Axiom 2 — Dimensional Independence

Dimensions of the architectural space are independent.

A change of value in one dimension does not imply a change in another dimension unless explicitly defined by a relation.

### Axiom 3 — Projection Consistency

Projections must preserve structural relations between artifacts.

#### Axiom 4 — Architectural Closure

The architecture must be closed under defined relations.

If a relation exists between artifacts, both must belong to the architecture.

(A_i, A_j) ∈ R ⇒ A_i, A_j ∈ 𝒜

---

END OF MatrixCore™ Architectural Space Framework
