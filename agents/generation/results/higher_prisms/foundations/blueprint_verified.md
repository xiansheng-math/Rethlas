# Foundations of the integral higher-prism candidate

Complete candidate proof for `higher_prisms/foundations`; verification is recorded separately. The classical results concern the original candidate, with its full integral operation algebra and joint derived completeness. Section G defines a separate derived extension over discrete operation algebras.

## Research summary and claim dependencies

The original candidate has an intrinsic conormal characterization and recovers all height-one prisms with compatible coefficients, without a boundedness hypothesis. Its classical morphisms are rigid even over nonnoetherian rings. Flat base change works with the prescribed target completeness; noetherian joint completion preserves full operations and regular immersions. Noetherian pairs and their morphisms satisfy effective descent for faithfully flat finite locally free operation-algebra covers. The original quotient must remain regular: a complete integral torsion example has primitive free conormal data but nonzero higher Tor after the required field lift. A separate category of derived quotients admits arbitrary operation-compatible base change with target joint completeness.

| Foundation | Resolved claim and exact scope | Proof and dependencies |
|---|---|---|
| A | Ordinary degree-zero full integral theory; canonical cofree lifts; natural jointly completed coefficient extension; automatic continuity; perfected-residue detection of finite modules and perfect complexes | Conventions; A1–A3, using R09, RW, BF and DC |
| B | Conormal isomorphism iff fieldwise normalization for an ordinary regular immersion; finite Witt-coordinate test at fixed E; primitive conormal alone is insufficient | B1–B2 from A1 and KA; counterexample D4 |
| C | Exactly classical prisms with compatible W(k)-structure, including nonorientable and unbounded prisms | C1 from A1–A2, B1 and the precise delta-ring inputs stated there |
| D | Coefficient normalization, failure of the nonprimitive ideal, every specified Eisenstein family and the height-two specialization; singular torsion examples and proved failures of weakened hypotheses | D1–D5 from A–C; operation/topology limitations F-limitations |
| E | Ideal equality and derived rigidity for all classical candidates, without noetherianity or coefficient torsion assumptions; precise category over a fixed pair | E1–E2 from A2, B1; D4 excludes all complete operation algebras |
| F | Flat base change with target joint derived completeness for arbitrary rings; unique full joint completion for noetherian rings; effective descent of noetherian pairs and morphisms along faithfully flat finite locally free full operation-algebra covers | F-augmentation-nilpotent through F-effective-descent; dependencies A1–A2, B1, R09, RW and stated completion/descent inputs |
| Derived scope | Discrete full operation bases with finite local derived zero loci: arbitrary base change with target completeness and rigidity; fully faithful classical inclusion; discrete-quotient converse over noetherian bases or global complete presentations | G1–G4 from A1–A2, DC and KA |

All required A–F claims are resolved within the scopes explicitly stated. Arbitrary ordinary base change is false (D4); coefficient completeness alone is insufficient (D2). A general animated-base or unbounded integral-operation theory, arbitrary nonnoetherian joint completion preserving ordinary regularity, and formal Zariski descent are further work, not premises of this package. The candidate ideal is unindexed; no relationship with any indexed Witt ideal is used or proposed.

# conventions conv:categories

## statement

Fix the marked finite-height formal group and its Lubin–Tate theory as in the input. All rings are unital and commutative. Let \(\mathcal C_E\) be the ordinary **degree-zero integral** category of Rezk operation algebras. An object includes every integral, generally nonadditive power operation and every relation of that theory, not merely a module or algebra for the additive operation ring \(\Gamma\).

Concretely, this category is the coalgebra category for the actual Witt comonad described in input RW below: an object is an ordinary \(O\)-algebra \(A\) with an \(O\)-algebra map \(\nabla:A\to\mathbb W_E(A)\) satisfying \(\epsilon\nabla=\mathrm{id}\) and \(\mathbb W_E(\nabla)\nabla=\Delta\nabla\). Here \(\Delta\) is the comultiplication of integral iterated power operations (using the symmetric-group wreath-product inclusions), and maps commute with \(\nabla\). This specifies the integral structure even on torsion rings. The cofree structure on \(\mathbb W_E(S)\) is \(\Delta_S\).

There are three distinct objects: the algebraic approximation monad \(\mathbb T^{\mathrm{mod}}\) on graded \(E_*\)-modules; its degree-zero integral theory on commutative \(O\)-algebras, denoted \(\mathbb T_E\) here; and the additive operation algebra \(\Gamma\). We use \(\mathcal C_E=\operatorname{Alg}_{\mathbb T_E}\), with forgetful functor \(U:\mathcal C_E\to\mathrm{CAlg}_O\). This is the ungraded degree-zero theory in Rezk's Witt paper, not the claim that every graded operation algebra is concentrated in degree zero. Periodicity is encoded by the fixed invertible degree-two coefficient module; choosing its trivialization gives \(E_*=O[\beta^{\pm1}]\). Odd input operations and an arbitrary grading are not additional data in this classical candidate.

For an ideal \(I\), derived \(I\)-completeness means
\[
R\operatorname{Hom}_A(A[1/a],M)=0\quad(a\in I).
\]
For finitely generated \(I=(a_1,\ldots,a_r)\), this can equivalently be tested on its generators and computed by the inverse limit of the Koszul complexes on \(a_1^n,\ldots,a_r^n\). It is not, for arbitrary rings, defined as the unqualified inverse limit of ordinary quotients. On noetherian rings and finite modules it agrees with ordinary adic completeness.

A regular ideal of codimension \(h\) means a regular closed immersion: in neighborhoods of points of \(V(J)\), the ideal has a regular sequence of length \(h\). Off \(V(J)\) the quotient is zero. Regular sequences have successive nonzerodivisors and proper final ideal. Such an ideal is finitely generated and \(A/J\) is a perfect \(A\)-module. Indeed finitely many such neighborhoods, together with principal opens where \(J\) is the unit ideal, cover \(\operatorname{Spec}A\); the local Koszul resolutions give perfectness. This convention also treats the zero ring vacuously.

Tensor products with a superscript \(\mathbf L\) are derived tensor products of ordinary commutative rings, or equivalently in their animation. Statements about their underlying complexes are in \(D(A)\). Koszul complexes below describe these underlying complexes; no equivalence between arbitrary commutative differential graded algebras and animated rings in mixed characteristic is presumed.

## proof and primary inputs

We record complete applicable external statements and their meanings, so later uses have fixed hypotheses.

