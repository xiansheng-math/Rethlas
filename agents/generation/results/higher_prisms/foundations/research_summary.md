# Foundations of candidate higher prisms — research summary

Problem: `higher_prisms/foundations`. The verification service returned **correct**, with no critical errors and no gaps.

[Verified proof](blueprint_verified.md) · [Exact verifier report](verification/20261008T144815033422Z/verifier_response.json) · [Publication provenance](verification/accepted.json)

The proof retains the original classical candidate in the ordinary degree-zero category of full integral Rezk operation algebras. Its cofree coefficient object is intrinsic and has the natural presentation
\[
\mathbb W_E(K)\simeq
\bigl(W(K)\otimes_{W(k)}O\bigr)^{\wedge}_{(p,u_1,\ldots,u_{h-1})}
\simeq W(K)[[u_1,\ldots,u_{h-1}]].
\]
The completion here is joint, and agrees with the corresponding derived completion. Cofreeness, rather than an arbitrary choice of lift, determines every normalization test.

| Foundation | Result | Dependency in the blueprint |
|---|---|---|
| A | Precise integral category, coefficient extension, automatic continuity, Jacobson containment, nonvacuity and perfect-complex detection | Conventions; A1–A3 |
| B | Field normalization is equivalent to the intrinsic conormal isomorphism for regular immersions; a finite Witt-coordinate truncation computes the test | A1, B1–B2; D4 excludes removing regularity |
| C | At height one, exactly classical prisms with compatible W(k)-structure, with no boundedness, noetherianity or torsion-freeness assumption | A1–A2, B1, C1 |
| D | All specified coefficient and ramified tests resolved with actual operations; singular torsion examples and counterexamples to weakened axioms | D1–D5 |
| E | Every classical morphism satisfies ideal equality and the derived quotient equivalence, including over nonnoetherian rings | A2, B1, E1–E2 |
| F | Flat base change with target joint completeness; noetherian joint completion with unique full operations; effective descent of noetherian pairs and morphisms for faithfully flat finite locally free operation-algebra covers | F-augmentation-nilpotent through F-effective-descent |
| Derived extension | A separate category over discrete operation bases admits arbitrary derived base change with target joint completeness and rigidity | G1–G4 |

Three counterexamples clarify the definition. The ideal \((p^2,u_1,\ldots,u_{h-1})\) fails normalization despite regularity. The complete integral delta-ring
\[
B_N=W(k)[\epsilon]/(\epsilon^2,p^N\epsilon),\quad N\ge2,
\]
with \(\delta\epsilon=0\), has primitive free conormal for \((p)\) but
\(\operatorname{Tor}^{B_N}_2(W(K),B_N/p)\cong K\); ordinary arbitrary base change and replacement of regularity by conormal freeness therefore fail. Finally \(\mathbf Z_p\langle x\rangle,(x-p)\), with \(\delta x=0\), satisfies the regularity and normalization tests but is not jointly complete.

The ramified family uses the actual operations on \(E^0\mathbf{CP}^{\infty}\). Every specified field lift factors through its operation-compatible augmentation \(x\mapsto0\), giving the image sequence \((F(0),u_1,\ldots,u_{h-1})\). This does not identify those operations with an independently chosen Breuil–Kisin structure.

The descent theorem requires full operation-compatible cocycle data and proves descent of the operations, ideal, regular immersion, joint completeness and all field tests. Its cover class is faithfully flat finite locally free maps, and its pair rings are noetherian. No formal Zariski descent theorem is asserted.

The derived extension keeps operation bases discrete and equips them with finite local derived zero-locus quotients. Classical pairs embed fully faithfully. Discreteness characterizes the classical image over noetherian bases or for global complete presentations. General animated bases, unbounded operation theories and the unrestricted local nonnoetherian converse remain further work. No relationship with indexed Witt ideals or a pre-existing higher prismatic cohomology theory is assumed.
