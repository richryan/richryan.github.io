---
layout: post
title:  "The planning problem in search models"
date:   2017-07-24 23:23:00 -0400
categories: update
macrosquad_event: true
---

This post goes through the algebra of a planning problem in Shimer's manuscript,
_Labor Markets and Business Cycles_.
The setup of the problem is non-standard and unlike the problems we've solved all year,
although this point is subtle.
After laying out the problem, the non-standard approach is taken to first solve the problem
following the lecture notes.
Second, the problem is solved following the algorithm we've used all year;
namely, writing the problem so that we choose next period's state.
Of course the two approaches yield the same solution.


<!--more-->



# Statement of the planner's problem
See section 2.3, pp 41--43.

The planner maximizes the household's utility:

$$
\begin{align*}
\sum\limits_{t=0}^{\infty} \sum\limits_{s^{t}}^{} \beta^{t} \pi(s^{t})
\left[ \log(z(s^{t})n(s^{t})(1-v(s^{t}))) - \gamma n(s^{t})\right],
\end{align*}
$$

where \\( n(s^{t}) \\) is employment in history \\(s^{t}\\) and \\( z(s^{t})n(s^{t})(1-v(s^{t})) \\) is consumption in history \\( s^{t} \\).
The maximization is subject to the constraint on the evolution of employment:

$$
\begin{align*}
n(s^{t+1}) = (1-x)n(s^{t}) + f(\theta(s^{t}))(1-n(s^{t})).
\end{align*}
$$

The recruiter--unemployment ratio is

$$
\begin{equation}
\label{eq:1}
\theta(s^{t}) = \frac{v(s^{t})n(s^{t})}{1-n(s^{t})}.
\end{equation}
$$

Parameterizing utility this way means productivity has no effect on decisions because productivity enters additively into the objective function.
Using properties of the \\( \log \\) function the objective can be written as

$$
\begin{align*}
\sum\limits_{t=0}^{\infty} \sum\limits_{s^{t}}^{} \beta^{t} \pi(s^{t})
\left[ \log(n(s^{t})(1-v(s^{t}))) - \gamma n(s^{t})\right]
+ \sum\limits_{t=0}^{\infty}\sum\limits_{s^{t}}^{} \beta^{t} \pi(s^{t}) \log z(s^{t}).
\end{align*}
$$

Because productivity does not affect the evolution of employment,
productivity has no effect on the planner's choices of employment, tightness, and recruiter share.

# Algebra behind the lecture notes

The planner's problem written recursively is

$$
\begin{align*}
W(n) = \max_{\theta} \; \log(n-\theta(1-n)) - \gamma n + \beta W((1-x)n + f(\theta)(1-n)),
\end{align*}
$$

using the fact that

$$
\begin{align*}
n(s^{t})(1-v(s^{t})) &= n(s^{t}) \left( 1 - \frac{\theta(s^{t})(1-n(s^{t}))}{n(s^{t})} \right) \\
&= n(s^{t}) - \theta(s^{t})(1-n(s^{t})).
\end{align*}
$$

The first-order condition is

$$
\begin{align*}
\frac{-(1-n)}{n - \theta(1-n)} + \beta (1-n)f^{\prime}(\theta) W^{\prime}((1-x)n + f(\theta)(1-n)) = 0.
\end{align*}
$$

The envelope condition is

$$
\begin{align*}
W^{\prime}(n) = \frac{1+\theta}{n - \theta(1-n)} - \gamma + \beta [1-x-f(\theta)]W^{\prime}(n^{\prime}).
\end{align*}
$$

Because we're looking for a steady state where

$$
\begin{align*}
n^{\prime} = (1-x)n + f(\theta)(1-n) = n,
\end{align*}
$$

the steady-state envelope condition is

$$
\begin{align*}
W^{\prime}(n) \left[ 1-\beta(1-x-f(\theta)) \right] = \frac{1+\theta}{n - \theta(1-n)} - \gamma.
\end{align*}
$$

Together, then, in steady state, the first-order condition and the envelope condition yield

$$
\begin{equation}
\label{eq:3}
\frac{1}{n - \theta(1-n)} = \beta f^{\prime}(\theta) \frac{1}{1-\beta(1-x-f(\theta))}
\left[ \frac{1+\theta}{n - \theta(1-n)} - \gamma \right]
\end{equation}
$$

or

$$
\begin{align*}
\frac{1-\beta(1-x-f(\theta))}{\beta f^{\prime}(\theta)} = 1+\theta - \gamma \left[ n - \theta (1-n) \right].
\end{align*}
$$

In steady state (see the ECON 607 Ottonello notes on this point), it is true that

$$
\begin{align*}
u = 1-n = \frac{x}{x + f(\theta)} \text{ and } n = \frac{f(\theta)}{x+f(\theta)}.
\end{align*}
$$

