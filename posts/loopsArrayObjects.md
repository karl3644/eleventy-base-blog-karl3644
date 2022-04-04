---
title: Loops, arrays & objects.
description: Lesson on loops, arrays & objects.
date: 2022-03-26
tags: klao
layout: layouts/post.njk
---

# Loops

Loops are used to carry out a task a specific number of times, or until a condition is met. 

The below is a nested for loop. The loop starts at 1 continues running whilst the iteration counter is below or equal to 12. Inside the main loop, another loop is ran 12 times per iteration which in turn  logs the multiplication tables 1-12.

`for (let i = 1; i <= 12; i++) {`
  `for (let j = 1; j <=12; j++) {`
    `console.log(``${i} x ${j} = ${i * j}``);`
  `}`
`}`

# Arrays

# Objects & loops

The below is an object. It is similar to an array but contains both keys and values.

<ul>
`const favRecipe = {`
    <ul>
  `title: "bolognese",`
  `servings: 4,`
  `ingredients: ["onion", "garlic", "tomatoes", "mince meat"],`
  `diections: ["cook onions until brown", "add mince and brown", "add garlic and cook for a further minute", "add tomato sauce and reduce"]`
  </ul>
`};`
</ul>

This for..in loop iterates over the object and prints out the key and value:

`for (const property in favRecipe) {`
  `console.log(``${property}: ${favRecipe[property]}``);`
`}`

The below function takes in an object and prints out a string including the objects title using string literals.

`function letsCook(recipe) {`
    `console.log(``I\'m hungry! Let's cook ${recipe.title}``);`
`}`

`letsCook(favRecipe);`