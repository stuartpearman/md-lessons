# Data in Javascript

Start this lesson with the following structure:

	script.js
	index.html
	

## Arrays

An **array** in javascript, or any other language, is just a list. You can make a list of strings, a list of numbers, or mix it up, it doesn't matter. Here's an example of an array in javascript:

	var people = ["Kiesha", "Pablo", "Angela", "Tony"]

The only syntax you need to remember is that a list is enclosed in square brackets, and each item is separated by a comma. Once an item is in an array, you can access it with a numeric id starting with 0.
	
	people[0] // => Kiesha
	people[1] // => Pablo
	people[2] // => Angela
	people[3] // => Tony
	
### Pick your team
	
This is great so far, but without any context it's just more to memorize. So let's make a baseball team using our array and some handy functions.

	var team = [];  // creates a new array with nothing in it
	
	function pickPlayer(name) {
		team.push(name); // adds player to the end of the team array
	}
	
	pickPlayer("Kiesha");
	pickPlayer("Pablo");
	pickPlayer("Jocinda");
	
Javascript has a bunch of functions like the `push()` one that interact with arrays. Assume there's a function for what you want to do. To find this one, I typed "add item to end of array javascript" into google. There are functions that will remove items, rearrange them, etc.

## Loops

Our baseball team is pretty cool, but we want a way for our players to be displayed. A **loop** allows us to basically perform the same action on multiple different items all at once. There are a bunch of different types of loops, but the two most basic forms are the **for loop** and **while loop**. We're going to focus on the for loop, but if you are interested, feel free to browse the [W3Schools definition of the while loop]()

### For loop

A for loop basically creates a variable, and increases (or decreases) its value each time a block of code is run. When the variable reaches a designated stopping point, the loop is complete. Here is what it looks like:

	for (var i = 0; i < 9; i++) {
		// this will run 9 times
	}
	
Let's break it down.

	for ( arguments ) { code to be executed }
	
Above we have the basic structure, similar to how you would set up a function. The arguments in this case determine how many times out loop will run, and what our variable will be. Let's take a look what goes in between the two parentheses.

	var i = 0;
	
we're creating a variable called `i` (you can call it whatever you want). This will be our counter variable, and we can use it in our code block to do all sorts of things.

	i < 9;
	
The code between the brackets `{ ... }` will run as long as `i` is less than `9`.

	i++
	
This is the same as saying `i = i + 1`. We are increasing the value of `i` by `1` each time the loop is run.

#### Lets loop through our players

Let's continue building our baseball team and log the names of our players to the console.

	for (var i = 0; i < team.length; i++) {
		console.log(team[i]);
	}
	
Nice.

## Your project

Expand on what you learned:

- Make another array called `undrafted` for neighorhood kids who aren't on your team
- Modify your `pickPlayer` function to pick kids up from the `undrafted` array and put them into yor `team` array
	- for this you'll want to look up the `push` and `splice` javascript functions
- Loop through both arrays and output them to HTML using `document.querySelector`
	- **Challenge**: use `createElement` and `appendChild` to do this




