# Completion, flat base change, and finite locally free descent

This is the proof memo for the `classical_conormal` branch of
`higher_prisms/foundations`. It addresses foundation F and the completion issue
in A. It uses the ordinary, even, full integral Rezk operation-algebra category
fixed in foundation A. It does not replace that category by modules for the
additive operation algebra. The parent proof supplies the cofree lifts and the
conormal characterization in A–B. No partial proof has been submitted to the
whole-proof verifier.

## Dependencies and precise source statements

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

The sources have been read in the supplied versions, including the relevant
proofs. Downloaded copies of the two older operation papers are in
`downloads/higher_prisms/foundations/classical_descent/`. The proofs below of
joint continuity, operation-structure descent, and fieldwise-normalization
descent are new deductions from these inputs. Their statements are not being
attributed to Barthel–Frankland or to ordinary module descent.

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
global associativity or commutativity of \(K_E\) is not needed here.

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

## Claim status for the assigned branch

| Claim | Status and exact scope | Proof |
| --- | --- | --- |
| Joint continuity of the actual integral operations | Proved for every ordinary full operation algebra and every ideal containing \(\mathfrak mR\); no noetherian or torsion assumption | Lemmas F-augmentation-nilpotent and F-uniform-continuity |
| Preservation of full operation structure by joint completion | Proved for noetherian rings and \(I\supseteq\mathfrak mR\), including \(I=\mathfrak mR+J\); uniqueness is unconditional | Proposition F-joint-completion |
| Preservation of ordinary regular immersions by completion | Proved in the same noetherian class by flatness | Proposition F-joint-completion |
| Flat base change | Proved for operation-compatible flat maps with the specified target joint derived completeness; no noetherian or torsion assumption | Proposition F-flat-base-change |
| Completed flat base change | Proved when the intermediate ring being completed is noetherian | Proposition F-flat-base-change |
| Effective descent of pairs and all their morphisms | Proved for faithfully flat finite locally free full operation-algebra covers, for noetherian original candidate pairs, with full operation-compatible cocycle data | Theorem F-effective-descent |
| Extension to all ordinary localizations | False, even at height one | Example F-limitations |
| Arbitrary nonnoetherian completion preserving ordinary regularity; arbitrary animated full-operation completion; formal Zariski descent | Not asserted by this branch; outside the proved F theorem | Explicit scope of the preceding statements |

The assigned classical completion and finite-locally-free descent obligations
are resolved by these proofs, subject to integration with A's actual cofree
category and B's intrinsic conormal theorem. This memo is not a claim that the
entire A–F package has already passed verification.
