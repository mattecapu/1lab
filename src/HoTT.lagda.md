<!--
```agda
open import 1Lab.Equiv.Biinv

open import Algebra.Group.Homotopy
open import Algebra.Monoid
open import Algebra.Group

open import Cat.Instances.Sets.CartesianClosed
open import Cat.Instances.Sets.Congruences
open import Cat.Displayed.Univalence.Thin
open import Cat.Functor.Hom.Representable
open import Cat.Instances.Functor.Compose
open import Cat.Instances.Sets.Cocomplete
open import Cat.Functor.Equivalence.Path
open import Cat.Univalent.Rezk.Universal
open import Cat.Instances.Sets.Complete
open import Cat.Functor.Adjoint.Unique
open import Cat.Displayed.Univalence
open import Cat.Functor.Adjoint.Hom
open import Cat.Functor.Equivalence
open import Cat.Diagram.Congruence
open import Cat.Instances.Functor
open import Cat.Instances.Product
open import Cat.Functor.Adjoint
open import Cat.Instances.Slice
open import Cat.Displayed.Base
open import Cat.Instances.Sets
open import Cat.Univalent.Rezk
open import Cat.Allegory.Base
open import Cat.Functor.Base
open import Cat.Functor.Hom
open import Cat.Univalent
open import Cat.Morphism
open import Cat.Bi.Base
open import Cat.Prelude

open import Data.Set.Surjection
open import Data.Fin.Finite using (Finite-choice)
open import Data.Dec
open import Data.Nat using (ℕ-well-ordered ; Discrete-Nat)
open import Data.Sum

open import Homotopy.Space.Circle
open import Homotopy.Space.Torus
open import Homotopy.Base

open import Order.Base

import Algebra.Monoid.Category as Monoid
import Algebra.Group.Free as Group

module HoTT where
```
-->

# The HoTT Book?

While the 1Lab has not been consciously designed as a project to
formalise the HoTT book, in the course of our explorations into
formalised univalent mathematics, we have formalised a _considerable_
subset of the first part, and most of chapter 9. The vast majority of
the 1Lab is material that was _not_ covered in the HoTT book.

# Part 1 Foundations

## Chapter 2 Homotopy type theory

### 2.1 Types are higher groupoids

<!--
```agda
_ = sym
_ = _∙_
_ = ∙-id-l
_ = ∙-id-r
_ = ∙-inv-l
_ = ∙-inv-r
_ = ∙-assoc
_ = Ωⁿ⁺²-is-abelian-group
_ = Type∙
_ = Ωⁿ
```
-->

* Lemma 2.1.1: `sym`{.Agda}
* Lemma 2.1.2: `_∙_`{.Agda}
* Lemma 2.1.4:
  i. `∙-id-l`{.Agda}, `∙-id-r`{.Agda}
  ii. `∙-inv-l`{.Agda}, `∙-inv-r`{.Agda}
  iii. _Definitional in cubical type theory_
  iv. `∙-assoc`{.Agda}
* Theorem 2.1.6: `Ωⁿ⁺²-is-abelian-group`{.Agda}
* Definition 2.1.7: `Type∙`{.Agda}
* Definition 2.1.8: `Ωⁿ`{.Agda}

### 2.2 Functions are functors

<!--
```agda
_ = ap
_ = ap-comp-path
```
-->

* Lemma 2.2.1: `ap`{.Agda}
* Lemma 2.2.2:
  i. `ap-comp-path`{.Agda}
  ii. _Definitional in cubical type theory_
  iii. _Definitional in cubical type theory_
  iv. _Definitional in cubical type theory_

### 2.3 Type families are fibrations

<!--
```
_ = subst
_ = Σ-pathp
_ = transport-refl
_ = subst-∙
```
-->

* Lemma 2.3.1: `subst`{.Agda}
* Lemma 2.3.2: `Σ-pathp`{.Agda}
* Lemma 2.3.4: Our `ap`{.Agda} is dependent by nature.
* Lemma 2.3.5: `transport-refl`{.Agda}
* Lemma 2.3.9: `subst-∙`{.Agda}
* Lemma 2.3.10: _Definitional in cubical type theory_

### 2.4 Homotopies and equivalences

<!--
```agda
_ = homotopy-natural
_ = homotopy-invert
_ = is-iso
_ = transport⁻transport
_ = id-equiv
_ = Equiv.inverse
_ = _∙e_
```
-->

