---
title: DOM.
description: Lesson on document object model.
date: 2022-03-28
tags: kd
layout: layouts/post.njk
---

# DOM

## Task 1

Getting variables from the DOM by using different selectors:

Select elements by Id
<pre><code>
const form = document.getElementById('todo');
</code></pre>

Directly selecting elements
<pre><code>
const titleInput = form.elements.title;
</code></pre>

Select elements by Class
<pre><code>
getElementsByClassName('todo');
</code></pre>

## Task 2

The below function creates a list item element and uses the function parameter as text within the list item.

<pre><code>
const todoPane = document.getElementById('todo-pane');

function createElement(input) {
  let title = document.createTextNode(input);
  let list = document.createElement("li");
  list.appendChild(title);  
  return list
}

const newElement = createElement('This is the title');
todoPane.appendChild(newElement); 

</code></pre>

## Task 3

.remove() is a built in .js function which deleted an element. The below code is set to run when the page loads but it can be attached to run on an event. 

<pre><code>
let washing = document.querySelector('.todo')
washing.remove();
</code></pre>

## Task 4

An event listener is used to run a function at the time of an event. Below example runs a function at the time the forms submit button is pressed. Other events can be used such as on click, mouse down, key down etc.

<pre><code>
const form = document.forms.todo;

form.addEventListener('submit', function () {
 alert("im an alert");
});
</code></pre>

## Task 5

The event listener using a click event is used to remove the element with a class of .todo. 

<pre><code>
const listItem = document.querySelector(".todo");
listItem.addEventListener('click', function() {
  listItem.remove();
});
</code></pre>

## Task 6

By using all of the above snippets together, a small program can be created to add a list item to the page/DOM using user inputted text, and any of the created items can be removed by clicking on them. 

<pre><code>
const priorityImages = {
  low: 'https://cdn1.iconfinder.com/data/icons/prettyoffice8/256/Flag-green.png',
  medium: 'https://cdn1.iconfinder.com/data/icons/prettyoffice8/256/Flag-yellow.png',
  high: 'https://cdn1.iconfinder.com/data/icons/prettyoffice8/256/Flag-red.png',
};

const form = document.getElementById('todo');
const todoPane = document.getElementById('todo-pane');
const titleInput = form.elements.title;
const prioritySelect = document.getElementById('priority');
const allTodos = document.getElementsByClassName('todo');

form.addEventListener('submit', function (event) {
  let newTodo = createTodo(titleInput.value, prioritySelect.value);
  todoPane.appendChild(newTodo);
  titleInput.value = '';
  event.preventDefault();
});

function createTodo(title, priority) {
  let newTitle = document.createTextNode(title);
  let newListItem = document.createElement("li");
  let newImage = document.createElement("img");

  newImage.src = priorityImages[priority]
  newListItem.appendChild(newImage); 
  newListItem.appendChild(newTitle);
  newListItem.classList.add('todo', 'just-created');
  newListItem.addEventListener('click', function (event) {
    event.currentTarget.remove();
  });
  
  return newListItem;
}
</code></pre>