---
title: Functions and Control Flow.
description: Lesson on functions, global/local variables and control flow.
date: 2022-03-02
tags: kfacf
layout: layouts/post.njk
---

# Functions and Control Flow

In this lesson we learnt about declaring functions, invoking functions, using arguments, return statements, conditional statements & logical operators.

1. Task 1 is a function which outputs a sentence.

`function outputSentence() {`
    `console.log("This function outputs a sentence.")`
`}`

2. Task 2 takes 2 arguments and concatenates them using template literals.

`function concatName(firstName, lastName) {`
 `   console.log(`My name is ${firstName} ${lastName}.`)`
`}`

`concatName("Karl", "Higgins")`

3. Task 3 takes 2 arguments, concatenates them and returns the result after invoking.

`function updatedConcatName(firstName, lastName) {`
    `return ``My name is ${firstName} ${lastName} by using a return statement.``;`
`}`

`console.log(updatedConcatName("Karl", "Higgins"));`

4. Task 4 takes an argument and outputs a string based on the input. 

`let temperature = 55;`

`function temperatureFunction(temperature) {`
`    if(temperature < 0) {`
`        console.log("Stay inside.");`
`    } else if (temperature >=0 && temperature < 30) {`
`        console.log("Wear a coat and hat.");`
`    } else if (temperature >=30 && temperature < 50) {`
`        console.log("Wear a coat.");`
`    } else {`
`        console.log("Just pants and vest is fine.");`
`    }`
`}`

`temperatureFunction(temperature)`