* Lemma 2.4.3: `homotopy-natural`{.Agda}
* Lemma 2.4.4: `homotopy-invert`{.Agda}
* Lemma 2.4.6: `is-iso`{.Agda}
* Example 2.4.9: `transport⁻transport`{.Agda}
* Lemma 2.4.12: `id-equiv`{.Agda}, `Equiv.inverse`{.Agda}, `_∙e_`

### 2.7 Cartesian product types

<!--
```agda
_ = Σ-pathp-iso
```
-->

* Theorem 2.7.2: `Σ-pathp-iso`{.Agda}
* Theorem 2.7.3: Agda has definitional η equality for records.

### 2.9 Π-types and function extensionality

<!--
```agda
_ = funext
_ = funext-dep
```
-->

* Theorem 2.9.3: `funext`{.Agda} (no longer an axiom)
* Lemma 2.9.6: `funext-dep`{.Agda} (no longer an axiom)

### 2.10 Universes and univalence

<!--
```agda
_ = path→equiv
_ = univalence
_ = ua
_ = uaβ
_ = ua-id-equiv
_ = ua∙
_ = sym-ua
```
-->

* Lemma 2.10.1: `path→equiv`{.Agda}
* Theorem 2.10.3: `univalence`{.Agda}
  * `ua`{.Agda}, `uaβ`{.Agda}
  * `ua-id-equiv`{.Agda}, `ua∙`{.Agda}, `sym-ua`{.Agda}

### 2.11 Identity type

<!--
```agda
_ = is-equiv→is-embedding
_ = subst-path-left
_ = subst-path-right
_ = transport-path
_ = commutes→square
```
-->

* Theorem 2.11.1: `is-equiv→is-embedding`{.Agda}
* Lemma 2.11.2: `subst-path-left`{.Agda}, `subst-path-right`{.Agda}, `transport-path`{.Agda}
* Theorem 2.11.5: `commutes→square`{.Agda}

### 2.12 Coproducts

<!--
```agda
_ = ⊎Path.Code≃Path
```
-->

* Theorem 2.12.5: `⊎Path.Code≃Path`{.Agda}

## Chapter 3 Sets and Logic

### 3.1 Sets and n-types

<!--
```
_ = is-set
_ = Nat-is-set
_ = ×-is-hlevel
_ = Π-is-hlevel
_ = is-groupoid
_ = is-hlevel-suc
```
-->

* Definition 3.1.1: `is-set`{.Agda}
  * Example 3.1.2: _Definitional in cubical type theory._
  * Example 3.1.4: `Nat-is-set`{.Agda}
  * Example 3.1.5: `×-is-hlevel`{.Agda} (special case)
  * Example 3.1.6: `Π-is-hlevel`{.Agda} (special case)
* Definition 3.1.7: `is-groupoid`{.Agda}
* Lemma 3.1.8: `is-hlevel-suc`{.Agda} (special case)

### 3.3 Mere propositions

<!--
```
_ = is-prop
_ = prop-ext
_ = is-prop→is-set
_ = is-prop-is-prop
_ = is-hlevel-is-prop
```
-->

* Definition 3.3.1: `is-prop`{.Agda}
* Lemma 3.3.3: `prop-ext`{.Agda}
* Lemma 3.3.4: `is-prop→is-set`{.Agda}
* Lemma 3.3.5: `is-prop-is-prop`{.Agda}, `is-hlevel-is-prop`{.Agda}

### 3.5 Subsets and propositional resizing

<!--
```agda
_ = Σ-prop-path
_ = Ω
_ = □
```
-->

* Lemma 3.5.1: `Σ-prop-path`{.Agda}
* Axiom 3.5.5: `Ω`{.Agda}, `□`{.Agda}.

### 3.7 Propositional truncation

<!--
```agda
_ = ∥_∥
_ = ∃
```
-->

The type itself is defined as a higher-inductive type `∥_∥`{.Agda}. We
also define `∃`{.Agda} as a shorthand for the truncation of `Σ`{.Agda}.

### 3.9 The principle of unique choice

<!--
```agda
_ = is-prop→equiv∥-∥
_ = ∥-∥-univ
_ = ∥-∥-proj
```
-->

