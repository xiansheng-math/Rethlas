# Restricted derived quotients and actual-operation examples

This is the proof memo for the `derived_quotient` branch of
`higher_prisms/foundations`. It is not a whole-problem verifier submission.
The ambient ordinary integral operation category and the coefficient-cofree
theorem are inputs from foundations A. No operation structure on an animated
quotient, and no general animated Rezk monad, is asserted here.

The exact original problem is `data/higher_prisms/foundations.md`. The reference
guide has been read. In particular, the supplied Bhatt–Lurie source is titled
*The prismatization of p-adic formal schemes*, arXiv:2201.06124v1; the guide's
description as *Absolute prismatic cohomology* should not be copied into a final
bibliographic entry.

# definition def:restricted-derived-pair

## statement

Let \(\mathcal C_E\) be the ordinary category of full integral degree-zero
Rezk operation algebras over \(O\) identified in foundation A. Write
\(U:\mathcal C_E\to\mathrm{CAlg}_O\) for its forgetful functor. Assume the
proved cofree mapping property
\[
 \operatorname{Hom}_{\mathcal C_E}(A,\mathbb W_E(K))
 \simeq \operatorname{Hom}_{\mathrm{CAlg}_O}(U(A),K),
 \qquad O_K:=\mathbb W_E(K),
\]
with counit \(O_K\to K\), and the coefficient-ring identification from A.

A **restricted derived pair** is an ordinary \(A\in\mathcal C_E\) together
with a connective simplicial commutative \(A\)-algebra \(R\), satisfying:

1. \(A\to\pi_0R\) is surjective, with finitely generated kernel \(J\).
2. Zariski locally on \(\operatorname{Spec}A\), \(R\) is a derived zero
   locus of \(h\) functions. More explicitly, on a finite principal-open
   cover it has the form
   \[
    R\simeq A\mathbin{\otimes^{\mathbf L}_{A[t_1,\ldots,t_h]}} A,
    \tag{DQ}
   \]
   where the two polynomial-algebra maps send \(t_i\) respectively to
   \(d_i\) and to \(0\). The corresponding zero ring off the closed locus
   is allowed. All localizations in this condition are of the underlying
   rings; no localization of the operation structure is required.
3. \(A\) is derived \((\mathfrak mA+J)\)-complete.
4. For every compatible perfect-field point \(f:\pi_0R\to K\), the
   canonical cofree lift \(\widetilde f:A\to O_K\) makes the canonical
   augmented map
   \[
    O_K\otimes_A^{\mathbf L}R\longrightarrow K
   \]
   an equivalence.

Here the tensor product in (DQ), and those of quotient algebras below, are
homotopy pushouts of simplicial commutative rings. Their underlying derived
module tensor products compute the homotopy groups used in the proofs.

A morphism \((A,R)\to(B,S)\) consists of an ordinary operation-compatible
\(O\)-algebra map \(g:A\to B\) and an animated \(A\)-algebra map
\(R\to S\), with \(S\) regarded as an \(A\)-algebra using \(g\).
Thus \(g(J)\subseteq L:=\ker(B\to\pi_0S)\). It is automatically
continuous for the \((\mathfrak mA+J)\)-adic and
\((\mathfrak mB+L)\)-adic topologies.

## explanation

The phrase “derived zero locus” in this definition replaces regularity of the
ordinary quotient by a specified derived quotient. It adds quotient data and
does not silently alter the original classical definition. The operation
structure is only on the discrete base. The category is the appropriate
subcategory of the fibre product of the ordinary category
\(\mathcal C_E\) with the arrow infinity-category of animated rings over
the ordinary base-ring functor. Thus its definition requires no animation of
the higher operation theory.

