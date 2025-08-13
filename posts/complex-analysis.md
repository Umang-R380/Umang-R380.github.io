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