* Lemma 3.9.1: `is-prop→equiv∥-∥`{.Agda}
* Lemma 3.9.2: Implicit in e.g. `∥-∥-univ`, `∥-∥-proj`{.Agda}

### 3.11 Contractibility

<!--
```agda
_ = is-contr
_ = is-contr-is-prop
_ = retract→is-contr
_ = Singleton-is-contr
```
-->

* Definition 3.11.1: `is-contr`{.Agda}
* Definition 3.11.4: `is-contr-is-prop`{.Agda}
* Definition 3.11.7: `retract→is-contr`{.Agda}
* Definition 3.11.8: `Singleton-is-contr`{.Agda}

### Exercises

<!--
```agda
_ = equiv→is-hlevel
_ = ⊎-is-hlevel
_ = Σ-is-hlevel
_ = contractible-if-inhabited
_ = H-Level-Dec
_ = disjoint-⊎-is-prop
_ = ℕ-well-ordered
_ = is-prop≃equiv∥-∥
_ = Finite-choice
```
-->

* Exercise 3.1: `equiv→is-hlevel`{.Agda}
* Exercise 3.2: `⊎-is-hlevel`{.Agda}
* Exercise 3.3: `Σ-is-hlevel`{.Agda}
* Exercise 3.5: `contractible-if-inhabited`{.Agda}
* Exercise 3.6: `H-Level-Dec`{.Agda}
* Exercise 3.7: `disjoint-⊎-is-prop`{.Agda}
* Exercise 3.19: `ℕ-well-ordered`{.Agda}
* Exercise 3.21: `is-prop≃equiv∥-∥`{.Agda}
* Exercise 3.22: `Finite-choice`{.Agda}

## Chapter 4 Equivalences

### 4.2 Half adjoint equivalences

<!--
```agda
_ = is-half-adjoint-equiv
_ = is-iso→is-half-adjoint-equiv
_ = fibre
_ = fibre-paths
_ = is-half-adjoint-equiv→is-equiv
_ = linv
_ = rinv
_ = is-equiv→pre-is-equiv
_ = is-equiv→post-is-equiv
_ = is-iso→is-contr-linv
_ = is-iso→is-contr-rinv
```
-->

* Definition 4.2.1: `is-half-adjoint-equiv`{.Agda}
* Definition 4.2.3: `is-iso→is-half-adjoint-equiv`{.Agda}
* Definition 4.2.4: `fibre`
* Lemma 4.2.5: `fibre-paths`
* Theorem 4.2.6: `is-half-adjoint-equiv→is-equiv`{.Agda}
* Definition 4.2.7: `linv`{.Agda}, `rinv`{.Agda}
* Lemma 4.2.8: `is-equiv→pre-is-equiv`{.Agda}, `is-equiv→post-is-equiv`{.Agda}
* Lemma 4.2.9: `is-iso→is-contr-linv`{.Agda}, `is-iso→is-contr-rinv`{.Agda}

### 4.3 Bi-invertible maps

<!--
```agda
_ = is-biinv
_ = is-biinv-is-prop
```
-->

* Definition 4.3.1: `is-biinv`{.Agda}
* Theorem 4.3.2: `is-biinv-is-prop`{.Agda}

### 4.4 Contractible fibres

<!--
```agda
_ = is-equiv
_ = is-equiv→is-half-adjoint-equiv
_ = is-equiv-is-prop
```
-->

**Note**: This is our "default" definition of equivalence, but we
generally use it through the interface of half-adjoint equivalences.

* Definition 4.4.1: `is-equiv`{.Agda}
* Theorem 4.4.3: `is-equiv→is-half-adjoint-equiv`{.Agda}
* Lemma 4.4.4: `is-equiv-is-prop`{.Agda}

### 4.8 The object classifier

<!--
```agda
_ = Fibre-equiv
_ = Total-equiv
_ = Map-classifier
```
-->

* Lemma 4.8.1: `Fibre-equiv`{.Agda}
* Lemma 4.8.2: `Total-equiv`{.Agda}
* Theorem 4.8.3: `Map-classifier`{.Agda}

## Chapter 6 Higher inductive types

### 6.2 Induction principles and dependent paths

<!--
```agda
_ = to-pathp
_ = from-pathp
_ = S¹-rec
_ = Ωⁿ≃Sⁿ-map
```
-->

