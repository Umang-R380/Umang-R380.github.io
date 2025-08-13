# TANGENT VECTORS
*Authored by: Umang R*

---

## Tangent Vectors

We want an intrinsic definition of tangent vectors for arbitrary manifolds.  
In the plane, tangents are often seen as arrows in the ambient Euclidean space,  
but for manifolds we can define them without embedding.

---

### Tangent space in \(\mathbb{R}^n\)

Naively:
\[
T_a\mathbb{R}^n \cong \{(a,v): v \in \mathbb{R}^n\}.
\]
But instead of thinking of \(v\) as a geometric arrow,  
we can think of it as a **directional derivative**.

For \(f:\mathbb{R}^n\to\mathbb{R}\) smooth and \(v\in\mathbb{R}^n\),
\[
D_v f(a) = \lim_{t\to 0} \frac{f(a+tv)-f(a)}{t}.
\]
This is linear in \(v\) and satisfies the Leibniz rule.

---

### Derivations at a point

A **derivation at \(a\)** is a linear map \(\omega:C^\infty(\mathbb{R}^n) \to \mathbb{R}\)  
such that
\[
\omega(fg) = f(a)\,\omega(g) + g(a)\,\omega(f).
\]
We denote the set of all such maps by \(T_a\mathbb{R}^n\).

**Theorem:**  
Every \(v\in\mathbb{R}^n\) defines a derivation \(D_v|_a\) via
\[
D_v|_a(f) = D_v f(a),
\]
and the map \(v \mapsto D_v|_a\) is a vector space isomorphism
\[
\mathbb{R}^n \cong T_a\mathbb{R}^n.
\]

---

### Intrinsic definition for manifolds

For a smooth manifold \(M\) and \(a\in M\):  
a derivation at \(a\) is a linear map \(v:C^\infty(M)\to\mathbb{R}\)  
satisfying
\[
v(fg) = f(a)v(g) + g(a)v(f).
\]
The set of derivations at \(a\) is the tangent space \(T_a M\).

This definition doesn’t need an embedding into \(\mathbb{R}^n\).

---

## Differential of a smooth map

If \(F:M \to N\) is smooth, the **differential** at \(a\) is
\[
dF_a: T_a M \to T_{F(a)} N,\quad (dF_a(v))(f) = v(f \circ F).
\]

**Theorem:**
If \(F:M\to N\) and \(G:N\to P\) are smooth,
\[
d(G\circ F)_a = dG_{F(a)} \circ dF_a.
\]
If \(F\) is a diffeomorphism, then \(dF_a\) is an isomorphism and
\[
(dF_a)^{-1} = d(F^{-1})_{F(a)}.
\]

---

### Locality of derivations

If \(f,g\in C^\infty(M)\) agree on a neighborhood of \(p\in M\),  
then \(v(f)=v(g)\) for all \(v\in T_p M\).

---



