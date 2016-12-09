# CSS: Cascading Stylesheets

We've already learned how to lay out our pages and do a few pretty nice things in Bootstrap, and we've learned a little bit about classes. Sometimes we'll want to do a lot more with the design of our site that Bootstrap alone does not alone. That's where CSS comes into play.

This week we're going to learn:

- basic CSS *syntax*
- How to control spacing & layout with the box model
- How to change the colors of your type and background
- How to center your content
- Block and inline elements

# Syntax

Every CSS rule needs three things, an element `selector`, a `property`, and a `value`. Here's is a basic blueprint to go off of:

	selector {
		property: value;
	}

And here's a simple example:

	body {
		background-color: yellow;
		color: white;
	}
	
This CSS will set the backgound of the `<body>` element in your HTML to yellow, and set the color of all the text to white. Unadvisable.

## Breaking it down

There are a few simple rules things to remember about CSS.

A `selector` corresponds directly with one or many HTML elements.

A property describes something you want to change, and a value describes what you're setting that property to.

Everything between an openeing bracket `{` and closing bracket `}` will be applied to the element(s) targeted by the selector.

Always put a colon `:` after any property name, and a semicolon `;` after any value you've set.

# Colors

One simple thing you may try to do is add a splash of color to your site. There are basically two properties you should know, and you've already used them in this lesson: `color` and `background-color`.

## Hex and rgb

Above, you used some color names to define what colors you wanted, yellow and white. But if you want some really *fresh* colors, you'll want to use **hex codes** or **rgb colors**. RGB... why not RYB, this is not what I learned in 4th grade art! Welcome to madness. On a digital display, red, green, and blue mix to make colors.

RGB takes three values from 0-255, and hex takes 6 digits from 0-f on a special scale called **hexidecimal**. It goes from 0-9 then a-f. If it makes it easier, you can think of a-f as 10-16. The first two digits in a hex code represent red, the second two are green, and the final two are blue

Here are some nice HEX and RGB colors for reference.

	/* black */
		hex: #000000
		rgb: rgb(0,0,0)
		
	/* white */
		hex: #ffffff
		rgb: rgb(255,255,255)
		
	/* light gray */ 
		hex: #dddddd
		rgb: rgb(221,221,221)
		
	/* bright blue */
		hex: #00aacc
		rgb: rgb(0,170,204)
		
	/* loud orange */
		hex: #eeaa00
		rgb: rgb(238,170,0)



# Classes

You may remember using classes in the bootstrap lesson to change the layout of your page. Any class you set in your HTML can be accessed with a CSS selector. Say you've made a `div` to place a some content in, and you want it to have some special properties. You might give it a class like "content-block", like this:

	<div class="content-block">
		<h2>The truth about your cat</p>
		<p>When your cat is mad at you, it may be that they value food more than your friendship.</p>
	</div>

You can select that class in your CSS with a dot `.` like this:

	.content-block { ... }

And if you want to change something about that `h2`, but not *every* second-level heading, you can do that too:

	.content-block h2 { ... }

The space between `.content-block` and `h2` signifies that the `h2` is **nested** within the `.content-block` div. If you wanted to change something about the paragraph, it would work just the same way. You can even select a class within a class the same exact way.

## IDs

As well as classes, you can set an ID in HTML. The difference is that classes can be used throughout your website, and ID's can be used only once. In HTML you'll set an ID like so:

	<div id="someIdName">
	
and in CSS you'll access it with a `#` symbol:

	#someIdName { ... } 

# Fonts and sizing units

You can set the font of any element using the `font-family` property. It's often good to not only set one font, but a backup as well in case the first font does not work or load properly.

	font-family: helvetica, sans-serif;

You can also set the `font-size` of an element. There are two units you should be aware of: `px` and `em`. `px` is an absolute size, and `em` is relative. If you set the font-size in pixels, it will always be rendered in that size.

If you set it with `em` it will also take into account the font-size properties of parent elements, so you can increase the font-size of the entire document by setting the `body` font size. It is best practice to use `em` for font size in most cases, it allows for greater overall flexibility.

