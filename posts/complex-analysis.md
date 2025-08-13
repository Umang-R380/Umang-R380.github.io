# TANGENT VECTORS

*Authored by: Umang R*

---

## Tangent Vectors

This document presents an intrinsic approach to defining tangent vectors for arbitrary manifolds, moving beyond the traditional notion of tangent vectors as a subset of a larger Euclidean space. We begin by redefining the concept for the familiar Euclidean space before generalizing it to manifolds.

### Tangent Space in $\mathbb{R}^n$

For any $a \in \mathbb{R}^{n}$, the tangent space of $\mathbb{R}^{n}$ at $a$ can be defined as the set $\{(a,v): v \in \mathbb{R}^{n}\}$, where $v$ is a vector in $\mathbb{R}^{n}$. This tangent space, denoted as $T_a \mathbb{R}^{n}$, is isomorphic to $\mathbb{R}^{n}$. However, this vector-based definition isn't suitable for generalization.

A more fruitful approach is to define direction using **directional derivatives**. The directional derivative of a smooth function $f: \mathbb{R}^{n} \to \mathbb{R}$ at a point $a$ in the direction of a vector $v$ is given by:

$$ D_{v}f(a) = \lim_{t \to 0} \frac{f(a + tv) - f(a)}{t} $$

This formulation is key because the set of directional derivatives has a one-to-one correspondence with the set of vectors.

### Derivations

We now introduce the concept of a **derivation**, which is a formal, abstract way to define a tangent vector.

**Definition:** A map $\omega: C^{\infty}(\mathbb{R}^{n}) \to \mathbb{R}$ is called a **derivation** at $a \in \mathbb{R}^{n}$ if it satisfies:
1. The map is linear over $\mathbb{R}$.
2. For any $f,g \in C^{\infty}(\mathbb{R}^{n})$, it obeys the Leibniz rule: $\omega(fg) = f(a) \omega(g) + g(a) \omega(f)$.

The set of all derivations at $a$ forms the **tangent space** $T_a \mathbb{R}^{n}$. This set is a vector space over $\mathbb{R}$ and is isomorphic to $\mathbb{R}^{n}$.

**Theorem:** The map $v_a \to D_v|_a$ is an isomorphism from $\mathbb{R}^{n}$ onto $T_a \mathbb{R}^{n}$.

This theorem proves that the familiar directional derivatives are, in fact, derivations in disguise and that our new, abstract definition of a tangent vector is equivalent to the old one in $\mathbb{R}^n$.

**Corollary:** The set of partial derivatives $\left\{ \frac{\partial}{\partial x^i} \right\}_{i=1}^{n}$ forms a basis for the tangent space $T_a \mathbb{R}^{n}$.

### Generalizing to Manifolds

The derivation concept is the key to defining tangent vectors on general manifolds, where an ambient Euclidean space might not be available.

**Definition:** A map $ v : C^{\infty}(M) \to \mathbb{R} $ is called a **derivation** at a point $a \in M$ if it satisfies the linearity and Leibniz rules. The set of all derivations at $a$ forms the **tangent space** $T_a M$.

This definition is intrinsic and does not rely on any embedding, making it a powerful tool for studying manifold properties.

---

## Differential of a Smooth map

In vector spaces, the derivative of a function can be linearized. On manifolds, the structure is more complex, requiring us to generalize the derivative as a map between tangent spaces.

**Definition:** Suppose $F : M \to N$ is a smooth map between manifolds $M$ and $N$. The **differential of $F$** at a point $a \in M$ is a map
$$ dF_a : T_a M \to T_{F(a)} N $$
defined by
$$ (dF_a(v))(f) = v(f \circ F) $$
for all $v \in T_a M$ and $f \in C^{\infty}(N)$.

This map essentially tells us how a tangent vector in $M$ is transformed into a tangent vector in $N$ by the map $F$.

**Theorem:** If $F: M \to N$ is a diffeomorphism, then its differential $dF_p : T_p M \to T_{F(p)} N$ is an isomorphism, and $(dF_p)^{-1} = dF^{-1}_{F(p)}$.

This theorem states that if two manifolds have the same smooth structure, their tangent spaces are identical at corresponding points.

### Derivations are Local

The final key property of derivations is their local nature.

**Theorem:** Let M be a smooth manifold, $p \in M$, and $f,g \in C^{\infty}(M)$ be two functions that agree on some neighborhood of $p$. Then for any derivation $v$ at $p$, we have $v(f) = v(g)$.

This means that a tangent vector only "cares" about the behavior of a function in an infinitesimal neighborhood of the point, not its global properties.