Maps to a discrete field factor uniquely through \(\pi_0\), so the
augmentation in condition 4 is canonical. A local presentation (DQ) has
underlying \(A\)-module the finite Koszul complex
\(K_A(d_1,\ldots,d_h)\). One way to see this is to resolve the zero-section
quotient \(A[t_1,\ldots,t_h]/(t_1,\ldots,t_h)=A\) by its Koszul complex:
the polynomial variables are a regular sequence over every ring. Tensoring
that resolution along \(t_i\mapsto d_i\) gives the displayed complex.
In particular, \(R\) is a perfect \(A\)-module. Perfection is Zariski local
on a finite affine cover; this can equivalently be included in the definition
as the requirement of a locally finite complex of finite free modules.

Consequently \(R\), as an \(A\)-module, is derived
\((\mathfrak mA+J)\)-complete: complete complexes are closed under finite
cones and direct summands. The induced topology on \(\pi_0R=A/J\) is the
\(\mathfrak m\)-adic topology. No second completion of an operation
algebra is used in this construction.

# lemma lem:perfect-fibre-detection

## statement

Let \(B\) be any commutative ring and let \(P\) be a perfect complex of
\(B\)-modules. If
\[
 P\otimes_B^{\mathbf L}\kappa(\mathfrak n)=0
\]
for every maximal ideal \(\mathfrak n\), then \(P=0\). The same conclusion
holds if the test fields are arbitrary field extensions of these residue
fields, in particular their perfections in characteristic \(p\).

## proof

It suffices to show that \(P_{\mathfrak n}=0\) for every maximal ideal:
an arbitrary module is zero if all its maximal-ideal localizations are zero,
and localization commutes with homology. Over the local ring
\(B_{\mathfrak n}\), represent the perfect complex by a bounded complex
of finite free modules. Its reduction to the residue field is acyclic.

At the highest nonzero cochain degree \(b\), the map from degree \(b-1\)
to degree \(b\) is surjective modulo the maximal ideal. Its cokernel is
finite, so Nakayama makes the map surjective over the local ring. It splits
because its target is free. Split off this contractible two-term direct
summand and repeat on the shorter complex. Eventually no terms remain.
Hence the original local complex is contractible. A field extension is
faithfully flat, so vanishing after it is equivalent to vanishing before it.
No noetherian hypothesis on \(B\) is used. \(\square\)

# lemma lem:derived-base-change

## statement

Let \((A,R)\) be a restricted derived pair, and put
\(J=\ker(A\to\pi_0R)\). Let \(g:A\to B\) be an ordinary integral
operation-compatible \(O\)-algebra map. Assume precisely that \(B\) is
derived \((\mathfrak mB+JB)\)-complete. Then
\[
 (B,R_B),\qquad R_B:=B\otimes_A^{\mathbf L}R,
\]
is a restricted derived pair. No flatness assumption is needed.

## proof

The local presentations (DQ) pull back to derived zero loci of the images of
the same functions. Their finite principal-open cover pulls back to a cover
of \(\operatorname{Spec}B\). Connectivity and the right exactness of
\(\pi_0\) on connective pushouts give
\[
 \pi_0R_B=B\otimes_A\pi_0R=B/JB.
\]
The kernel remains finitely generated. Completeness is exactly the assumed
condition; it is not inferred from completeness of \(A\).

Let \(f_B:B/JB\to K\) be a compatible perfect-field point. It induces a
point \(f_A:A/J\to K\). The composite
\(A\to B\xrightarrow{\widetilde f_B}O_K\) is an operation-compatible
lift of \(f_A\). The cofree mapping property therefore identifies it with
\(\widetilde f_A\). Associativity of derived tensor products now gives,
compatibly with the augmentations,
\[
 O_K\otimes_B^{\mathbf L}R_B
 \simeq O_K\otimes_A^{\mathbf L}R
 \simeq K.
\]
This proves normalization. \(\square\)

# lemma lem:derived-rigidity

## statement

Every morphism \((A,R)\to(B,S)\) of restricted derived pairs induces an
equivalence
\[
 B\otimes_A^{\mathbf L}R\xrightarrow{\ \sim\ }S.
 \tag{DR}
\]
In particular \(JB=L\), where \(J=\ker(A\to\pi_0R)\) and
\(L=\ker(B\to\pi_0S)\). No noetherian or torsion-free hypothesis is
needed.

## proof

