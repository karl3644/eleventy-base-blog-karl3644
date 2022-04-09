---
title: Loops, arrays & objects practical.
description: Loops, arrays & objects practical session.
date: 2022-03-26
tags: klaop
layout: layouts/post.njk
---

# Practical session

## Shopping cart parts 1-3

In this practical we took an object and created a function to apply a discount to certain itmes. 

<pre><code>
let shoppingCart = [
  { name: "loaf of bread", type: "food", quantity: 1, price: 0.85 },
  { name: "multipack beans", type: "food", quantity: 1, price: 1 },
  { name: "mushrooms", type: "food", quantity: 10, price: 0.1 },
  { name: "can of beer", type: "alcohol", quantity: 4, price: 1.1 },
  { name: "prosecco", type: "alcohol", quantity: 1, price: 8.99 },
  { name: "steak", type: "food", quantity: 2, price: 3.99 },
  { name: "blue cheese", type: "food", quantity: 1, price: 2.99 },
  { name: "candles", type: "home", quantity: 3, price: 1.99 },
  { name: "cheesecake", type: "food", quantity: 1, price: 4.99 },
  { name: "onions", type: "food", quantity: 3, price: 0.4 },
];

let discount = .8;

function shopping(cartArray, discountAmount, type) {
  let totalPrice = 0;
  
  for (const property of cartArray) {
    if (property.type === type || type === "any") {
      
      totalPrice += ((property.quantity * property.price) * discountAmount)
    } else {
      totalPrice += (property.quantity * property.price)    
    }
  }
  return totalPrice.toFixed(2);
}

console.log("£" + shopping(shoppingCart, discount, "any"));
</code></pre>

The function takes an array, a discount amount and a type as arguments. With this information the function loops over the object searching for the type (food, alcohol, home) and applies the discount from a variable to any item with the type entered. Each iteration increases the totalPrice array by the amount and then returns this to 2 decimals places.

If the type argument is entered as "any" then the discount applies to all items. 

## Shopping cart parts 4-5

We are using the same object as the above but this time returning items dependant upon if their price is between a certain value range.

<pre><code>
 let shoppingCart = [
  { name: "loaf of bread", type: "food", quantity: 1, price: 0.85 },
  { name: "multipack beans", type: "food", quantity: 1, price: 1 },
  { name: "mushrooms", type: "food", quantity: 10, price: 0.1 },
  { name: "can of beer", type: "alcohol", quantity: 4, price: 1.1 },
  { name: "prosecco", type: "alcohol", quantity: 1, price: 8.99 },
  { name: "steak", type: "food", quantity: 2, price: 3.99 },
  { name: "blue cheese", type: "food", quantity: 1, price: 2.99 },
  { name: "candles", type: "home", quantity: 3, price: 1.99 },
  { name: "cheesecake", type: "food", quantity: 1, price: 4.99 },
  { name: "onions", type: "food", quantity: 3, price: 0.4 }
];

function priceSplit(cart, lowPrice, highPrice, quantity) {
  let arrItems = [];
  let priceTimesQuantity = 0;

  for (const property of cart) {
    if (quantity == true) {
      priceTimesQuantity = property.price * property.quantity;
      if (priceTimesQuantity >= 2 && priceTimesQuantity <= 5) {
        arrItems.push(property.name);
      }
    } else if (property.price >= 2 && property.price <= 5) {
      arrItems.push(property.name);
    }
  }
  return arrItems;
}

console.log(priceSplit(shoppingCart, 2, 5, true));
console.log(priceSplit(shoppingCart, 2, 5, false));
</code></pre>

The new function takes an object, two prices and a boolean as arguments.

If the quantity argument is true then the item quantity is multiplied by the item price. If this calculated value is between the two values entered (2 - 5 in this example) then the item is added to a new array and returned once all items have been checked.

If the quantity argument is false then the loop simply checks if the single item value (regardless of quantity) is between the two values and returns these items.