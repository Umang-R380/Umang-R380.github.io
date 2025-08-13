%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% A General & Clean LaTeX Note-Taking Template
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

\documentclass[11pt, a4paper]{article}

% --- PACKAGES ---
\usepackage[margin=1in]{geometry}      % For setting sensible page margins
\usepackage{amsmath, amssymb, amsthm}  % Essential packages for math
\usepackage{graphicx}                  % For including images
\usepackage{hyperref} 
\usepackage[utf8]{inputenc}

\usepackage{mathtools}

% Let  $ a \vcentcolon  = b $
% Let  $ a \coloneqq  b $                 % For clickable links and references
\hypersetup{
    colorlinks=true,
    linkcolor=blue,
    urlcolor=teal,
}

% --- ENVIRONMENTS (Optional, for structured notes) ---
% These are useful for organizing definitions, theorems, etc.
\theoremstyle{definition}
\newtheorem{definition}{Definition}[section]
\newtheorem{example}{Example}[section]

\theoremstyle{plain}
\newtheorem{theorem}{Theorem}[section]
\newtheorem{corollary}{Corollary}[section]

\theoremstyle{remark}
\newtheorem{remark}{Remark}[section]


% --- YOUR CUSTOM COMMANDS (MACROS) ---
% Add your own shortcuts here to save time
\newcommand{\R}{\mathbb{R}} % The set of real numbers
\newcommand{\C}{\mathbb{C}} % The set of complex numbers
\newcommand{\Z}{\mathbb{Z}} % The set of integers


% --- DOCUMENT START ---
\begin{document}

% --- TITLE SECTION (Optional) ---
% You can delete this part if you don't need a formal title.
\title{\textbf{TANGENT VECTORS}}
\author{Umang R}
 % Or use a specific date like \date{August 12, 2025}
\maketitle
\hrule % Adds a horizontal line for separation

\section{Tangent Vectors}

note that we need a way to define tangent for arbitary manifold, we know the notion of tangent vectors for shapes in euclidean plane as a subset of a bigger space, but when dealing with manifold we employ a more intristic approach where we dont use any ambient space in which manifold is embedded.
first we will define tangent space for normal euclidean plane, we will do that as follows
% \newtheorem{}{Tangent Space}
\begin{definition}
For any $a \in \R^{n}$, The tangent space of $\R^{n}$ at a is defined as the set {$(a,v): v \in \R^{n}$} where $v$ is a vector in $\R^{n}$.
\end{definition}
Note that Tangent space of $\R^{n}$ is isomorphic to $\R^{n}$ hence we think of it like this in an intrinsic way instead of relying on any other embedding spaces
but well note that this way of describing tangent space by vectors woudnt be fruitfull if we want to generalise it, we need an equivalent formalisation but something that can be abstracted into out manifolds hence we define same notion of direction but with directional derivative.

note that directional derivative of a function $f: \R^{n} \to \R$ at a point $a$ in the direction of a vector $v$ is defined as
$$ D_{v}f(a) = \lim_{t \to 0} \frac{f(a + tv) - f(a)}{t} $$

key motivation to do this way the fact that vectors as defined previously in tangent space and this set of directional derivatibe have one to one correspondence, which will see newcommand

now we define following objects
\begin{definition}
A map $\omega: C^{\infty}(\R^{n}) \to \R$ is called a \textbf{derivation} at $a \in \R^{n}$ if it satisfies the following properties:
\begin{itemize}
    \item The map is linear over $\R$.
    \item For any $f,g \in C^{\infty}(\R^{n})$, we have $\omega(fg) = f(a) \omega(g) + g(a) \omega(f)$.
\end{itemize}
\end{definition}
We will later realise that our familiar directional derivatives are just derivations in disguise.
we denote set of of all derivation at a as $T_a \R^{n}$,