Both sides of (DR) are perfect \(B\)-modules. Let \(P\) be the cone of
their comparison map; it is perfect. Derived
\((\mathfrak mB+L)\)-completeness implies
\(\mathfrak mB+L\subseteq\operatorname{Jac}(B)\), by the radical lemma
from foundation A. Thus every maximal residue field \(\kappa(\mathfrak n)\)
is a characteristic-\(p\) field extending \(k\), and its perfection
\(K\) is an allowed test field. The residue map factors through
\(B/L=\pi_0S\), and, since \(g(J)\subseteq L\), gives a point of
\(\pi_0R\) as well.

Cofree uniqueness again identifies the cofree lift from \(A\) with the
composite of \(g\) and the lift from \(B\). After tensoring (DR) with
\(O_K\), both sides identify with \(K\) by normalization. The comparison
commutes with their canonical augmentations, so it is an equivalence.
Further derived tensoring along \(O_K\to K\) proves
\(P\otimes_B^{\mathbf L}K=0\). Lemma
`lem:perfect-fibre-detection` gives \(P=0\). Taking \(\pi_0\) gives
\(B/JB=B/L\) compatibly with the quotient maps, hence \(JB=L\).

Notice the intermediate fibres over \(K\) are generally
\(K\otimes_{O_K}^{\mathbf L}K\), not the discrete field \(K\). Only
the equivalence of the comparison map is needed. \(\square\)

## source and applicability

This adapts the argument of Bhatt–Lurie, *The prismatization of p-adic formal
schemes*, `paper_id=Bhatt-Lurie-prismatization`, `arXiv id=2201.06124v1`,
`theorem_id=Remark 2.9 (label AnimPrismStrict)`. Its complete assertion used
as motivation is: a morphism of animated prisms
\((A\to A/I)\to(B\to B/J)\) induces an equivalence
\(B\otimes_A^{\mathbf L}A/I\to B/J\), and therefore also an equivalence
of the corresponding generalized invertible ideals. In that paper an
animated prism has an animated \(\delta\)-ring as base and a generalized
Cartier divisor whose fibre is an invertible module. Its proof uses perfect
module quotients, completeness to obtain residue-field points, and the
cofree Witt lifts. The proof above uses precisely those features and supplies
the higher-codimension argument in full. It does not apply the paper's
height-one animation construction to Rezk operations at higher height.

# corollary cor:derived-over-fixed-pair

## statement

Fix a restricted derived pair \((A,R)\). Its category of restricted derived
pairs over \((A,R)\) is equivalent to the ordinary category of integral
operation-compatible \(A\)-algebras \(B\) that are derived
\((\mathfrak mB+JB)\)-complete, where \(J=\ker(A\to\pi_0R)\).

## proof

The base-change lemma constructs a pair over \((A,R)\) from each such
\(B\). Conversely, rigidity identifies the quotient of any pair over
\((A,R)\) with \(B\otimes_A^{\mathbf L}R\), and identifies its ordinary
ideal with \(JB\). Given a map of operation \(A\)-algebras, the universal
property of this pushout supplies a contractible space of compatible maps
of the quotients under \(R\). These constructions are inverse. This is an
assertion about the category **over the fixed pair**; the unrestricted
category of pairs retains its quotient data. \(\square\)

# lemma lem:complete-global-koszul

## statement

Let \(A\) be any ring, derived complete for the proper finitely generated
ideal \(J=(d_1,\ldots,d_h)\). If \(K_A(d_1,\ldots,d_h)\) is discrete,
then \(d_1,\ldots,d_h\) is an ordinary regular sequence in that order.

## proof

We recall the needed completeness facts and their proofs. For \(f\in A\),
derived \(f\)-completeness is equivalent to vanishing of
\(R\operatorname{Hom}_A(A[1/f],-)\). The module \(A[1/f]\) has the
two-term free telescope resolution
\[
 0\longrightarrow\bigoplus_{n\ge0}A
 \xrightarrow{\,e_n\mapsto e_n-fe_{n+1}\,}
 \bigoplus_{n\ge0}A\longrightarrow A[1/f]\longrightarrow0.
\]
Applying \(R\operatorname{Hom}\) identifies it with the homotopy inverse
limit of repeated multiplication by \(f\). The hyper-Ext spectral
sequence has only columns 0 and 1. Its short exact edge sequences show
that a complex is derived \(f\)-complete if and only if every homology
module is. These complete complexes are closed under cones and direct
summands.

