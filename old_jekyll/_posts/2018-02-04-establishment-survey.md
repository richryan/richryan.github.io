---
layout: post
title:  "On the establishment survey"
date:   2018-02-04 11:18:00 -0400
categories:
macrosquad_402: true
---

Are people who "run their own business" included in the Current Employment Statistics program?
It depends.

<!--more-->

## Background on the CES

Usually on the first Friday of each month the Bureau of Labor Statistics releases data on current employment in the "Employment Situation."
The quoted _level_ of employment comes from the Current Employment Statistics survey,
aka the establishment or payroll survey.

Getting data on the level of employment should be doable because these data are collected for tax purposes.
"Unemployment Insurance (UI) is a federal--state program jointly financed through Federal and state employer payroll taxes (federal/state UI tax). Generally, employers must pay both state and Federal unemployment taxes if: (1) they pay wages to employees totaling $1,500, or more, in any quarter of a calendar year; or, (2) they had at least one employee during any day of a week during 20 weeks in a calendar year, regardless of whether or not the weeks were consecutive. However, some state laws differ from the Federal law and employers should contact their state workforce agencies to learn the exact requirements."[^1]
<!-- But data are collected at the state level. -->

In Rhode Island, for example, employers of one or more workers are subject to the Employment Security and the Temporary Disability Insurance Acts.
Anyone subject to these acts will be taxed and have their data collected by the state of RI.
These data are then compiled by the state of Rhode Island and reported to the Bureau of Labor Statistics in something called the ES-202 Report.

From these state-level data, which are at the UI account number,
the CES creates a sampling frame.
The CES sampling method is based on state, industry, and employment size&mdash;in other words, the CES wants to make sure it's hitting industry and employment numbers at the state level.
The sample is updated twice a year using updated UI-based universe data,
providing information on firm births and deaths,
which is something macroeconomists are into.[^2]

Once the sampling frame is set,
the BLS attempts to collect data from the sample of establishments.
The BLS encourages participation by tailoring their data collection to what the firm prefers.
Initially each firm is called.
Then data are collected according to something called Computer Assisted Telephone Interviewing,
which hopefully leads to self-reporting.

Fun fact: "Very large, multiestablishment firms are often enrolled via personal visit,
and ongoing reporting is established via electronic data interchange,"
which are apparently "electronic files."[^3]

The CES survey sample includes about 160,000 US firms and covers about 400,000 worksites.

That all seems perfectly clear, but the edges seem a little funny.
For example, chapter 2 of the BLS Handbook of Methods states that domestic workers in private homes are excluded from the CES survey.
But in Rhode Island, employers of domestic workers who have paid $1,000 or more in total cash wages in any calendar quarter are subject to UI tax.[^4]
I'm not sure if the Rhode Island employers of domestic workers can be part of the CES sample.
Also, the crew of a fishing boat made up of less than 10 people whose sole remuneration is a share of the catch are not counted.
I don't know if this is a state-level thing,
decided by state legislators.
This fuzziness might explain the 97 percent coverage rate of the CES.

## Answer to the question

If the 10 people running their own business in question 9 of Mankiw 9e, p 45 are paying UI taxes and the business is incorporated, then they are counted as employed in the establishment survey.
If they own a fishing vessel in the state of Rhode Island and pay their crew according to a lay system (see _Moby-Dick_ where Ishmael secured the 300th lay or 1/300 of net profits&mdash;Queequeg secured the 90th lay),
then no.

If the person running their own business is doing it through 1099s or if the business is unincorporated,
then they would not be counted in the establishment survey.
The unincorporated self-employed are not counted in the establishment survey.

And that's why you could make a case that the answer to 9 is either 55 or 65.

You can read even more about the details in Mary Bowler and Teresa L. Morisi's article "Understanding the employment measures from the CPS and CES survey" published in the [February 2006 issue of the Monthly Labor Review](https://www.bls.gov/opub/mlr/2006/02/art2full.pdf).


***

[^1]: You can find more information [here](https://ows.doleta.gov/unemploy/uitaxtopic.asp)
[^2]: You can read about this is the [BLS Handbook of Methods](https://www.bls.gov/opub/hom/pdf/homch2.pdf).
[^3]: So like a spreadsheet? The documentation seems overly complicated here.
[^4]: This comes from the Rhode Island Employer Handbook [here](http://www.dlt.ri.gov/lmi/pdf/eh/emphand.pdf).