Using these expressions in the first-order condition leads to

$$
\begin{align*}
\frac{1-\beta(1-x-f(\theta))}{\beta f^{\prime}(\theta)} =
1+\theta - \gamma \left[ \frac{f(\theta)}{x+f(\theta)} - \theta \frac{x}{x+f(\theta)} \right]
\end{align*}
$$

or

$$
\begin{align*}
\frac{1-\beta(1-x-f(\theta))}{\beta f^{\prime}(\theta)} =
1+\theta - \gamma \frac{f(\theta) - \theta x}{f(\theta) + x},
\end{align*}
$$

which gives the expression for \\( \mathcal{T} \\) on p 43.

# How we normally solve the problem
The procedure in the previous section is not the procedure we've used to solve dynamic programming problems.
Indeed, not.
Usually we choose next period's state;
that is, we solve:

$$
\begin{align*}
W(n) = \max_{n^{\prime}} \; \log(n-\theta(1-n)) - \gamma n + \beta W(n^{\prime})
\end{align*}
$$

subject to

$$
\begin{equation}
\label{eq:2}
\theta = f^{-1} \left( \frac{n^{\prime}-(1-x)n}{1-n} \right).
\end{equation}
$$

Now the problem is in the familiar form.
Seeing a problem like this on an exam, this is the approach I'd take---this is how we've solved these types of problems all year.

## First-order conditions

The first-order condition for \\( n^{\prime} \\) is

$$
\begin{align*}
\frac{-(1-n)}{n - \theta (1-n)} \frac{\partial \theta}{\partial n^{\prime}} + \beta W^{\prime}(n^{\prime}) = 0.
\end{align*}
$$

The envelope condition is

$$
\begin{align*}
W^{\prime}(n) = \frac{1}{n - \theta (1-n)}
\left\{ 1 - (1-n) \frac{\partial \theta}{\partial n} + \theta \right\} - \gamma.
\end{align*}
$$

Now we just need to figure out the relationships between \\( \theta \\) and employment.
Using the expression for \\( \theta \\) in equation \eqref{eq:2},[^fn1]

$$
\begin{align*}
\frac{\partial \theta}{\partial n^{\prime}} = \frac{1}{f^{\prime}(\theta)} \frac{1}{1-n}.
\end{align*}
$$

And

$$
\begin{align*}
\frac{\partial \theta}{\partial n} = \frac{1}{f^{\prime}(\theta)}
\frac{-(1-x)(1-n) + n^{\prime} - (1-x)n}{(1-n)^{2}}.
\end{align*}
$$

Recall that in steady state \\( n^{\prime} - (1-x)n = f(\theta)(1-n) \\).
This relationship allows us to simplify the latter:

$$
\begin{align*}
\frac{\partial \theta}{\partial n} = \frac{1}{f^{\prime}(\theta)}
\frac{-(1-x) + f(\theta)}{1-n}.
\end{align*}
$$

Using the expressions for the partial derivatives,
the first-order condition becomes

$$
\begin{align*}
0 &= \frac{-1}{n - \theta (1-n)} \frac{1}{f^{\prime}(\theta)} + \beta W^{\prime}(n^{\prime}) \\
&= \frac{-1}{n - \theta (1-n)} \frac{1}{f^{\prime}(\theta)}
+ \beta \frac{1}{n - \theta (1-n)}
\left\{ 1 - (1-n) \frac{\partial \theta}{\partial n} + \theta \right\} - \beta \gamma \\
\implies 0 &= -\frac{1}{\beta f^{\prime}(\theta)}
+ \left\{ 1 - (1-n) \frac{\partial \theta}{\partial n} + \theta \right\} - \gamma \left[ n - \theta (1-n) \right].
\end{align*}
$$

Developing our developing equation further using the expression for \\( \partial \theta / \partial n \\),
we have

$$
\begin{align*}
0 &= -\frac{1}{\beta f^{\prime}(\theta)}
+ \left\{ 1 - \frac{-1 + x + f(\theta)}{f^{\prime}(\theta)}
+ \theta \right\} - \gamma \left[ n - \theta (1-n) \right].
\end{align*}
$$

Which can be developed further as

$$
\begin{align*}
\frac{1 - \beta (1 - x - f(\theta))}{\beta f^{\prime}(\theta)} = 1 - \theta - \gamma \left[ n - \theta (1-n) \right].
\end{align*}
$$

This is the same expression as the one in equation \eqref{eq:3}.
Done: we've established that you can choose either \\( \theta \\) or \\( n^{\prime} \\).
Our standard approach is to choose \\( n^{\prime} \\).

***
[^fn1]: For properties of the inverse see the [ECON 607 Ottonello notes](https://umich.box.com/s/xczz87igzno3lzpfkapiurrp8izzivud) or Russell A. Gordon's _Real Analysis_, pp 135--136.