If a derived \(f\)-complete module \(M\) has surjective multiplication
by \(f\), then \(M=0\). Otherwise a nonzero element can be extended,
by successively choosing preimages, to a nonzero element of
\(\varprojlim(M\xleftarrow f M\xleftarrow f\cdots)\), contradicting
the vanishing of the preceding homotopy inverse limit.

Put \(C=K_A(d_1,\ldots,d_{h-1})\). It is derived \(d_h\)-complete
because \(A\) is and \(C\) is a finite complex of finite free modules.
Its homology modules are therefore derived \(d_h\)-complete. The exact
triangle
\[
 C\xrightarrow{d_h}C\longrightarrow K_A(d_1,\ldots,d_h)
\]
and the assumed vanishing of positive homology imply that \(d_h\) acts
surjectively on \(H_i(C)\) for every \(i>0\). The preceding observation
kills those groups. Now the same triangle identifies
\(H_1(K_A(d_1,\ldots,d_h))\) with the kernel of multiplication by
\(d_h\) on \(H_0(C)=A/(d_1,\ldots,d_{h-1})\). This kernel is zero.
Apply induction to the shorter complex. Every prefix ideal is proper
because the final ideal is proper. This gives ordinary regularity.

The standard reference for the completeness facts, whose relevant proofs
have just been supplied, is the Stacks Project,
`paper_id=Stacks-Project`, `theorem_id=Tag 091N, Lemmas 15.93.1,
15.93.6, 15.93.7`, with no arXiv identifier. Their applicable statements are:
derived \(f\)-completeness is equivalent to completeness of all cohomology
modules; derived \(I\)-complete modules form a weak Serre subcategory;
and a derived \(I\)-complete module \(M\), for finitely generated \(I\),
vanishes if \(M/IM=0\). These statements require no noetherian hypothesis.
The proof uses them only for principal ideals and finite Koszul complexes.
\(\square\)

## scope warning

The global completeness used here can be lost on ordinary localization.
Consequently this lemma alone does not prove the converse for every locally
presented nonnoetherian derived zero locus. The proved comparison scopes are
the noetherian case, height one, and the global-presentation case. This limitation does
not affect base change or rigidity of the restricted derived category.

# lemma lem:classical-comparison

## statement

The assignment \((A,J)\mapsto(A,A/J)\) embeds the original classical
candidate category fully faithfully into the restricted derived category.
Here “regular immersion” has its usual finite-type local meaning, so a
finite affine cover carries regular sequences of the specified length.

For a restricted derived pair over a noetherian ordinary base \(A\), the
object lies in this classical image if and only if \(R\) is discrete.
The same equivalence holds at \(h=1\) over an arbitrary ordinary base.
For arbitrary \(A\), discreteness says that its local defining sequences
are Koszul-regular. One may not omit the distinction between Koszul and
ordinary regularity without an additional argument.

