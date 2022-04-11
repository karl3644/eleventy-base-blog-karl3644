---
title: DOM lesson 2.
description: Practical lesson on document object model.
date: 2022-03-30
tags: kd2
layout: layouts/post.njk
---

# DOM Practical

Buttons were created with a class of `buttonFilter`. Each animal is given a button and a button was created to show all (5 in total).

<pre><code>
<input class="buttonFilter" type="radio" name="animalType" id="panda" value="panda">
<label for="panda">Panda</label>

<input class="buttonFilter" type="radio" name="animalType" id="all" value="all" checked>
<label class="buttonFilter" for="all" value="all">Show All</label>
</code></pre>

16 image elements were also created containing pictures of the 4 animals. 
<pre><code>
<img animal="panda" alt="laying" src="https://images.pexels.com/photos/4444036/pexels-photo-4444036.jpeg?auto=compress&cs=tinysrgb&w=300">
</code></pre>

A class of `imageFilter` has been added to each img element, and an attribute has been added to identify each animal `animal="panda"`
<pre><code>
<img class="imageFilter" animal="panda" alt="sleeping" src="https://images.pexels.com/photos/4741847/pexels-photo-4741847.jpeg?auto=compress&cs=tinysrgb&w=300">
</code></pre>

The selection of buttons and images have been stored in a variable for later use.
<pre><code>
let animalRadios = document.forms[0].elements.animalType;
let images = document.getElementsByClassName("imageFilter");
</code></pre>

A loop is run which filters the animal pictures every time a change happens (different buttons are selected)
<pre><code>
for (let i = 0; i < animalRadios.length; i++) { // loop over animal array and run filterAnimal function every iteration
  let item = animalRadios[i];
  item.addEventListener('change', filterAnimals)
}
</code></pre>

The function `filterAnimals` below is run in the above example. It checks if the selected radio button matches an image and applies a css rule of hidden if not, leaving the selected image visable. 

<pre><code>
function filterAnimals() { // function to check if the selected radio button matched the image. if does then removed hidden property of selected
	const selectedAnimal = animalRadios.value;
  filter = selectedAnimal;
  
  for (const image of images) {
    if (selectedAnimal === "all" || selectedAnimal === image.getAttribute("animal")) {
      image.classList.remove("hidden");
      image.removeAttribute("filtered");
    }
    else {
      image.classList.add("hidden");
      image.setAttribute("filtered", true); // setting attribute so the search can see if already filtered
    }
  }
  displayFunction()
}
</code></pre>

A search function is also run to find keywords. This filters out animals which are walking, or sleeping etc. 

It takes text entered in the search box and uses a conditional to check if the text entered is included in the img alt tags.

<pre><code>
function searchAnimals() {
  let searchBoxInput = searchBox.value.toLowerCase();
  searchString = searchBoxInput;
 
  for (let i = 0; i < images.length; i++) {
    let singleImageAlts = images[i].alt;
    let imgAtt = images[i].getAttribute("filtered");
    
    if (singleImageAlts.includes(searchBoxInput) && images[i].getAttribute("filtered") === null) {
      images[i].classList.remove("hidden");
    } else {
      images[i].classList.add("hidden");
    } 
  }
  displayFunction()
}
</code></pre>

Both the above functions also update a display function which gives a text indication of what the user has filtered & searched for. 
<pre><code>
const displayFunction = () => {
  return document.getElementById('textDescription').textContent = `Showing animals that match the search ${searchString} and the filter ${filter}.`;
 }
</code></pre>