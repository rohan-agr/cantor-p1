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
- Rather than calling this project directory "p1-stats", let's name it "fibonacci-generator"
- Rather than calling the new file "main.cpp", let's call it fib.py
- Don't complete the "Add Existing Files" Section. We will not be using these files. Once you get to this section, you have completed the necessary sections of this tutorial.

**Pro-tip:** Make sure you are in the right directory before making directories (Documents, Desktop, etc).

At this point, your Cantor directory should look something like this. Use the *tree* command in your terminal to view the files in your working directory.

```console
% tree
.
└── fibonacci-generator
    └── fib.py

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
>>> fibonacci_numbers = [0, 1, 1, 2, 3, 5, 8]
>>> fibonacci_numbers
[0, 1, 1, 2, 3, 5, 8]
```

A list can contain items of different types, but this is rarely the best implementation.

```console?lang=python&prompt=>>>,...
>>> my_list = ['r', 7, "string", 21]
>>> my_list
````

We can *index* into a list using square brackets:


```console?lang=python&prompt=>>>,...
>>> fibonacci_numbers[4]
3
````

You may be wondering why the above command returned 3, even though the fourth number in my list was 2. This is because Python, like many other languages, utilizes *0-based indexing*. We count items in a list starting with the number 0, rather than the number 1:

```console?lang=python&prompt=>>>,...
>>> fibonacci_numbers[0]
0
>>> fibonacci_numbers[1]
1
>>> fibonacci_numbers[2]
1
>>> fibonacci_numbers[3]
2
>>> fibonacci_numbers[4]
3
>>> fibonacci_numbers[5]
5
>>> fibonacci_numbers[6]
8
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

Now that we have a grasp on the fundamental operations that will guide most of our programming, let's take it one step further with our first program. In the above example, we [hard coded](https://www.pcmag.com/encyclopedia/term/hard-coded) the first few numbers in the Fibonacci series. Let's write a program to perform this task and return numbers in the Fibonacci sequence.

### Version Control - Git

A great first step in any programming project is version control. Here, we will use [git](https://www.geeksforgeeks.org/ultimate-guide-git-github/) to save our project as it undergoes various stages in development, and as you begin to work on team projects it is a valuable tool to allow multiple people to work on the same project in a synchronized fashion. Use the below tutorial to get started initializing our repository:

[Version Control Tutorial](https://eecs485staff.github.io/p1-insta485-static/setup_git.html)

<div class="primer-spec-callout info" markdown="1">
**Remember:** We are working in a different directory than the one discussed in the tutorial. Your present working directory should look like this:

```console
% pwd
/Users/rohanagrawal/Documents/cantor/fibonacci-generator
```

And don't forget, our directory already has a file in it - *fib.py*. Don't worry about pushing this file to git yet, we'll do it below.

</div>

```console
% git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	fib.py

nothing added to commit but untracked files present (use "git add" to track)
% git add .
% git commit -m "<Your descriptive commit message>"          
[main (root-commit) 5488d56] <Your descriptive commit message>
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 fib.py
rohanagrawal@MacBook-Pro-791 fibonacci-generator % git push -u origin main
Enumerating objects:
.
.
.
branch 'main' set up to track 'origin/main'.
```

<div class="primer-spec-callout info" markdown="1">
**Pro-tip:** If at any point in the tutorial you need a refresher on how to upload your files to git, the commands in the above terminal window will walk you through it.

```git status``` gives us the "status" of your repository. It will let us know about any files that have been modified since the last commit.

```git add .``` adds "untracked" (modified) files to our commit. To only add certain files, we can "git add" them one-by-one. The "." is a shortcut to add all untracked files.

```git commit -m "<Your descriptive commit message>"``` "commits" the added files. This is like saving a file in your laptop. A more descriptive commit message makes it easier to understand the contents of each commit. This is useful for collaborators to understand code changes, or to be able to quickly switch back to an older version of the project.

```git push -u origin main``` "pushes" (sends) commits to "origin" (the remote repository hosted on github) from "main" (your local git repository). 

Technically, origin and main only refer to our current working branches, but those specifics are outside the scope of this tutorial.

</div>

### Your First Loop

Time to write some code! Open up our folder in your IDE. You should see *fib.py* as one of the files in your file explorer. 

<div class="primer-spec-callout info" markdown="1">
**Pro-tip** VSCode users can navigate to thir working directory in their terminal and type ```code .``` to quickly open the directory in VSCode.
</div>

Our goal is to generate Fibonacci Numbers, a sequence of numbers where each number is the sum of the two preceding. In programming, *loops* are a great tool for performing iterative tasks. Let's copy the code from section 3.2 of the [Python Tutorial](https://docs.python.org/3/tutorial/introduction.html#first-steps-towards-programming) to generate the Fibonacci Numbers that are under 10:

```python
1 a, b = 0, 1
2 while a < 10:
3     print(a)
4     a, b = b, a+b
```

```
Shall I compare thee to a summer’s day?
Thou art more lovely and more temperate:
Rough winds do shake the darling buds of May,
And summer’s lease hath all too short a date:
Sometime too hot the eye of heaven shines,
And often is his gold complexion dimm’d;
And every fair from fair sometime declines,
By chance or nature’s changing course untrimm’d;
But thy eternal summer shall not fade
Nor lose possession of that fair thou owest;
Nor shall Death brag thou wander’st in his shade,
When in eternal lines to time thou growest:
So long as men can breathe or eyes can see,
So long lives this and this gives life to thee.
```


Once we save (Cmd-S, Ctrl-S, or File->Save), we should be able to run our program from the command line:

```console
% python3 fib.py
0
1
1
2
3
5
8
```

Let's try to understand this code. We first initialized variables *a* and *b* to the values 0 and 1, respectively. (In  practice, such uninformative variable names are bad practice. But for our simple use-case here they will work). These variables now represent the first two entries in the Fibonacci Sequence. 

```while``` - while begins our loop. Lines 3 and 4 are inside this loop. Python uses indentation to nest together different lines of code. Here, any lines with a single indent under line 2 will become part of the while loop. To write code outside of this loop, all we need to to is un-indent.

Loops use *conditions* to determine whether they should run again. Otherwise, they would just run forever in an *infinite loop* . Try replacing line 2 with ```while True:``` and run your code again with ```python3 fib.py``` (remember to save). You should get the following error:

```console
Traceback (most recent call last):
  File "/Users/rohanagrawal/Documents/cantor/fibonacci-generator/fib.py", line 3, in <module>
    print(a)
ValueError: Exceeds the limit (4300 digits) for integer string conversion; use sys.set_int_max_str_digits() to increase the limit
```

So the code didn't run in an infinite loop - but it came close. Our error message tells us that we generated Fibonacci Numbers exceeding 4300 digits! This demonstrates the importance of bounding our loops. Let's revert line 2 to it's previous state and save our code.

<div class="primer-spec-callout info" markdown="1">
Now may be a good time to push to git! Take a look at the version
</div>



## Acknowledgements

The setup tutorials linked above are all course materials provided by the EECS staff here at the University of Michigan. All credit goes to them in the production of these materials.

Some code in Fibonacci Project taken from https://docs.python.org/3/tutorial/index.html . All credit goes to the authors of this tutorial.

Project Specificiation authored by Rohan Agrawal.
