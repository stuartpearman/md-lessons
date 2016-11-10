# What We'll Be Covering

This project is going to be a good amount of setup, and we're going to be covering a lot of the nitty gritty aspects of your development workflow. You may be bored, you will probably run into a few errors, but at the end of it, you will have a website hosted online!

- Installing a Terminal program, Git, and Atom
- Navigating files in the command line
- Creating a simple HTML file
- Using Git for version control
- Hosting a website online

# Your First Tool

The **command line** or **terminal** is a *lovely* tool that you'll be using a lot in this class. If you've never used your terminal before, then get ready to party.

If you are running on a **Mac** or **Ubuntu**, then congrats! You have a suitable terminal already installed. Find the program called terminal and open it up.

If you are on **Windows**, then download [Git Bash](https://git-scm.com/download/win), go through the install, and run the program.

# Using the Command Line

If you've never used your Terminal before, it may not look like much, but your terminal allows you to run *commands* on your computer. Just like *Finder* on Mac or *Explorer* on Windows, you can use the terminal to navigate the files and folders on your computer. Lets try it! Type `pwd` into the terminal window and press `Enter`. The terminal will *print* a line that looks something like this:

	/Users/yourname

You just told the terminal to **Print Working Directory**, that's what `pwd` stands for. What does that mean? Here are a few **vocab** words that should help:

- **Print - ** output some information
- **Directory -** The same as a folder
- **Working directory - ** The directory you're currently in

So print working directory or `pwd` is basically like asking your terminal "what folder am I working in?" You could even think of it as asking "where am I?"

Another useful "where am I" command is `ls`, try entering that into your terminal. You'll probably see something like this if your on a Mac:

	Applications  Documents  Downloads  Library  filename.ext

You can think of `ls` as the *list* command, and that's exactly what it does. What you're seeing is the list of **files** and **directories** in your working directory. This is super useful for understanding where you are in your *file system*.

## Code

	ls # list files in the current directory
	pwd # print path to working directory

# Navigating Files

So we know where we are, *neat*. But we're not going to be able to do much if we stay in one place. This is where the `cd` command comes in handy.  `cd` stands for **Change Directory** and it does just that. If you enter the name of a directory after `cd`, you'll make *that* directory your working directory. The command should look something like this:

	cd somedirectory

Now pick a directory and `cd` into it. Remember: you can use `pwd` and `ls` to see *where you are*, and what *files* and *directories* are in your working directory. After you've changed directories, use `pwd` to verify that your *path* has changed.

If you want to move backwards a directory, to the directory that *encloses* your current directory, enter this into your terminal window:

	cd ..

You'll use `..` to signify the enclosing directory, and `.` to signify your current directory. 

Lets go back and break the `cd` command into two parts. First we have the command itself `cd` -- then you have the directory's name `somedirectory`. This is called a **parameter**, and many terminal commands require them. You'll see parameters in most any programming language you could encounter, and they allow commands like `cd` to be flexible. We'll learn more about them later.

So what happens if we have a directory called "cat pictures", will `cd cat pictures` work? *No*, because the space indicates that the *parameter* is done. What you *could* enter instead is `cd cat\ pictures`, the backslash indicating that the space *should* be included in the parameter. If this bothers you, a dash is often a good alternative, `cd cat-pictures` works just fine.

## Code

	cd somedirectory    # works fine
	cd some-directory   # works fine
	cd some\ directory  # works fine, don't forget the backslash!
	cd some directory   # will not work
	
	.          # the current directory
	..         # the enclosing directory
	../..      # 2 levels back
	../../..   # 3 levels back
	

# Atom and Git

We're now able to navigate our files, it's a great day so far, but now we're going to dive into two more tools, **Atom** and **Git**.

## Atom

**Atom** is our text editor of choice, it has a lot of nice themes and features for writing code in whatever way you like best.

[Download the Atom text editor](https://atom.io/)

If you get stumped, you can find more detailed instructions for installing Atom at [this resource](http://flight-manual.atom.io/).

## Git

**Git** is a tool that manages *version control* in your coding projects, either projects you're working on individually, or with a group of developers.

### Mac Installation

Copy this line into your terminal:

	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

It will start an installation for Homebrew, a *package manager* for Mac (it may take a while). Homebrew makes it easy install and manage a lot of tools we'll be using in this class, including Git.

Once this is done, run `brew install git` from your terminal.

### Ubuntu

Run `sudo apt-get install git` from the terminal.

### Windows

You already installed Git earlier when you ran the install for Git Bash, nothing to do here!

## Github

**Github** is a website where you can find the majority of modern open source projects on the web. It uses Git to create *Repositories* where you can track, share, and host your code on the web. You'll need to [create an account on Github](https://github.com/) so we can view, and grade your code projects in this class.

# Your First Project

For your first project, we're going to be:

- Creating an HTML file in Atom
- Making a repository in GitHub
- Pushing our code up to GitHub
- Hosting our project online

## Organization

Pick somewhere on your computer to keep all your project files for the class. name it something you'll remember, like `MI449`. *Organizing files thoughtfully* is a huge part of web development, and doing so from the start will save you a lot of time.

Within your new folder, create a *second* folder and name it `project1`. 

*Note: you can name your folder whatever you'd like, just make sure you are using a system that works well for you.*

# Using Atom

Atom is a text editor with a vast array of extensions, themes, and features you can fiddle with and tweak to your liking. There are useful shortcuts for common patterns you might run across in code, and flexibility in formatting so that you can write code to your preference. I recommend exploring some of the many packages and themes available at [atom.io](http://atom.io).

## Creating an HTML File

What we are going to be doing, however, is creating a new file to use in our first project. In the top bar go to `File > Add Project Folder` and select the `project1` folder you just created.

You should see a sidebar pop up with the name of your folder. When this folder has files and directories within it, you'll be able to browse everything inside of it. This is called the *file system* or *file tree*.

Type in `Cmd + N` on Mac, or `Ctrl + N` on windows to create a new file. Name this file *index.html*.

You can now write whatever you want in this file. When you save, Atom will save all your changes to the file. And just like that you're writing code! Go ahead and write "Hello World" into the file, or mabe a joke, something about your pets, whatever you want -- it really doesn't matter for this exercise.

## Check The Results

Now navigate to your folder in *Finder* or *Explorer*. If you double click your new file, it should open in a browser. If not, you can right click and select a browser to open your file.

You should now see the contents of your file in the browser window. You've just made a *sweet* website.

# Create a Git Repository

From your Github account, look for a green button that says "New Repository". It will bring you to a page where you fill out a number of options for creating a Github Repository. Give your repository the name MI449-project1. No need to change anything else on this page. Click "Create Repository". 

## Git Remotes

Congrats! You just created your first repository on Github. There are no files in your repository right now, but there are a few key things to notice.

You may see a url that looks something like this :a

	https://github.com/yourusername/MI449-project.git

That's a special url called a **remote**. Git uses a remote to *push* and *pull* code to and from your repository. You'll be using it to connect this repository to a directory on your computer.

Navigate to your `project1` folder in the terminal using the commands we learned earlier. Remember, you can verify you're in the correct directory by using `pwd`. 

## Initializing a Repository

From there enter `git init`. This command makes your directory into a Git Repository! Pretty exciting, but it still isn't connected with your repository on Github. So let's add the *remote* to your repository

## Adding Your Remote

Remember the url from earlier? That's the remote you need to link the existing repository with your brand new one. You'll do this by running the following in your terminal

	git remote add origin your-remote-url  # replace your-remote-url with your github remote

If we break this command down, we are *adding* the *git remote* to the repository, and assigning the remote the name *origin*.

## Viewing Remotes

To view the remotes that are available in a git repository, you can run:

	git remote -v

It should output your url for the remote *origin*. It'll show the same remote twice, one url to *push* changes to github, and one to *fetch* changes from github -- in this case they'll be identical.

## Code

	git init   # initializes your directory as a Git Repository
	git remote add origin some-url   # adds the remote at some-url to your repository with the name origin
	git remote -v  # view the remotes in a repository

# Push Your Code

Pushing your code up is actually a 3-step process. Before going through the steps one-by-one, there is a useful command you should know.

	git status

`git status` will essentially show you the status of your code -- whether your code is ahead of what's on github, whether files have been modified, created or deleted, and more. If you are curious, you can refer to the [git status documentation](https://git-scm.com/docs/git-status). Go ahead and run `git status` in your terminal.

It should show that one file is *untracked*, the `index.html` file you just created. It will also prompt you to `add` the file. You can do this by running the following command:

	git add -A

If you run a `git status` again, you'll see `new file: index.html` under `changes to be committed`. You can *commit* this file by running:

	git commit -m 'first commit'

`-m` is a flag short for *message*, and "first commit" is your *commit message*. These messages are used to give context to the changes you make, and can be very helpful when working with other developers, or if you need to go back and look at previous *commits*.

If your commit worked properly, `git status` will show that there is `nothing to commit`. At this point you'll be able to *push* your code up to Github.

	git push origin master

You may be prompted to login with your github username and password. If all goes well, you will have just successfully pushed to GitHub! To check that it worked, navigate to your repository on GitHub. If it was successful, you'll see your index.html file right there, pretty cool!

Lets break this down. That command *pushes* your code to the remote *origin*. Within your repository there are also **branches**. By default you are working in the branch *master*, but many teams will use many different branches for many different things. We'll be creating a branch in just a minute to host our file on the web.

## Why All Three Commands?

Before we move on you might be wondering, what is the difference between git add, git commit, and git push? A good analogy would be loading up a truck for a shipment.

First, you need to sort through which boxes need to go on the truck and ready them for it arrives. Next, you need to load up the boxes into the truck before the driver can take them away. When everything is ready, you're good to send the driver off to wherever the shipment needs to go.

You can think of `git add`, `git commit`, and `git push`in this same way. Selecting your files, commiting them for delivery, and shipping them off to Github.

## Code

	git status   # Check the git status (tracked, untracked, modified, etc.) of your files
	git add -A   # Add all changes to your next commit
	git commit -m 'message about commit'   # ready a group of changes to be pushed to Github
	git push origin master   # Push code to your repository at the remote origin and the branch master

# Deploy Your Project

It can actually be fairly simple to deploy a static site, there are tons of different options for doing so. The one we're going to use is called *GitHub Pages*. In GitHub Pages, if you make a *gh-pages* branch in your repository, it will host your porject at a special url -- *username*.github.io/*repository-name* -- where *username* is your GitHub username, and *repository-name* is the name of your repository.

Lets try it! Make sure you're still in your project folder, and enter this command into your terminal:

	git push origin master:gh-pages

It's the same as the command you entered earlier, but this time you are pushing from your *master* branch to the *gh-pages* branch. Now go to *username*.github.io/*repository-name*. If your push worked, you should see the contents of your file in the browser window.

## Diagnosing a Problem

When you run into a problem in Git, running a `git status` is often a good place to start. Sometimes you'll forget to commit your files before pushing, or you won't have added your files before committing. Much like `ls` and `pwd`, `git status` is a nice *where am I* command while you're going through the steps.

If you get an error message, it is always helpful to read what it says. Sometimes they are very cryptic, but if you don't understand what it's trying to tell you, copy the error into Google. Chances are someone has already had the same problem you're having. You'll find a lot of good information on [stackoverflow.com](http://stackoverflow.com), as well as GitHub, and different blogs throughout the web.

# Look Ma, I Made It!

That's right, we're all done! What you learned today may become second nature to you, and it may not. Learning to code can definitely be frustrating, but it can be fun and rewarding too. You're now free to go on to the next lesson.