* Remark 6.2.3: `to-pathp`{.Agda}, `from-pathp`{.Agda}
* _Induction principle for $\bb{S}^1$: by pattern matching.
* Lemma 6.2.5: `S¹-rec`{.Agda}
* Lemma 6.2.9: `Ωⁿ≃Sⁿ-map`{.Agda} for `n = 1`{.Agda}

### 6.3 The interval

<!--
```agda
_ = [0,1]
_ = I
_ = interval-contractible
```
-->

This is the higher inductive type `[0,1]`{.Agda}, not the interval type
`I`{.Agda}.

* Lemma 6.3.1: `interval-contractible`{.Agda}

### 6.4 Circles and spheres

<!--
```agda
_ = refl≠loop
```
-->

* Lemma 6.4.1: `refl≠loop`{.Agda}

### 6.6 Cell complexes

<!--
```agda
_ = T²
```
-->

* The torus: `T²`{.Agda}.

### 6.9 Truncations

<!--
```agda
_ = ∥-∥₀-elim
```
-->

* Lemma 6.9.1: `∥-∥₀-elim`{.Agda}

### 6.10 Quotients

<!--
```agda
_ = Coeq
_ = _/_
_ = Coeq-univ
```
-->

We define the quotient `_/_`{.Agda} in terms of coequalisers
`Coeq`{.Agda}.

* Lemma 6.10.3: `Coeq-univ`{.Agda}.

### 6.11 Algebra

<!--
```agda
_ = Monoid-on
_ = Group-on
_ = πₙ₊₁
_ = Monoid.Free⊣Forget
_ = Group.make-free-group
```
-->

* Definition 6.11.1: `Monoid-on`{.Agda}, `Group-on`{.Agda}
* Definition 6.11.4: `πₙ₊₁`{.Agda}
* Lemma 6.11.5: `Monoid.Free⊣Forget`{.Agda}
* Lemma 6.11.6: `Group.make-free-group`{.Agda}

## Chapter 7 Homotopy n-types

### 7.1 Definition of n-types

<!--
```agda
_ = is-hlevel
_ = retract→is-hlevel
_ = Π-is-hlevel
_ = n-Type-is-hlevel
```
-->

* Definition 7.1.1: `is-hlevel`{.Agda}
* Theorem 7.1.4: `retract→is-hlevel`{.Agda}
* Corollary 7.1.5: `equiv→is-hlevel`{.Agda}
* Theorem 7.1.7: `is-hlevel-suc`{.Agda}
* Theorem 7.1.8: `Σ-is-hlevel`{.Agda}
* Theorem 7.1.9: `Π-is-hlevel`{.Agda}
* Theorem 7.1.10: `is-hlevel-is-prop`{.Agda}
* Theorem 7.1.11: `n-Type-is-hlevel`{.Agda}

### 7.2 Uniqueness of identity proofs and Hedberg's theorem

<!--
```agda
_ = set-identity-system
_ = identity-system→hlevel
_ = Discrete→is-set
_ = Discrete-Nat
_ = hubs-and-spokes→hlevel
_ = hlevel→hubs-and-spokes
```
-->

* Theorem 7.2.2: `set-identity-system`{.Agda}, `identity-system→hlevel`{.Agda}
* Theorem 7.2.5: `Discrete→is-set`{.Agda}
* Theorem 7.2.6: `Discrete-Nat`{.Agda}
* Theorem 7.2.7: `hubs-and-spokes→hlevel`{.Agda}, `hlevel→hubs-and-spokes`{.Agda}

### 7.3 Truncations

<!--
```agda
_ = n-Tr-is-hlevel
_ = n-Tr-elim
```
-->

* Lemma 7.3.1: `n-Tr-is-hlevel`{.Agda}
* Lemma 7.3.2: `n-Tr-elim`{.Agda}
* Theorem 7.3.12: `n-Tr-path-equiv`{.Agda}

# Part 2 Mathematics

## Chapter 8 Homotopy theory

The only non-trivial result worth mentioning from Chapter 8 is the
fundamental group of the circle.

### 8.1 π₁(S¹)

<!--
```agda
_ = S¹Path.Cover
_ = S¹Path.encode
_ = S¹Path.decode
_ = S¹Path.encode-decode
_ = S¹Path.encode-loopⁿ
_ = ΩS¹≃integers
```
-->

