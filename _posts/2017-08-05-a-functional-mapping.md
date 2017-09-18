---
layout: post
title:  "A functional equation"
date:   2017-08-05 13:34:00 -0400
categories: update
macrosquad_event: true
---

The 2015 midterm from 605 features a functional equation of the form

$$
\begin{aligned}
V(k,p,s) &= \max \left\{ V_{\text{trade}},V_{\text{no trade}} \right\},
\end{aligned}
$$

where

$$
\begin{aligned}
V_{\text{trade}} = u(k^{N}) - pk^{N} + spk^{N} + \mathbb{E} \left[ V(k^{N}(1-\delta),p^{\prime},s^{\prime}) | p,s \right]
\end{aligned}
$$

and

$$
\begin{aligned}
V_{\text{no trade}} = u(k) + \beta \mathbb{E} \left[ V(k(1-\delta),p^{\prime},s^{\prime}) | p,s \right]
\end{aligned}
$$

This post goes through how you can establish that there exists a unique solution to the functional equation.
<!--more-->

The details are provided on the exam. Here’s a sketch of a proof that
establishes that there is a unique solution to the Bellman equation.

The \\( T \\) operator
----------------

Let \\(B(\Psi) \\) denote the set of bounded functions
\\( R: \Psi \rightarrow \mathbb{R} \\) equipped with the \\( \sup \\) norm
\\( \lVert R \rVert = \sup_{\psi \in \Psi} R(\psi) \\).

Define the operator \\(T\\) on \\(B(\Psi)\\) as

$$
\begin{aligned}
(TR)(k,p,s) = \max_{\text{trade}, \text{no trade}}  \Bigg\{
&u(k^{N}) - pk^{N} + spk^{N} + \beta \mathbb{E} \left[ R(k^{N}(1-\delta),p^{\prime},s^{\prime}) | p,s \right], \\
& u(k) + \beta \mathbb{E} \left[ R(k(1-\delta),p^{\prime},s^{\prime}) | p,s \right] \Bigg\}.
\end{aligned}
$$

We’re going to show that \\(T\\) maps the set of bounded functions into
bounded functions and verify that it satisfies the monotonicity and
discounting hypotheses of Blackwell’s sufficient conditions for a
contraction (theorem 5.11). Because \\( B(\Psi) \\) is a complete normed
vector space (theorem 5.8), the contraction mapping theorem (theorem
5.10) admits one and only one fixed point \\( R^{\star} \in B(\Psi) \\).[^1]

Bounded to bounded
-----------------

Take any \\( R \in B(\Psi) \\). Since \\( R \\) is bounded, there exist
\\(  \underline{R} \\) and \\( \overline{R} \\) such that
\\( \underline{R} \leq R(\psi) \leq \overline{R} \\) for all \\( \psi \\).

Then

$$
\begin{aligned}
(TR)(k,p,s) &= \max_{\text{trade}, \text{no trade}}  \Bigg\{
&&u(k^{N}) - pk^{N} + spk^{N} + \beta \mathbb{E} \left[ R(k^{N}(1-\delta),p^{\prime},s^{\prime}) | p,s \right], \\
&&& u(k) + \beta \mathbb{E} \left[ R(k(1-\delta),p^{\prime},s^{\prime}) | p,s \right] \Bigg\} \\
&\leq \max_{\text{trade}, \text{no trade}} \Bigg\{
&& u(k^{N}) + \beta \overline{R}, \\
&&& u(k) + \beta \overline{R} \Bigg\},
\end{aligned}
$$

where the last
line uses properties of the stochastic process for \\(s\\). Then

$$
\begin{aligned}
(TR)(k,p,s) \leq u(k^{N}) + \beta \overline{R},
\end{aligned}
$$

assuming that \\(u\\) is increasing. As long as \\(u\\) is bounded (meaning
\\(u(k^{N}) < M\\) for some \\(M \in \mathbb{R} \\)), we’ve established that \\(T\\)
takes the space of bounded functions to bounded functions; that is, \\(T\\)
is a self map.

Satisfying Blackwell’s sufficiency conditions for a contraction
---------------------------------------------------------------

Because the space of bounded functions is complete, if we can show that
\\(T\\) satisfies Blackwell’s sufficiency conditions for a contraction,
we’ll have a contraction mapping on a complete metric space. The
contraction mapping theorem tells us that \\(T\\) has exactly one fixed point
*and* gives us a bound for how close we are to the exact solution using
the method of successive approximation.

Monotonicity looks straightforward. How about discounting? That’s going
to be easy too. For any \\(c \geq 0\\), the \\( \beta c \\) part is going to come
out of both expectations for the trade and no-trade options. Remark 5.8
of the [ECON 605 Leahy notes](https://umich.box.com/s/qwizsx7l6ejrnzdunmrckznnwhge2h9y) applies.

I was very lose with defining the set \\(\Psi \\) and laying out the properties of \\( u \\), etc.
These details, along with details about establishing monotonicity and discounting, are provided in several places in the notes.
See, for example, Remark 5.8; sections 6.1, 6.2, and 6.4; the introduction to Section 11; and section 11.2.
Those parts of the notes apply the theorems more rigorously.
This post is meant to be a *sketch*.

***

[^1]: All references to theorems refer to the [ECON 605 Leahy notes](https://umich.box.com/s/qwizsx7l6ejrnzdunmrckznnwhge2h9y).
