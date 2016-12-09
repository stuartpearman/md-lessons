# Basic Programming

# Variables

Variables are used to store a value. These values can affect any number of things in your applications. Here are some examples:

- the number of times an event will happen
- the name of a character
- a url of a website
- the size of an element

Think back to CSS properties and values. These are variables too, and they affect all of the visual properties of your website. We'll be working in Javascript, but these principals work in Ruby, PHP, C#, and pretty much any programming syntax you can think of.

Think about what variables describe you as a person. Age: 23, Hair Color: brown, Employeed: true. If we were to declare those in javascript, the syntax would look like this:

	var age = 23;
	var hairColor = "brown";
	var employed = true;
	
We're using three main types of variables here, a `number`, `string`, and `boolean`. Number is fairly self explanatory, a string is any text variable, and boolean is basically true/false.

# Functions

Variables are nice for holding information, but if we want to actually *change* things, we'll generally want to use **functions**.

Functions are used throughout programming too. Think of the terminal commands you used earlier -- cd, ls, pwd -- these are functions. When you *call* the function `ls` in the terminal, it outputs a list of the available files and folders.

A timeless and somewhat lame example is a function that simply outputs "hello world" to the document. Here's how it goes in Javascript:

	function greeting () {
		document.write("Hello World");
	}
	
If we call this function once, it will output "Hello World" one time. A cool thing about functions, though, is that once we create them, we can use them as many times as we want. Like this:

<!-- <a class="jsbin-embed" href="http://jsbin.com/qepubijoqi/1/embed?js,output">JS Bin on jsbin.com</a><script src="http://static.jsbin.com/js/embed.min.js?3.40.2"></script> -->

## Syntax breakdown

Before we get too far, lets break down the syntax of a function

	function nameOfFunction ( parameter ) { ... }
	
1. `function` is used use the same way as `var`. It's saying "we're about to declare a function"
2. `nameOfFunction` can be anything, whatever you want the name of your function to be
3. `( parameter )` between the opening and closing parentheses goes a `parameter`, some functions have parameters and some don't. We'll talk more about this in a moment.
4. `{ ... }` Between the opening and closing braces is where all the magic in a function is set up. Be careful to always close braces (and parentheses) when you open them.

## Input -> Output

This is where functions get fun. Remember the terminal command `cd`. It requires an **input** from the user, the name of whichever directory you'd like to change to. 

This is a big concept, think of a recipe, input ingredients into the function, output cookies. Or an assembly line. Input raw materials, run them through the many functions in the factory, output all sorts of things.

This is where parameters come into play. Let's change the last function a bit.

	function greeting ( name ) {
		document.write("Hello" + name);
	}
	
We've now taken a very rigid function and made it flexible. We can say hello to whoever now. Sure, still kinda boring, but how much cooler is a robot who can call you by name rather than saying the same 10 things over and over? Way cooler.

# Event Listeners & Built-in Functions

So it's pretty lame having to call our functions in javascript everytime we want them to run, that's not very interactive. This is true, and event listeners are the missing key.

Event listeners wait for an **event** to happen, and then do something when it does. There are a ton of them, but a simple one is the click event. Let's check it out.

<!-- <a class="jsbin-embed" href="http://jsbin.com/fivotopovi/1/embed?js,output">JS Bin on jsbin.com</a><script src="http://static.jsbin.com/js/embed.min.js?3.40.2"></script> -->

	var button = document.getElementById("button");
	var content = document.getElementById("content");
	
	function greeting (name) {
  		content.innerHTML += "Hello" + name;
	}

	button.addEventListener("click", function(){
  		greeting("pablo");
	});
	
The first thing to notice is `document.getElementById()`. This is a function built into javascript, and it finds an HTML element with the given ID. We found an element with the id "button", and one with the id "content". We set these each to a variable so we can use them later.

We still have our greeting function, but now instead of just outputing some content, we're outputing the message into the `innerHTML` of our `content` element that we set earlier.

At the bottom, we're adding a "click" event listener to our `button`, which we also set earlier. Upon clicking the button, any code we put between the curly brackets of the `function` will run. In this case we're calling the greeting function and saying hello to Pablo.

## Event Listener Syntax

Let's look at this line a little closer.

	button.addEventListener("click", function () { ... })
	
What's going on here? First off, you've probably started to notice that some functions can be attached to the end of variables using a dot, like `button.addEventListener` or `document.getElementById`. For now, all you need to know is that other than that, they're still the same syntax as other functions.

If it's still the same syntax, why is there *another function* inside the `addEventListener` function? That doesn't seem the same. Sometimes a function will take a second function as a parameter. This is called a **callback** function. A callback function is just a regular function, but it's run *within* another function, almost always at the end.

So the addEventListener function *waits* for an event, and when that event is triggered (in this case a click), it runs the callback.


# Project 