* Definition 8.1.1: `S¹Path.Cover`{.Agda}
* Definition 8.1.5: `S¹Path.encode`{.Agda}
* Definition 8.1.6: `S¹Path.decode`{.Agda}
* Lemma 8.1.7: `S¹Path.encode-decode`{.Agda}
* Lemma 8.1.8: `S¹Path.encode-loopⁿ`{.Agda}
* Corollary 8.1.10: `ΩS¹≃integers`{.Agda}

## Chapter 9 Category theory

Since a vast majority of the 1Lab's mathematics consists of pure
category theory, or mathematics done with a very categorical
inclination, this is our most complete chapter.

### 9.1 Categories and Precategories

<!--
```agda
_ = Precategory
_ = is-invertible
_ = _≅_
_ = is-invertible-is-prop
_ = Cat[_,_]
_ = ≅-is-set
_ = path→iso
_ = is-category
_ = equiv-path→identity-system
_ = Univalent.Ob-is-groupoid
_ = Hom-transport
_ = path→to-sym
_ = path→to-∙
_ = Poset
_ = Rel
_ = Sets-is-category
```
-->

[Cat.Morphism](Cat.Morphism.html), [Cat.Univalent](Cat.Univalent.html).

* Definition 9.1.1: `Precategory`{.Agda}
* Definition 9.1.2: `is-invertible`{.Agda}, `_≅_`{.Agda}
* Lemma 9.1.3: `is-invertible-is-prop`{.Agda}, `≅-is-set`{.Agda}
* Lemma 9.1.4: `path→iso`{.Agda}
* Definition 9.1.6^[We use a slightly different definition of univalence
for categories. It is shown equivalent to the usual formulation by
`equiv-path→identity-system`]: `is-category`{.Agda}
* Example 9.1.7: `Sets-is-category`{.Agda}
* Lemma 9.1.8: `Univalent.Ob-is-groupoid`{.Agda}
* Lemma 9.1.9: `Hom-transport`{.Agda} (9.1.10), `path→to-sym`{.Agda} (9.1.11), `path→to-∙`{.Agda} (9.1.12/9.1.13)
* Example 9.1.14: `Poset`{.Agda}
* Example 9.1.19: `Rel`{.Agda}

### 9.2 Functors and Transformations

<!--
```agda
_ = Functor
_ = _=>_
_ = Nat-path
_ = Nat-is-set
_ = Functor-path
_ = componentwise-invertible→invertible
_ = Nat-iso→Iso
_ = Functor-is-category
_ = _F∘_
_ = _◂_
_ = _▸_
_ = F∘-assoc
_ = Prebicategory.pentagon
_ = Prebicategory.triangle
_ = Cat
```
-->

* Definition 9.2.1: `Functor`{.Agda}
* Definition 9.2.2: `_=>_`{.Agda}
  * The paragraph immediately after 9.2.2 is `Nat-path`{.Agda} and
    `Nat-is-set`{.Agda}
  * The one after that is `Functor-path`{.Agda}.
* Definition 9.2.3: `Cat[_,_]`{.Agda}
* Lemma 9.2.4: If: `componentwise-invertible→invertible`{.Agda}; Only if: `Nat-iso→Iso`{.Agda}
* Theorem 9.2.5: `Functor-is-category`{.Agda}
* Theorem 9.2.6: `_F∘_`{.Agda}
* Definition 9.2.7: `_◂_`{.Agda}, `_▸_`{.Agda}
* Lemma 9.2.9: `F∘-assoc`{.Agda}
* Lemma 9.2.10: See the definition of `Prebicategory.pentagon`{.Agda} for `Cat`{.Agda}.
* Lemma 9.2.11: See the definition of `Prebicategory.triangle`{.Agda} for `Cat`{.Agda}.

### 9.3 Adjunctions

<!--
```agda
_ = _⊣_
_ = is-left-adjoint-is-prop
```
-->

* Lemma 9.3.1: `_⊣_`{.Agda}
* Lemma 9.3.2: `is-left-adjoint-is-prop`{.Agda}

### 9.4 Equivalences


<!--
```agda
_ = is-equivalence
_ = is-faithful
_ = is-full
_ = is-fully-faithful
_ = is-split-eso
_ = is-eso
_ = ff+split-eso→is-equivalence
_ = Essential-fibre-between-cats-is-prop
_ = ff+eso→is-equivalence
_ = is-precat-iso
_ = is-equivalence→is-precat-iso
_ = is-precat-iso→is-equivalence
_ = Precategory-identity-system
_ = Category-identity-system
```
-->

