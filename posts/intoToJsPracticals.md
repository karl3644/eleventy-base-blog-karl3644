---
title: Intro to JS Practicals.
description: Practical session on functions & switch statements.
date: 2022-03-03
tags: kitjp
layout: layouts/post.njk
---

# JS Practical

## Percentage Calculator

The page HTML contains 3 inputs - percentage, number & results display (deactivated), and a button.

<pre><code>
<input type="text" id="percentage" placeholder="Percentage">
<input type="text" id="number" placeholder="Number">
<input type="text" id="result" placeholder="result" disabled>
<button onclick="percentageCalculator()">Calculate</button>
</code></pre>

The button contains an onclick event listener which runs the percentage calculator function.

<pre><code>
function percentageCalculator() {
  let percentage = document.getElementById("percentage").value; // value grabbed from HTML file with id percentage
  let number = document.getElementById("number").value; // value grabbed from HTML file with id number
  let result = percentage * (number / 100); // line which carries out the calculation
  
  document.getElementById("result").value = result; // value assigned into HTML element with id of result
  
  console.log(result);
}
</code></pre>

## Switch Statement

A switch statement is another way of taking inputs and running functions based upon the input.

Ths function takes 2 arguments - a drink and size. The drink tells the switch statement which function/lines of code to run, and the size argument is used within template literals to show the drink size.

<pre><code>
function drinkOrder(drink, size) {
  
  switch (drink) {
    case 'cola':
      console.log(`You have ordered a ${size} Coca-cola`);
    break;
    case 'lemon':
      console.log(`You have ordered a ${size} Lemonade`);
    break;
    case 'orange':
      console.log(`You have ordered a ${size} Orange`);
    break;
    default:
      console.log(`Sorry, we are out of ${drink}.`);
    break;
  }
}

drinkOrder("cola", "large");
</code></pre>

## Calculator

Similar to the above, this function uses a switch statement and takes 3 arguments in total (2 numbers and an operator).

The operator argument tells the function which lines of code to run.

If any operator is missing then the switch statement will display a default results of "Arguments missing".

<pre><code>
function calculator(number1, number2, operator) {
  
  let result;
  let message;
  
  switch(operator) {
    case '+':
     result = number1 + number2;
     return message =`${number1} ${operator} ${number2} = ${result}`
    break;
    case '-':
     result = number1 - number2;
     return message =`${number1} ${operator} ${number2} = ${result}``
    break;
    case '/':
     result = number1 / number2;
     return message =`${number1} ${operator} ${number2} = ${result}`
    break;`
    case '*':
     result = number1 * number2;
     return message =`${number1} ${operator} ${number2} = ${result}`
    break;
    case '%':
     result = number1 % number2;
     return message =`${number1} ${operator} ${number2} = ${result}`
    break;
    default:
      return result = "Arguments missing"
    break;
  }
}
console.log(calculator(10, 4, ``%``));
</code></pre>