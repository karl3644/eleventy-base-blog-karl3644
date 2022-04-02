---
title: Programming Concepts.
description: Lesson on Javascript and what is can be used for.
date: 2022-03-02
tags: kpc
layout: layouts/post.njk
---

# Programming Concepts

In this lesson we learnt about declarting variables, data types and output methods. The task was as follows:

1. First of all, we created variables containing numbers as the data type for the pre tip total and the tip percentage.

`let preTipTotal = 21.50;`
`let tipPercentage = 12.5;`

2. These variable were then multiplied together to give the tip total.

`let tipTotal = (preTipTotal * tipPercentage) / 100;`

3. The calculated total is then calculated by adding together the tip total and the pre tip total.

`let calculatedTotal = tipTotal + preTipTotal;`

4. This is then output to the console using a string, template literals and rounding the calculated figure to to 2 decimal place.

`console.log(``Your total bill is £${calculatedTotal.toFixed(2)}, which includes a tip of £${tipTotal.toFixed(2)}.``);`