* Definition 9.4.1: `is-equivalence`{.Agda}
* Definition 9.4.3: `is-faithful`{.Agda}, `is-full`{.Agda}, `is-fully-faithful`{.Agda}
* Definition 9.4.4: `is-split-eso`{.Agda}
* Lemma 9.4.5: `ff+split-eso→is-equivalence`{.Agda}
* Definition 9.4.6: `is-eso`{.Agda}
* Lemma 9.4.7: `Essential-fibre-between-cats-is-prop`{.Agda}, `ff+eso→is-equivalence`{.Agda}
* Definition 9.4.8: `is-precat-iso`{.Agda}
* Lemma 9.4.14: `is-equivalence→is-precat-iso`{.Agda}, `is-precat-iso→is-equivalence`{.Agda}
* Lemma 9.4.15: `Precategory-identity-system`{.Agda}
* Theorem 9.4.16: `Category-identity-system`{.Agda}

### 9.5 The Yoneda lemma

<!--
```agda
_ = _^op
_ = _×ᶜ_
_ = Curry
_ = Uncurry
_ = Hom[-,-]
_ = よ
_ = よ-is-fully-faithful
_ = Representation
_ = Representation-is-prop
_ = hom-iso→adjoints
```
-->

* Definition 9.5.1: `_^op`{.Agda}
* Definition 9.5.2: `_×ᶜ_`{.Agda}
* Lemma 9.5.3: `Curry`{.Agda}, `Uncurry`
  * The $\hom$-functor: `Hom[-,-]`{.Agda}
  * The Yoneda embedding: `よ`{.Agda}
* Corollary 9.5.6: `よ-is-fully-faithful`{.Agda}
* Corollary 9.5.7: _As a corollary of `Representation-is-prop`{.Agda}_
* Definition 9.5.8: `Representation`{.Agda}
* Theorem 9.5.9: `Representation-is-prop`{.Agda}
* Lemma 9.5.10: `hom-iso→adjoints`

### 9.6 Strict categories

This chapter is mostly text.

* Definition 9.6.1: [Strict precategories](Cat.Instances.StrictCat.html)

### 9.7 Dagger categories

We do not have a type of dagger-categories, but note that we do have the
closely-related notion of [allegory].

[allegory]: Cat.Allegory.Base.html

### 9.8 The structure identity principle

<!--
```agda
_ = Structured-objects-is-category
_ = is-category-total
_ = Thin-structure-over
_ = Displayed
```
-->

* Definition 9.8.1: `Thin-structure-over`{.Agda}, generalised into `Displayed`{.Agda}
* Theorem 9.8.2: `Structured-objects-is-category`{.Agda}, generalised into `is-category-total`{.Agda}

### 9.9 The Rezk completion

<!--
```agda
_ = Rezk-completion-is-category
_ = weak-equiv→pre-equiv
_ = weak-equiv→pre-iso
_ = eso→pre-faithful
_ = eso-full→pre-ff
_ = Rezk-completion
_ = Complete-is-eso
_ = Complete-is-ff
_ = Complete
```
-->

* Lemma 9.9.1: `eso→pre-faithful`{.Agda}
* Lemma 9.9.2: `eso-full→pre-ff`{.Agda}
* Lemma 9.9.4: `weak-equiv→pre-equiv`{.Agda}, `weak-equiv→pre-iso`{.Agda}
* Theorem 9.9.5: `Rezk-completion`{.Agda}, `Rezk-completion-is-category`{.Agda}, `Complete`{.Agda}, `Complete-is-ff`{.Agda}, `Complete-is-eso`{.Agda}.

### Exercises

<!--
```agda
_ = is-equivalence.F⁻¹⊣F
_ = Total-space-is-eso
_ = slice-is-category
_ = Total-space-is-ff
_ = Prebicategory
_ = Total-space
_ = Slice
```
-->

* Exercise 9.1: `Slice`{.Agda}, `slice-is-category`{.Agda}
* Exercise 9.2: `Total-space`{.Agda}, `Total-space-is-ff`{.Agda}, `Total-space-is-eso`{.Agda}
* Exercise 9.3: `is-equivalence.F⁻¹⊣F`{.Agda}
* Exercise 9.4: `Prebicategory`{.Agda}