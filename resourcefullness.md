# Resourcefullness, Bootstrap, and Classes

# Reading Documentation

Reading documentation is one of the most important skills of web development. Knowing a lot of things is much less valuable than having resourcefulness in understanding new information. But resourcefullness is something that *must be learned* for most people.

Here's what you can expect to learn in this lesson.



# Create Your Project Files

Make a new folder in your MI449 folder entitled "project 2". In this folder you'll make the following files:

## index.html

Setup the document by making the `<html>`, `<head>`, and `<body>` tags and a title. You can use the `html` + `tab` shortcut to do this in one fell swoop.

Add this code in the body of the document:

	<div class="container">
		<h1>Some Title</h1>
		<p>Some content</p>
	</div>
	
This may not look like much yet, but we're about to add Bootstrap. When we do, your project is going to start to look kinda sweet.

# Linking Bootstrap to your Project

Go to [getbootstrap.com/getting-started](getbootstrap.com/getting-started)

Press the big `download` button! unpack the .zip file it gives you, and copy the folder into your project.

If you refresh the page, you won't see any differences yet. This is because you need to **link** bootstrap to your `index.html` file.

In the head of your document, add the following:

	<link href="..." >

Right at the bottom, before closing the `<body>` tags, add the following two lines:

	<script src="..."></script>
	
in the head of the document

The first one is the bootstrap *stylesheet*, and the second is bootstrap's javascript file.

Linking files allows to add all sorts of lovely functionality to our website, add in special themes and styling, and keep our files shorter and thus more readable. CSS makes our website pretty, and javascript  brings it to life.

# Bootstrap CSS

The bootstrap documentation is split into 3 different sections. The first is bootstrap CSS. This contains special classes we use to adjust our site's layout
		
# Classes

Classes in HTML are used to describe an HTML element. In making websites, there will be many times when you want to create elements that look the same in several different places. Instead of writing specific styles for each element, you can use classes to create a consistent look and feel.

Bootstrap uses CSS to create reusable styles that help make our websites look good and consistent.

# Bootstrap Javascript

Bootstrap also has a Javascript section. This is full of interactive functionality that you can add to items

Add the following to your code:

	<a class="btn btn-primary" data-toggle="modal" data-target="#myModal"></a>
	
This will create a button that, when clicked, toggles the modal with the id `#myModal`. BUT before we create the modal, there will be nothing to toggle. The `data-target` does not yet exist. Let's make it:
    		
    <div class="modal fade" id="myModal">
  		<div class="modal-dialog">
 			<div class="modal-content">
      			<div class="modal-body">
    				Write your content in here!
    			</div
    		</div>
    	</div>
    </div>

### Indentation

It is common for divs to be nested multiple levels deep. It may be a little intimidating at first. There are several bootstrap components that are similarly nested, and if you don't indent your code, it will be much harder to read later on if you want to make changes.

# Bootstrap Components

The third section of the Boostrap docs is Components. Many of the components combine javascript and CSS to create an element that can be used for a specific purpose. In the project this week, you'll need to make use of all three of bootsrap's documentation sections.


# Read the Docs

You now have a bit of a grasp on how to use bootstrap and all the resources at your fingertips to go even further. Here's the challenge for this lesson:

- Create a 3 column layout
	- in small screens, unfold the columns to occupy the full width of the screen
- Create a jumbotron section in your webpage
- Add a button which, when pressed, opens a modal dialog
- Adjust your modal to have a modal-header and modal-body sections

