# MatrixCore™ Architectural Space Framework

Version: 1.0  
Status: Stable  
Date: 2026-03-20  

Author: Jan Zdráhal  
ORCID: https://orcid.org/0009-0005-2012-1234  
DOI: https://doi.org/10.5281/zenodo.19153595   
Web: https://matrixcore.org  

---

## Overview

MatrixCore™ Architectural Space Framework defines a formal, architecture-neutral meta-model for representing architectures as structured configurations of artifacts within a multidimensional architectural space.

The framework provides a deterministic structural foundation independent of domain interpretation, implementation technologies, and representation formats.

---

## Scope

This specification defines:

- architectural space based on Cartesian product of dimensions
- structural representation of architectural artifacts
- relations between artifacts
- invariant constraint mechanisms
- projection mechanisms for interpretation layers

This specification does not define:

- runtime behavior
- execution semantics
- implementation technologies
- domain-specific interpretation semantics

---

## Conceptual Structure

The specification is organized into the following conceptual components.

### Architectural Space

Multidimensional space defined as a Cartesian product of architectural dimensions.

- dimensions define structural coordinates
- value sets define admissible positions
- space enables structural embedding of artifacts

### Artifacts and Relations

Artifacts are structural subsets of architectural space connected through relations.

- artifacts represent architectural entities
- relations represent structural connections
- architecture is a finite set of artifacts

### Invariants and Profiles

Constraints restrict admissible architectures without modifying the core model.

- invariants define structural validity conditions
- profiles specialize admissible subspaces
- extensions preserve compatibility with the core model

### Projections

Projection mechanisms provide interpretation layers over architecture.

- projections map structure into representation space
- multiple projections may coexist
- projections do not modify structural definitions

---

## Canonical Version

The canonical version of this specification is defined by the DOI record:

https://doi.org/10.5281/zenodo.19153595

Repository working versions may contain drafts that are not canonical.

---

## Publication

DOI:  
https://doi.org/10.5281/zenodo.19153595  

Repository:  
https://github.com/jan-zdrahal/matrixcore-architectural-space-framework  

Release tag:  
v1.0  

---

## Versioning

Version identifiers follow semantic versioning.

v1.0 — initial stable release  
v1.1 — clarifications, wording improvements, examples  
v2.0 — changes affecting the formal model

Canonical versions are immutable once published.

---

## Related Specifications

MatrixCore System Overview  
https://doi.org/10.5281/zenodo.19154320  

MatrixCore Design Principles  
https://doi.org/10.5281/zenodo.19155760  

MatrixCore Licensing Model  
https://doi.org/10.5281/zenodo.19160540  

---

## License

This specification is licensed under:

Creative Commons Attribution-NoDerivatives 4.0 International (CC BY-ND 4.0)

https://creativecommons.org/licenses/by-nd/4.0/
