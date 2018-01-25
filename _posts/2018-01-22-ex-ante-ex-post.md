---
layout: post
title:  "<em>Ex ante</em> versus <em>ex post</em> interest rates"
date:   2018-01-22 18:56:00 -0400
categories:
macrosquad_402: true
---


<!--more-->

The difference between *ex ante* and *ex post* interest rates has to do with the Fisher equation.
If you took a couple more macro classes after ECON 402,
you'd expect the Fisher effect to be expressed as the relationship between the nominal interest rate and *expected* inflation:

$$
\begin{align*}
i_t = r_t + \mathbb{E}_t \pi_{t+1},
\end{align*}
$$

where \\( \mathbb{E}_t \\) is the expectations operator conditional on all information available at time \\( t \\).
Which simply means that the decision maker is using newspapers, FRED, the internet, etc.
to make a guess about what they think inflation will be.
The decision maker has to make a guess because they don't know what inflation *will* be
between time \\( t \\) and \\( t+1 \\).

Now think about a borrower and a lender deciding on the terms of a contract.
The number written on the contract is a nominal interest rate (usually, not always).
And to get that number they need to agree on a forecast of inflation.
(The borrower may even welcome a high rate of interest if they thought their wages were going to rise significantly.)
That means they have to form an expectation of inflation.

"The real interest rate that the borrower and lender expect when the load is made"
is called the *ex ante* real interest rate.
As time passes and people make decisions in the economy, prices are realized, which determine the actual rate of inflation.
"The real interest rate that is actually realized" is called the *ex post* interest rate.
This can only be inferred after the fact.
See p. 117 of Mankiw, 9e.

When Chair Ben Bernanke came to U-M, he talked about "open mouth operations,"
a play on open-market operations,
which are the usual puchases and sales of government bonds that the Fed makes.
Because interest rates were pinned at zero,
Chair Berenanke talked about lowering real interest rates by increasing inflation expectations:

$$
\begin{align*}
r_t = i_t - \mathbb{E}_t \pi_{t+1}.
\end{align*}
$$

Chair Bernanke talked about promising not to raise interest rates&mdash;no matter what&mdash;which
would increase \\( \mathbb{E}_t \pi_{t+1} \\) thereby lowering \\( r_t \\).
It was pretty clear Chair Bernanke had the Fisher effect in mind.

There's nothing deep behind the terms *ex ante* interest rate and *ex post* interest rate.
And, in fact, it's even messier in practice&mdash;what interest rate and what measure of inflation?
There are lots of interest rates and several measures of inflation.
