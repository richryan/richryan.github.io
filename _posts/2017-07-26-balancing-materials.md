---
layout: post
title:  "Balancing material"
date:   2017-07-26 17:03:00 -0400
categories: update
macrosquad_event: true
---

This post goes through national accounting in a market structure that
features two types of firms: capital-leasing and final-good firms. You
can contrast this setup with the setup in question II of the ECON 607
final.

Materials must balance in any economy.

<!--more-->

Capital-leasing and final-good firms
====================================

Consider an economy where the market structure features both
capital-leasing and final-good firms.

-   The household owns both types of firms.

-   The capital-leasing firms rent capital to the final-goods firms.
    Capital-leasing firms optimally accumulate capital for the economy.

-   The final-good firms have access to a classical production function
    that combines capital and labor to produce the final good (bananas).

-   Both firms rebate profits to the household.

Final-good firms earn no profits
--------------------------------

Final-good firms rent capital from capital-leasing firms and hire labor
from the household.

The optimization problem of the final-good firms results in the inputs
being paid their marginal products. Because the production technology is
homogeneous of degree one in capital and labor, Euler’s theorem tells us
\\( Y = F_{K}K + F_{N}N \\). Therefore \\( Y = RK + WN = 0 \\), establishing that
final-good firms earn no profits. See remark 2.1 of the ECON 605
Stolyarov notes.

Capital-leasing firms earn a profit
-----------------------------------

Capital-leasing firms earn a flow profit of

$$\begin{aligned}
\Pi_{t}^{\text{leasing}} = R_{t}K_{t} - I_{t}.
\end{aligned}$$

They earn revenue \\(R_{t}K_{t} \\) by leasing capital to final-good firms and make
decisions about investment. What’s the price of investment?
\\( \Pi_{t}^{\text{leasing}} \\) is in real terms. The price of a brick is one
(in terms of bananas)—a brick is equivalent to a banana in this economy.

Capital-leasing firms optimally accumulate capital, ensuring that
Jorgenson’s formula holds.

The household’s budget constraint
---------------------------------

The household owns both capital-leasing and final-good firms. All firms
rebate profits to the household. Because the final-good firms earn no
profits, we can forget about this source of income.

Another source of income for the household is labor income. The
household earns labor income by supplying labor to final-good firms.

Let’s also suppose that the household carries around cash to purchase
goods. At this point, we have to make a timing assumption. Let \\( M_{t} \\)
denote the beginning-of-period cash. \\( M_{t} \\) represents the _stock_ of
money the household enters the period with. At the end of the period the
household will have \\( M_{t+1} \\) dollars.

Everything so far is pretty standard---you’ve heard this story before.
Here’s more of the story. Let’s follow the convention of denoting
everything in real terms; that is, in terms of bananas.

The final-good firm makes bananas. It’s profits are in terms of bananas.
It pays the capital-leasing firm in bananas. The capital-leasing firm
earns profits through the rental of bananas and rebates these to the
household. The household receives bananas from capital-leasing firms.

Given that capital-leasing firms are returning bananas to the household,
how does the stock of money increase or decrease? And if there is a
representative household, how does the stock of money decrease or
increase? The only way for the stock of money to increase or decrease is
through transfers from whoever prints money. For the sake of the story,
this is the treasury, which is the only function of the government.[^1]
In other words,

$$
\begin{equation}
\label{eq:1}
M_{t+1}-M_{t} = T_{t}.
\end{equation}
$$

Turning to the household’s budget constraint, the household divides its
resources between consumption, bonds, and money. Bonds are nominally
riskless and pay interest \\( i_{t} \\). The household earns labor income and
receives dividends from their ownership of capital-leasing firms.
Putting these pieces together, an allocation must satisfy

$$
\begin{aligned}
C_{t} + \frac{M_{t+1}}{P_{t}} + \frac{B_{t+1}}{(1+i_{t})P_{t}} =
W_{t}N_{t} + \Pi^{\text{leasing}}_{t} + \frac{B_{t}}{P_{t}} + \frac{M_{t}}{P_{t}} + \frac{T_{t}}{P_{t}}.
\end{aligned}$$

Note that the budget constraint is in *real* terms; that is, in terms of
bananas, not dollars. It is important to make the denomination of
dividends agree with the denomination of the household budget
constraint.

Balancing materials
-------------------

If bonds are in zero net supply, then \\( B_{t} = 0 \\).[^2] Combined with \eqref{eq:1}, the
household budget constraint becomes

$$
\begin{aligned}
C_{t} = W_{t}N_{t} + \Pi_{t}^{\text{leasing}} = W_{t}N_{t} + R_{t}K_{t} - I_{t}.
\end{aligned}
$$

Because capital and labor get paid their marginal products, we can write
the latter as

$$
\begin{aligned}
C_{t} = F_{Nt}N_{t} + F_{Kt}K_{t} - I_{t}
\end{aligned}
$$

or

$$
\begin{aligned}
C_{t} = Y_{t} - I_{t}.
\end{aligned}
$$

This is the material-balance condition. We started from the household’s
budget constraint and ended up at the material-balance condition.

Investment adjustment costs: bananas into the sea
=================================================

What if the capital-leasing firm faces nonlinear adjustment costs?
Denote adjustment costs with \\( \Psi_{t} \\). The material-balance condition
is going to be

$$
\begin{aligned}
C_{t} + I_{t} = Y_{t} - \Psi_{t}.
\end{aligned}
$$

Professor Stolyarov would call this “bananas into the sea.” The adjustment costs are simply
subtracted from output.

If the adjustment costs are parameterized as in section 11.1 of the ECON
605 Leahy notes,

$$
\begin{align*}
\Psi_{t} = \frac{\gamma}{2} \left( \frac{I_{t}}{I_{t-1}} - 1 \right)^{2}I_{t-1},
\end{align*}
$$

then we’re back to \\( Y = C + I \\) in steady state. Only out of steady state
will bananas be thrown into the sea.

***

[^1]: Unless the government engages in the collection of taxes, other
    lump-sum transfers, or consumption.

[^2]: They might not be if there is government debt, for example, a case
    we covered in ECON 605.