note that this set is a vector space over $\R$, infact it is isomorphic to $\R^{n}$
Now we will study some properties of these derivations.
\begin{theorem}
  suppose that $ a \in \R^{n}$ and $f,g \in C^{\infty}(\R^{n})$, then the map $\omega: T_a \R^{n} \to \R$ defined by $\omega \in T_a \R^{n}$ is a derivation at $a$.  
  \begin{itemize}
    \item if $f$ is a constant function, then $\omega(f) = 0$.
    \item if $f(a) = g(a) = 0$, then $\omega(fg) = f(a)\omega(g) + g(a)\omega(f) = 0$.
  \end{itemize}
  \begin{proof}
    Left as an exercise for the reader.
  \end{proof}
\end{theorem}
now think of these set of all derivation (i.e $T_a\R^{n}$) as a property of a point (coz thats kind of what it is), think of it as all the velocity vectors possible from that point are infintely compressed into a point. These intution would help in generalising the definition fro arbitary manifolds.
now why should you think of them like this, and why do we exactly consider them to be same as direction out nect theorem will answer that question precisely.
\begin{theorem}
    let $a \in \R^{n}$
    \begin{itemize}
        \item For each geometric vector $v_a \in \R^{n}$, the map $D_v|_a: C^{\infty}(\R^{n}) \to \R$ defined by $D_v|_a(f) = D_vf(a)$ is a derivation at $a$.(i.e Size of our derivation is "atleast" this Much, Now we will Claim that its exactly this Much)
        \item The map $v_a \to D_v|_a $ is an isomorphism from $ \R^{n}_a  \text{ onto } T_a \R^{n} $.
    \end{itemize}
    \begin{proof}
        1) is trivial so will just prove ii)
        Now Linearity of the Map is Shown by writing the following element in range as a Gradient,
        Now we will Prove Injectivity, We Assume That $D_v|_a$ is a Zero derivation and suppose $v_a = v_i e_i$ ,
        where $e_i$ is the standard basis of $\R^{n}$, then we have For $ X^{j} : \R^{n} \to \R$ That $D_v|_a(X^{j}) = v_i \frac{\partial X^{j}}{\partial x_i}(a) = v_i$, which implies that $v_i = 0$ for all $i$, hence $v_a = 0$.
        Hence we have shown the injectivity now we will show Surjectivity
        Let $\omega \in T_a \R^{n}$ be a derivation at $a$, then we can define a vector $v_a$ such that $D_v|_a(f) = \omega(f)$ for all $f \in C^{\infty}(\R^{n})$, So first we need a candidate for such $v_a$ , suppose that $v_i = \omega(X^{i})$.
        Then we have $\omega = D_v|_a$, For this we will Use taylors formula
        $$f(x) = f(a) + \sum_{i = 1}^{n}\frac{\partial f}{\partial x^i} (a) (x^i - a^i) + \sum_{i,j = 1}^{n}(x^i - a^i)(x^j - a^j)\int_{0}^{1} (1-t) \frac{\partial^2 f}{\partial x^i \partial x^j}(a +t(x-a))dt$$
        On operating this function on $\omega$, we get that the integration terms vanish along with the constant term $f(a)$, and we get
        \[
            \omega(f) = \sum_{i = 1}^{n} \frac{\partial f}{\partial x^{i}}(a) v_i
        \]
        Hence we are done
    \end{proof}
\end{theorem}
Note that from this we can derive a corollary that all the partial operators forms a basis for our $T_a\R^{n}$. for manifold it will be a bit complicated

\begin{corollary}
    The set of partial derivatives $\left\{ \frac{\partial}{\partial x^i} \right\}_{i=1}^{n}$ forms a basis for the tangent space $T_a \R^{n}$.
\end{corollary}

\begin{definition}
    A map $ v : C^{\infty}(M) \to \R $ is called a \textbf{derivation} at a point $a \in M$ if it satisfies the following properties:
    \begin{itemize}
        \item The map is linear over $\R$.
        \item The map satisfies the Leibniz rule: $v(fg) = f(a)v(g) + g(a)v(f)$ for all $f,g \in C^{\infty}(M)$.
    \end{itemize}