There is an additional nonnoetherian case: if \(R\) has a global
presentation \(A//(d_1,\ldots,d_h)\), discreteness does imply ordinary
regularity, under the joint derived completeness already imposed.

## proof

A regular sequence has an acyclic positive-degree Koszul complex, so its
derived quotient is its ordinary quotient. Inductively, tensoring the
two-term resolution for the next nonzerodivisor resolves the next quotient.
These local identifications show that every classical pair defines a
restricted derived pair, with exactly the same fieldwise normalization and
completeness condition. Animated maps to a discrete ring form a discrete
mapping space and factor uniquely through \(\pi_0\). Hence a map between
two such quotients over an operation map exists exactly when the ideal maps
into the target ideal, and is then unique. This proves full faithfulness.

Conversely, at a point of \(\operatorname{Spec}A\) containing \(J\),
a local presentation of a discrete \(R\) has Koszul homology zero in all
positive degrees. If \(A\) is noetherian, the defining functions lie in
the maximal ideal of its local ring; Koszul regularity and ordinary
regularity then agree. One can see the converse directly by induction:
write the full Koszul complex as the cone of the last defining element on
the shorter Koszul complex. The vanishing of positive homology makes that
element act surjectively on every positive homology module of the shorter
complex. These modules are finite over the noetherian local ring, so
Nakayama kills them. The vanishing of the first homology of the full
complex then gives injectivity on the ordinary shorter quotient. Induct
on the length. At \(h=1\), no noetherian assumption is needed:
the sole positive Koszul homology is the annihilator of the local defining
element. For completeness, the higher-length noetherian assertion is the
applicable statement
of the Stacks Project, `paper_id=Stacks-Project`, `theorem_id=Tag 062D,
Lemma 15.31.7`: if \((T,\mathfrak n)\) is noetherian local, \(M\ne0\)
is a finite \(T\)-module, and \(a_i\in\mathfrak n\), then being an
\(M\)-regular, \(M\)-Koszul-regular, \(M\)-\(H_1\)-regular, or
\(M\)-quasi-regular sequence are equivalent. There is no arXiv identifier.
Its proof proceeds through regular implies Koszul implies \(H_1\) implies
quasi-regular, and the noetherian local quasi-regular criterion. We apply it
with \(M=T=A_{\mathfrak q}\); each hypothesis has been checked. The
noetherian finiteness is precisely what makes that reverse implication
available. The preceding lemma supplies the separate global complete argument
without this hypothesis. \(\square\)

# lemma lem:delta-quotient-construction

## statement

In height one put \(W=W(k)\). The \(\delta\)-rings in the examples below
are actual full integral operation algebras. If a \(\delta\)-ring ideal is
generated by elements \(r_i\) with \(\delta(r_i)\) in the ideal, then
the ideal is stable under \(\delta\), so the quotient inherits all
\(\delta\)-identities, even when the quotient has \(p\)-torsion.

## proof

Use the integral identities
\[
 \delta(a+b)=\delta(a)+\delta(b)
       -\frac{(a+b)^p-a^p-b^p}{p},\qquad
 \delta(ab)=a^p\delta(b)+b^p\delta(a)+p\delta(a)\delta(b).
\]
The correction polynomial for a sum of elements of an ideal lies in that
ideal, and the product identity shows that arbitrary multiples of each
generator remain stable. Thus sums of such multiples remain stable. The
quotient operation is well defined: if \(b\) is in the ideal, the same
sum identity gives \(\delta(a+b)-\delta(a)\) in the ideal.

At height one the full cofree comonad is the classical \(p\)-typical Witt
comonad, and its coalgebras are \(\delta\)-rings with the compatible
\(W(k)\)-structure. The precise supplied source is Rezk,
*The Witt filtration of Lubin–Tate deformation rings*,
`paper_id=Rezk-Witt-filtration`, `arXiv id=2603.12490v1`,
`theorem_id=Example 1.1`: for a height-one formal group over \(k\),
\(O=W(k)\), \(\mathbb W_E\) is the classical \(p\)-typical Witt
functor on \(W(k)\)-algebras, and the comonad structure recovers the theory
of \(\delta\)-rings. The parent height-one comparison audits this category
identification. The examples below first construct \(\delta\) on a
\(p\)-torsion-free ring and then take a proved \(\delta\)-stable quotient;
they never infer a \(\delta\)-structure from a Frobenius lift on a
\(p\)-torsion ring. \(\square\)

# counterexample ex:nonflat-primitive-conormal

## statement

For any integer \(N\ge2\), let
\[
 B_N=W[\epsilon]/(\epsilon^2,p^N\epsilon),\qquad L=(p),
 \qquad\delta(\epsilon)=0.
\]
Then \(B_N\) is a noetherian, derived \((p,L)\)-complete full integral
height-one operation algebra, and \(W\to B_N\) is operation compatible.
The following assertions hold:

- \(L/L^2\) is free of rank one over \(B_N/L\).
- Every fieldwise conormal map for \(L\) is an isomorphism.
- \(p\) is a zero divisor in \(B_N\); thus \((B_N,L)\) is not a
  classical candidate.
- More strongly, the ordinary quotient does not satisfy fieldwise derived
  normalization:
  \[
   \operatorname{Tor}^{B_N}_2(W(K),B_N/p)\simeq K\ne0
  \]
  for every compatible perfect extension \(K/k\).
- The derived quotient \((B_N,B_N//p)\) is a restricted derived pair,
  obtained by base change from the genuine classical normalization pair
  \((W,(p))\).

## proof

Start with the \(p\)-torsion-free ring \(W[\epsilon]\), with Frobenius
lift \(\phi_W\) on coefficients and \(\phi(\epsilon)=\epsilon^p\).
It has \(\delta(\epsilon)=0\). We have
\[
 \delta(\epsilon^2)=0,\qquad
 \delta(p^N\epsilon)=\delta(p^N)\epsilon^p\in(\epsilon^2).
\]
The preceding lemma proves stability of the entire ideal. Thus the quotient
carries actual integral operations. As a \(W\)-module,
\[
 B_N=W\oplus(W/p^N)\epsilon.
\]
It is a finite module over the complete noetherian discrete valuation ring
\(W\), so is noetherian and classically \(p\)-adically complete, hence
derived \(p\)-complete. Its nonzero annihilator of \(p\) is
\[
 M:=B_N[p]=p^{N-1}(W/p^N)\epsilon\simeq k.
\]
For \(N\ge2\), \(M\subseteq pB_N\). The surjection
\[
 B_N/pB_N\longrightarrow pB_N/p^2B_N,\qquad\bar b\longmapsto pb,
\]
has kernel \((B_N[p]+pB_N)/pB_N=0\), proving conormal freeness.

Since \(B_N/p=k[\epsilon]/(\epsilon^2)\), every compatible field point
kills \(\epsilon\). The projection \(B_N\to W\), followed by the
coefficient map \(W\to W(K)\), is an operation-compatible lift of this
point. Cofreeness identifies it as the canonical lift. It sends \(p\) to
\(p\). Therefore the induced conormal map takes a basis to the basis of
\(pW(K)/p^2W(K)\), and is an isomorphism.

The underlying complex of \(Q:=B_N//p\) is
\([B_N\xrightarrow p B_N]\), in homological degrees 1 and 0. Hence
\(\pi_1Q=M\), \(\pi_0Q=B_N/p\), and there is a truncation triangle
\[
 M[1]\longrightarrow Q\longrightarrow B_N/p.
\]
Tensor it with \(W(K)\) over \(B_N\). The middle term is
\([W(K)\xrightarrow p W(K)]\simeq K\). The long exact homotopy
sequence yields
\[
 \pi_2\bigl(W(K)\otimes_{B_N}^{\mathbf L}B_N/p\bigr)
 \simeq H_0\bigl(W(K)\otimes_{B_N}^{\mathbf L}M\bigr)
 =W(K)\otimes_{B_N}M=K.
\]
The final equality holds because \(M\simeq k\) as a \(B_N\)-module,
with \(p\) and \(\epsilon\) acting by zero. This proves failure of
ordinary normalization. The base-change lemma gives the positive derived
assertion, or it follows directly from the same two-term complex.
Finally \(W\to B_N\) is nonflat because \(B_N[p]\ne0\), whereas a
flat \(W\)-module has injective multiplication by \(p\).
\(\square\)

## consequence

This is a single actual-operation counterexample to three proposed
strengthenings: arbitrary ordinary base change preserves classical pairs;
conormal freeness can replace regularity; and primitive conormal maps alone
imply normalization of an ordinary quotient. It includes completeness and
noetherianity, so their addition does not repair those statements.

# example ex:torsion-singular-classical

## statement

For every integer \(N\ge1\), put
\[
 C_N=W[[d]][\epsilon]/(\epsilon^2,p^N\epsilon),
 \qquad J=(d),\qquad \delta(d)=1,\quad\delta(\epsilon)=0.
\]
Then \((C_N,J)\) is a genuine classical height-one candidate. Its ring
has nonzero \(p\)-torsion and is singular and nonreduced. Thus neither
\(p\)-torsion-freeness nor regularity of the ambient ring follows from the
candidate axioms.

## proof

First put a Frobenius lift on the \(p\)-torsion-free ring
\(W[[d]][\epsilon]\) by
\[
 \phi|_W=\phi_W,\qquad \phi(d)=d^p+p,
 \qquad\phi(\epsilon)=\epsilon^p.
\]
Substitution in formal series converges for the \((p,d)\)-adic topology
because \(d^p+p\in(p,d)\). It defines a ring endomorphism and reduces
to Frobenius modulo \(p\). Thus \(\delta=(\phi-(-)^p)/p\) exists,
with the stated values. The computations in the preceding counterexample
show that \((\epsilon^2,p^N\epsilon)\) is \(\delta\)-stable.

The underlying \(W[[d]]\)-module is
\[
 C_N=W[[d]]\oplus(W/p^N)[[d]]\epsilon.
\]
Multiplication by \(d\) is injective on both summands. The quotient is
\(W[\epsilon]/(\epsilon^2,p^N\epsilon)\ne0\), so \(d\) is a regular
generator. The displayed finite module is classically \((p,d)\)-complete,
hence derived \((p,d)\)-complete; the ring is noetherian.

Here the canonical cofree lift can be given explicitly. There is a unique
\(q_p\in p\mathbf Z_p\) satisfying
\[
 q_p=q_p^p+p.
\]
Indeed iteration of \(q\mapsto q^p+p\), starting at zero, converges on
\(p\mathbf Z_p\): for \(a,b\) there,
\(a^p-b^p\in p^{p-1}(a-b)\mathbf Z_p\). The same estimate proves
uniqueness. Furthermore \(q_p/p\equiv1\pmod p\).

Every compatible perfect-field point of \(C_N/d\) sends both \(p\)
and \(\epsilon\) to zero. The map
\[
 C_N\longrightarrow W(K),\qquad d\longmapsto q_p,
 \quad\epsilon\longmapsto0,
\]
with the coefficient Witt map, is well defined by convergence of formal
series. It commutes with Frobenius: \(\phi(q_p)=q_p=q_p^p+p\).
Since the target is \(p\)-torsion-free, the Frobenius equality also gives
compatibility with \(\delta\). Its reduction is the prescribed field
point, so cofreeness makes it the canonical lift. The regular quotient has
derived base change
\[
 [W(K)\xrightarrow{q_p}W(K)]\simeq K,
\]
because \(q_p\) is \(p\) times a unit. This proves all candidate axioms.

The nonzero element \(p^{N-1}\epsilon\) is killed by \(p\). The element
\(\epsilon\ne0\) is nilpotent. More concretely the local ring has
Krull dimension 2, since its reduction is \(W[[d]]\), while its maximal
ideal \((p,d,\epsilon)\) has three independent classes modulo its square.
Thus it is not regular. The quotient by \(d\) is likewise a singular
nonreduced ring. \(\square\)

# counterexample ex:coefficient-complete-only

## statement

Let \(A=W\langle x\rangle\) be the ring of restricted power series
\(\sum_{n\ge0}a_nx^n\), where \(a_n\to0\) \(p\)-adically, with
\(\delta(x)=0\), and put \(J=(x-p)\). This ring is coefficient
\(p\)-complete, its ideal \(J\) is regular, and it satisfies the specified
perfect-field normalization with actual integral operations. It is not
derived \((p,J)\)-complete. Thus coefficient completeness does not
replace joint completeness, even when the other classical axioms hold.

## proof

The ring is the \(p\)-adic completion of \(W[x]\), and is
\(p\)-torsion-free. The map applying \(\phi_W\) to coefficients and
substituting \(x^p\) for \(x\) preserves restricted power series,
reduces to Frobenius, and supplies \(\delta(x)=0\).

The ring embeds into the domain \(W[[x]]\), so \(x-p\) is a
nonzerodivisor. Evaluation at \(x=p\) induces \(A/(x-p)\simeq W\).
To check its kernel, for \(a(x)=\sum a_nx^n\), the quotient
\((a(x)-a(p))/(x-p)\) has coefficient of \(x^j\) equal to
\(\sum_{n\ge j+1}a_np^{n-1-j}\). These sums converge and their
valuations tend to infinity with \(j\), so the quotient is still a
restricted power series.

Every compatible field point of \(A/J=W\) sends \(x\) to zero. Its
canonical operation-compatible lift is evaluation at \(x=0\) followed
by \(W\to W(K)\): this is an operation map because it commutes with
the defining Frobenius lifts, and its reduction is the given point.
It takes \(x-p\) to \(-p\), hence the two-term resolution gives
\(W(K)\otimes_A^{\mathbf L}A/J\simeq K\).

But \((p,J)=(p,x)\) is not contained in \(\operatorname{Jac}(A)\):
\(A/p=k[x]\) has a maximal ideal \((x-1)\), whose inverse image in
\(A\) does not contain \(x\). The radical consequence of derived
completeness therefore excludes derived \((p,J)\)-completeness.
\(\square\)

# counterexample ex:vacuity-without-completeness

## statement

If joint completeness is dropped altogether, compatible perfect-field
points need not exist even for a nonzero integral operation algebra with a
regular proper ideal.

## proof

In height one take \(A=W[1/p][x]\), with Frobenius \(\phi_W\) extended
to the coefficient field and \(\phi(x)=x^p\), and let \(J=(x)\).
The expression \((\phi(a)-a^p)/p\) defines the integral
\(\delta\)-identities because \(p\) is invertible, so this is a full
height-one operation algebra over \(W\). Its ideal \(J\) is proper and
regular. No unital map \(A/J=W[1/p]\to K\) exists for a field \(K\)
of characteristic \(p\). The fieldwise condition is therefore vacuous.
Here \((p,J)=A\), so derived joint completeness would force \(A=0\).
This explains exactly which omitted axiom normally prevents this example.
\(\square\)

# Branch claim-status table

| Claim | Status and exact scope | Proof |
|---|---|---|
| Restricted derived category | Defined over ordinary full integral operation algebras; animated quotient only | `def:restricted-derived-pair` |
| Arbitrary base change | Proved when the new ordinary operation base is derived complete for the extended joint ideal | `lem:derived-base-change` |
| Derived rigidity | Proved with no noetherian or torsion assumptions | `lem:derived-rigidity` |
| Classical full faithfulness | Proved for ordinary finite-type regular immersions | `lem:classical-comparison` |
| Discrete derived quotient implies classical | Proved for noetherian bases, height one, and globally presented complete quotients | `lem:classical-comparison`, `lem:complete-global-koszul` |
| Nonnoetherian local converse beyond these cases | Not claimed; localization need not preserve completeness | Scope warning after `lem:complete-global-koszul` |
| Arbitrary ordinary base change | Refuted with actual integral operations, noetherianity, and completeness | `ex:nonflat-primitive-conormal` |
| Free primitive conormal replaces regularity | Refuted in the same actual-operation example | `ex:nonflat-primitive-conormal` |
| Torsion-free or nonsingular total ring is forced | Refuted by genuine classical candidates | `ex:torsion-singular-classical` |
| Coefficient completeness replaces joint completeness | Refuted while preserving the other axioms | `ex:coefficient-complete-only` |
| Field-point nonvacuity without completeness | Refuted | `ex:vacuity-without-completeness` |
| General animated/unbounded higher-operation monad | Further work; no construction or theorem asserted | Initial scope and definition |

The proof memo resolves the assigned derived-quotient and example obligations.
The other branches retain responsibility for the complete A–F package,
including effective descent and joint completion of operation structures.