For some context, here are the default font-size values in `em`s of a few elements:

	p: 1em
	h1: 2em
	h2: 1.5em
	h3: 1.17em

# Spacing

Something you'll definitely want to tweak is spacing. We have 4 main properties we use that affect the spacing of any element. We'll talk about the first 3 right now, `border`, `padding`, `margin`

## Border

If you imagine every element as a box, the edge of that box would be the border. If you don't set a width to the border, then it's just the point where the inside of the element ends and the outside begins.

To set a border, you need three things, `border-width`, `border-style`, and `border-color`. Or you can use the shorthand:

	border: 1px solid #ccc;
	
This combines all three properties into one.

## Padding

Padding is the space on the inside of the box. Between the edge of the element and your content, you'll want a little space so your text isn't crowded. Padding can be set on each side individually, or all together. Here are a few ways to set padding.

Same padding on all sides:

	padding: 20px;
	
20px on the top and bottom, 10px on the left and right:

	padding: 20px 10px;
	
Different padding on all four sides:

	padding-top: 10px;
	padding-right: 20px;
	padding-bottom: 15px;
	padding-left: 4px;
	
Or:

	padding: 10px 20px 15px 4px;

## Margin

Margin is the space on the outside of an element. This gives your element breathing room between itself and other elements. It can be written much like padding. All the following are valid:

	margin: 10px;
	margin: 20px 10px;
	margin: 20px 10px 30px 10px;
	margin-top: 30px;
	

# Setting Width and Height

Before we set the width of an element explicitly, we should make the distinction between three types of elements: block, inline, and inline-block.

**Block elements** will take up the full width of their container unless otherwise set. So if the parent width is half of the page, a block element will fill that. Even if the text in the element does not fill the element, the outer edges of its box will stretch to the edge. Even if the width is explicitly set to less than that of its container, it will still push all other elements below.

**Inline elements** will act much like text, and take up the amount of space that their content occupies. Unlike block elements, inline elements can be placed side-by-side. A link or `<a>` tag is an example of an inline element. Width, height, and vertical padding or margin do not apply to inline elements. Horizontal padding and margin will still work however.

**Inline-block elements** will be sized based on their content, like inline elements, and they can be placed side by side. However, all other rules that apply to block elements apply to inline-block elements, so padding, margin, width, and height can be set as normal. This is how images behave.

We can even change an element's type with the CSS `display` property.

	display: inline-block;

Often, we don't really want to set an element's width explicitly, but we want it to have some space for the content to live. Buttons are a good example of this. We can set the element as `inline-block`, and give it a bit of padding. 

## Setting Width and height

We can, however, set width with the `width` propertiy in CSS. You can set this as a pixel width:

	width: 100px;
	
Even better a lot of the time is setting a `max-width`:

	max-width: 400px;
	
This allows your element to collapse as the screen gets smaller.
	
You'll many times want to set a width based on the size of the container. You can do that too:

	width: 50%;
	
You can even combine a max-width and a percentage width for some lovely results.

It's pretty rare that you'll want to explicitly set `height`, but you can do that as well. You can set height in pixels just like width, but a percentage height often doesn't work at all, a horrible truth about CSS.

# Centering all the Things

There are actually *many* horrible truths about CSS. One is that there are a *whole loaf* of ways to center things, and some of them are just weird. Here are two ways.

## Margin: 0 auto

If your element is a block element *and* you've set a width explicitly, you can center it by applying the style:

	margin: 0 auto;
	
Note that this sets the top and bottom margin to 0, and the left and right margin to auto. If you want a little more vertical margin, you can always do this:

	margin: 10px auto;
	
## Text-align

If it's inline or inline block, you'll have to set a style on the *parent* element. So if you have a button that you want to center, and its parent element has a class of `button-container`, you can center that button like so:

	.button-container {
		text-align: center;
	}

This is also how you will center text. You can use it on headings, paragraphs, etc. if you just want to center the text.