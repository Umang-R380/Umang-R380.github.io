# TANGENT VECTORS
*Authored by: Umang R*

---

## Tangent Vectors

We want an intrinsic definition of tangent vectors for arbitrary manifolds. In the plane, you can picture tangents as sitting inside an ambient Euclidean space, but for manifolds we don’t want to rely on any embedding.

We’ll start in Euclidean space and then abstract.

### Tangent space in \(\mathbb{R}^n\)

**Definition.** For any \(a \in \mathbb{R}^{n}\), the **tangent space** of \(\mathbb{R}^{n}\) at \(a\) can be defined (naively) as
\[
T_a\mathbb{R}^n \cong \{(a,v): v \in \mathbb{R}^n\}.
\]
This is isomorphic to \(\mathbb{R}^n\), but this vector-based definition isn’t great for generalization.

A better route is to encode “direction” via **directional derivatives**. For a smooth \(f:\mathbb{R}^n\to\mathbb{R}\), the directional derivative at \(a\) in the direction \(v\in\mathbb{R}^n\) is
\[
D_v f(a) \;=\; \lim_{t\to 0}\frac{f(a+tv)-f(a)}{t}.
\]

Key fact: geometric vectors \(v\) at \(a\) correspond **one-to-one** with directional-derivative operators \(f \mapsto D_v f(a)\). That correspondence is what survives on manifolds.

### Derivations at a point

**Definition.** A map \(\omega:C^\infty(\mathbb{R}^n)\to\mathbb{R}\) is a **derivation at \(a\in\mathbb{R}^n\)** if
1. \(\omega\) is \(\mathbb{R}\)-linear, and  
2. \(\omega(fg) = f(a)\,\omega(g) + g(a)\,\omega(f)\) for all \(f,g\in C^\infty(\mathbb{R}^n)\).

Denote the set of all derivations at \(a\) by \(T_a\mathbb{R}^n\). This is a vector space (in fact isomorphic to \(\mathbb{R}^n\)).

**Theorem.** Let \(a\in\mathbb{R}^n\), \(f,g\in C^\infty(\mathbb{R}^n)\), and \(\omega\in T_a\mathbb{R}^n\). Then:
- If \(f\) is constant, \(\omega(f)=0\).
- If \(f(a)=g(a)=0\), then \(\omega(fg)=0\).

*Proof.* Routine; left as an exercise.

Now think of \(T_a\mathbb{R}^n\) as “all possible velocities compressed at \(a\)”. Next we prove that these derivations are exactly the same thing as directional derivatives.

**Theorem.** Let \(a\in\mathbb{R}^n\).
1. For each vector \(v\in\mathbb{R}^n\), the map \(D_v|_a:C^\infty(\mathbb{R}^n)\to\mathbb{R}\) defined by \(D_v|_a(f)=D_v f(a)\) is a derivation at \(a\).
2. The map \(v\mapsto D_v|_a\) is a vector space isomorphism \(\mathbb{R}^n \xrightarrow{\sim} T_a\mathbb{R}^n\).

*Sketch.* (1) is standard. For (2), injectivity: if \(D_v|_a=0\) and \(v=\sum_i v^i e_i\), then applying to coordinate functions \(x^j\) gives \(v^j=0\), so \(v=0\).  
Surjectivity: given \(\omega\in T_a\mathbb{R}^n\), set \(v^i := \omega(x^i)\) and \(v=\sum_i v^i e_i\). Taylor’s formula at \(a\) yields
\[
\omega(f)=\sum_{i=1}^n \frac{\partial f}{\partial x^i}(a)\,v^i \;=\; D_v f(a).
\]
Done.

**Corollary.** \(\left\{ \frac{\partial}{\partial x^i}\big|_a \right\}_{i=1}^n\) is a basis of \(T_a\mathbb{R}^n\).

### Intrinsic definition on a manifold

**Definition.** Let \(M\) be a smooth manifold and \(a\in M\). A map \(v:C^\infty(M)\to\mathbb{R}\) is a **derivation at \(a\)** if it is linear and satisfies the Leibniz rule
\[
v(fg)=f(a)\,v(g)+g(a)\,v(f)\qquad\forall f,g\in C^\infty(M).
\]
The set of derivations at \(a\) is the **tangent space** \(T_a M\).

Observation: tangent vectors are **local** objects. You don’t need any ambient space to define them.

---

## Differential of a smooth map

For manifolds, “derivative” is a map between tangent spaces.

**Definition.** If \(F:M\to N\) is smooth, the **differential** at \(a\in M\) is
\[
dF_a : T_a M \to T_{F(a)} N,\qquad (dF_a(v))(f) \;=\; v(f\circ F),
\]
for all \(v\in T_a M\) and \(f\in C^\infty(N)\). One checks this is indeed a derivation at \(F(a)\).

**Theorem.** If \(F:M\to N\) and \(G:N\to P\) are smooth maps between smooth manifolds, then
\[
d(G\circ F)_a \;=\; dG_{F(a)} \circ dF_a.
\]
If \(F\) is a diffeomorphism, then \(dF_a: T_a M \to T_{F(a)} N\) is an isomorphism and
\[
(dF_a)^{-1} \;=\; d(F^{-1})_{F(a)}.
\]

*Proof.* Direct from the definition and the chain rule via pullbacks.

**Locality of derivations.** If \(f,g\in C^\infty(M)\) agree on some neighborhood of \(p\in M\), then for every \(v\in T_p M\) we have \(v(f)=v(g)\).  
*Idea:* Apply \(v\) to a bump function \(\psi\) that is \(1\) on a neighborhood where \(f=g\) and vanishes near \(p\) otherwise; then \(v(\psi(f-g))=0\).

---


