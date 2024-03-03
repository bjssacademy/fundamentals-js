# Javascript

For those who know nothing about Javascript, but enough about the fundamentals of programming!

This is not an extensive guide to JavaScript, nor is it intended to be. It will allow you to add minimal interactivity to a static website, and covers some of the very fundamentals of the language.

There are plenty of places to learn JavaScript, or *JS* as it's more commonly known, in-depth like [W3 Schools](https://www.w3schools.com/js/default.asp).

This guide assumes you have completed the previous fundamental guides on HTML and CSS.

<!-- TOC -->

- [Javascript](#javascript)
    - [What is it?](#what-is-it)
    - [Learning Javascript](#learning-javascript)
        - [The Console](#the-console)
    - [Variables](#variables)
        - [Also, Const!](#also-const)
        - [let vs var](#let-vs-var)
    - [Structured/Block Programming](#structuredblock-programming)
        - [Scope](#scope)
        - [Code example](#code-example)
        - [Using Var](#using-var)
            - [Generally, you should use this rule](#generally-you-should-use-this-rule)
        - [Another way of thinking about scope](#another-way-of-thinking-about-scope)
    - [Dynamic vs static Language](#dynamic-vs-static-language)
        - [Dynamic Languages Create Issues](#dynamic-languages-create-issues)
    - [Control Flow](#control-flow)
    - [Loops](#loops)
    - [Arrays](#arrays)
        - [Array Iteration](#array-iteration)
    - [Functions](#functions)
        - [In the console](#in-the-console)
    - [Tasks](#tasks)
        - [Node.js](#nodejs)
- [Getting JS to do things on our page](#getting-js-to-do-things-on-our-page)
    - [JavaScript Events](#javascript-events)
    - [Event Handler](#event-handler)
        - [Example](#example)
        - [Common Events](#common-events)
- [Selecting Elements](#selecting-elements)
- [Objects & Properties](#objects--properties)
    - [What’s an Object?](#whats-an-object)
    - [Variables & Objects](#variables--objects)
    - [Object Properties](#object-properties)
        - [Chaining](#chaining)
            - [Example](#example)
            - [Full Code](#full-code)
    - [Object Methods](#object-methods)
        - [Example – Remove() method](#example--remove-method)
    - [Tasks](#tasks)
        - [Onclick methods & properties](#onclick-methods--properties)
- [Including JS in your HTML](#including-js-in-your-html)
    - [Script tag](#script-tag)
    - [A note on rendering](#a-note-on-rendering)
        - [Generally…](#generally)
    - [Adding Functions](#adding-functions)
    - [External Javascript](#external-javascript)
    - [Third Party Javascript](#third-party-javascript)
    - [Third Party Javascript](#third-party-javascript)
        - [Tips for Using Libraries](#tips-for-using-libraries)
- [Workshop 1](#workshop-1)
    - [Let’s update our profile site!](#lets-update-our-profile-site)
- [Workshop 2](#workshop-2)
    - [With the new Slider code…](#with-the-new-slider-code)
- [Workshop 3 - Advanced](#workshop-3---advanced)
    - [Working With APIs](#working-with-apis)

<!-- /TOC -->

## What is it?

- A programming language

- First designed to make web pages more interactive

- Now runs not just in browsers, but almost anything

---

JavaScript is a programming language or, in other words, a means by which a computer is instructed to do things. All web browsers understand JavaScript and you can take advantage of that to make web pages do things.

JavaScript started as a way to make web pages more interactive. Nowadays JavaScript runs in more places than just web browsers — it runs on web servers, phones and even robots. 

## Learning Javascript

![](<img/Javascript 101 Autosaved0.png>)

### The Console

For the sake of simplicity I'll assume you are using Google Chrome to read this page (if you aren't it's probably easier on both of us if you follow along with Chrome).

First, right click anywhere on the screen and hit Inspect Element, then click on the Console tab. 

![](<img/Javascript 101 Autosaved1.png>)

You should see a window that looks like:

![](<img/Javascript 101 Autosaved2.png>)

This is a console, otherwise known as a "command line" or "terminal". 

Type `1 + 1` into the console and then hit the Enter key and watch what happens.

Using the console is a very important part of learning JavaScript. 

We'll be using this console to start with, as it allows us to execute JavaScript without having to install anything (we'll do that later).

## Variables

Very straightforward, we use the var keyword to declare the variable mySentence, and assign it a value of "My word, what a sunny day!", which is a string:

```js
var mySentence = "My word, what a sunny day!"
```

> A string is just a series of letter or numbers enclosed in quotes, like a sentence or paragraph or question or quote.

Strangely, this being JS, we can also use the let keyword to do exactly the same thing:

```js
let mySentence = "My word, what a sunny day!"
```

Even more strange, because this is is JS we don’t actually need to use the var or let keywords at all……

![](<img/Javascript 101 Autosaved3.png>)

### Also, Const!

Const, short for constant, is a variable that is declared and assigned at the same time and cannot be changed.

![](<img/Javascript 101 Autosaved4.png>)

Here's a look at things you cannot do with `const` that you can with `var` or `let`:

![](<img/Javascript 101 Autosaved5.png>)


### let vs var

![](<img/Javascript 101 Autosaved6.jpg)

`let` allows you to declare variables that are limited to the scope of a block statement, or expression on which it is used, unlike the `var` keyword, which declares a variable globally, or locally to an entire function regardless of block scope. 

`var` uses a concept called "hoisting". If you use `var` the variable is considered globally available anywhere due to how scope is used in JS and in block programming in general.

## Structured/Block Programming

In computer programming, a block or code block or block of code is a lexical structure of source code which is grouped together. Blocks consist of one or more declarations and statements:

![](<img/Javascript 101 Autosaved7.png>)

### Scope

Variables declared in one block are not accessible from another block if they are local. Variables live in block of code. In Javascript they *used to* have ONLY the var keyword.

![](<img/Javascript 101 Autosaved8.png>)

However, variables declared in a parent block *are* available in their descendant, or children blocks:

![](<img/Javascript 101 Autosaved9.png>)


### Code example

![](<img/Javascript 101 Autosaved10.png>)

Using `let` on line 2 means it has created a variable named “y”, but it cannot be seen outside of its code block, or scope. The scope here is defined by the enclosing curly braces.

You can type this into the console for yourself!

### Using Var

However, using VAR we can make a variable global – that is, accessed from anywhere in the code:

![](<img/Javascript 101 Autosaved11.png>)

Using `var` on line 2 means it has created another variable named “y”, but it has been "hoisted" outside its code block and is available to both conditions. 

![](<img/Javascript 101 Autosaved12.png>)

And it's even available outside of those conditions as it's global:

![](<img/Javascript 101 Autosaved13.png>)

#### Generally, you should use this rule

> Thou shalt use only let or const!

### Another way of thinking about scope

![](<img/Javascript 101 Autosaved14.png>)

To understand scope, let's imagine a set of nesting dolls. Each nesting doll represents a different scope level.

- Global Scope: Imagine the largest nesting doll, which represents the global scope. Variables defined in the global scope are accessible from anywhere in your code. They are like items placed in the outermost doll that can be seen and accessed by anyone.
- Function Scope: Now, picture a smaller nesting doll inside the global one. It represents a function scope. When you define variables or functions within a function, they become part of that function's scope. These variables and functions can only be accessed from within that function or from nested scopes within it. It's like placing items inside this smaller doll, where they are visible and reachable only inside that specific doll.
- Block Scope: Now, imagine another smaller nesting doll inside the function scope doll. This represents a block scope. Block scopes are created by statements like if, for, or while loops, or even just a pair of curly braces {}. Variables defined within a block scope are only accessible within that block or nested blocks. It's like placing items inside this even smaller doll, visible and reachable only within the confines of that block.
- Lexical Scope (Closure): Picture a smaller nesting doll inside the block scope doll. This represents a closure or lexical scope. When a function is defined inside another function, the inner function has access to variables in its own scope, as well as variables in the outer function's scope. It's like placing a doll inside another doll, where the inner doll can access the items of both the inner and outer dolls.

## Dynamic vs static Language
 
If you have come from a statically-typed language like Go, Java or C#, that we can’t declare a variable of one type, and assign it another type – you can see the code below.

This is because Go is a *statically-typed language*. 

![](<img/Javascript 101 Autosaved15.png>)
![](<img/Javascript 101 Autosaved17.png>)

Javascript, on the other hand, is a *dynamic language* and will let you change the type, because it only checks when it runs, not when it compiles like Go.

![](<img/Javascript 101 Autosaved16.png>)
![](<img/Javascript 101 Autosaved18.png>)

### Dynamic Languages Create Issues

Let’s take a simple function here that adds two numbers, stored in variables a and b, both set to 1.

The main problem here is that we can change b to “hello” and javascript does not complain, it just treats both params as string and concatenates them together and returns us a string:

![](<img/Javascript 101 Autosaved19.png>)

![](<img/Javascript 101 Autosaved20.png>)

Imagine you used that return value somewhere else, expecting it to be a number rather than string? You wouldn’t find that out until runtime! The only way to know if you have a problem is to run the program and try it, you get no help from the compiler because there isn’t one!

So you have to be very careful when using JS that you know what you are doing and do extra work to validate your inputs, because everything in JS can be a string, or treated like one.

## Control Flow

As we can see – control flow via `if` statements are almost exactly the same as in many other languages, but the conditional is wrapped in parenthesis `()` and the code to execute for each condition block in scoped by curly braces `{}`.

![](<img/Javascript 101 Autosaved22.png>)

In the example below we assign the numbers 10 and 20 to the variables `n1` and `n2` respectively, then evaluate the condition by checking if `n1` is equal to `n2`.

What will it print out?

![](<img/Javascript 101 Autosaved21.png>)

## Loops

Again, very similar to what we have seen before, this is a counting loop:

![](<img/Javascript 101 Autosaved23.png>)

JavaScript supports different kinds of loops:

- `for` - loops through a block of code a number of times
- `for/in` - loops through the properties of an object
- `for/of` - loops through the values of an iterable object
- `while` - loops through a block of code while a specified condition is true
- `do/while` - also loops through a block of code while a specified condition is true

https://www.w3schools.com/js/js_loop_for.asp

## Arrays

Arrays in JavaScript are much like any other language in how you construct them. Assuming we have a list of friend names, we might want to store them together:

```js
let friends = ["Bob", "Sue", "Elaine", "Kaushik"]
```

This makes it easier to add and remove friends from the list as there are *methods* we can use such as `pop()` to remove an element from the array, as well as iterate round them to send them all messages.

https://www.w3schools.com/js/js_arrays.asp

### Array Iteration

Arrays have a special method for iterating over them called `forEach`, to which you have to pass a `function`:

```js
const numbers = [45, 4, 9, 16, 25];
let txt = "";
numbers.forEach(myFunction);

function myFunction(value, index, array) {
  txt += value + "<br>";
}
```

https://www.w3schools.com/js/js_array_iteration.asp

## Functions

Functions in JS are quite similar to other languages.

To declare a function, you use the keyword `function`, followed by the name of the function so you can call it, and any parameters:

![](<img/Javascript 101 Autosaved24.png>)

You’ll notice that unlike other language, JS doesn’t need us to specify the return type. 

For instance in Go we would have to specify string as the return type, but since JS is a *dynamic language*, we don’t need to. 

This makes things look easy but causes problems using methods – how do we know what we are going to be returned?

### In the console

Go ahead and type the function into the console and press Enter:

![](<img/Javascript 101 Autosaved25.png>)

You’ll notice that it says undefined here, don’t worry about that, it’s because we haven’t called the function! We've written the function, but at no point have we said we want to use it!

Let's go ahead and call the function by using its name, and passing it the required parameter (a string):

![](<img/Javascript 101 Autosaved26.png>)

What you’ll notice as you type in the string you want to send, the function is already starting to tell you what it returns!

![](<img/Javascript 101 Autosaved27.png>)

And when you finally hit enter, you get back the result in the console. And you can carry on calling this function in the console until you refresh the page – give it a try!

## Tasks

* Install [Node](#nodejs)
  * Node is a Javascript runtime; we need it to run JS locally when not in a browser
* [Unzip the provided file](/code/js101.zip) on your computer
* From your unzipped file, navigate to folder `js101`
* Open VS Code from this folder (`code .`)
* From the files shown, you want to use `temp.js`:

![Alt text](img/Picture35.png>)

> We’ve written the calling code for you, *there is no need to change any of this*

You will have to comment out calling code you have not yet written a function for, otherwise you will get errors.

You need to write 3 functions:
- addNumbers
- printNumbers
- isDog

* Bonus task: The following code produces a random number between 1 and 6:
    * Math.floor(Math.random() * 6) + 1;
    * Write a function that accepts a parameter x, and produces x * random numbers. Eg if x was 10, it would produce 10 random numbers.

### Node.js
https://nodejs.org/en/download 

Node is a Javascript runtime; we need it to run JS locally when not in a browser.

To run .js files outside of a browser, navigate to the folder in the terminal and type: 

```node filename.js ```

to execute the file (replace `filename.js` with the actual name of your file)


# Getting JS to do things on our page

## JavaScript Events

HTML events are "things" that happen to HTML elements.

When JavaScript is used in HTML pages, JavaScript can "react" to these events.

---

An HTML event can be something the browser does, or something a user does. Here are some examples of HTML events:
- An HTML web page has finished loading
- An HTML input field was changed
- An HTML button was clicked

Often, when events happen, you may want to do something. JavaScript lets you execute code when events are detected.

## Event Handler

HTML allows event handler attributes, with JavaScript code, to be added to HTML elements.

With single quotes:

```<element event = 'some JavaScript'>```

With double quotes:

```<element event = "some JavaScript">```

### Example

![](<img/Javascript 101 Autosaved28.png>)

Shorthand for, when this button is clicked, run this bit of javascript!

### Common Events

| Event | Description |
| :-: | :-: |
| onchange | An HTML element has been changed |
| onclick | The user clicks an HTML element |
| onmouseover | The user moves the mouse over an HTML element |
| onmouseout | The user moves the mouse away from an HTML element |
| onkeydown | The user pushes a keyboard key |
| onload | The browser has finished loading the page |

---

There are other events we can use too (and lots of others). But these are events that are commonly used.

Can you think of some examples where you might use these events?

# Selecting Elements

`document.getElementById` is a JavaScript function that allows you to access and manipulate elements in an HTML document. It is part of the Document Object Model (DOM), which is a programming interface for web documents.

The DOM represents the structure of an HTML page as a hierarchical tree-like structure, where each element (like a paragraph, heading, button, etc.) is a node in the tree. Each node can have properties and methods associated with it.

![](<img/Javascript 101 Autosaved29.png>)

With `document.getElementById`, you can find a specific element in the HTML document by its unique identifier, known as the "id" attribute. The function takes the id of the element you want to access as an argument and returns the corresponding element node.


![](<img/Javascript 101 Autosaved30.png>)

So here, the result of the `getelementbyid` is that it selects the entire \<p> element, and stores a reference to it (as an object) in the variable `paragraphElement`.

Now we have that reference, we can perform actions, such as changing the inner HTML – the text inside the tags – to whatever we like. For example if we changed it to Goodbye:

![](<img/Javascript 101 Autosaved31.png>)

# Objects & Properties

## What’s an Object?

An object is a thing we can interact with and examine. It's a more *complex data type*.

Things in the physical world we can interact with have certain characteristics and abilities.

Right now I'm looking at a hoover, because that's on my list of things to do after I finish writing this. That hoover has certain things I can interact with, like turning it on and off, and certain characteristics like how full the bag is.

Things that we can interact with are known as *methods*.

Things that we can examine and change are known as *properties*.

---

What we've actually done in our previous code when we found an element by using its `id` attribute is use the `document` library's method `getElementById()` to return an *object*.

We can then use the object and its own *properties* and *methods*:

![](<img/Javascript 101 Autosaved32.png>)

So our `paragraphElement` is an *object*, and we change one if its *properties*.

---
![](<img/Javascript 101 Autosaved33.gif)

In real life, a car is an object.
A car has properties like weight and color, and methods like start and stop:

| Object | Properties | Methods |
| :-: | :-: | :-: |
| car | car.name = Fiat<br>car.model = 500<br>car.weight = 850kg<br>car.colour = white | car.start()<br>car.drive()<br>car.brake()<br>car.stop() |

All cars have the same properties, but the property values differ from car to car.
All cars have the same methods, but the methods are performed at different times.

## Variables & Objects
```js
//Simple assign – car holds the string “Fiat”

let car = "Fiat";

//Objects are variables too. But objects can contain many values.

//This code assigns many values (Fiat, 500, white) to a variable named car:

const car = {type:"Fiat", model:"500", colour:"white"};
```
---

The important thing here is to know that variables can hold objects, not just simple data types such as `string`, `int` or `boolean`, but complex objects with multiple properties that have their own methods.

> NOTE: Const is often used for objects rather than let….

## Object Properties
```js
let car = "Fiat";

Console.log(car) prints “Fiat”

const car = {type:"Fiat", model:"500", colour:"white"};

Console.log(car) prints {type:"Fiat", model:"500", colour:"white"}

Console.log(car.type) prints “Fiat”
```
---

To print the type of car, we have to use the property `type`, otherwise it will print out the `OBJECT literal`. Try it in the console in Chrome. Try to print out the model property.

### Chaining

We can “chain” things together, if they are an object by acting on their properties without using an intermediate variable. This “dot notation” is used extensively on objects, but for now we’re just explaining it.

![](<img/Javascript 101 Autosaved34.png>)

#### Example

![](<img/Javascript 101 Autosaved35.png>)

#### Full Code

![](<img/Javascript 101 Autosaved36.png>)

https://www.w3schools.com/js/tryit.asp?filename=tryjs_event_onclick1

## Object Methods

So *properties* are things we can change, like name, text, attribute values and so on. But *methods* are things that operate like functions (they provide functionality on the object) and are known as *methods*.

| Object | Properties | Methods |
| :-: | :-: | :-: |
| car | car.name = Fiat<br>car.model = 500<br>car.weight = 850kg<br>car.colour = white | car.start()<br>car.drive()<br>car.brake()<br>car.stop() |

So in our car example, we can change its properties, like name, model, weight. But its methods are things that we can *make happen* without knowing how it achieves it internally.

In the car example we have `start`, `drive`, `brake`, and `stop`. We can’t change *how* it starts or drives, but we can call the method!

```js
car.start()

car.stop()
```
---

So if we call the method `car.start()`  the car starts moving, and we call the method stop to stop it. We haven’t changed the properties of the car, it’s colour or name, we’ve just *acted* upon it.

### Example – Remove() method

![](<img/Javascript 101 Autosaved38.png>)

https://www.w3schools.com/jsref/dom_obj_all.asp

## Tasks

### Onclick methods & properties

* Create a new `index.html` file in your js101 folder
* Scaffold it with html boilerplate code
* In the body:
  * Create a p element with the id of `myid`
  * Create a table element with the id of `table1`
* Create three buttons, one with text “Show the date”, one with “Hide the table”, and one with “Show the table”
* Add the `onclick` event to the buttons
* Using the selector code `document.getElementById(‘yourelementidhere’)`
  * Use the `innerHTML` method to change the p element to the current date by calling the JS `Date()` function
  * Find the properties to show/hide the table element from the DOM
* Challenge – can you add another button that inserts a new row to the table every time it is clicked?

# Including JS in your HTML

## Script tag

To include JS in your HTML page you use the \<script> tag:

```js
<script type="text/javascript">

alert(“Hi!”);

</script>
```

Anything inside the script tag will be treated as JS code.

In this example, it will show an alert popup dialog with the text “hi!”.

You can include JS anywhere in your file, but you’ll often find it in the `head` tag…but that can cause problems if you don’t know what you are doing. And that’s due to the way the page renders, or how the browser reads the HTML document.

![](<img/Javascript 101 Autosaved39.png>)


## A note on rendering

When JavaScript code is included in an HTML file within the \<script> tags, the order of execution follows a *top-to-bottom* approach:

![](<img/Javascript 101 Autosaved40.png>)

Understanding this order of execution is important for ensuring that the JavaScript code behaves as intended and interacts correctly with the HTML elements and structure of the page.

Let's see an example (and you can also see and execute the broken code in the file `orderofexecution.html` in the unzipped file):

![](<img/Javascript 101 Autosaved41.png>)

![](<img/Javascript 101 Autosaved42.png>)

We are trying to execute code on an element that has *not yet been rendered to the screen*. This is becaus eof the *order of execution* reads from top to bottom and executes in that order.

You need the element to be *rendered* before you can *act* on it:

![](<img/Javascript 101 Autosaved43.png>)

### Generally…

* Generally your script tag and JS goes just before the closing body tag
* Remember, the order of execution is important!
  * A function is only executed when it is called_
* You cannot rely on things in the DOM to be there before your code executes

## Adding Functions

```js
<script>

	function_deleteTable() {

		document.getElementById(“table1”).remove()

	}

</script>

<button_onclick=“deleteTable()”>Remove Table!</button>
```

You can also wrap your code in a *function*. This means it will not be executed until it is called, stopping the issue with order of execution - as long as you call the function after your elements are rendered of course!

## External Javascript

We can also have our javascript in another file, known as external javascript:

```html
<script src="myScript.js"></script>
```

Placing scripts in external files has some advantages:

- It separates HTML and code

- It makes HTML and JavaScript easier to read and maintain

- Cached JavaScript files can speed up page loads

To add several script files to one page  - use several script tags:

Example:

```html
<script src="myScript1.js"></script><script src="myScript2.js"></script>
```
## Third Party Javascript

JavaScript libraries are a bunch of JavaScript code written by somebody else, and you can load them in your HTML to use the library’s code in your own code.

Here's an example of importing the library "[sweetalert](https://sweetalert.js.org/)"

![](<img/Javascript 101 Autosaved44.png>)

You can find the code in `swal.html` to run:

![](<img/Javascript 101 Autosaved45.png>)

### Tips for Using Libraries

Even after you find a library, learning how to use it might seem a little overwhelming: how do you know what variables and functions are offered by a library? How do you know what code you should write to make something happen?

Figuring out the answers to those questions is a huge part of coding. So if you feel confused, that’s normal! Here are a few tips to help you through the process:

- Read the documentation

- Break the problem down

- Go back to the documentation

- Test out your assumptions in a test files

- Use the internet

- Ask for help

---

Find the documentation. This should always be your first step. Start by reading through the library’s website, which should include documentation. For example, the Sweet Alert guides contain examples that use the library.

Read through the documentation. You don’t have to memorize anything, and you don’t have to become an expert in the library. But you should read through the different sections of the documentation. Get a high-level understanding of the different features offered by the library. Spend some time becoming familiar with the library. You should be able to write a one-paragraph summary of what the library does and some of its main features.

Break your problem down into smaller steps. If you have a big goal, you can start to feel like you don’t even know where to start. If so, then you need to split your goal up into smaller sub-goals. For example, if my goal was to show an input element in an alert box, I would start by getting a normal alert working, and then I’d work my way forward from there.

Go back to the documentation. Now that you have a single small step in mind, go back to the documentation and read about that particular small step in more detail.

Write test programs. If you’re working in small steps this should come pretty naturally. Don’t just work out of a single file that contains your end goal project. Write smaller standalone programs that test out just one feature of the library before you try integrating it into your bigger project. I almost always have a standalone index.html file on my dekstop that I use for testing smaller parts by themselves.

Use search engines. If you’re stuck on a particular step, then try typing what you’re trying to do into a search engine. For example, searching for “SweetAlert show input” returns a bunch of results. Try to work that into the test program you’re writing.

# Workshop 1

## Let’s update our profile site!

> This task assumes you have previously done the HTML fundamentals.

Add a new page, `gallery.html`

Create a new folder called `pictures` and add in 5 or 6 pictures (.jpg or .png format) of your choice

Using the slick library [https://kenwheeler.github.io/slick/](https://kenwheeler.github.io/slick/) create a multiple item carousel of pictures

> Don’t forget your navigation!

# Workshop 2

## With the new Slider code…

Externalise the CSS into a separate file

Externalise the Javascript into a separate file

Wrap the javascript in a function that you have to call from the HTML file to execute

What does `addEventListener` do?

# Workshop 3 - Advanced

## Working With APIs

Open the `api.html` file.

We are using the JavaScript's `fetch` to get data from a remote API and display it.

Fetch is asynchronous - this means the program doesn’t wait for the result, but continues execution, unless you explicitly `await` the result.

Read the code. Can you follow what is going on?

https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch



