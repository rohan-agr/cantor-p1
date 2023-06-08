---
layout: spec
latex: true
mermaid: true
---

Cantor P1: Fibonacci
======================

## Introduction

Welcome to Cantor! This first project will get you started on your programming journey. 
For those of you who already have some programming experience, feel free to skim through this tutorial 
to brush up on any development concepts.

### Some Notes

Before we get started, here are some notes about how Cantor projects are structured:

- Our projects are process-oriented. In some of our projects, specifications will lead you towards a “sub-optimal” approach. Typically, these are geared towards teaching an important concept that will enhance your understanding of the underlying ideas behind fundamental programming concepts. In some cases, they teach strategies that will help you become a more effective coder as you undertake more complex projects, but may seem redundant now. In any case, feel free to reach out to your mentors to ask questions, but focus on the journey, not the destination.

- Throughout the project specifications, you’ll find links like this one. Click the links! Even if you have an understanding of the concepts being described, these links will typically help you get a more thorough understanding of the subject matter (any may provide a hint on the next step of the project).

- Some steps may seem ambiguous. This is intentional. We encourage you to think critically and use all the tools in your toolbox to problem-solve. So don’t be afraid to use google, stack overflow, etc to explore solutions. We will typically link documentation to any technology you are using in the project specification.

- Don’t use ChatGPT to generate code. When working on large projects, it is a tool that can help you be a more efficient and effective programmer.  Used as a starting point for further research, it can be a valuable learning resource. But for the scope of the smaller projects we write, asking it to write code can only stunt your learning and hinder your progress later on. And anyway, it’s unreliable. You’ll find better code through a Google search anyway.

### Overview

Let’s get started.

Generating Fibonacci Numbers in Python.

In this tutorial we will:

- Introduce the command line
- Install some useful tools to our devices
- Set up an IDE (Interactive Development Environment)
- Write a simple function in Python
- Use version control to store code changes


### Learning Goals
- [ ] Command Line
- [ ] Interacting with the development environment
- [ ] Version control using git
- [ ] Basic Python (control flow, iteration, etc.)


## Command Line Tools

Let's install some command line tools and get to know the command line. Linux users will have these tools by default.

### macOS Setup
[macOS Setup Tutorial](https://eecs485staff.github.io/p1-insta485-static/setup_macos.html)

### Windows Setup
[Windows Setup Tutorial](https://eecs485staff.github.io/p1-insta485-static/setup_wsl.html)

### Command Line

Now that we’ve set all of that up, let’s learn about the CLI (Command Line Interface)

[CLI Tutorial](https://eecs280staff.github.io/tutorials/cli.html)

## Dev Environment

Next, let’s set up our development environment (most Cantor members use VS Code, however you are free to choose whichever you prefer).

- [VS Code (recommended)](https://eecs280staff.github.io/tutorials/setup_vscode.html)
- [XCode](https://eecs280staff.github.io/tutorials/setup_xcode.html)
- [Visual Studio](https://eecs280staff.github.io/tutorials/setup_visualstudio.html)

Some modifications to the tutorial "Create a project" section to serve the needs of this project:
- Rather than naming the directory "eecs280", let's name it "cantor"
- Rather than calling this project directory "p1-stats", let's name it "PROGRAM-NAME"
- Rather than calling the new file "main.cpp", let's call it FILENAME
- Don't complete the "Add Existing Files" Section. We will not be using these files. Once you get to this section, you have completed the necessary sections of this tutorial.

**Pro-tip:** Make sure you are in the right directory before making directories (Documents, Desktop, etc).

At this point, your Cantor directory should look something like this. Use the *tree* command in your terminal to view the files in your working directory.

```console
% tree
.
└── cantor-calc
    └── calc.py

2 directories, 1 file
```


## The Python Interpreter

That was a lot of setup. Let's start coding.

[Python Tutorial] (https://docs.python.org/3/tutorial/index.html)


The Python interpreter allows us to experiment with simple code in a very basic environment. We'll use it as we go through the Python tutorial and pick up some beginner programming concepts. Start it up in your terminal with the *python3* command:

```console
% python3
Python 3.11.2 (main, Feb 16 2023, 03:15:23) [Clang 14.0.0 (clang-1400.0.29.202)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

You can exit the interpeter at any time by pressing *Ctrl-D* or entering the command *exit()*. We'll stay in the interpreter for now.

Let's turn to chapter 3 in the Python tutorial. (Feel free to take a look at the first two chapters, but don't worry if some concepts feel new.) Read through the chapter and complete the exercises, and feel free to use the interpreter to follow along.

Once you're ready, let's run through some examples:

### 3.1.1 - Numbers
- We wish to use Python to compute 12345 + 65432. Try running the command in the interpreter. Your output should look like this:

```console?lang=python&prompt=>>>,...
>>> 12345 + 65432
77777
```

As mentioned in the tutorial, this number is of the type *int*. We'll dive into the types later, but int is the most commonly used type to describe integer numbers. Let's take this number and divide it by 63:

```console?lang=python&prompt=>>>,...
>>> 77777 / 63
1234.5555555555557
```

Division in Python always returns a *float*, a more precise data type when dealing with non-integer numbers. 

### 3.1.2 - Strings

The *String* data type allows us to store and manipulate sequences of characters. Run the following code, replacing the text inside the quotations with your own name:

```console?lang=python&prompt=>>>,...
>>> first_name = "Rohan"
```

You won't see any output. This makes sense - we didn't ask the interpreter to give us anything. We initialized a *variable*. A variable is simply a way to refer to a certain piece of data. The interpreter now associates *first_name* with your first name! We can verify this with the *print()* command:

```console?lang=python&prompt=>>>,...
>>> print(first_name)
Rohan
```

*print()* is an example of a function. More on this later.

Let's save our last name in a similar variable.

```console?lang=python&prompt=>>>,...
>>> last_name = "Agrawal"
```

Let's put these together. In programming, gluing strings together in this fashion is called *concatenating*.

```console?lang=python&prompt=>>>,...
>>> first_name + last_name
'RohanAgrawal'
```

That's a good start, but we should've included a space in between the two names. Let's try again:

```console?lang=python&prompt=>>>,...
>>> first_name + " " + last_name
'Rohan Agrawal'
```

And to wrap it all up, we can save our full name in a *full_name* variable and print it to the console:

```console?lang=python&prompt=>>>,...
>>> full_name = first_name + " " + last_name
>>> print(full_name)
Rohan Agrawal
```

### 3.1.3 - Lists

Lists are an example of a *compound* data type, which groups together separate values.

```console?lang=python&prompt=>>>,...
>>> fibonacci_numbers = [1, 1, 2, 3, 5, 8, 13]
>>> fibonacci_numbers
[1, 1, 2, 3, 5, 8, 13]
```

A list can contain items of different types, but this is rarely the best implementation.

```console?lang=python&prompt=>>>,...
>>> my_list = ['r', 7, "string", 21]
>>> my_list
````

We can *index* into a list using square brackets:


```console?lang=python&prompt=>>>,...
>>> fibonacci_numbers[4]
5
````

You may be wondering why the above command returned 5, even though the fourth number in my list was 3. This is because Python, like many other languages, utilizes *0-based indexing*. We count items in a list starting with the number 0, rather than the number 1:

```console?lang=python&prompt=>>>,...
>>> fibonacci_numbers[0]
1
>>> fibonacci_numbers[1]
1
>>> fibonacci_numbers[2]
2
>>> fibonacci_numbers[3]
3
>>> fibonacci_numbers[4]
5
>>> fibonacci_numbers[5]
8
>>> fibonacci_numbers[6]
13
````

With any data type, we must be careful not to index "out of bounds", or ask for a value outside the scope of the list. 


```console?lang=python&prompt=>>>,...
>>> fibonacci_numbers[7]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
>>> len(fibonacci_numbers)
7
```

*Using 0-based indexing, the 7th index in this list would refer to the eight item. This list only has stores seven values, so attempting to read index 7 results in an error*.

## Fibonacci Numbers

Now that we have a grasp on the fundamental operations that will guide most of our programming, let's take it one step further with our first program. In the above example, we [hard coded](https://www.pcmag.com/encyclopedia/term/hard-coded) the first few numbers in the Fibonacci series. Let's write a [function](https://www.w3schools.com/python/python_functions.asp#:~:text=A%20function%20is%20a%20block,return%20data%20as%20a%20result.) In this 

### Version Control - Git

A great first step in any programming project is version control. Here, we will use [git](https://www.geeksforgeeks.org/ultimate-guide-git-github/) to save our project as it undergoes various stages in development, and as you begin to work on team projects it is a valuable tool to allow multiple people to work on the same project in a synchronized fashion. Use the below tutorial to get started initializing our repository:

[Version Control Tutorial](https://eecs485staff.github.io/p1-insta485-static/setup_git.html)

<div class="primer-spec-callout info" markdown="1">
**Remember:** We are working in a different directory than the one discussed in the tutorial. Your present working directory should look like this:

```console
% pwd
/Users/rohanagrawal/Documents/Cantor
```

</div>

<div class="primer-spec-callout info" markdown="1">
**Hint:** Try looking up this documentation...
</div>

## Acknowledgements

The setup tutorials linked above are all course materials provided by the EECS staff here at the University of Michigan. All credit goes to them in the production of these materials.
