---
layout: post
title:  "Practice with lag operators"
date:   2017-07-13 18:05:00 -0400
categories: update
macrosquad_event: true
---

A few examples dealing with lag operators were added to the ECON 605 Leahy notes.
They go through the "forward" and "backward" solutions to first-order linear difference equations
and are included in section 2, "Practice with the lag operator," which is new.

I also added Monday office hours from 1:00--3:00 pm in Foster library.
They are listed under [MacroSquad]({{ site.url}}/macrosquad).
We'll try out this time and adjust accordingly.

<!--more-->

***

These notes mostly come from chapter 2 of James Hamilton's _Time Series Analysis_.
They were motivated by the proposed solutions to the 2011 midterm.
Michael alerted me to some dubious algebra there and we came up with a few notes on the inverse operator that is seemingly used in the solution.[^fn1]
The result is a very useful framework for solving linear difference equations.

***

Consider the difference equation
$$
y_{t} = \phi y_{t-1} + w_{t}.
$$
Using the lag operator we can write this as

$$
(1 - \phi L) y_{t} = w_{t}.
$$

When \\( \| \phi \| < 1 \\) we had the cool inverse result, which we used to get the Wold representation of a time series in section 1:[^fn2]

$$
(1 - \phi L)^{-1} = (1 + \phi L + \phi^{2}L^{2} + \phi^{3}L^{3} + \cdots ).
$$

But what happens when \\( \| \phi \|  > 1 \\)?
Hamilton cites Sargent who suggests solving the difference equation forward
by applying the inverse operator

$$
\begin{align*}
(1 - \phi L)^{-1} &= \frac{- \phi^{-1}L^{-1}}{1 - \phi^{-1}L^{-1}} \\
&= - \phi^{-1}L^{-1} \left( 1 + \phi^{-1}L^{-1} + \phi^{-2}L^{-2} + \phi^{-3}L^{-3} + \cdots \right),
\end{align*}
$$

where \\( L^{-1} x_{t} = x_{t+1} \\), \\( L^{-2} x_{t} = x_{t+2} \\), etc.
In other words, you solve the difference equation forward as opposed to backward.

The details are included in section 2 of the
[ECON 605 Leahy notes](https://umich.box.com/s/qwizsx7l6ejrnzdunmrckznnwhge2h9y).
The example from the 2011 midterm leads to a very cool interpretation of the benefit of hiring a worker---it's proportional to the discounted sum of the differences between the value of output and the wage.
There's also an example based on, of course, Jorgenson's formula :sparkles:

***

[^fn1]: Does anyone know what's going on there?

[^fn2]: We also applied this technique on the last day of 605 or 607 and I remember commenting that it took the whole year to finally use the result we wrote down on day 1 of class.