\end{definition}
we had the nice correspondence in case of $\R^{n}$ between our tangent space and OG space but here since structure is locally euclidean we can have some complicacy and we will handle that with care so that we get everything out of this definition.
Note that i have just realised that tangent vector are local object we always visualised them as arrows hence we thought it were result of abient space out original space was in but no we can define tangent vector like this in an intrinsic way too!!

\section{Differential of a Smooth map}
Now note that if we have a smooth map then in case of vector space we could linearise the problem to find a derivative but here in case of manifold the structure is more complicated. We need to take into account the local charts and the transition maps between them. hence its not possible to always linearise the problem but instead we will generelise our definition of derivition as maps between tangent spaces rather then spaces itselfs.
\begin{definition}
Suppose $F : M \to N$ is a smooth map between manifolds $M$ and $N$. Then the \textbf{differential of $F$} at a point $a \in M$ is a map
\[
    dF_a : T_a M \to T_{F(a)} N
\]
defined by
\[
    (dF_a(v))(f) = v(f \circ F)
\]
for all $v \in T_a M$ and $f \in C^{\infty}(N)$.
\end{definition}
Now this is up to you to think why the element $v(f \circ F)$ in $T_{F(a)} N$ is a derivation :p.

\begin{theorem}
    Let $M,N,P$ be smooth manifolds and $F : M \to N$, $G : N \to P$ be smooth maps.
    If $F$ is a diffeomorphism, then $dF_p : T_p(M) \to T_{F(p)}(N)$ is an isomorphism,
    and $(dF_p)^{-1} = dF^{-1}_{F(p)}$.
\end{theorem}
This Theorem Just says that if we have a same smooth structure, then Tangent spaces at all point in those two manifolds are indentical.
\begin{proof}
    Let $p \in M$ and $q = F(p) \in N$. Since $F$ is a diffeomorphism, there exists a smooth inverse $F^{-1} : N \to M$ such that $F^{-1}(q) = p$.
    The differential of $F^{-1}$ at $q$ is given by
    \[
        dF^{-1}_q : T_q N \to T_p M
    \]
    defined by
    \[
        (dF^{-1}_q(w))(g) = w(g \circ F^{-1})
    \]
    for all $w \in T_q N$ and $g \in C^{\infty}(M)$.
    
    Now, we need to show that $(dF_p)^{-1} = dF^{-1}_q$. For any $v \in T_p M$, we have
    \[
        (dF_p(v))(f) = v(f \circ F)
    \]
    and
    \[
        (dF^{-1}_q(w))(g) = w(g \circ F^{-1}).
    \]
    
    By the chain rule, we have
    \[
        (dF_p(v))(f) = v(f \circ F) = v(F^*f),
    \]
    where $F^*f$ is the pullback of $f$ under $F$. Similarly,
    \[
        (dF^{-1}_q(w))(g) = w(g \circ F^{-1}) = w(F^*g).
    \]
    
    Thus, we can conclude that $(dF_p)^{-1} = dF^{-1}_q$, completing the proof.
\end{proof}

Note that Derivation acts locally and following theorem solidifies it 

\begin{theorem}
    Let M be a smooth manifold, $ p \in M$, and $f,g \in C^{\infty}(M)$ such that these f,g agree on some neightbourhood of p, then vf = vg
    \begin{proof}
    Let h = f - g, then h(p) = 0 , now we need to consider another function that would be zero at p to conclude this, we dont need to go far because such a fucntion is a smooth bump, 
    consider $ \psi$ such that its 1 identically on support of h, now since h is zero in some neighbourhood og p there exist a circle around p for which $\psi$ is 0, hence $v(\psi .h )$ = 0 since both are zero at P
    \end{proof}
\end{theorem}

\end{document}
