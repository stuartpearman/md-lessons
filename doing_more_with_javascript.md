# Doing more with javascript

Go ahead and start from scratch with the same file structure as the last lesson.

	index.html
	script.js
	
Set up your HTML file and link your javascript file just like before. Copy the following into your javascript file.

	var message = "hello";
	
	function changeMessage () {
		message = "goodbye";
	}
	
We'll be doing more with this in a little bit, but for now, start your local server and head to `localhost:8080` in your browser.

===

## Element inspector

Any modern browser you has a feature for developers called the **element inspector**. This is an awesome tool for understanding how all the different pieces of your of your website are working together. You may also hear this being called the developer tools, or developer panel. Don't worry, these all mean the same thing.

Here are instructions for accessing the inspector in [Chrome](https://developer.chrome.com/devtools), [Firefox](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Open_the_Inspector), and [Safari](https://developer.apple.com/library/content/documentation/AppleApplications/Conceptual/Safari_Developer_Guide/GettingStarted/GettingStarted.html#//apple_ref/doc/uid/TP40007874-CH2-SW1).

I encourage you to look up keyboard shortcuts for any of these browsers, for instance in Chrome, you can pull up the element inspector with the shortcut `Command` + `Option` + `i` on MacOS or `Ctrl` + `Shift` + `i` on Windows.

### The console

In your element inspector, there will be a tab labeled `console`. This is your **javascript console**, and you can use it to debug and test out javascript code. Make sure you're on the URL for this week's project and type `message` into the console window. Just like the terminal, press enter to see the result.

If you followed the steps from the first slide, you'll see the console output `"hello"` on the next line. Now enter `changeMessage()` into the console, and the try typing `message` again. This time it should say `"goodbye"`.

The console allows you to not only check the values of your variables, but run functions too. You can test out all new code right from the console.

### Reading errors

The console is also where you'll go to check for errors. In your javascript file, change `"hello"` to `hello` without quotes. Refresh your page and try typing in `message` again. You'll get an error, something like this:

	# => Uncaught ReferenceError: hello is not defined
	
you should also see `script.js:1` next to it. This is telling you what file your error is in, and what line of that file. Now, you can go right to line 1 and fix the error, rather than having to guess.

### Logging information to the console

As well as accessing information from the console, you can log anything you want to the console right from your javascript file. This is great for testing. Try this:

	console.log(Math.random())
	
This will give you a random decimal between 0 and 1. If you keep refreshing, the number will continue to change.

===

## If statements

Now let's learn a new core concept in coding logic. You can think of the **If statement** like a railroad switch. If the switch is on, the train will take a different track, if it's off, the train will continue straight. Here's how it looks in javascript:

	if (expression) { ... }

The if statement works by checking an **expression**. If the expression is true, it will run the code between the brackets. If it's false, it will just ignore that code. Here are some examples of what an expression might look like:

	message === "hello" // Checks equality of string
	someBoolean === true // Checks if true
	someNumber === 12 // Checks equality of number
	someNumber > 5 // Greater than
	someNumber < 10 // Less than
	someNumber >= 7	// Greater than or equal to
	someNumber <= 8 // Less than or equal to

All of these expressions are comparing the left side to the right. You'll notice we're using `===` not `=`. What's the difference? `=` *assigns* value, where `===` *compares* two values. They are two distinct operations and can not be used interchangeably.



===


## Flip a coin

Let‘s use the Math.randomO function we learned in the last example to build a coin flipper.

	function flip () {
		var coin = Math.random()
		if (coin > 0.5)	{
			return "heads";
		} else {
			return "tails";
		}
	}
	
You may have noticed two new things in this function. First, the word `return`. 

### Returning a value

When we ask a function to **return** something, we are telling it to output a value. We don't always know what we want to do with a value when we are writing a function, or we may want to use the function in a few different ways. Using return allows us to use the output of a function as if it were any other value.

We can even use return to create new variables from a function. We could do the following for instance:

	var flip1 = flip();
	var flip2 = flip();
	var flip3 = flip();
	var flip4 = flip();
	
and we'll be given four brand new variables, each representing independent flips.

### If / else

The second thing you probably noticed was the word `else` after our if block. We can use this to say: if the expression is not true, run this code instead.

	if ( expression ) {
		// if the expression is true, this code will run
	} else {
		// if not, this other code will run
	}

===

## Roll a 4-sided die

Let's change our code to roll a 4-sided die (a.k.a. [tetrahedron](https://en.wikipedia.org/wiki/Tetrahedron)). How do we do this? First I'll show you the simple way:

	function roll () {
		var rollNumber = Math.random() * 4;

		if (roll < 1) {
			return 1;
		} else if (roll < 2) {
			return 2;
		} else if (roll < 3) {
			return 3;
		} else {
			return 4;
		}
	}

Awesome, we just made a 4-way switch using `else if`. Because we multiplied the output of `Math.random()` by 4, we were able to work with more manageable whole numbers. You probably have some idea already, but the `else if` statement is essentially doing this:
	
	function roll () {
		var rollNumber = Math.random() * 4;

		if (roll < 1) {
			return 1;
		} else {
			if (roll < 2) {
				return 2;
			} else {
				if (roll < 3) {
					return 3;
				} else {
					return 4;
				}
			}
		}
	}

This code would work totally fine, but it's a lot uglier than the example above. The `if / else if / else` switch is, in essence, just a nice way of writing a nested `if /else` switch.

A lot of code can be broken down into simpler building blocks, like the above. If you keep breaking things down, they become simpler and simpler pieces, until all you have are 1's and 0's: the most basic switch of all, not so different from `if / else` :)

===

## Put it all together and what do you get?

For this lesson's activity, we're going to put together a little dice rolling app. Here are the requirements:

1. A button that when pressed rolls a six-sided die
2. A div that displays the number rolled in a large font

Hints:

- Use an **event listener** to trigger some roll function 
- Use `document.getElementById()` or `document.querySelector()` to save the button and roll display elements to a variable
- Do a google search for `innerHTML`. Find a good resource and use it with your roll display to change the value

