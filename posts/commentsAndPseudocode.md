---
title: Pseudo Code and Comments.
description: Lesson on Pseudo Code.
date: 2022-03-05
tags: kp
layout: layouts/post.njk
---

# Comments

Comments are used for adding further detail to code if required. It helps readability for yourself and other people working on your code. 

`function percentageCalculator() {`
  `let percentage = document.getElementById("percentage").value; // value grabbed from HTML file with id percentage`
  `let number = document.getElementById("number").value; // value grabbed from HTML file with id number`
  `let result = percentage * (number / 100); // line which carries out the calculation`
  
  `document.getElementById("result").value = result; // value assigned into HTML element with id of result`
  
  `console.log(result);`
`}`


# Pseudocode
Pseudo code is a way to write algorithms in a language such as english which is intended for people to read and understand, as opposed to computers. It is useful for planning purposes and a way for people to understand programs without the need to know code. 

## fixStart
<ul>
create fixStart function which takes an input_string
    <ul>
    create new variable firstCharacter which is 1st character of input_string
    create new empty variable called output_string
    LOOP through each character in the input_string using string length as iterator
        <ul>
        compare each character to the firstCharacter variable
        IF 1st character of input_string
            <ul>
            add character into output_string
            </ul>
        ELSE IF character iteration equals firstCharacter
            <ul>
            add character * into output_string
            </ul>
        ELSE add non matching character into output_string
        </ul>
    RETURN output_string
    </ul>
<ul>
## reading list
 create a variable which is an array of objects containing book title, author and alreadyRead (true/false)
 LOOP over each object using array length
     check the alreadyRead key
     IF alreadyRead is true
         console log "You have already read ${title} + ${author}
     ELSE alreadyRead is false
         console log "you still need to read ${title} + ${author}