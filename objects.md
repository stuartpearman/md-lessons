# Objects

## What is an Object?

Objects are used when you want to make something with a lot of properties. Let's say we're making a card game called Battle Goats. It's war, and you're assembling an army of goats to battle a rival goat nation. Each goat has a stat for attack, attack type, mental strength, and a special ability. Here's a card for a normal goat, Helga:

	{   
		name: "Helga"
		attack: 4
		attackType: "Shovel Hooves"
		mentalStrength: 6
		specialAbility: "Trench Digging -- increases your armies defenses by 2"
	}

Each stat is represented by a **key** and a **value**. In the attack stat, `attack` is the key, `4` is the value.

If you were going to build this card game, you wouldn't have just one card. You would probably have a whole deck:

	var goats = [
		{
			name: "Helga",
			attackType: "Shovel Hooves"
		},
		{
			name: "Bruce"
			attackType: "Spitting Grass"
		},
		{
			name: "Fabian",
			attackType: "Aquatic Sneak"
		}
	]
	
We often want to make a lot of different objects with similar properties like this. This is a very common way of organizing data.
	
Think back to the baseball team. Instead of making a list of names, you could make a list of *players*, where every stat affects the way they shape the game: Kiesha could be a power hitter, Pete could be super fast, and Pablo could be an all-around beast.

## What are all these dots for?

Once we have an object, we can use `dot notation` to access different properties in the object.

	goats[0].name === "Helga"
	goats[2].attackType === "Aquatic Sneak"

We've actually been using dot notation all along. Most of the variables we interact with in javascript actually *are* objects to some extent. Even a simple string:

	"hello".length === 5

And HTML tags have a *ton* of properties when you open them up and take a look.

	var content = document.querySelector('.someElement');
	content.addEventListener("click", function () { ... });
	content.style.padding;
	content.nodeName;
	
And the best part is you can actually change most of them, and you can achieve a lot of awesome effects by just changing a few of properties.

Basically, **objects are everywhere**. If you can think of something, you can probably make it as an object.

### Methods

We can also give objects their own functions. You'll sometimes hear these referred to as **methods**, this is just a common word for function and you'll hear it used in many different programming languages. Say we want to add the trench digging function to our goat Helga so she can strengthen her army's defenses. It might look something like this.

	helga.digTrench = function () {
		army.defense += 2;
	}
	

## Constructor functions

This is cool, but it's more common that we'll be creating objects in our app than through directly editing javascript code. We'll want to be able to create a function that takes information from our user, and turns it into an object that we can use later. When we're done, we should be able to create a goat by passing some options into our new function:

	
	createGoat("Helga", "Aquatic Sneak");
	
So let's get started. First, we'll want our goat array set up:

	var goats = [];

And we'll have a function that takes two parameters:

	function createGoat (name, ability) { ... }

Cool, with these parameters we'll generate an object and add it to the `goats` array. We'll also generate some skills. To make sure our game is balanced, we'll have these be out of 10 skill points:

	function createGoat (name, ability) {
		var attack = Math.floor(Math.random * 10);   // creates a random number 0-10
		var brainpower = 10 - attack;                // spends remaining points out of 10
		
		goats.push({
			name: name,
			attackType: ability,
			attack: attack,
			mentalStrength: brainpower
		});
	}

An important distinction is that in `name: name`, the first `name` in the pair is the **key**, and the second is the **value**. We're creating the property `name` in our object, and assigning it a value of whatever our first parameter is when we call the function. So if we call `createGoat("Helga", "Aquatic Sneak")`, the object will look something like this:

	{
		name: "Helga",
		attackType: "Aquatic Sneak",
		attack: 7,
		mentalStrength: 3
	}

## Let's make some cards

Here is your project. Make a few goats with the constructor function you just created, and output their information onto your website. Some tips:

- use a for loop to iterate through each goat
- use dot notation to access individual properties of each goat
- use createElement and appendChild functions to create HTML elements for each property. Here is the [W3Schools resource for appendChild](http://www.w3schools.com/jsref/met_node_appendchild.asp)



