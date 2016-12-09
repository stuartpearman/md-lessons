# HTML

In this lesson we're going to be setting up a local server and learning the basics of HTML. 

# Setup a Local Web Server

Github pages hosts your site on a server. When you're still building the site, you'll want to use a **local server** to create a similar experience on your computer.

The server we'll be using is called `live-server` and it requires a software called `npm`. npm stands for Node Package Manager, and it is the bridge to a lot of amazing tools that are used all the tim in development.

To download npm, you'll need to go to the Node website and...

Once you've downloaded this, run `node -v` in the terminal. If it tells you a version number, then you've successfully downloaded node. Do the same for npm: `npm -v`. Again, if it gives you a version, you've successfully downloaded and installed npm.

## Installing Live Server

Now from the terminal run `npm install -g live-server`. This installs live-server *globally*, which means you'll be able to use it in any directory from your terminal.

To run the server, enter `live-server` into the terminal. It should open the browser showing the contents of your new file, but if not, you can navigate to `localhost:8080` in your browser window. You'll see this localhost commonly when using similar local servers.


# HTML Tags

Open up Atom

type in html shortcut

	<!DOCTYPE html>
	<html>
	<head>
		<title></title>
	</head>
	<body>

	</body>
	</html>
	
What you see here is HTML code. HTML uses **tags** to open and close elements. An opening tag looks like this:

	<tagname>
	
And A closing tag will have a slash before the name of the tag, like this:

	</tagname>

Anything that comes *after* an opening tag and *before* a closing tag is nested inside of that tag. So in the example above, the `title` tag is nested within the `head`.

	<head>
		<title></title>
	</head>
	
And we use indentation to keep track of nested tags. It's much easier to understand how the above example is nested than this: 

	<head><title></title></head>
	

# Setting up your document
	
If you followed the slide before, you already set up your document. It's not the most exciting thing, but it's important to understand what you've just done.
	
## Doctype

This line: 

	<!DOCTYPE html>
		
tells the browser that the document should be read as HTML. This is a special tag, and does not need to be closed like the other tags that we're using.

## Html

The opening and closing `html` tags indicate the start and end of any HTML in the document. Everything within these tags will be read and interpreted by the browser.

## Head

The head is where we'll put information that needs to be loaded *before* loading the rest of page.

	<head>
		<meta charset="UTF-8">
		<title>Your Title</title>
	</head>

We have the title here, as well as the **character set** that should be used, which is UTF-8. Declaring the character set allows the browser to output alphanumeric characters and symbols from the English language and many others.
	
## Body

The body is where we will put all of our HTML elements that will appear on the page.

	<body>
	
	</body>
	
# Basic Content Tags

## Headings

	h1, h2, h3, h4
	
## The Paragraph

	<p></p>

## Lists	
	
### Unordered List

	<ul>
		<li>Apple</li>
		<li>Pear</li>
		<li>Banana</li>
	</ul>

### Ordered List
	
	<ol>
		<li>Preheat the oven to 350 degrees</li>
		<li>Mix together the eggs, butter, sugar, brown sugar, and vanilla</li>
		<li>Mix the remaining dry ingredients in a separate bowl</li>
		<li>Combine and add the chocolate chips, bam!</li>
	</ol>
	
# Links

Links are a bit different than the other tags we've learned so far. They require an attribute to work:

	<a href="http://google.com">google</a>
	


# Images
	
images are similar to the `<a>` or `anchor` tag, but instead of taking the user to another destination, it will plop in image from the given url directly into the document.

	<img alt="" src="">
	

	
# Divs

The `div` is basically the building block element in HTML. It doesn't have a preferred way of being used, like paragraphs, lists, etc. It can be used for pretty much anything, and is often the element of choice for visual structure on a page.

	<div></div>
	
# Other Elements

We've covered only a very small number of elements here, but there are *tons* more -- tables, forms, header and footer tags, you name it. We'll be sprinkling these in throughout the class, but if you'd like to learn more [Link to a resource]