**R09.** `paper_id=Rezk-congruence-2009`, `arXiv=0902.2499v2`, `theorem_id=Proposition 4.23`, with §§4.18–4.22: the forgetful functor from integral graded \(\mathbb T^{\mathrm{mod}}\)-algebras to graded commutative coefficient algebras reflects isomorphisms and has both left and right adjoints; it is monadic and comonadic and preserves limits and colimits. The degree-zero form is the ordinary theory used in the next input. Its proof constructs the free objects on even and odd generators, uses their colimit presentations, and represents the functor \(B\mapsto\operatorname{Hom}(UB,R)\) to obtain the right adjoint. Thus this is about full integral algebras, including on rings with torsion. The separate congruence criterion, Theorem A of the same paper, reconstructs a full integral structure from a \(p\)-torsion-free \(\Gamma\)-algebra exactly when the designated Frobenius congruence holds; it does not license such reconstruction on arbitrary torsion rings. [Source](https://arxiv.org/abs/0902.2499v2).

**RW.** `paper_id=Rezk-Witt-filtration-2026`, `arXiv=2603.12490v1`, `theorem_id=§§1–4, Theorem 1.2, Propositions 3.1–3.2, 4.1, 4.4–4.6`: for the ordinary degree-zero integral theory, \(U\) is both monadic and comonadic. Its cofree object's underlying ring \(\mathbb W_E(R)\) is the ring of compatible sequences
\[
(a_n)\in\prod_{n\ge0}E^0B\Sigma_n\otimes_O R,\qquad
 a_0=1,\quad \operatorname{res}(a_{i+j})=a_i\boxtimes a_j,
\]
with transfer addition and componentwise multiplication. The counit is \((a_n)\mapsto a_1\). Each \(E^0B\Sigma_n\) is finite free over \(O\), and the representing algebra \(P=\bigoplus_n E^\vee_0B\Sigma_n\) is a polynomial algebra with finitely many generators in each weight, supported in prime-power weights. There is a decreasing ideal filtration \(\mathcal I_d(R)\), defined by vanishing of components of positive weight less than \(p^d\), with \(\mathcal I_1=\ker(\mathbb W_E(R)\to R)\), \(\mathbb W_E(R)=\varprojlim_d\mathbb W_E(R)/\mathcal I_d\), and zero intersection. The coefficient map \(O\to\mathbb W_E(k)\) is an isomorphism. For each perfect \(k\)-algebra \(R\), there are natural isomorphisms
\[
 W(R)\otimes_{W(k)}\bigl(\mathbb W_E(k)/\mathcal I_d(k)\bigr)
 \simeq\mathbb W_E(R)/\mathcal I_d(R).
\]
The successive filtration quotients for perfect inputs are finite sums of the additive group of \(R\), with the natural Teichmüller scalar rule; for \(R=k\) they have finite length over \(W(k)\). At height one the full comonad is the ordinary \(p\)-typical Witt comonad, whose coalgebras are \(\delta\)-rings with the compatible \(W(k)\)-structure (Example 1.1). [Source](https://arxiv.org/abs/2603.12490v1).

We checked the proofs: representability uses finite free duality; the perfect-base-change statement uses Frobenius-inverted Teichmüller scalars and induction through the successive filtration quotients. Theorem 1.2 is proved in §8 by the characteristic-\(p\) isogeny tower, its cofinality on Artinian deformations, and the exact sequences of Proposition 8.8 and Corollary 8.9. None of these statements involves the candidate ideal \(J\). We use the filtration only to establish the coefficient ring and its topology.

**BF.** `paper_id=Barthel-Frankland-completion-2015`, `arXiv=1311.7123v3`, `theorem_id=Theorem 3.19, Corollary 3.20, Theorem 5.1(5)–(8), Proposition A.6`: the module monad \(\mathbb T^{\mathrm{mod}}\) preserves \(L_0\)-equivalences, so \(L_0\mathbb T^{\mathrm{mod}}\) is a monad on \(L\)-complete coefficient modules. Its algebras identify with the full subcategory of ordinary module-monad algebras having \(L\)-complete underlying modules. Completion \(L_0\) of an ordinary algebra carries the induced structure. Here \(L_0\) is the zeroth derived functor of coefficient-\(\mathfrak m\)-adic module completion, not completion at an arbitrary ideal involving \(J\). In the regular noetherian coefficient setting, the higher derived completion functors vanish on an \(L\)-complete module. The proof of Theorem 5.1 transports the monad through the reflective subcategory using the isomorphism \(L\mathbb T\to L\mathbb T L\); it requires preservation of these equivalences and cannot be applied with a different reflector without proof. [Source](https://arxiv.org/abs/1311.7123v3).

**DC.** `paper_id=Stacks-Project`, `arXiv=not applicable`, `theorem_id=Tag 091N, Lemmas 15.93.1–8, 15.93.18, 15.93.20, 15.93.24`: derived completeness has the Hom/localization characterization above; complete objects are closed under limits and cones, and their cohomology modules are complete. The complete modules form a weak Serre subcategory, hence are closed under kernels, cokernels, and extensions. Completeness depends only on the radical of the ideal and is unchanged by restricting scalars along a ring map and extending the ideal. For a finitely generated ideal, derived Nakayama says that a complete complex \(M\) with \(M\otimes_A^{\mathbf L}A/I=0\) is zero. A complete module is classically complete precisely when it is also separated. The proofs use the two-term free telescope resolution of \(A[1/a]\) and the inverse system of Koszul complexes. [Source](https://stacks.math.columbia.edu/tag/091N).

**KA.** `paper_id=Stacks-Project`, `arXiv=not applicable`, `theorem_id=Tag 062D, Lemmas 15.31.2, 15.31.5–7; Tag 00NN, Lemma 10.106.3; Tag 00DV, Lemma 10.20.1`: a regular sequence has a Koszul resolution; Koszul regularity is preserved by flat base change; Koszul regularity gives a free conormal module on the indicated classes; over a noetherian local ring and for elements of its maximal ideal, ordinary regularity and Koszul regularity are equivalent. In a regular local ring of dimension \(h\), any minimal \(h\)-element generating set of the maximal ideal is a regular sequence. Finally, a finite module \(M\) with \(IM=M\) and \(I\subseteq\operatorname{Jac}(A)\) vanishes, and generators of \(M/IM\) lift to generators of \(M\). These are used only in the stated finite/noetherian ranges; the Koszul implication for arbitrary rings is proved by induction with mapping cones. [Koszul source](https://stacks.math.columbia.edu/tag/062D), [regular local source](https://stacks.math.columbia.edu/tag/00NN), [Nakayama source](https://stacks.math.columbia.edu/tag/00DV).


**NC.** `paper_id=Stacks-Project`, `arXiv id=not applicable`, `theorem_id=Tags 00IP (Krull intersection), 00MA, 00MB, 031C, 05GH (noetherian completion)`: if \((R,\mathfrak n)\) is noetherian local and \(M\) is finite, then \(\bigcap_{r\ge1}\mathfrak n^rM=0\). For a finitely generated ideal \(I\) of a noetherian ring, completion is exact on finite modules, the completion of a finite module is its tensor product with \(\widehat R\), the map \(R\to\widehat R\) is flat, the completed ring is noetherian and \(I\widehat R\)-adically complete, and \(\widehat R/I^n\widehat R=R/I^n\). Artin–Rees proves exactness and closedness, and exactness on finite ideals proves flatness. These statements justify the finite-module and noetherian uses below; no corresponding assertion for arbitrary rings is inferred. [Krull intersection](https://stacks.math.columbia.edu/tag/00IP), [completion](https://stacks.math.columbia.edu/tag/00MA), [flatness](https://stacks.math.columbia.edu/tag/00MB), [noetherianity](https://stacks.math.columbia.edu/tag/031C), [finite-module comparison](https://stacks.math.columbia.edu/tag/05GH).

# proposition A1: cofree fields and coefficient extension

## statement

There is a right adjoint \(R_E\) to \(U\), with \(UR_E=\mathbb W_E\), and natural bijections
\[
 \operatorname{Hom}_{\mathcal C_E}(A,R_E(S))
 \simeq\operatorname{Hom}_{\mathrm{CAlg}_O}(UA,S).
 \tag{A1.1}
\]
For every perfect field extension \(K/k\), put intrinsically \(O_K=UR_E(K)\) and let \(\epsilon_K:O_K\to K\) be the counit. With any compatible Lubin–Tate coordinates,
\[
 O_K\simeq\bigl(W(K)\otimes_{W(k)}O\bigr)^{\wedge}_{(p,u_1,\ldots,u_{h-1})}
 \simeq W(K)[[u_1,\ldots,u_{h-1}]],
 \qquad \ker\epsilon_K=\mathfrak m_K=(p,u_1,\ldots,u_{h-1}).
 \tag{A1.2}
\]
The displayed completion is also the derived completion of the displayed derived tensor product. For every field point \(f:A/J\to K\) in the input, (A1.1) produces a unique full operation map \(\widetilde f:A\to R_E(K)\) and \(\epsilon_K\widetilde f=f\circ(A\to A/J)\). This lift is functorial both in \(A\) and in extensions of perfect fields.

## proof

The adjunction is R09/RW. In particular, its bijection is exactly composition with the counit, so reduction of the adjoint lift is the prescribed map, with no lifting choice.

Here are the topology details required to use RW for a possibly infinite field extension. Write \(I_d\) for the filtration ideals on \(O=\mathbb W_E(k)\), only in this proof. Each \(O/I_d\) has finite length as a \(W(k)\)-module, by its finite filtration with the successive quotients in RW. It is local and killed by a power of \(p\); it is therefore Artinian, and \(I_d\) contains a power of \(\mathfrak m\). Also \(\bigcap I_d=0\).

We prove the other cofinality rather than asserting that this filtration is a power filtration. If \(R\) is complete noetherian local and \(L_d\) are descending ideals with zero intersection, the images of \(L_d\) in the finite-length module \(R/\mathfrak n^r\) stabilize to submodules \(V_r\). The maps \(V_{r+1}\to V_r\) are surjective: choose a common sufficiently late index at which both images have stabilized. Thus any nonzero element of any \(V_r\) lifts to a compatible sequence in \(\varprojlim V_r\subset R\). For every fixed \(d\), this sequence lies in the closure of \(L_d\), which equals \(L_d\): indeed \(\bigcap_r\mathfrak n^r(R/L_d)=0\) by Krull intersection for the finite module \(R/L_d\). This contradicts \(\bigcap L_d=0\). Therefore \(V_r=0\), and some \(L_d\subset\mathfrak n^r\). Applying this to \(I_d\) proves the claimed cofinality.

RW now gives, naturally,
\[
 O_K=\varprojlim_d W(K)\otimes_{W(k)}(O/I_d)
     =\varprojlim_r W(K)\otimes_{W(k)}(O/\mathfrak m^r).
\]
The latter limit is precisely \(W(K)[[u_1,\ldots,u_{h-1}]]\): modulo \((p,u)^r\) only finitely many monomials occur, with coefficients modulo the corresponding powers of \(p\), and their inverse limit consists of arbitrary power series over \(W(K)\). The map to \(K\) is constant-term reduction, since \(I_1=\mathfrak m\) and the same finite-level base-change statement applies at \(d=1\).

The \(W(k)\)-module \(W(K)\) is torsion-free over the discrete valuation ring \(W(k)\), hence flat. Consequently the initial derived tensor product is ordinary. The ring \(B=W(K)\otimes_{W(k)}O\) is flat over \(O\), so \(p,u_1,\ldots,u_{h-1}\), and their positive powers, are regular in \(B\). Its derived joint completion is therefore the inverse limit of its ordinary quotients by these powers: the Koszul resolutions have no higher homology, and the quotient transition maps are surjective. Cofinality with total powers yields the limit already computed. This also specifies all tensor and completion conventions in (A1.2).

All maps came from the counit, coefficient map and perfect-base-change maps of RW. Their naturality proves functoriality. In particular, for \(K\to K'\), the conormal comparison
\[
 (\mathfrak m_K/\mathfrak m_K^2)\otimes_K K'
 \simeq\mathfrak m_{K'}/\mathfrak m_{K'}^2
 \tag{A1.3}
\]
is immediate in the displayed coordinates and hence independent of their choice.

The intrinsic coefficient object is \((R_E(K),\epsilon_K)\); equivalently it is the universal Lubin–Tate deformation coefficient object for the marked group after perfect residue-field extension. Its coordinate presentation is a computation, not part of the definition of a pair. A coordinate change changes bases in (A1.3) but not this object. An isomorphism of the underlying marked formal-group data transports the Lubin–Tate theory, its power-operation theory, the cofree adjunction and the candidate category. No canonical equivalence for unrelated formal groups of the same height is asserted.

# proposition A2: topology, nonvacuity and detection

## statement

Give \(A\) the \(I=\mathfrak mA+J\)-adic topology, \(A/J\) its quotient topology, and \(O_K\) its \(\mathfrak m_K\)-adic topology. Every specified field point to the discrete field \(K\), its cofree lift, and every operation-compatible map \(g:(A,J)\to(B,L)\) carrying \(J\) into \(L\), is continuous. This does not require noetherianity or classical separatedness.

If \(A\) is derived \(I\)-complete, then \(I\subseteq\operatorname{Jac}(A)\). A nonzero such ring has a specified perfect-field point of \(A/J\). Perfected residue fields at all maximal ideals detect zero finite modules, isomorphisms between finite projective modules, and equivalences of perfect complexes over \(A\) or \(A/J\). The original normalization axiom still quantifies over all specified perfect-field points.

## proof

A field point kills \(\mathfrak m\); its kernel in \(A/J\) therefore contains the quotient ideal of definition. For the lift, reduction of \(\widetilde f(J)\) is zero, so \(\widetilde f(J)\subseteq\mathfrak m_K\), and coefficient compatibility gives \(\widetilde f(\mathfrak mA)\subseteq\mathfrak m_K\). Hence \(\widetilde f(I^n)\subseteq\mathfrak m_K^n\). Similarly \(g(I^n)\subseteq(\mathfrak mB+L)^n\). These are direct proofs of continuity. A ring can have this ideal topology without being separated; we do not silently replace derived completeness by classical completeness.

For \(a\in I\) and \(b\in A\), DC shows that the cokernel \(A/(1-ab)\) of multiplication by \(1-ab\) is derived \(ab\)-complete. On that cokernel \(ab\) acts as the identity. The inverse telescope of identity maps is the cokernel itself, while completeness makes it zero. Thus \(1-ab\) is a unit for every \(b\), proving \(a\in\operatorname{Jac}(A)\). If \(A\ne0\), any maximal ideal \(\mathfrak q\) contains \(I\), so \(A/J\to\kappa(\mathfrak q)\to\kappa(\mathfrak q)^{\mathrm{perf}}\) is a specified field point. The induced map \(k\to\kappa(\mathfrak q)\) is injective, as it is a unital map out of a field. This establishes nonvacuity, including without noetherianity.

A finite module with zero fibers at all maximal ideals vanishes by local Nakayama. For a perfect complex, localize at a maximal ideal and represent it by a bounded complex of finite free modules. If its residue complex is acyclic, split off a contractible summand whenever a differential has a unit entry. After finitely many such splittings all differential entries are in the maximal ideal. The residual complex now has zero differentials after reduction; acyclicity forces every remaining free module to have rank zero. Thus the localized complex was zero. Vanishing at all maximal localizations gives global vanishing. A faithfully flat extension from a residue field to its perfection does not alter these tests. Apply the same proof to the cone to detect equivalences.

The quotient \(A/J\) is itself derived complete for its quotient ideal \(\mathfrak m(A/J)\): its perfect local resolutions make it a perfect \(A\)-module, and a perfect module over a derived complete ring is complete by DC and closure under finite cones and retracts. Restricting and extending ideals then gives the assertion. This argument does not use a possibly false statement that arbitrary quotients preserve derived completeness.

Only these finite-module and perfect-complex tests are asserted. Perfect fields do not detect arbitrary modules or all generic geometry. For example \(\mathbf Q_p/\mathbf Z_p\ne0\), but its ordinary tensor with the only residue field of \(\mathbf Z_p\) is zero. Nor have we replaced the axiom for all field points by a test only at closed points.

# proposition A3: relation to completion categories

## statement

The candidate is meaningful in \(\mathcal C_E\) with the separate condition of derived \((\mathfrak mA+J)\)-completeness. Its underlying coefficient module is derived \(\mathfrak m\)-complete, so is compatible with the coefficient \(L\)-complete theory of BF. This compatibility retains the joint completeness condition. A general animation or unbounded extension of the entire Rezk theory is not used to define classical pairs.

## proof

Completeness for every element of \(\mathfrak mA+J\) implies completeness for the coefficient generators of \(\mathfrak m\). The telescope definition is unchanged by restriction of scalars, by DC. Over the regular noetherian coefficient ring the Koszul model computes derived coefficient completion and its zeroth homology is \(L_0\); thus the underlying module is \(L\)-complete. The BF equivalence gives the compatible completed module-monad algebra. It does not remove the additional vanishing tests for elements of \(J\). The cofree adjunction in A1 is the ordinary one; the field \(K\) need not itself be an operation algebra.

# proposition B1: intrinsic primitivity

## statement

Let \(J\) be a regular ideal of codimension \(h\) in an ordinary integral operation algebra \(A\). For a specified field point \(f:A/J\to K\), the cofree lift defines intrinsically
\[
 c_f:(J/J^2)\otimes_{A/J,f}K\longrightarrow
       \mathfrak m_K/\mathfrak m_K^2,\qquad
 [d]\otimes\lambda\longmapsto\lambda[\widetilde f(d)].
 \tag{B1.1}
\]
The following conditions are equivalent:

1. The canonical augmentation \(O_K\otimes_A^{\mathbf L}A/J\to K\) is an equivalence.
2. The image ideal \(\widetilde f(J)O_K\) equals \(\mathfrak m_K\).
3. \(c_f\) is an isomorphism of \(h\)-dimensional \(K\)-vector spaces.

No noetherianity or torsion-freeness of \(A\) is needed. No completeness of \(A\) is needed for this pointwise assertion. Both ordinary and completed derived base change have the same value here.

## proof

The lift sends \(J^2\) into \(\mathfrak m_K^2\). Multiplication by \(a\in A\) on its target reduces to multiplication by \(f(a\bmod J)\), proving that the indicated balanced map is well-defined. This is the conormal functor for the square of quotient maps \((A,J)\to(O_K,\mathfrak m_K)\); it is intrinsic, without any choice of coordinates or operations presenting the theory.

Let \(\mathfrak p\) be the inverse image of zero under \(A\to K\). Choose \(s\notin\mathfrak p\) such that \(J_s\) is generated by a regular sequence \(d_1,\ldots,d_h\). Since \(f(s)\ne0\), the element \(\widetilde f(s)\) is a unit in the local ring \(O_K\). The ring lift therefore extends uniquely to \(A_s\); there is no assertion that \(A_s\) has a full operation structure. Set \(q_i=\widetilde f_s(d_i)\). Localization and the Koszul resolution give
\[
 O_K\otimes_A^{\mathbf L}A/J
 \simeq O_K\otimes_{A_s}^{\mathbf L}(A/J)_s
 \simeq K_{O_K}(q_1,\ldots,q_h).
 \tag{B1.2}
\]
All \(q_i\) belong to \(\mathfrak m_K\).

An equivalence in (1) implies on degree zero that \(O_K/(q_1,\ldots,q_h)\to K\) is an isomorphism, which is (2). If (2) holds, the \(h\) generators of the maximal ideal of the regular local ring \(O_K\) form a minimal generating set, since its embedding dimension is \(h\). They are a regular sequence by KA, so their Koszul complex resolves \(K\) with the prescribed augmentation. This proves (1).

Regularity of \(J_s\) identifies its conormal module with the free module on \([d_i]\). In these bases, \(c_f\) has columns \([q_i]\). Nakayama in the noetherian local coefficient ring says these columns span \(\mathfrak m_K/\mathfrak m_K^2\) exactly when the \(q_i\) generate \(\mathfrak m_K\). Both sides have dimension \(h\), proving (2)–(3). Changing generators changes the source basis by its invertible transition matrix evaluated under \(f\); changing regular coefficient parameters changes the target basis invertibly. The intrinsic map stays unchanged. Its naturality in pairs and perfect-field extensions follows from A1.

Finally (B1.2) is a bounded finite free complex over the complete noetherian ring \(O_K\). Such a complex is derived \(\mathfrak m_K\)-complete. Its derived completion therefore changes nothing, whether or not normalization holds.

Regularity was used to obtain a resolution of the **ordinary** quotient. Conormal freeness alone proves neither that resolution nor this equivalence. The algebraic example \(A=K[\epsilon]/\epsilon^2\), \(J=(\epsilon)\), has free rank-one conormal but \(H_1K_A(\epsilon)=(\epsilon)\ne0\). A counterexample with actual integral operations is included later.

# proposition B2: what operations say about primitivity

## statement

Formula (B1.1) is an intrinsic criterion using the full operation theory through its cofree adjunction. At fixed \(E\), it can be computed from a finite truncation of the integral Witt coordinates, with a truncation depending only on \(E\). This is an abstract finite-coordinate test, not an asserted universal elementary formula in a small set of additive operations. At height one it becomes the explicit distinguishedness test in C1.

## proof

Choose \(d\) such that \(I_d\subseteq\mathfrak m^2\), using the cofinality proved in A1. RW's natural perfect-base-change isomorphisms imply
\(\mathcal I_d(K)\subseteq\mathfrak m_K^2\). The quotient by \(\mathcal I_d(K)\) is determined by the finitely many polynomial generators of the representing algebra \(P\) of weight less than \(p^d\). For an element \(a\in A\), its cofree lift has coordinates obtained by applying the corresponding integral scalar operations to \(a\), followed by the given ring point \(A\to K\). This is exactly the adjunction formula: the structure map \(A\to\mathbb W_E(A)\) followed by \(\mathbb W_E(A\to K)\). Therefore these finitely many values determine the image of \(\widetilde f(a)\) modulo \(\mathfrak m_K^2\). For localized generators \(a/s\), include the same data for \(s\) and invert its image in the finite quotient. Project from that truncated Witt ring to \(O_K/\mathfrak m_K^2\), then compute (B1.1).

This projection is part of a specified finite ring construction, not an unproved polynomial formula over imperfect rings. Extracting closed formulas or a minimal list of familiar operations at general height is further work and is not needed by B1. The torsion cases cannot be treated by replacing integral operations with their additive shadows.

# proposition C1: exact height-one recovery

## statement

At height one, \(\mathcal C_E\) is the category of \(\delta\)-rings with a chosen \(\delta\)-compatible \(W(k)\)-algebra structure. The original candidates, with their morphisms, are exactly the classical prisms with that structure. This includes locally principal Cartier ideals; orientability means that this ideal is globally principal. Neither boundedness nor noetherianity nor \(p\)-torsion-freeness is an additional hypothesis.

## proof

We use RW Example 1.1 as an identification of full comonads, not just of additive operations. Explicitly a \(\delta\)-ring has a function satisfying
\[
\delta(0)=\delta(1)=0,\quad
\delta(a+b)=\delta(a)+\delta(b)-\sum_{i=1}^{p-1}\frac1p\binom pi a^ib^{p-i},
\]
\[
\delta(ab)=a^p\delta(b)+b^p\delta(a)+p\delta(a)\delta(b).
\]
Its Frobenius lift is \(\phi(a)=a^p+p\delta(a)\); a Frobenius lift alone need not specify these integral data in the presence of \(p\)-torsion. The chosen coefficient structure commutes with the canonical Witt \(\delta\)-structure. The coefficient ring for a perfect field is \(W(K)\), with its usual Witt Frobenius.

The applicable classical definition is: a prism is a \(\delta\)-ring \(A\) with an ideal \(J\) defining a Cartier divisor, with \(A\) derived \((p,J)\)-complete and \(p\in J+\phi(J)A\). Its morphisms are \(\delta\)-maps carrying ideals into ideals. This is `paper_id=Bhatt-Scholze-prisms`, `arXiv=1905.08229v4`, `theorem_id=Definition 3.2`. The exact auxiliary statement from Lemma 2.25 is: if \(p,d\in\operatorname{Jac}(A)\), then \(\delta(d)\) is a unit if and only if \(p\in(d,\phi(d))\). Lemma 3.1 extends this to locally principal ideals by a faithfully flat ind-Zariski localization trivializing the ideal while retaining the Jacobson conditions. Its hypotheses include those radical conditions and do not include boundedness. We give the requisite field and local/global argument directly. [Source](https://arxiv.org/abs/1905.08229v4).

For any local generator with \(\widetilde f(d)=pu\), operation compatibility gives
\[
 f(\delta(d))=\delta(pu)\bmod p
 =\bigl(\phi(u)-p^{p-1}u^p\bigr)\bmod p=\bar u^{\,p}.
 \tag{C1.1}
\]
The conormal scalar is \(\bar u\), not \(\bar u^p\). Their nonvanishing tests agree over a field. Localization of \(d\) is legitimate as follows. At a maximal ideal \(\mathfrak q\supseteq(p,J)\), the complement is \(\phi\)-stable: \(\phi(s)\equiv s^p\pmod{\mathfrak q}\). Thus \(A_{\mathfrak q}\) carries the localized \(\delta\)-structure. The precise source is the statement of Bhatt–Scholze Lemma 2.15: localization of a \(\delta\)-ring at a multiplicative subset \(S\) satisfying \(\phi(S)\subseteq S\) has a unique compatible \(\delta\)-structure and is initial among \(\delta\)-algebras inverting \(S\). Its proof uses the torsion-free free \(\delta\)-ring presentation, then ordinary pushouts, so applies with torsion. The localized lift to \(W(K)\) respects this structure.

Suppose first that the candidate axioms hold. Every maximal ideal contains \((p,J)\) by A2. Choose a generator \(d\) of \(J_{\mathfrak q}\), and use the perfected residue field. B1 and (C1.1) show that the residue of \(\delta(d)\) is nonzero, hence \(\delta(d)\) is a unit in \(A_{\mathfrak q}\). Now
\(p=\delta(d)^{-1}(\phi(d)-d^p)\in J_{\mathfrak q}+\phi(J)A_{\mathfrak q}\). Here localization commutes with this generated ideal, because both \(s\) and \(\phi(s)\) are inverted. Membership in an ideal is detected at all maximal localizations, so \(p\in J+\phi(J)A\).

Conversely suppose the classical prism axioms hold. At any specified field point choose a local generator and extend its lift as in B1. Its image is \(q\in pW(K)\). The ideal \(\widetilde f(J)W(K)=(q)\) is invariant under Witt Frobenius: in the discrete valuation ring \(W(K)\), Frobenius is an automorphism fixing \(p\), and preserves every ideal. The global prism condition therefore implies \(p\in(q,\phi(q))=(q)\). Hence \((q)=(p)\), proving normalization by B1. This direction also covers nonclosed field points.

If \(J=(d)\) globally, (C1.1) at every maximal ideal proves directly that the field condition is equivalent to \(\delta(d)\in A^\times\). If \(d\) is replaced by a local unit times \(d\), the product identity gives \(\delta(vd)\equiv v^p\delta(d)\pmod{(p,d)}\), explaining the invariance of the local unit test. A chosen global generator is extra data; it is not demanded of all pairs.

For comparison with the animated formulation, the complete applicable external statement is `paper_id=Bhatt-Lurie-prismatization`, `arXiv=2201.06124v1`, `theorem_id=Definition 2.4, Lemmas 2.12–2.13, Corollary 2.14`: for a discrete \(\delta\)-ring with a generalized invertible ideal \(\alpha:I\to A\) and derived \((p,I)\)-completeness, the condition that every corresponding perfect-field Witt base change of the derived quotient is the residue field is equivalent to \(p\in(\alpha(I),\phi(\alpha(I)))\). If \(\alpha\) is injective this is a classical prism; the resulting embedding of classical prisms into animated prisms is fully faithful with essential image those with both ring and quotient discrete. The proof uses ind-Zariski trivialization, the radical condition and the same valuation-one calculation, not boundedness. Our proof shows why restricting to compatible extensions of the fixed \(k\) still detects the required maximal ideals. The supplied file has this actual paper title, even though one guide row calls it *Absolute prismatic cohomology*. [Source](https://arxiv.org/abs/2201.06124v1).

# proposition D1: the coefficient and ramified tests

## statement

The pair \((O,\mathfrak m)\) is a candidate. The regular ideal \((p^2,u_1,\ldots,u_{h-1})\) is not primitive and does not define a candidate. With the actual topological full integral operations on
\(A=E^0(\mathbf{CP}^{\infty})=O[[x]]\), every ramified family in the input is a candidate, and its quotient is \(W(k)[[x]]/(F(x))\) with the prescribed coefficient map \(u_i\mapsto f_i(x)\). At height two, \(J=(x^e-p,u-x)\), \(e\ge2\), has conormal matrix \(\operatorname{diag}(-1,1)\) at its specified field points, in the indicated bases.

## proof

The coefficients \(O=\pi_0E\) carry their full operations. The first ideal is the parameter ideal in a complete regular local ring of dimension \(h\). Its field points have the canonical coefficient lift \(O\to O_K\), so the Koszul complex on \(p,u_1,\ldots,u_{h-1}\) resolves \(K\). For the second ideal the same lift gives the regular image sequence \(p^2,u_1,\ldots,u_{h-1}\); its quotient is \(W(K)/p^2\), not \(K\). Equivalently its conormal matrix has first column zero in \(\mathfrak m_K/\mathfrak m_K^2\). Its ideal of joint completion still has radical \(\mathfrak m\), so this failure is solely the field condition.

For the ramified family, the function spectrum \(F(\Sigma^\infty_+\mathbf{CP}^{\infty},E)\) is a commutative \(E\)-algebra under pointwise multiplication and is \(K(h)\)-local: maps into it from an acyclic spectrum equal maps into the local spectrum \(E\) after smashing with \(\Sigma^\infty_+\mathbf{CP}^{\infty}\), which preserves acyclicity. The topological-to-integral-algebra functor of R09 therefore gives the required **full** structure on its \(\pi_0\). Complex orientation identifies this ring with \(O[[x]]\); the even cell filtration yields \(E^0\mathbf{CP}^n=O[x]/x^{n+1}\), vanishing odd groups, surjective transition maps and no Milnor \(\varprojlim^1\). Evaluation at the basepoint is an operation-compatible augmentation
\(\varepsilon:A\to O\), \(x\mapsto0\), by functoriality of power operations. This constructs the structure, rather than postulating arbitrary formulas on a power series ring.

Write \(R=W(k)\) and \(F=x^e+a_{e-1}x^{e-1}+\cdots+a_0\), with all \(a_i\in pR\), and \(a_0/p\in R^\times\). The elementary Eisenstein and division arguments show that \(S=R[[x]]/(F)\) is the finite free \(R\)-algebra \(R[x]/(F)\), a complete discrete valuation ring with uniformizer the image of \(x\). For clarity, monic division expresses every element uniquely on \(1,x,\ldots,x^{e-1}\); the relation gives \(p\) equal to a unit times \(x^e\), the local maximal ideal is \((x)\), and the ring is a domain by the Eisenstein irreducibility criterion over the fraction field of the discrete valuation ring \(R\). Thus it is a one-dimensional regular local domain.

In \(A=R[[u_1,\ldots,u_{h-1},x]]\), \(F\) is a nonzerodivisor, and
\(A/(F)=S[[u_1,\ldots,u_{h-1}]]\). Each \(f_i(x)\) has zero constant term and defines an element of the maximal ideal of \(S\). Translation of the \(u_i\) by these elements is an automorphism of this complete power series ring; its inverse is the opposite translation. Hence \(u_1-f_1(x),\ldots,u_{h-1}-f_{h-1}(x)\) are a regular sequence in \(A/(F)\), in the order displayed. Their quotient is \(S\). This proves precisely the requested regularity and quotient description.

Set \(I=\mathfrak mA+J\). Modulo \(\mathfrak m\), the polynomial \(F\) becomes \(x^e\), so \(\sqrt I=(p,u_1,\ldots,u_{h-1},x)\). All generators of \(J\) belong to this maximal ideal. Noetherianity gives cofinality of its powers with powers of \(I\), so \(A\) is classically and derived \(I\)-complete. This checks the joint topology directly; it is not inferred from coefficient completeness alone.

Every specified perfect-field point of \(S\) sends \(x\) to zero, since \(F\bmod p=x^e\). Thus the composite \(A\to S\to K\) is precisely \(A\xrightarrow{\varepsilon}O\to k\to K\). The map \(A\xrightarrow{\varepsilon}O\to R_E(K)\) already respects all operations. By (A1.1), it is the unique canonical lift. Consequently the image sequence is exactly
\[
 F(0),\ u_1-f_1(0),\ldots,u_{h-1}-f_{h-1}(0)
 =F(0),u_1,\ldots,u_{h-1}.
\]
Since \(F(0)/p\) is a unit, this generates \(\mathfrak m_K\) and is regular. Proposition B1 proves normalization. For \(F=x^e-p\) and \(f_1=x\) its linear terms are \(-p,u\), which gives the asserted matrix.

These operation structures are not identified merely by the Eisenstein quotient. For instance, for multiplicative height-one \(E\) and the coordinate \(x=L-1\), the actual Adams operation is \(\phi(x)=(1+x)^p-1\), hence
\[
 \delta(x)=\sum_{i=1}^{p-1}\frac1p\binom pi x^i.
\]
The familiar Breuil–Kisin choice \(\phi(x)=x^p\) has \(\delta(x)=0\). Both have augmentation zero, but they differ as structures in this coordinate. In fact they are not isomorphic as augmented \(W(k)\)-\(\delta\)-algebras in this multiplicative example: on the augmentation conormal line the former Frobenius acts as multiplication by \(p\), while the latter acts as zero, and an invertible change of basis cannot intertwine these actions over the torsion-free coefficient ring.

# counterexamples D2: completeness, field detection and operation stability

## statement

Joint completeness cannot be replaced merely by coefficient completeness. Dropping completeness can make the field axiom vacuous and destroy rigidity. A candidate ideal is not in general stable under the operations, and its quotient need not be an operation algebra.

## proof

At height one let \(A=\mathbf Z_p\langle x\rangle\), the classical \(p\)-completion of \(\mathbf Z_p[x]\), with \(\delta(x)=0\), and let \(J=(x-p)\). The structure extends from the polynomial \(\delta\)-ring by the following precise result: `paper_id=Bhatt-Scholze-prisms`, `arXiv=1905.08229v4`, `theorem_id=Lemma 2.17`: for any \(\delta\)-ring and finitely generated ideal \(I\) containing \(p\), every \(\delta\) operation is uniformly \(I\)-adically continuous and the classical \(I\)-completion has a unique compatible \(\delta\)-structure. Its proof uses the addition/product identities to show \(\delta(I^{2^{n+1}})\subseteq I^{2^n}\). This applies with \(I=(p)\). [Source](https://arxiv.org/abs/1905.08229v4).

The ring \(A\) is a domain, since it embeds in \(\mathbf Z_p[[x]]\), so \(x-p\) is regular. Every specified field point of \(A/J\) sends \(x\) to zero. The augmentation \(x\mapsto0\) respects \(\delta\), and cofreeness therefore gives the lift with image \(x-p=-p\); fieldwise normalization holds. However \((p,J)=(p,x)\), and \(1-x\) is not invertible in \(A\), since modulo \(p\) it becomes the nonunit \(1-x\in\mathbf F_p[x]\). Proposition A2 shows that \(A\) is not derived \((p,J)\)-complete. Its joint completion is \(\mathbf Z_p[[x]]\). Thus even coefficient completeness, regularity and the full field condition together do not supply joint completeness.

For vacuity and failed rigidity, take the actual height-one operation algebra \(R=\mathbf Q_p[[t]]\) with \(\phi=\mathrm{id}\) and \(\delta(a)=(a-a^p)/p\), and with its usual compatible \(\mathbf Z_p\)-structure. This satisfies the integral \(\delta\) identities because division by \(p\) is legitimate and \(\phi\) is a ring map. Both \((t^2)\) and \((t)\) are regular principal proper ideals. There are no unital maps from their quotients to a characteristic-\(p\) field. Thus their field conditions are vacuous, while the identity map carries \((t^2)\) into \((t)\) without ideal equality. Neither ring is derived jointly complete: its joint ideal contains the unit \(p\), and completeness at the unit ideal forces the ring to be zero. This is precisely the hypothesis that fails.

Finally, \((\mathbf Z_p,(p))\) is a genuine prism, but \(\delta(p)=1-p^{p-1}\) is a unit, so its ideal is not \(\delta\)-stable. Its quotient cannot inherit a compatible \(\delta\)-structure: applying \(\delta\) to the image of \(p=0\) would give both zero and the image of that unit. In the explicit height-two, prime-two theory of `paper_id=Rezk-height-two-2008`, `arXiv=0812.1320v1`, `theorem_id=§§2.1–2.7 and 4`, the coefficient ring is \(\mathbf Z_2[[a]]\), with \(Q_1(a)=3\) and the full integral operation \(\theta(2)=-1\). Thus \((2,a)\) is not even stable under the indicated additive operation, and \((2)\) is not stable under the full integral operation. The formulas follow by applying the stated coefficient commutation relations to \(1\), and from \(Q_0(2)=2=4+2\theta(2)\). This illustration uses the paper's left-module convention and does not substitute its additive algebra for the full theory. [Source](https://arxiv.org/abs/0812.1320v1).

# lemma D3: forming integral torsion quotients

## statement

In a \(\delta\)-ring, if an ideal is generated by \(r_i\) with \(\delta(r_i)\) in that ideal, the entire ideal is \(\delta\)-stable and the quotient inherits a full integral \(\delta\)-structure, including when it has \(p\)-torsion.

## proof

In the product identity for \(\delta(ar_i)\), every term is in the ideal. In the addition identity for a sum of such multiples, both the \(\delta\) terms and every monomial in the correction polynomial lie in the ideal. This proves stability. The addition identity applied to \(a+b\) for \(b\) in the ideal also gives \(\delta(a+b)-\delta(a)\) in the ideal, proving that the quotient operation is well defined and inherits every identity.

# counterexample D4: primitive conormal with a nonregular ordinary quotient

## statement

Let \(h=1\), \(W=W(k)\), and \(N\ge2\). The actual integral operation algebra
\[
 B_N=W[\epsilon]/(\epsilon^2,p^N\epsilon),\quad
 \delta(\epsilon)=0,\quad L=(p)
\]
is noetherian and derived \((p,L)\)-complete. Its conormal module \(L/L^2\) is free of rank one and all its specified conormal maps are isomorphisms. Nevertheless \(L\) is not regular and
\[
 \operatorname{Tor}^{B_N}_2(W(K),B_N/p)\simeq K\ne0.
 \tag{D4.1}
\]
Thus primitive free conormal data do not replace regularity, even with completeness and noetherianity. The operation-compatible nonflat map \(W\to B_N\) from the normalization pair disproves arbitrary classical base change. Its derived base change \((B_N,B_N//p)\) is a restricted derived pair.

## proof

Begin with the torsion-free \(W[\epsilon]\), whose Frobenius lift extends the Witt Frobenius and sends \(\epsilon\) to \(\epsilon^p\). It gives \(\delta\epsilon=0\). Now
\[
 \delta(\epsilon^2)=0,\qquad
 \delta(p^N\epsilon)=\delta(p^N)\epsilon^p\in(\epsilon^2).
\]
Lemma D3 constructs the full integral structure on the quotient. This does not infer a \(\delta\)-structure just from a Frobenius lift on a ring with torsion. The finite module decomposition
\(B_N=W\oplus(W/p^N)\epsilon\) proves noetherianity and classical, hence derived, \(p\)-completeness. Its nonzero annihilator of \(p\) is \(M=p^{N-1}k\epsilon\); since \(N\ge2\), it is contained in \(pB_N\). The map
\[
 B_N/p\longrightarrow pB_N/p^2B_N,\quad\bar b\mapsto pb,
\]
has kernel \((B_N[p]+pB_N)/pB_N=0\), proving conormal freeness.

Every specified field point kills \(\epsilon\). The projection \(B_N\to W\to W(K)\) respects operations and reduces to that point, so is its canonical lift. It carries the basis element \(p\) of the conormal to the basis element \(p\) in the coefficient conormal. But the two-term derived quotient \(Q=B_N//p\) has \(\pi_1Q=M\) and \(\pi_0Q=B_N/p\). The truncation triangle
\(M[1]\to Q\to B_N/p\), after tensoring with \(W(K)\), has middle term the Koszul complex on \(p\) in \(W(K)\), which is \(K\). Its long exact homotopy sequence gives
\[
 \pi_2(W(K)\otimes_{B_N}^{\mathbf L}B_N/p)
 = H_0(W(K)\otimes_{B_N}^{\mathbf L}M)
 =W(K)\otimes_{B_N}M=K,
\]
since \(M\simeq k\) with \(p\) and \(\epsilon\) acting by zero. This proves (D4.1). The element \(p\) is a zero divisor, and \(W\to B_N\) cannot be flat since its tensor of multiplication by \(p\) is not injective.

# example D5: singular classical pairs with coefficient torsion

## statement

At height one, for every \(N\ge1\),
\[
 C_N=W(k)[[d]][\epsilon]/(\epsilon^2,p^N\epsilon),\quad
 J=(d),\quad\delta(d)=1,\quad\delta(\epsilon)=0
\]
is a classical candidate. It has nonzero \(p\)-torsion, and both the ambient ring and its quotient are singular and nonreduced. The classical axioms therefore force neither coefficient torsion-freeness nor a regular ambient ring.

## proof

On the torsion-free ring \(W(k)[[d]][\epsilon]\), define \(\phi(d)=d^p+p\), \(\phi(\epsilon)=\epsilon^p\), and the Witt Frobenius on coefficients. Substitution in formal series converges in the \((p,d)\)-topology, so this is a ring map lifting Frobenius and defines the indicated integral \(\delta\). The same generator computations as D4 and D3 show that the quotient ideal is \(\delta\)-stable. Its module decomposition is
\[
 C_N=W(k)[[d]]\oplus(W(k)/p^N)[[d]]\epsilon.
\]
Multiplication by \(d\) is injective on both summands and has nonzero quotient, so \(J\) is regular. This finite module is classically and derived \((p,d)\)-complete. C1 already proves normalization from \(\delta(d)=1\); here is an explicit cofree check as well.

There is a unique \(q_p\in p\mathbf Z_p\) with \(q_p=q_p^p+p\). Successive substitution starting at zero converges, since for \(a,b\in p\mathbf Z_p\), \(a^p-b^p\in p^{p-1}(a-b)\mathbf Z_p\); the same estimate proves uniqueness. Moreover \(q_p/p\equiv1\pmod p\). Every specified field point kills \(d,\epsilon,p\). The convergent coefficient map \(C_N\to W(K)\), \(d\mapsto q_p\), \(\epsilon\mapsto0\), commutes with Frobenius, because Witt Frobenius fixes \(\mathbf Z_p\) and \(q_p=q_p^p+p\). As its target has no \(p\)-torsion, this equality also implies \(\delta\)-compatibility. Cofreeness identifies it with the required lift. Its Koszul quotient is \([W(K)\xrightarrow{q_p}W(K)]\simeq K\).

The element \(p^{N-1}\epsilon\ne0\) is killed by \(p\), and \(\epsilon\ne0\) is nilpotent. The local ambient ring has dimension two (its reduction is \(W(k)[[d]]\)) but embedding dimension three, with independent classes \(p,d,\epsilon\). Its quotient by \(d\) has dimension one and embedding dimension two. Thus both are singular. These examples keep the full operations and regular immersion; they are not conditional constructions.
# proposition E1: morphisms and rigidity

## statement

A morphism of original classical candidates is a full integral operation-compatible \(O\)-algebra map \(g:A\to B\) with \(g(J)\subseteq L\). It is automatically continuous by A2. For every such morphism,
\[
 JB=L,\qquad B\otimes_A^{\mathbf L}A/J\xrightarrow{\sim}B/L.
 \tag{E1.1}
\]
This holds first in the noetherian complete category and, with exactly the original regular-immersion and derived-completeness hypotheses, in arbitrary rings. It does not say that every complete operation algebra over \(A\) is a classical candidate: preservation of regularity is an additional issue.

## proof

First inspect the requested local calculation. For a perfected residue field \(K\) of a maximal ideal \(\mathfrak q\) of \(B\), A2 makes it a point of \(B/L\). Compose with \(g\) to obtain the point of \(A/J\). Naturality of the cofree adjunction identifies the two maps from \(A\) to \(O_K\). The induced comparison
\[
 (J/J^2)\otimes_{A/J}K\longrightarrow(L/L^2)\otimes_{B/L}K
\]
therefore fits between two isomorphisms to \(\mathfrak m_K/\mathfrak m_K^2\), by B1, and is an isomorphism. Choose regular generators \(d_i\) of \(J\) in a neighborhood of the inverse-image point and \(e_j\) of \(L\) near \(\mathfrak q\), and write \(g(d_i)=\sum_j M_{ji}e_j\) after localizing. The residue determinant of \(M\) is nonzero. Over \(B_{\mathfrak q}\), \(M\) is invertible, whence the two ideals agree. At all maximal ideals this proves \(JB=L\). The change-of-basis map also identifies their Koszul complexes, so the image sequence is Koszul regular. In the noetherian local case KA says it is an ordinary regular sequence. These facts prove the derived assertion locally at maximal ideals, not just equality of ideals.

Here is a second global argument that proves the full arbitrary-ring statement and records precisely why no finiteness of homology modules is being assumed. Both \(A/J\) over \(A\) and \(B/L\) over \(B\) are perfect. Thus the cone \(C\) of the canonical comparison in (E1.1) is perfect over \(B\). For every maximal \(\mathfrak q\) and \(K\) as above, associativity and naturality identify its base change to \(O_K\) with the cone of a map
\[
 O_K\otimes_A^{\mathbf L}A/J\longrightarrow
 O_K\otimes_B^{\mathbf L}B/L.
\]
Both sides are the discrete residue field \(K\) by the two candidate axioms. The map agrees with their canonical augmentations, and hence is the identity of \(K\) as an \(O_K\)-algebra. Thus \(C\otimes_B^{\mathbf L}O_K=0\), and then \(C\otimes_B^{\mathbf L}K=0\). Proposition A2 for perfect complexes gives \(C=0\). On \(H_0\), this yields \(B/JB=B/L\) via the canonical quotient, so it also proves ideal equality.

For arbitrary local rings the argument asserts Koszul regularity of a chosen image sequence. Without an additional argument, a change of generators does not promote every such sequence to sequential ordinary regularity in arbitrary rings; that promotion is unnecessary for (E1.1), since the exhibited complexes already give the derived equivalence. The target ideal itself is an ordinary regular immersion by hypothesis. The noetherian statement includes sequential regularity of the image generators. This distinguishes the derived conclusion from the mere equality of ordinary ideals.

# corollary E2: the category over a fixed classical pair

## statement

Fix a classical candidate \((A,J)\). Its category of classical candidates over \((A,J)\) identifies with the full subcategory of operation-compatible \(A\)-algebras \(B\) such that \(B\) is derived \((\mathfrak mB+JB)\)-complete and \(JB\) is a regular ideal of codimension \(h\). It is not the category of all complete operation \(A\)-algebras.

## proof

Rigidity forces the target ideal to be \(JB\), proving uniqueness. Conversely suppose the two displayed conditions on \(B\) hold. For a field point of \(B/JB\), naturality identifies the restricted lift on \(A\) with its cofree lift. Its image of \(J\) generates \(\mathfrak m_K\) by the source normalization and B1. The image of \(JB\) generates the same ideal in \(O_K\). Applying B1 to the regular target ideal proves that \((B,JB)\) is a candidate, and E1 then also proves the derived quotient assertion. Maps in the indicated full subcategory automatically carry extended ideals into extended ideals. The nonflat torsion example below shows why the regularity condition cannot be omitted.

# conventions conv:F-inputs

## statement and source proofs

Write \(\mathcal C_E\) for the ordinary category of full integral, even operation
algebras, with underlying ordinary commutative \(O\)-algebra functor \(U\).
Write \(T\) for the module monad, to keep it distinct from the theory on
commutative algebras. For \(n\geq 0\), put
\[
 S_n=E^0(B\Sigma_n),\qquad
 \epsilon_n:S_n\longrightarrow O.
\]
Here \(\epsilon_n\) is restriction to the trivial subgroup. Tensor products in
this memo are ordinary unless a derived tensor or a completion is explicitly
written.

The following source facts are used with their actual integral meanings.

1. **Finite freeness and the full theory.** `paper_id`: Charles Rezk, *The
   congruence criterion for power operations in Morava E-theory*;
   `arXiv id`: `0902.2499v2`; `theorem_id`: Proposition 3.17, Remark 3.20,
   Propositions 4.12 and 4.14, Lemma 4.21, Corollary 4.19, and Proposition 4.23.
   The relevant complete statements are: the localized extended power of a
   finite free \(E\)-module is finite free, and is even when that module is even;
   each \(T_n\) preserves filtered colimits and reflexive coequalizers; the
   natural map
   \[
   T(M_1)\otimes_O\cdots\otimes_O T(M_r)
       \longrightarrow T(M_1\oplus\cdots\oplus M_r)
   \]
   is an isomorphism; restriction of the total operation \(P_n(a)\) to the
   trivial subgroup is \(a^n\); and the forgetful functor from integral
   \(T\)-algebras to commutative coefficient algebras preserves colimits and
   is plethyistic (it is conservative and has both adjoints). Its limits are
   computed on the underlying algebras. The even restriction gives the
   category used here. In particular, pushouts over full operation algebras
   have underlying ordinary ring tensor products. Source:
   <https://arxiv.org/abs/0902.2499>.

   The proof of Proposition 3.17 uses cyclic-group calculations, the exponential
   formula, wreath products, and the Sylow-subgroup retract. Proposition 4.14
   transports the exponential formula through the Kan-extension construction.
   Proposition 4.23 uses preservation of limits and colimits to construct both
   adjoints. These are statements about the full integral theory, including its
   nonlinear operations.

2. **Total-operation formulas.** The \(\mathcal C_E\)-structure gives a ring map
   \(P:R\to\mathbb W_E(R)\), whose components lie in \(S_n\otimes_O R\), and
   satisfy
   \[
   P_n(ab)=P_n(a)P_n(b),\qquad P_0(a)=1,
   \]
   \[
   P_n(a+b)=\sum_{i+j=n}
       \operatorname{Tr}_{\Sigma_i\times\Sigma_j}^{\Sigma_n}
       (P_i(a)\boxtimes P_j(b)),\qquad
   (\epsilon_n\otimes 1)P_n(a)=a^n.
   \tag{F.0}
   \]
   The transfers in this formula are \(O\)-linear maps between finite free
   coefficient modules. These are the multiplication and addition laws in the
   cofree Witt functor itself, rather than a claim that \(P_n\) is additive.
   `paper_id`: Charles Rezk, *The Witt filtration of Lubin–Tate deformation
   rings*; `arXiv id`:
   `2603.12490v1`; `theorem_id`: Section 2, Proposition 2.1, Lemma 2.2,
   Proposition 3.1. The supplied extracted text defines the Witt functor by
   these formulas and identifies its representing algebra
   \(\bigoplus_n E_0^\vee B\Sigma_n\). For an operation algebra the structure
   map into the cofree algebra is a ring map, so the same formulas apply.
   Source: <https://arxiv.org/abs/2603.12490>. This is the Witt-filtration
   paper, distinct from the same author's *Cofreeness of the Lubin–Tate
   deformation ring*, arXiv:2603.12492.

3. **What coefficient completion alone proves.** `paper_id`: Tobias Barthel
   and Martin Frankland, *Completed power operations for Morava E-theory*;
   `arXiv id`: `1311.7123v3`; `theorem_id`: Theorem 3.19, Corollary 3.20,
   Theorem 5.1(5)–(8). If \(L_0\) denotes zeroth derived completion of
   coefficient modules at \(\mathfrak m\), then
   \(L_0T(M)\to L_0T(L_0M)\) is an isomorphism. The functor
   \(\widehat T=L_0T\iota\) is a monad. For every \(T\)-algebra \(R\),
   \(L_0R\) has a unique compatible full operation structure, and
   \(\widehat T\)-algebras are equivalent to the full subcategory of
   \(T\)-algebras with \(L_0\)-complete underlying module. Source:
   <https://arxiv.org/abs/1311.7123>.

   Their proof reduces to finite powers, proves a coefficient-mod-\(\mathfrak
   m\) insensitivity estimate for the module monad, and uses reflective
   localization of monads. The ideal in this theorem is the coefficient ideal.
   The theorem does **not**, by itself, identify \(L_0R\) with the
   \((\mathfrak mR+J)\)-completion. The direct continuity proof below handles
   that additional ideal.

4. **Noetherian completion.** `paper_id`: Stacks Project; `arXiv id`: not
   applicable; `theorem_id`: Tags
   [00MA](https://stacks.math.columbia.edu/tag/00MA),
   [00MB](https://stacks.math.columbia.edu/tag/00MB),
   [031C](https://stacks.math.columbia.edu/tag/031C), and
   [05GH](https://stacks.math.columbia.edu/tag/05GH).
   For an ideal \(I\) of a noetherian ring \(R\), completion is exact on finite
   modules, finite-module completion is tensoring with \(\widehat R\), and
   \(R\to\widehat R\) is flat. The completed ring is noetherian and
   \(I\widehat R\)-adically complete, with
   \(\widehat R/I^n\widehat R\cong R/I^n\). Exactness follows from
   Artin–Rees; applying it to finitely generated ideals proves flatness.

5. **Derived completion over a noetherian ring.** `paper_id`: Stacks Project;
   `arXiv id`: not applicable; `theorem_id`: Tags
   [0920](https://stacks.math.columbia.edu/tag/0920),
   [0921](https://stacks.math.columbia.edu/tag/0921), and
   [0922](https://stacks.math.columbia.edu/tag/0922).
   For finitely generated \(I=(f_1,\ldots,f_r)\), derived completion is
   \(\mathbf R\varprojlim_n(K\otimes_R^{\mathbf L}
   K(R;f_1^n,\ldots,f_r^n))\). If \(R\) is noetherian, this equals
   \(\mathbf R\varprojlim_n(K\otimes_R^{\mathbf L}R/I^n)\).
   The proof uses Artin–Rees to make the negative Koszul homology pro-zero.
   Applied to \(K=R[0]\), the surjective tower \(R/I^n\) shows that derived
   completion is the ordinary completed ring in degree zero.

6. **Module descent.** `paper_id`: Stacks Project; `arXiv id`: not applicable;
   `theorem_id`: [023N](https://stacks.math.columbia.edu/tag/023N), Proposition
   35.3.9. If \(R\to S\) is faithfully flat, extension of scalars is an
   equivalence between \(R\)-modules and \(S\)-modules with a cocycle descent
   isomorphism over \(S\otimes_R S\). The inverse is the equalizer of the
   two descent maps. The proof first makes a faithfully flat base change after
   which the cover has a section, then explicitly constructs the inverse using
   that section and the cocycle identity. We apply this to the underlying
   algebra module and its ideal. Multiplication and the unit descend by full
   faithfulness, and their ring identities descend because faithful flatness
   detects equality.

The relevant definitions and proofs in these sources were checked. Joint continuity, operation-structure descent and fieldwise-normalization descent below are deductions proved here; they are not being attributed to the coefficient-completion or module-descent theorems.

# lemma lem:F-augmentation-nilpotent

## statement

For every \(n\geq 1\), \(S_n\) is finite free over \(O\), and the ideal
\[
 N_n=\ker(S_n/\mathfrak mS_n\xrightarrow{\bar\epsilon_n} k)
\]
is nilpotent. Thus there is an integer \(c_n\geq 1\) with \(N_n^{c_n}=0\).

## proof

Finite freeness and evenness follow from Rezk Proposition 3.17 and Remark 3.20
in source 1, applied to \(E\), and duality for a finite free \(E\)-module.
Let \(K_E=E/(p,u_1,\ldots,u_{h-1})\) be the associated two-periodic residue
field spectrum, formed as the smash over \(E\) of the individual cofibers
\(E/p,E/u_1,\ldots,E/u_{h-1}\). Only a unital multiplication on this spectrum
is required; no commutative ring spectrum structure is asserted, especially
at \(p=2\). Here is an explicit construction. For a degree-zero nonzerodivisor
\(x\in\pi_0E\), write \(C=E/x\). Since \(\pi_1C=0\), applying
\([-,C]_E\) to the cofiber sequence shows that restriction to the bottom cell
gives \([C,C]_E\cong\pi_0C\). In particular the self-map \(x:C\to C\)
is null. Smashing the same cofiber sequence with \(C\) makes one unit insertion
\(C\to C\wedge_E C\) a split monomorphism. Choose a retraction
\(\mu_x:C\wedge_E C\to C\). The other unit insertion also becomes the
identity after applying \(\mu_x\), because that composite and the identity
agree on the bottom cell and \([C,C]_E\to\pi_0C\) is injective. Thus
\(\mu_x\) is two-sided unital. Tensor these multiplications over \(E\), using
the symmetry of \(E\)-modules, to obtain a two-sided unital multiplication on
\(K_E\) for which \(E\to K_E\) is multiplicative. This argument is also the
one in Strickland, *Products on MU-modules*, `paper_id` of that title,
`arXiv id`: `math/0011122`, `theorem_id`: Lemma 3.2, Corollary 3.3, and
Lemma 3.4: for an even commutative ring spectrum and an even nonzerodivisor
\(x\), the self-action of \(x\) on its cofiber is null, a multiplication on
the cofiber exists, and any multiplication agreeing with its unit on the
bottom cell is two-sided unital. The paper also proves associativity, but
global associativity or commutativity of \(K_E\) is not needed here. [Source](https://arxiv.org/abs/math/0011122).

Successively taking the cofibers of multiplication by the regular coefficient
sequence gives
\[
 K_E^0(B\Sigma_n)=S_n/\mathfrak m S_n,
 \qquad K_E^1(B\Sigma_n)=0.
\]
Indeed, at each step the cohomology before taking that cofiber is the even
free coefficient module modulo the preceding parameters, so multiplication by
the next parameter is injective and the cofiber long exact sequence has the
asserted quotient and zero odd part. This quotient isomorphism is
multiplicative, since the unit \(E\to K_E\) is multiplicative; its surjectivity
therefore identifies the product on \(K_E^0(B\Sigma_n)\) with the actual
commutative quotient product on \(S_n/\mathfrak mS_n\). In particular
\(K_E^0(B\Sigma_n)\) is a finite-dimensional \(k\)-vector space. The
skeletal product argument below only uses this multiplication and relative
cup products, so it applies equally at the prime two.

Here is the skeletal nilpotence argument, with its separation issue included.
Choose a connected finite-type CW model \(X\) for \(B\Sigma_n\), with a single
zero-cell, and denote its finite skeleta by \(X^{(d)}\). Each
\(K_E^q(X^{(d)})\) is finite-dimensional over \(k\), as follows by induction
over its finitely many cells. The images in any fixed term of the skeletal
inverse system therefore stabilize. Its derived inverse limit in degree one
vanishes. The skeletal telescope gives the Milnor exact sequence
\[
 0\longrightarrow \varprojlim
 {}^1_d K_E^{-1}(X^{(d)})
 \longrightarrow K_E^0(X)
 \longrightarrow \varprojlim_d K_E^0(X^{(d)})
 \longrightarrow0.
\]
For completeness, this sequence is obtained by expressing \(X\) as the
sequential homotopy colimit of its skeleta, applying the cochain functor, and
taking the long exact sequence of the fiber of \(1-\text{shift}\) on the
product of the cochain spectra. Its first term is zero by the preceding
stabilization. Consequently the skeletal kernel filtration on \(K_E^0(X)\)
is separated.

Set \(F^d=\ker(K_E^0(X)\to K_E^0(X^{(d-1)}))\), \(d\geq1\). These are
descending subspaces of a finite-dimensional vector space. Since their
intersection is zero, \(F^d=0\) for some \(d\). The skeletal filtration is
multiplicative: \(F^aF^b\subseteq F^{a+b}\). One sees this from the relative
cup product and a cellular diagonal; the smash of quotients whose cells start
in dimensions \(a\) and \(b\) has no cell below dimension \(a+b\). The first
term \(F^1\) is the augmentation ideal, because \(X^{(0)}\) is a point.
Thus \((F^1)^d\subseteq F^d=0\), proving the lemma.

This is the detailed version, for every symmetric group, of the nilpotence
argument used in the proof of Rezk Lemma 12.2. It does not infer nilpotence from
connectedness alone without the finite-dimensional and separation arguments.

# lemma lem:F-uniform-continuity

## statement

Let \(R\in\mathcal C_E\), without a noetherian or torsion assumption. Let
\(I\subseteq R\) be any ideal containing \(\mathfrak mR\). Every finite-arity
scalar operation of the full integral theory is uniformly \(I\)-adically
continuous.

More explicitly, for fixed \(n\geq1\), choose the nilpotence exponents of the
preceding lemma and put \(c=\max_{1\leq j\leq n}c_j\). Then for all
\(a\in R\), \(r\geq1\), and \(b\in I^{cr}\),
\[
 P_n(a+b)-P_n(a)\in I^r(S_n\otimes_O R).
 \tag{F.1}
\]

## proof

Put \(D_j=S_j\otimes_O R\) and
\[
 H_j=\ker\bigl(D_j\xrightarrow{\epsilon_j\otimes1}R\longrightarrow R/I\bigr).
\]
Since \(\mathfrak mR\subseteq I\), reduction modulo \(ID_j\) identifies
\(H_j/ID_j\) with \(N_j\otimes_k R/I\). The augmentation is split over
the coefficient ring, so this kernel identification holds for arbitrary
\(R/I\). Consequently
\[
 H_j^{c_j}\subseteq ID_j.
 \tag{F.2}
\]
For \(y\in I\), the last formula in (F.0) gives \(P_j(y)\in H_j\). If
\(z=y_1\cdots y_N\), with every \(y_i\in I\), multiplicativity gives
\[
 P_j(z)\in H_j^N\subseteq I^{\lfloor N/c_j\rfloor}D_j.
 \tag{F.3}
\]

Every element of \(I^N\) is a finite sum of such products. Iterating the
addition formula (F.0) expresses \(P_j(z_1+\cdots+z_t)\) as a sum indexed by
\(i_1+\cdots+i_t=j\), followed by transfers from
\(\Sigma_{i_1}\times\cdots\times\Sigma_{i_t}\). In every summand at least
one \(i_\ell\) is positive. If \(j\leq n\), the corresponding factor is in
\(I^{\lfloor N/c\rfloor}(S_{i_\ell}\otimes_O R)\) by (F.3). External
products and the \(O\)-linear transfers preserve this ideal multiple. Thus
\[
 P_j(I^N)\subseteq I^{\lfloor N/c\rfloor}D_j
 \quad(1\leq j\leq n).
 \tag{F.4}
\]
There is no bound on the number of summands required here: each individual
element has a finite expression, and membership in an ideal is preserved by
arbitrary finite sums.

Subtract the \(j=0\) term from the binary addition formula:
\[
 P_n(a+b)-P_n(a)=
 \sum_{j=1}^n
 \operatorname{Tr}_{\Sigma_{n-j}\times\Sigma_j}^{\Sigma_n}
 (P_{n-j}(a)\boxtimes P_j(b)).
\]
Equation (F.4) with \(N=cr\) gives (F.1). A coordinate of \(P_n\) in an
\(O\)-basis of the finite free \(S_n\) is therefore uniformly continuous.

These coordinates detect all operations, including nonlinear ones. Indeed,
an \(r\)-ary operation is represented by an element of \(T(O^{\oplus r})\).
The exponential isomorphism in source 1 identifies this with
\(T(O)^{\otimes r}\), and
\(T(O)=\bigoplus_n\operatorname{Hom}_O(S_n,O)\). Any one element involves
only finitely many weights and a finite sum of tensors. Its evaluation is
therefore a polynomial, with coefficients in \(O\), in scalar coordinates of
the \(P_n\) on the \(r\) inputs. Addition and multiplication are uniformly
continuous for an ideal-adic topology, so this proves the assertion for every
finite-arity operation. The finitary description follows from preservation of
sifted colimits by \(T\); all axioms are equalities between operations of
finite arity. No additive-operation approximation has been used.

# proposition prop:F-joint-completion

## statement

Let \(R\in\mathcal C_E\) be noetherian, and let \(I\subseteq R\) contain
\(\mathfrak mR\). The classical \(I\)-adic completion
\[
 \widehat R=\varprojlim_n R/I^n
\]
has a unique full integral operation structure for which the canonical ring
map \(R\to\widehat R\) is operation-compatible. The map is flat,
\(\widehat R\) is noetherian, and its ordinary and derived
\(I\widehat R\)-completions agree with itself. This construction is functorial
for operation maps carrying \(I\) into the chosen target ideal.

If \(J\subseteq R\) defines a regular immersion of codimension \(h\), then
\(J\widehat R\) defines a regular immersion of codimension \(h\) along its
vanishing locus. In particular the proposition applies to the actual joint
ideal \(I=\mathfrak mR+J\).

## proof

The noetherian completion facts in source 4 identify the completion topology
with the \(I\widehat R\)-adic topology, give density of \(R\), and give a
complete separated target. Extend every finite-arity operation by uniform
continuity using Lemma F-uniform-continuity. Equivalently, evaluate the
operation on Cauchy representatives and use its uniform continuity to see that
the resulting limit is independent of all choices. All operation axioms hold
on the dense image of \(R^r\) and are equalities of continuous functions, so
they hold on \(\widehat R^r\). This defines the full integral structure.

Any other compatible full operation structure on \(\widehat R\) is itself
uniformly \(I\widehat R\)-adically continuous by the preceding lemma, since
\(I\widehat R\) contains \(\mathfrak m\widehat R\). Density therefore makes
it identical with this one. The same argument proves functoriality of
completed maps. This is uniqueness among all compatible full integral
structures, without an extra continuity assumption on the competitors.

Flatness and noetherianity are source 4. Source 5 identifies derived completion
of a noetherian ring with its classical completion in degree zero. For
regularity, choose regular generators on an open neighborhood of the
contraction of a point of \(V(J\widehat R)\). Flatness preserves successively
the injections that define a regular sequence and identifies its quotient with
the tensor product of the old quotient. The same generators therefore form a
regular sequence near that point and generate the extended ideal.

No assertion that \(J\) or \(R/J\) is closed under operations is needed.
Nor has \(\mathfrak mR+J\) been replaced by \(\mathfrak mR\).

# proposition prop:F-flat-base-change

## statement

Let \((A,J)\) be an original classical candidate. Let \(g:A\to B\) be a flat
map in \(\mathcal C_E\). If \(B\) is derived
\((\mathfrak mB+JB)\)-complete, then \((B,JB)\) is a candidate, and
\[
 B\otimes_A^{\mathbf L}A/J\simeq B/JB.
 \tag{F.5}
\]
This assertion needs neither noetherianity nor torsionfreeness; it uses the
ordinary regular-sequence convention of the original candidate.

If \(B_0\) is noetherian and \(A\to B_0\) is a flat operation-compatible map,
then
\[
 B=\widehat{B_0}_{\,\mathfrak mB_0+JB_0}
\]
with the full operation structure of Proposition F-joint-completion satisfies
the preceding conclusion. In this second statement noetherianity is imposed
on the ring being completed, and completion is the genuine joint completion.

## proof

Flatness preserves the local regular generators of \(J\), and it gives (F.5).
For a compatible perfect-field point \(f:B/JB\to K\), compose with
\(A/J\to B/JB\), obtaining \(f_A\). By the cofree mapping property,
\[
 \widetilde f\circ g=\widetilde{f_A}:A\longrightarrow O_K.
\]
Associativity of derived tensor products and (F.5) then give
\[
 O_K\otimes_B^{\mathbf L}B/JB
 \simeq O_K\otimes_A^{\mathbf L}A/J
 \simeq K.
\]
The equivalence is compatible with the specified augmentation to \(K\).
Together with the assumed joint completeness this proves the first statement.

In the second statement Proposition F-joint-completion makes \(B_0\to B\)
an operation-compatible flat map, and makes \(B\) complete in the required
joint topology. Apply the first statement to \(A\to B\).

The proof works as well if the source pair is not yet complete but already
has its regular immersion and fieldwise normalization. Thus completion also
turns any such noetherian source into a candidate. Perfect-field points of
the source and its completion coincide: both factor through
\(A/(\mathfrak mA+J)\), and completion does not change this quotient. Their
cofree lifts agree under restriction. The source lift sends
\(\mathfrak mA+J\) into \(\mathfrak m_K\), so its extension to the
completion is also the ordinary continuous extension into the complete ring
\(O_K\).

# lemma lem:F-finite-faithful-splitting

## statement

If \(A\to B\) is faithfully flat and finite locally free, there is an
\(A\)-linear map \(r:B\to A\) with \(r(1)=1\). For any ideal \(I\subseteq A\),
if \(B\) is \(IB\)-adically complete, then \(A\) is \(I\)-adically complete.
If \(A\) is noetherian and complete, every finite \(A\)-module is complete;
in particular, all finite tensor powers of \(B\) over \(A\) are complete.

## proof

Consider the image ideal of the evaluation homomorphism
\(B^\vee=\operatorname{Hom}_A(B,A)\to A\), \(\lambda\mapsto\lambda(1)\).
At a prime \(\mathfrak p\), the finite free algebra \(B_\mathfrak p\) has
nonzero fiber over \(\kappa(\mathfrak p)\), by faithful flatness. Its unit is
therefore nonzero in that fiber. A vector in a finite free module over a local
ring which is nonzero modulo the maximal ideal has a unit coordinate; a
linear functional sends that vector to 1. Since duals of finite projective
modules commute with localization, the evaluation ideal localizes to the
whole ring at every prime. It is therefore \(A\), proving the existence of
\(r\).

The unit inclusion splits \(A\)-linearly, so \(B=A\oplus\ker(r)\) as an
\(A\)-module. The same direct-sum decomposition holds modulo \(I^n\),
compatibly in \(n\). Taking inverse limits shows that the completion map of
\(A\) is a direct summand of that of \(B\); if the latter is an isomorphism,
so is the former. The assertion about finite modules is source 4. No ring
section of \(A\to B\), nor an operation-compatible retraction, was asserted
or used.

# lemma lem:F-regular-descent

## statement

Let \(A\to B\) be faithfully flat with \(A\) and \(B\) noetherian, and let
\(J\subseteq A\). If \(JB\) defines a regular immersion of codimension
\(h\), then so does \(J\).

## proof

Fix \(\mathfrak p\supseteq J\), and choose \(\mathfrak q\supseteq JB\)
above it. The map \(A_\mathfrak p\to B_\mathfrak q\) is faithfully flat:
it is flat and local. Write \(A_0=A_\mathfrak p\), \(B_0=B_\mathfrak q\).
Flat base change identifies
\[
 (J/J^2)\otimes_A B\cong JB/(JB)^2.
\]
Since the right side has rank \(h\) over \(B/JB\), taking residue-field
fibers shows that \(J_\mathfrak p/\mathfrak pJ_\mathfrak p\) has dimension
\(h\). Choose lifts \(d_1,\ldots,d_h\in J_\mathfrak p\) of a basis. They
generate \(J_\mathfrak p\) by Nakayama.

At \(B_0\), this list and any regular list of \(h\) generators of
\(JB_0\) are related by an invertible matrix: their classes are bases of
\(JB_0/\mathfrak q JB_0\), and hence the transition matrix has unit
determinant. The corresponding Koszul complexes are isomorphic. Thus
\(K_{B_0}(d_1,\ldots,d_h)\) is acyclic in positive homological degrees.
Faithful flatness gives the same acyclicity over \(A_0\).

For clarity, in a noetherian local ring a finite list in the maximal ideal
with acyclic positive Koszul homology is an ordinary regular sequence. Prove
this by induction on its length. Express the Koszul complex on the whole
list as the cone of multiplication by the last element on the complex on
the preceding list. The long exact homology sequence makes multiplication by
the last element surjective on each positive homology module of the
preceding complex. Those modules are finite. Nakayama makes them zero. The
degree-one part of the same sequence then says that the last element is
injective on the quotient by the preceding list. Induction proves the claim.
Apply it to the \(d_i\). Regularity spreads from this localization to an open
neighborhood, since the finitely many annihilator modules are finite.
This proves the result at every point of \(V(J)\).

The noetherian hypothesis is used for that Koszul-to-ordinary-regularity
argument and for spreading to an open neighborhood. This proof does not
identify those notions over all nonnoetherian rings. It is consistent with
the stronger general descent statement in Stacks Tag 0694 for
Koszul-regular immersions, whose terminology must not be silently replaced
by ordinary regular sequences.

# lemma lem:F-normalization-descent

## statement

Suppose \(A\to B\) is faithfully flat finite locally free in
\(\mathcal C_E\), \(J\subseteq A\) defines a regular immersion of codimension
\(h\), and \((B,JB)\) satisfies fieldwise normalization. Then \((A,J)\)
satisfies fieldwise normalization, independently of completeness.

## proof

Let \(f:A/J\to K\) be one of the specified perfect-field points. The
\(K\)-algebra
\[
 D=(B/JB)\otimes_{A/J,f} K
\]
is finite-dimensional and nonzero, because it is faithfully flat over \(K\).
Choose a maximal ideal of \(D\); its residue field \(K'\) is finite over
\(K\), hence perfect. The resulting map \(f':B/JB\to K'\) is a compatible
point lying over \(f\) and the extension \(K\hookrightarrow K'\).

Write \(\beta_f\) for the intrinsic conormal map of foundation B. Flatness
and the naturality of cofree lifts give the commutative square
\[
\begin{array}{ccc}
 (J/J^2)\otimes_{A/J,f}K\otimes_K K'
   &\xrightarrow{\beta_f\otimes_K K'}&
 (\mathfrak m_K/\mathfrak m_K^2)\otimes_K K'\\
 \downarrow\scriptstyle\cong&&\downarrow\scriptstyle\cong\\
 (JB/(JB)^2)\otimes_{B/JB,f'}K'
   &\xrightarrow{\beta_{f'}}&
 \mathfrak m_{K'}/\mathfrak m_{K'}^2.
\end{array}
\]
The right vertical isomorphism is the coefficient-conormal base-change
isomorphism proved in foundation A, using the actual completed coefficient
object. It is not an assertion that an uncompleted tensor of power-series
rings gives that coefficient object. The left is flat conormal base change.
Commutativity follows because the two operation-compatible maps
\(A\to O_{K'}\) reduce to the same \(A\to K'\), and cofreeness makes them
identical.

The bottom arrow is an isomorphism by normalization upstairs and the conormal
theorem. Hence \(\beta_f\otimes_K K'\), and therefore \(\beta_f\), is an
isomorphism. Apply the conormal theorem over \(K\). This proves the required
derived equivalence to \(K\) for every \(f\).

# theorem thm:F-effective-descent

## statement

For a full integral operation algebra \(R\), let \(\mathcal P(R)\) be the
category of **noetherian original candidate pairs** \((A,J)\), equipped with
an operation-compatible map \(R\to A\). Morphisms are
operation-compatible \(R\)-algebra maps taking the source ideal into the
target ideal. They are automatically continuous for the joint ideal-adic
topologies, since they carry \(\mathfrak mA+J\) into the corresponding
target ideal.

For any operation-compatible map \(R\to S\) which is faithfully flat and
finite locally free on underlying rings, extension of scalars induces an
equivalence
\[
 \mathcal P(R)\ \simeq\
 \operatorname{Desc}_{S/R}(\mathcal P).
 \tag{F.6}
\]
The right side consists of a pair \((A',J')\in\mathcal P(S)\) and an
isomorphism of **full integral operation-algebra pairs** between its two
pullbacks to \(S\otimes_R S\), satisfying the cocycle identity over
\(S\otimes_R S\otimes_R S\). Morphisms must commute with that descent
isomorphism. Tensor products here are ordinary operation-algebra pushouts.
All pair rings that occur in these pullbacks are already complete in their
joint topologies, so no implicit completion or derived tensor is hidden in
this notation.

The base \(R\) is an auxiliary operation algebra, not necessarily a candidate
pair, and no ideal on \(R\) is prescribed. Thus (F.6) is a descent theorem
for the pairs themselves over operation-algebra covers. It does not identify
the category of pairs with operation algebras over one fixed candidate pair.

## proof

**Existence of pullback.** If \((A,J)\in\mathcal P(R)\), then
\(A_S=A\otimes_R S\) is finite locally free over \(A\). It is noetherian,
and as a finite \(A\)-module it is complete for
\((\mathfrak mA+J)A_S\). The underlying tensor ring is the tensor pushout
in \(\mathcal C_E\), by source 1. Proposition F-flat-base-change makes
\((A_S,JA_S)\) a candidate. The same reasoning applies to its iterated
Cech pullbacks, which are finite over \(A\). This establishes every category
and pullback in (F.6).

**Descent of the ring and the full operations.** Start with an object of the
right side. Forget operations and apply module descent, source 6, to the
underlying algebra module \(A'\). Its multiplication and unit commute with
the descent maps, so they descend to a commutative \(R\)-algebra \(A\).
Explicitly, \(A\) is the equalizer of the two maps
\[
 A'\rightrightarrows A'\otimes_R S
\]
defined by the descent datum, with the usual identifications of the two
pullbacks. The canonical map \(A\otimes_R S\to A'\) is a ring
isomorphism.

Both equalizer maps are maps of full operation algebras, because the descent
isomorphism is required to be so. Limits of the full integral theory are
computed on underlying algebras. Consequently the equalizer \(A\) has a
full integral operation structure; concretely, it is closed under every
finite-arity operation. The map \(R\to A\) is operation-compatible, as is
\(A\to A'\). The tensor-pushout property now makes the canonical map
\(A\otimes_R S\to A'\) an operation-algebra map. Its underlying ring map
is an isomorphism, and the forgetful functor is conservative; it is therefore
an isomorphism of full operation algebras. This proves that the given full
operation structure, not just its coefficient or additive portion, descends.

**The ideal.** The descent isomorphism carries the two extensions of \(J'\)
onto one another. Module descent applied to \(J'\subseteq A'\) gives an
\(A\)-submodule \(J\subseteq A\) with \(JA'=J'\); it is the contraction
\(A\cap J'\). Multiplication compatibility shows that it is an ideal.
Neither \(A'/J'\) nor \(A/J\) is being made an operation algebra.

**Noetherianity and regularity.** The map \(A\to A'\) is faithfully flat
finite locally free, as the base change of \(R\to S\). Since \(A'\) is
noetherian, so is \(A\): an ascending chain of ideals stabilizes after
extension to \(A'\), and faithful-flat contraction brings that stabilization
back to \(A\). Lemma F-regular-descent gives the regular immersion of
codimension \(h\) defined by \(J\).

**The specified completeness.** Put \(I=\mathfrak mA+J\). Its extension
to \(A'\) is exactly \(\mathfrak mA'+J'\). By the candidate hypothesis
and noetherianity, \(A'\) is classically complete for that ideal. Lemma
F-finite-faithful-splitting makes \(A\) \(I\)-adically complete. Source 5
then gives derived \(I\)-completeness. Thus the descent proof uses the
actual joint ideal throughout.

**Normalization.** Lemma F-normalization-descent applies to \(A\to A'\)
and \(J\), proving fieldwise normalization downstairs. Therefore
\((A,J)\in\mathcal P(R)\). The construction has recovered the given descent
object after base change, so descent is effective.

**Morphisms and uniqueness.** A morphism of descent data gives a morphism of
underlying descended algebras by the equalizer construction and faithful flat
descent. It respects every integral operation: this identity can be checked
after the faithfully flat, hence injective, map from the target algebra to
its cover. It preserves ideals because this containment can likewise be
checked after faithfully flat base change. Conversely every morphism of
descended pairs gives such a compatible morphism upstairs. These operations
are inverse. This proves full faithfulness, the uniqueness of the descended
pair up to unique compatible isomorphism, and (F.6).

# examples ex:F-limitations

## statement

The coefficient-ideal condition in the continuity proof cannot simply be
dropped, and arbitrary ordinary localizations need not inherit integral
operations. These failures already occur in the genuine height-one theory.

## proof

Take \(k=\mathbf F_p\), \(R=\mathbf Z_p[x]\), and the Frobenius lift
\(\phi|_{\mathbf Z_p}=\mathrm{id}\), \(\phi(x)=x^p+p\). The ring is
\(p\)-torsionfree, and
\(\delta(a)=(\phi(a)-a^p)/p\) defines its genuine integral height-one
operation structure. For \(I=(x)\),
\[
 \delta(x^N)\bmod x=p^{N-1}\neq0
 \qquad(N\geq1).
\]
Thus \(x^N\to0\) \(x\)-adically but its \(\delta\)-images do not tend to
zero. This disproves automatic continuity for arbitrary ideals. It does not
claim that this ring has no noncontinuous operation extension to an
\(x\)-adic completion.

If the ordinary localization \(\mathbf Z_p[x,x^{-1}]\) had a compatible
\(\delta\)-structure, its Frobenius lift would send the unit \(x\) to
\(x^p+p\). But the units of the Laurent polynomial ring over the domain
\(\mathbf Z_p\) are exactly \(c x^a\) with \(c\in\mathbf Z_p^\times\)
and \(a\in\mathbf Z\): comparing lowest and highest exponents in a product
equal to 1 proves this description. Therefore \(x^p+p\) is not a unit,
a contradiction.

These examples justify including operation-compatibility in the flat
base-change theorem. The established descent covers are faithfully flat
finite locally free maps of full operation algebras. No unrestricted formal
Zariski theorem is claimed here; it would require a separate construction of
the relevant completed localizations and their full operation structures.


# definition G1: a restricted derived extension

## statement

A restricted derived pair is a discrete \(A\in\mathcal C_E\), together with a connective animated \(A\)-algebra \(R\), such that:

1. \(A\to\pi_0R\) is surjective with finitely generated kernel \(J\).
2. On a finite principal-open cover of \(\operatorname{Spec}A\), the quotient is a derived zero locus of \(h\) functions:
   \[
   R\simeq A\otimes_{A[t_1,\ldots,t_h]}^{\mathbf L}A,
   \quad t_i\mapsto d_i\text{ on one side and }t_i\mapsto0\text{ on the other}.
   \tag{G1.1}
   \]
   The zero ring away from its closed locus is allowed. This condition concerns underlying rings, not operation structures on their localizations.
3. \(A\) is derived \((\mathfrak mA+J)\)-complete.
4. For every specified perfect-field point \(f:\pi_0R\to K\), its cofree lift makes \(O_K\otimes_A^{\mathbf L}R\to K\) an equivalence.

Morphisms are full operation maps \(g:A\to B\) together with animated \(A\)-algebra maps \(R\to S\). This defines an infinity-category as a subcategory of the fiber product of \(\mathcal C_E\) and the arrow category of animated rings over their base-ring functors. It is an extension with extra quotient data, not a redefinition of classical pairs. It does not put operations on \(R\) or presume a general animated Rezk monad.

## proof of basic properties

The polynomial variables \(t_i\) are a regular sequence over every ring. Their Koszul resolution of the zero section, tensored along \(t_i\mapsto d_i\), shows that the underlying complex in (G1.1) is \(K_A(d_1,\ldots,d_h)\). Thus \(R\) is perfect over \(A\), by the finite-cover criterion for perfectness. It is derived jointly complete as a perfect module over \(A\); its homotopy modules are complete by DC. Maps from a connective animated ring to a discrete field factor uniquely through \(\pi_0\), so the augmentation in condition 4 is canonical. A morphism carries the kernel ideal into the target kernel ideal and is continuous by the same ideal-power argument as A2.

# proposition G2: base change and rigidity in the restricted extension

## statement

Let \((A,R)\) be a restricted derived pair and let \(A\to B\) be a full integral operation map with \(B\) derived \((\mathfrak mB+JB)\)-complete. Then
\( (B,B\otimes_A^{\mathbf L}R)\) is a restricted derived pair, with no flatness hypothesis. Every morphism \((A,R)\to(B,S)\) induces an equivalence
\[
 B\otimes_A^{\mathbf L}R\xrightarrow{\sim}S,
 \quad JB=\ker(B\to\pi_0S).
 \tag{G2.1}
\]
Over a fixed restricted derived pair, the category is equivalent to the ordinary category of full operation \(A\)-algebras \(B\) satisfying the displayed joint completeness condition.

## proof

Derived zero-locus presentations pull back, as do their finite open cover and their finite generators. Connectivity gives \(\pi_0(B\otimes_A^{\mathbf L}R)=B/JB\). Completeness is exactly the assumption on \(B\), not a consequence of completeness of \(A\). For a point \(B/JB\to K\), naturality of cofreeness identifies the restricted lift on \(A\). Associativity then gives
\[
 O_K\otimes_B^{\mathbf L}(B\otimes_A^{\mathbf L}R)
 \simeq O_K\otimes_A^{\mathbf L}R\simeq K
\]
with its canonical augmentation.

For rigidity, take the perfect cone of the comparison in (G2.1). At a maximal ideal of \(B\), its perfected residue field is a permitted point of \(\pi_0S\), by the radical argument A2. The two cofree base changes are \(K\), and the comparison respects their augmentations, hence is an equivalence. A further derived base change to \(K\) kills the cone. Perfect detection A2 proves (G2.1), and \(\pi_0\) gives ideal equality. The two individual derived fibers over \(K\) here are typically \(K\otimes_{O_K}^{\mathbf L}K\), with exterior Tor; they are not being identified with the discrete field.

This proof adapts but does not apply as a higher-height black box the following precise height-one result: `paper_id=Bhatt-Lurie-prismatization`, `arXiv=2201.06124v1`, `theorem_id=Remark 2.9 (AnimPrismStrict)`: a morphism of animated prisms induces an equivalence of the base-changed quotient with the target quotient and consequently of generalized invertible ideals. Their objects have animated \(\delta\)-rings and codimension-one generalized Cartier divisors. Their proof uses the same perfect cone, residue-field and cofree-Witt argument; we have supplied its replacement for the objects actually defined in G1. [Source](https://arxiv.org/abs/2201.06124v1).

Finally the base-change construction is inverse to forgetting the quotient over a fixed pair, by (G2.1). For an operation \(A\)-algebra map \(B\to B'\), the universal property of the pushout supplies a contractible space of quotient maps under the fixed \(R\). This proves the categorical equivalence, including its mapping spaces. Without a fixed source pair the quotient data remain part of an object.


The example D4 has a positive interpretation in this category: base-changing \(W(k),(W(k)/p)\) along the nonflat full operation map \(W(k)\to B_N\) gives the restricted derived pair \((B_N,B_N//p)\). Its normalization follows directly from the Koszul complex on \(p\) in \(W(K)\), although its ordinary quotient fails D4.

# lemma G3: complete Koszul regularity

## statement

If a ring \(A\) is derived complete for a proper ideal \(J=(d_1,\ldots,d_h)\), and \(K_A(d_1,\ldots,d_h)\) has no positive homology, then the sequence is an ordinary regular sequence in that order. No noetherianity is needed for this global assertion.

## proof

If a derived \(a\)-complete module \(M\) has surjective multiplication by \(a\), then \(M=0\). Otherwise successively lifting a nonzero element along that surjection gives a nonzero element in the ordinary inverse limit of the multiplication-by-\(a\) system. This is the zeroth homology of its homotopy inverse limit, which vanishes by derived completeness. This is also the principal-ideal case of DC's derived Nakayama.

Set \(C=K_A(d_1,\ldots,d_{h-1})\). Its homology modules are derived \(d_h\)-complete, because \(A\) is and \(C\) is a finite free complex, using DC. The triangle \(C\xrightarrow{d_h}C\to K_A(d_1,\ldots,d_h)\) shows that multiplication by \(d_h\) on every \(H_i(C)\), \(i>0\), is surjective. The preceding observation kills those groups. The vanishing of \(H_1\) of the full complex then makes \(d_h\) injective on \(H_0(C)=A/(d_1,\ldots,d_{h-1})\). Induction proves that the prefix is regular too; every prefix ideal is proper since the final ideal is proper.

# proposition G4: precise classical comparison and further derived scope

## statement

The functor \((A,J)\mapsto(A,A/J)\) embeds original classical candidates fully faithfully into the restricted derived category. Over noetherian bases its image consists precisely of the objects with discrete quotient. The same converse holds without noetherianity for a quotient with a global presentation (G1.1). For arbitrary locally presented nonnoetherian objects the proved implication from discreteness is Koszul regularity; the general upgrade to a locally ordinary regular immersion is not asserted here. A general animated-base or unbounded higher operation theory is further work.

## proof

A regular quotient has its Koszul resolution and thus its ordinary quotient agrees with the derived zero locus. All field and completeness conditions are then unchanged. Animated maps into a discrete ring form a discrete mapping space and factor through \(\pi_0\). Consequently a map between two classical quotients over an operation map exists exactly when it carries the source ideal into the target ideal, and it is unique. This proves full faithfulness.

If \(R\) is discrete, a local Koszul presentation is exact in positive degrees. At every point of its support, over a noetherian local base the generators lie in the maximal ideal, so KA converts this Koszul regularity to ordinary regularity. The regular-immersion assertion holds on neighborhoods: after choosing the finite generators there, the finitely generated successive annihilator modules over a noetherian ring vanish on a smaller neighborhood when their localizations vanish. Conversely ordinary regularity makes the quotient discrete. In the global nonnoetherian case, joint completeness implies completeness for the subideal \(J\), and G3 gives the converse directly. Ordinary localization can lose completeness, so this global argument has not proved the unrestricted local nonnoetherian converse. This explicitly delimits the extension while leaving the proved classical package and G2 intact.


# theorem thm:foundations — the complete foundational package

## statement

For the candidate higher-prism pair $(A,J)$ defined in this problem, establish a mathematically explicit integral ambient category and canonical perfect-field lifts, and resolve foundations A–F by complete proofs or precise proved counterexamples. The resulting foundational theorem must state the exact hypotheses under which the conormal characterization, height-one recovery, normalization and ramified examples, morphism rigidity, base change, and effective descent hold. It must distinguish the original candidate from any repaired variant, identify the scope of nonnoetherian and derived extensions, and separate further questions from the verified classical results. The final proof must not presume a relationship with indexed Witt ideals or a pre-existing higher prismatic cohomology theory.

## proof

Use the original classical definition in the input, interpreted in the ordinary degree-zero full integral category of the conventions. The following exact package resolves the requested foundations.

1. **Ambient category, topology and detection.** A1 constructs the canonical cofree lift and proves the natural coefficient formula with joint derived completion of the derived coefficient tensor. A2 proves continuity in the prescribed ideal topologies, the Jacobson containment and nonvacuity for every nonzero complete ring, and the finite/perfect range of perfected-residue detection. A3 gives the precise relation to the coefficient-completed monad; it retains joint completeness. None of these assertions requires noetherianity of a candidate.
2. **Primitivity and height one.** For any ordinary regular immersion of codimension \(h\), B1 proves equivalence of the original canonical derived field normalization, generation of \(\mathfrak m_K\), and the intrinsic conormal isomorphism, for every specified field point. Local generators, coefficients, and their trivializations play no definitional role. B2 proves the finite-coordinate computation at fixed \(E\); no small general formula is postulated. C1 proves equivalence with all classical prisms carrying the compatible \(W(k)\)-structure, including locally principal and unbounded cases, and distinguishes the scalar \(\bar u\) from \(\bar u^p\).
3. **Examples and necessary hypotheses.** D1 proves the normalization and all the specified ramified examples with their actual topological operations and cofree augmentation lifts; it proves that the nonprimitive coefficient ideal fails. D2 proves that coefficient completeness cannot replace joint completeness, that removing completeness permits vacuity and failed rigidity, and that the prism ideal need not be operation-stable. D3–D4 give an actual noetherian integral torsion operation algebra with primitive free conormal but nonzero higher Tor, excluding removal of regularity and arbitrary ordinary base change. D5 supplies singular classical examples with nonzero coefficient torsion. No assertion of coefficient torsion-freeness or ambient regularity is implicit in the definition.
4. **Morphisms.** E1 proves \(JB=L\) and \(B\otimes_A^{\mathbf L}A/J\simeq B/L\) for every map of original candidates, first with the requested local noetherian regular-generator calculation and then with a perfect-complex proof valid for arbitrary rings. E2 identifies precisely the full subcategory of operation algebras over one fixed pair: the extended ideal must still be an ordinary regular immersion and the target must be jointly derived complete.
5. **Base change, completion and descent.** F-flat-base-change proves classical flat base change for operation maps whose target is jointly derived complete, with no noetherian or torsion hypothesis. F-uniform-continuity proves continuity of every full integral operation for any ideal containing the coefficient ideal. F-joint-completion then gives the unique full integral structure, flatness and preservation of ordinary regular immersions for noetherian joint completions. Finally F-effective-descent is an equivalence of categories for noetherian original pairs over any auxiliary operation base, under faithfully flat finite locally free maps of full operation algebras with full operation-compatible cocycle data. Its proof descends the operations, ring, ideal, regular immersion, exact joint completeness, field normalization and all morphisms. These are the established covers; no formal Zariski or unrestricted flat-descent claim is hidden in the conclusion.
6. **Derived scope and remaining questions.** G1 is an explicitly separate category over discrete full operation bases, with finite local derived zero-locus quotients of codimension \(h\). G2 proves arbitrary operation-compatible base change subject to target joint completeness and proves rigidity. G3–G4 prove the fully faithful classical comparison and characterize discrete quotients over noetherian bases or for global complete presentations. For arbitrary locally presented nonnoetherian derived quotients the ordinary-regularity converse is not claimed. General animated bases, unbounded operation theories, more general completion and further cover classes remain questions, without affecting any of the preceding classical conclusions.

Every required foundation therefore has a proved affirmative statement with explicit scope or a proved negative test. The original candidate was retained throughout A–F. The derived extension was separately defined and every assertion about it used here was proved. The only indexed filtration used in A1–B2 computes the intrinsic coefficient object; it is never identified with the unindexed ideal \(J\). No pre-existing higher prismatic cohomology theory, indexed-ideal relationship, envelope, or application is assumed.
