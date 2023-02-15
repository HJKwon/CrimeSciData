--- 
title: "Modelling Criminological Data"
author: "Eon Kim and Joanna Hill (based on material developed with Juanjo Medina and Reka Solymosi)"
date: "2023-02-15"
site: bookdown::bookdown_site
documentclass: book
biblio-style: apalike
link-citations: yes
description: "This is the course material for Modelling Criminological Data."
---

# Preface {-}

This is the lab note you will be using during the labs for the module *Modelling Criminological Data*. Every week you will have to use these materials during the lab sessions. The idea is that you read this lab note and try to run the code we provide in your own machine. Try not to just 'copy and paste' the codes in the lab note. Try to understand them. Along the way you will see you have to complete a series of exercises to check that you are correctly understanding the materials that we introduce. We hope you find these materials useful. This lab note is a work in process, so if you have any suggestions/find some errors, please don't hesitate to get in touch by submitting an issue to the [GitHub repository](https://github.com/eonk/mcd_book) or via email on eon.kim@manchester.ac.uk.

<!--chapter:end:index.Rmd-->

# A first lesson about R

## Install R & RStudio
We recommend that you use your own laptops for this course. If you have not already, then please download and install R and RStudio onto your laptops. 
- click [here](https://www.youtube.com/watch?v=eD07NznguA4) for instructions using Windows or
- [here](https://www.youtube.com/watch?v=cX532N_XLIs&list=PLqzoL9-eJTNDw71zWePXyHx3_cm_fMP8S) for instructions using a Mac. If you are using a Mac it would be convenient that you use the most up to date version of OS or, at least one compatible with the most recent version of R. Read [this](https://www.howtogeek.com/350906/how-to-check-which-version-of-macos-youre-using/) if you want to check how to do that.

If you prefer, you can always use any of the PCs in the computer cluster. All of them already have the software installed. 

## Open up and explore RStudio
In this session we will focus in developing basic familiarity with R Studio. You can use R without using R Studio, but R Studio is an app that makes it easier to work with R. R Studio automatically runs R in the background. We will be interacting with R in this course unit via R Studio.

![](imgs/rstudio.PNG){width=80%}

When you first open R Studio, you will see (as in the image above) that there are 3 main panes. The bigger one to your left is the console. If you read the text in the console you will see that R Studio is indeed opening R and you can see what version of R you are running. Depending on whether you are using the cluster machines or your own installation this may vary, but don't worry too much about it. 

![](imgs/openscript.PNG){width=80%}

The view in R Studio is structured so that you have 4 open panes in a regular session. Click in the *File* drop down Menu, select *New File*, then *R Script*. You will now see the 4 window areas in display. On each of these areas you can shift between different views and panels. You can also use your mouse to re-size the different windows if that is convenient.

![](imgs/the4views.PNG){width=80%}

Look for example at the bottom right area. Within this area you can see that there are different tabs, which are associated with different views. You can see in the tabs in this section that there are different views available: *Files*, *Plots*, *Packages*, *Help*, and *Viewer*. The **Files** allow you to see the files in the physical directory that is currently set up as your working environment. You can think of it like a window in Windows Explorer that lets you see the content of a folder. 

In the **plots** panel you will see any data visualisations or graphical displays of data that you produce. We haven't yet produced any, so it is empty at the moment. If you click in **packages** you will see the packages that are currently available in your installation. What is a "package" in this context?

Packages are modules that expand what R can do. There are thousands of them. A few come pre-installed when you do a basic R installation. Others you pick and install yourself. This term we will introduce some important packages we recommend and you should install.

The other really useful panel in this part of the screen is the **Help** viewer. Here you can access the documentation for the various packages that make up R. Learning how to use this documentation will be essential if you want to be able to get the most from R.

In the diagonally opposite corner, the top left, you should now have an open script window. The **script** is where you write your programming code, the instructions you send to your computer. A script is nothing but a text file where you can write. Unlike other programs for data analysis you may have used in the past (Excel, SPSS), you need to interact with R by means of writing down instructions and asking R to evaluate those instructions. R is an *interpreted* programming language: you write instructions (code) that the R engine has to interpret in order to do something. And all the instructions we write can and should be saved in a script, so that you can return later to what you did.

One of the key advantages of doing data analysis this way is that you are producing a written record of every step you take in the analysis. The challenge though is that you need to learn this language in order to be able to use it. That will be the main focus of this course, teaching you to write R code for data analysis purposes. 

As with any language the more you practice it, the easier it will become. More often than not you will be doing a lot of cutting and pasting from chunks of code we will give you. But we will also expect you to develop a basic understanding of what these bits of code do. It is a bit like cooking. At first you will just follow recipes as they are given to you, but as you become more comfortable in your "kitchen" you will feel more comfortable experimenting.

The advantage of doing analysis this way is that once you have written your instructions and saved them in a file, you will be able to share it with others and run it every time you want in a matter of seconds. This creates a *reproducible* record of your analysis: something that your collaborators or someone else anywhere (including your future self, the one that will have forgotten how to do the stuff) could run and get the same results than you did at some point earlier. This makes science more transparent and transparency brings with it many advantages. For example, it makes your research more trustworthy. Don't underestimate how critical this is. **Reproducibility** is becoming a key criteria to assess good quality research. And tools like R allow us to enhance it. You may want to read more about reproducible research [here](http://theconversation.com/the-science-reproducibility-crisis-and-what-can-be-done-about-it-74198).

## Customising the RStudio look
RStudio allows you to customise the way it looks. For example, working with white backgrounds is not generally a good idea if you care about your eyesight. If you don't want to end up with dry eyes not only it is good you follow the 20-20-20 rule (every 20 minutes look for 20 seconds to an object located 20 feet away from you), but it may also be a good idea to use more eye friendly screen displays. 

Click in the *Tools* menu and select *Global options*. This will open up a pop up window with various options. Select *Appearance*. In this section you can change the font type and size, but also the kind of theme background that R will use in the various windows. I suffer from poor sight, so I often increase the font type. I also use the *Tomorrow Night Bright* theme to prevent my eyes to go too dry from the effort of reading a lightened screen, but you may prefer a different one. You can preview them and then click apply to select the one you like. This will not change your results or analysis. This is just something you may want to do in order to make things look better and healthier for your.

## Getting organised: R Projects
Whenever you do analysis you will be working with a variety of files. You may have an Excel data set (or some other type of data set file, like csv for example), a Microsoft Word file where you are writing down the essay with your results, but also a script with all the programming code you have been using. R needs to know where all these files sit in your computer. Often you will get error messages because you are expecting R to find one of these files in the wrong location. **It is absolutely critical thus that you understand how your computer organises and store files.** Please watch the video below to understand the basics of file management and file paths: 

[Windows users](https://www.top-windows-tutorials.com/file-paths/)

[MAC users](https://www.switchingtomac.com/tutorials/osx/5-ways-to-reveal-the-path-of-a-file-on-macos/)

The best way to avoid problems with file management in R is using what RStudio calls **R Projects**.

Technically, a RStudio project is just a directory (a folder) with the name of the project, and a few files and folders created by R Studio for internal purposes. This is where you should hold your scripts, your data, and reports. You can manage this folder with your own operating system manager (eg., Windows Explorer) or through the R Studio file manager (that you access in the bottom right corner set of windows in R Studio).

When a project is reopened, R Studio opens every file and data view that was open when the project was closed last time around. Let's learn how to create a project. Go to the *File* drown menu and select *New Project*.

![](imgs/newproject.png){width=80%}

That will open a dialog box where you ask to specify what kind of directory you want to create. Select new working directory in this dialog box.

<img src="https://user-images.githubusercontent.com/98951792/215291834-4b1ef9b9-7423-4f1f-8df3-316c3b520875.png">

Now you get another dialog box (at least you have an older version of R Studio) where you have to specify what kind of project you want to create. Select the first option *New Project*.

<img src="https://user-images.githubusercontent.com/98951792/215292002-901f94d9-ac91-472d-8e08-0367dedb8a7b.png">

Finally, you get to select a name for your project (in the image below I use the code for this course unit, but you can use any sensible name you prefer) and you will need to specify the folder/directory in which to place this directory. If you are using a cluster machine use the P: drive, otherwise select what you prefer in your laptop (preferably, to avoid problems later, not your desktop in Windows machines).

<img src="https://user-images.githubusercontent.com/98951792/215292026-e843c5d4-8c9a-433a-bcc8-009bf46d8de9.png">

With simple projects a single script file and a data file is all you may have. But with more complex projects, things can rapidly become messy. So you may want to create subdirectories within this project folder. I typically use the following structure in my own work to put all files of a certain type in the same subdirectory:

+ *Scripts and code*: Here I put all the text files with my analytic code, including rmarkdown files which is something we will introduce much later in the semester.

+ *Source data*: Here I put the original data. I tend not to touch this once I have obtained the original data.

+ *Documentation*: This is the subdirectory where I place all the data documentation (e.g., codebooks, questionnaires, etc.)

+ *Modified data*: All analysis involve doing transformations and changing things in the original data files. You don't want to mess up the original data files, so what you should do is create new data files as soon as you start changing your source data. I go so far as to place them in a different subdirectory.

+ *Literature*: Analysis is all about answering research questions. There is always a literature about these questions. I place the relevant literature for the analytic project I am conducting in this subdirectory.

+ *Reports and write up*: Here is where I file all the reports and data visualisations that are associated with my analysis.

You can create these subdirectories using Windows Explorer or the Files window in R Studio. 

## Functions: Talk to your computer
So far we hace covered an introduction to the main interface you will be using and talk about RStudio projects. In this unit you will be using this interface and using and creating files within your RStudio projects to produce analysis based on programming code that you will need to write using the R language.

Let's write some very simple code using R to talk to your computer. First open a new script within the project you just created. Type the following instructions in the script window. After you are done click in the top right corner where it says *Run* (if you prefer quick shortcuts, you can select the text and then press Ctrl +  Enter):


```r
print("I love stats")
```

```
## [1] "I love stats"
```

Congratulations!!! You just run your first line of R code! 👏👏

In these handouts you will see grayed boxes with bit of code on it. You can cut and paste this code into your script window and run the code from it to reproduce our results. As we go along we will be covering new bits of code. 

Sometimes in these documents you will see on them the results of running the code, what you see printed in your console or in your plot viewer. The results will appear enclosed in a box as above.

The R languages uses **functions** to tell the computer what to do. In the R *language* functions are the *verbs*. You can think of functions as predefined commands that somebody has already programmed into R and tell R what to do. Here you learnt your first R function: *print*. All this function does is to ask R to print whatever it is you want in the main console (see the window in the bottom left corner). 

In R, you can pass a number of **arguments** to any function. These arguments control what the function will do in each case. The arguments appear between brackets. Here we passed the text "I love stats" as an argument. Once you execute the program, by clicking on *Run*, the R engine sends this to the CPU of your machine in the form of binary code and this produces a result. In this case we see that result printed in the main console.

Every R function admits different kind of arguments. Learning R involves not only learning different functions but also learning what are the valid arguments you can pass to each function. 

![](imgs/consoleresults.PNG){width=80%}

As indicated above, the window in the bottom left corner is the main **console**.You will see that the words "I love stats" appear printed there.  If rather than using R Studio you were working directly from R, that's all you would get: the main console where you can write code interactively (rather than all the different windows you see in R Studio). You can write your code directly in the main console and execute it line by line in an interactive fashion. However, we will be running code from scripts, so that you get used to the idea of properly documenting all the steps you take. 

## More on packages
Before we described packages as elements that add the functionality of R. What most packages do is they introduce new functions that allow you to ask R to do new different things.

Anybody can write a package, so consequently R packages vary on quality and complexity. You can find packages in different places, as well, from official repositories (which means they have passed a minimum of quality control), something called GitHub (a webpage where software developers post work in progress), to personal webpages (danger danger!). In early 2017 we passed the 10,000 mark just in the main official repository, so the number of things that can be done with R grows exponentially every day as people keep adding new packages.

When you install R you only install a set of basic packages, not the full 10,000 plus. So if you want to use any of these added packages that are not part of the basic installation you need to first install them. You can see what packages are availabe in your local install by looking at the *packages* tab in the bottom right corner panel. Click there and check. We are going to install a package that is not there so that you see how the installation is done. 

![](imgs/packages.PNG){width=80%}

If you just installed R in your laptop you will see a shortish list of packages that constitute the basic installation of R. If you are using one of the machines in the computer cluster this list is a bit longer, because we asked IT to install some of the most commonly used packages. But knowing how to install packages is pretty essential, since you will want to do it very often.

We are going to install a package called "cowsay" to demonstrate the process. In the Packages panel there is an *Install* menu that would open a dialog box and allows you to install packages. Instead we are going to use code to do this. Just cut and paste the code below into your script and then run it:


```r
install.packages("cowsay")
```

Here we are introducing a new function "install.packages" and what we have passed as an argument is the name of the package that we want to install. This is how we install a package *that is available in the official CRAN repository*. Given that you are connecting to an online repository you will need an internet connection every time you want to install a package. [CRAN](https://cran.r-project.org/) is an official repository that has a collection of R packages that meet a minimum set of quality criteria. It's a fairly safe place to get packages from. If we wanted to install a package from somewhere else we would have to adapt the code. Later this semester you will see how we install packages from GitHub.

This line of code (as it is currently written) will install this package in a personal library that will be located in your P: drive if you are using a cluster machine. If you are using a Windows machine this code will place this package within a personal library in your Documents folder. Once you install a package, it will remain in the machine/location where you install it until you physically delete it.

How do you find out what a package does? You look at the relevant documentation. In the Packages window scroll down until you find the new package we installed listed. Here you will see the name of the package (cowsay), a brief description of what the program is about, and the version you have installed (an indication that a package is a good package is that it has gone through several versions, that means that someone is making sure the package gets regular updates and improvements). The version I have for cowsay is 0.7.0. Yours may be older or newer. It doesn't matter much at this point. 

Click in the name *cowsay*. You will see that R Studio has now brought you to the Help tab. Here is where you find the help files for this package, including all the available documentation.

Every beginner in R will find these help files a bit confusing. But after a while, their format and structure will begin to make sense to you. Click where it says *User guides, package vignettes, and other documentation*. Documentation in R has become much better since people started to write **vignettes** for their packages. They are little tutorials that explain with examples what each package does. Click in the *cowsay::cowsay_tutorial* that you see listed here. What you will find there is an html file that gives you a detailed tutorial on this package. You don't need to read it now, but remember that this is one way to find help when using R. 

Let's try to use some of the functions of this package. We will use the "say" function:


```r
say("I love stats")
```

You will get an error message telling you that this function could not be found. What happened?? This will be the first of many error messages you will get. An error message is the computer way of telling you that your instructions are somehow incomplete or problematic and, thus, is unable to do what you ask. It is frustrating to get these messages and a critical skill for you this semester will be to overcome that frustration and try to understand why the computer cannot do what you ask. Finding out the source of the error and solving it is what these labs are all about. There is nothing wrong with getting errors. The problem is if you give up and let your frustration get the best of you.

So why are we getting this error? Installing a package is only the first step. The next step, when you want to use it in a given session, is to **load** it. 

Think of it as a pair of shoes. You buy it once, but you have to take them from your closet and put them on when you want to use them. Same with packages, you only install once, but need to load it from your library every time you want to use it -within a given session (once loaded it will remain loaded until you finish your session).

To see what packages you currently have **loaded** in your session, you use the `search()` function (you do not need to pass it any arguments in this case).


```r
search()
```

```
## [1] ".GlobalEnv"        "package:stats"     "package:graphics" 
## [4] "package:grDevices" "package:utils"     "package:datasets" 
## [7] "package:methods"   "Autoloads"         "package:base"
```

If you run this code, you will see that `cowsay` is not in the list of loaded packages. Therefore your computer cannot use any of the functions associated with it until you load it. To load a package we use the **library** function. So if we want to load the new package we installed in our machine we would need to use the following code:


```r
library("cowsay")
```

Run the `search` function again. You will see now this package is listed. So now we can try using the function "say" again.


```r
say("I love stats")
```

```
## 
##  -------------- 
## I love stats 
##  --------------
##     \
##       \
##         \
##             |\___/|
##           ==) ^Y^ (==
##             \  ^  /
##              )=*=(
##             /     \
##             |     |
##            /| | | |\
##            \| | |_|/\
##       jgs  //_// ___/
##                \_)
## 
```

You get a random animal in the console repeating the text we passed as an argument. If we like a different animal we could pass an argument to select it. So, say, we want to have cow rather than a random animal, then we would pass the following arguments to our function.


```r
say("I love stats", "cow")
```

```
## 
##  ----- 
## I love stats 
##  ------ 
##     \   ^__^ 
##      \  (oo)\ ________ 
##         (__)\         )\ /\ 
##              ||------w|
##              ||      ||
```

This is an important feature of arguments in functions. We said how different functions admits different arguments. Here by specifying `cow` the function is printing that particular animal. But who is it that when we didn't specify a particular kind of animal we still got a result? That happened because functions always have default arguments that are necessary for them to run and that you do not have to make explicit. Default arguments are implicit and do not have to be typed. The `say` function has a default argument `random` which will print a random character or animal. It is only when you want to change the default that you need to make an alternative animal explicit.

Remember, you only have to install a package that is not already installed once. But if you want to use it in a given session you will have to load it within that session using the `library` function. Once you load it within a session the package will remain loaded until you terminate your session (for example, by closing R Studio). Do not forget this.

## Objects: creating an object
We have seen how the first argument that the "say" function takes is the text that we want to convert into speech for our given animal. We could write the text directly into the function (as we did above), but now we are going to do something different. We are going to create an object to store the text.

An **object**? What do I mean? In the same way that everything you do in R you do with functions (your verbs), everything that exist in R is an object. You can think of objects as boxes where you put stuff. In this case we are going to create an object called *my_text* and inside this object we are going to store the text "I love stats". How do you do this? We will use the code below:


```r
my_text <- "I love stats."
```

This bit of code is simply telling R we are creating a new object with the assigned name ("my_text"). We are creating a box with such name and inside this box we are placing a bit of text ("I love stats"). The arrow `<-` you see is the **assignment operator**. This is an important part of the R language that tells R what we are including inside the object in question.

Run the code. Look now at the *Environment* window in the right top corner. We see that this object is now listed there. You can think of the Environment as a warehouse where you put stuff in, your different objects. Is there a limit to this environment? Yes, your RAM. R works on your RAM, so you need to be aware that if you use very large objects you will need loads of RAM. But that won't be a problem you will encounter in this course unit.

Once we put things into these boxes or objects we can use them as arguments in our functions. See the example below:


```r
say(my_text, "cow")
```

```
## 
##  ----- 
## I love stats. 
##  ------ 
##     \   ^__^ 
##      \  (oo)\ ________ 
##         (__)\         )\ /\ 
##              ||------w|
##              ||      ||
```

## More on objects 
Now that we have covered some of the preliminaries we can move to talk about data. In Excel you are used to see your data in a spreadsheet format. If you need some recap
, you should review some of the materials that is designed for UG students in Criminology. This [chapter](https://maczokni.github.io/MSCD_labs/week1.html#data-variables-and-observations) will be helpful to have a better understanding of the notion of a data set, levels of measurement, and tidy data.

R is considerably more flexible than Excel. Most of the work we do here will use data sets or **dataframes** as they are called in R. But as you have seen earlier you can have *objects* other than data frames in R. These objects can relate to external files or simple textual information ("I love stats"). This flexibility is a big asset because among other things it allow us to break down data frames or the results from doing analysis on them to its constitutive parts (this will become clearer as we go along).

Technically R is an *Object Oriented language*. Object-oriented programming (OOP) is a programming language model organized around objects rather than "actions" and data rather than logic.

As we have seen earlier, to create an object you have to give it a name, and then use the assignment operator (the `<-` symbol) to assign it some value. 

For example, if we want to create an object that we name "x", and we want it to represent the value of 5, we write:


```r
x <- 5
```

We are simply telling R to create a **numeric object**, called `x`, with one element (5) or of length 1. It is numeric because we are putting a number inside this object. The length is 1 because it only has one element on it, the number 5.

You can see the content of the object `x` in the main console either by using the print function we used earlier or by auto-printing, that is, just typing the name of the object and running that as code:


```r
x
```

```
## [1] 5
```

When writing expressions in R is very important you understand that **R is case sensitive**. This could drive you nuts if you are not careful. More often than not if you write an expression asking R to do something and R returns an error message, chances are that you have used lower case when upper case was needed (or vice-versa). So always check for the right spelling. For example, see what happens if I use a capital 'X':


```r
X
```

```
## Error in eval(expr, envir, enclos): object 'X' not found
```

You will get the following message: `"Error in eval(expr, envir, enclos): object 'X' not found"`. R is telling us that `X` does not exist. There isn't an object `X` (upper case), but there is an object `x` (lower case). Error messages in R are pretty good at telling you exactly what went wrong.

Remember computers are very literal. They are like dogs. You can tell a dog "sit" and if it has been trained it will sit. But if you tell a dog "would you be so kind as to relax a bit and lay down in the sofa?", it won't have a clue what you are saying and will stare at you like you have gone mad. Error messages are computers ways of telling us "I really want to help you but I don't really understand what you mean" (never take them personal, computers don't hate you).

When you get an error message or implausible results, you want to look back at your code to figure out what is the problem. This process is called **debugging**. There are some proper systematic ways to write code that facilitate debugging, but we won't get into that here. R is very good with automatic error handling at the levels we'll be using it at. Very often the solution will simply involve correcting the spelling.

A handy tip is to cut and paste the error message into Google and find a solution. If anybody had given me a penny for every time I had to do that myself, I would be Bill Gates by now. You’re probably not the first person to make your mistake, after all, and someone on the internet has surely already found a solution to your issue. People make mistakes all the time. It's how we learn. Don't get frustrated, don't get stuck. Instead look for a solution. These days we have Google. We didn't back in the day. Now you have the answer to your frustration within quick reach. Use it to your advantage.

## Naming conventions for objects in R
You may have noticed the various names I have used to designate objects (`my_1st_vector`, `the_smiths`, etc.). You can use almost any names you want for your objects. Objects in R can have names of any length consisting of letters, numbers, underscores ("_") or the period (".") and should begin with a letter. In addition, when naming objects you need to remember: 

+ *Some names are forbidden*. These include words such as FALSE and TRUE, logical operators, and programming words like Inf, for, else, break, function, and words for special entities like NA and NaN.

+ *You want to use names that do not correspond to a specific function.* We have seen, for example, that there is a function called `print()`, you don't want to call an object "print" to avoid conflicts. To avoid this use nouns instead of verbs for naming your variables and data.

+ *You don't want them to be too long* (or you will regret it every time you need to use that object in your analysis: your fingers will bleed from typing).

+ *You want to make them as intuitive to interpret as possible.*

+ *You want to follow consistent naming conventions.* [R users are terrible about this](http://journal.r-project.org/archive/2012-2/RJournal_2012-2_Baaaath.pdf). But we could make it better if we all aim to follow similar conventions. In these handouts you will see I follow the `underscore_separated` convention -see [here](https://style.tidyverse.org/syntax.html) for details.

It is also important to remember that R will always treat numbers as numbers. This sounds straightforward, but actually it is important to note. We can name our variables almost anything. EXCEPT they cannot be numbers. Numbers are **protected** by R. 1 will always mean 1. 

If you want, give it a try. Try to create a variable called 12 and assign it the value "twelve". As we did last week, we can assign something a meaning by using the "<-" characters.


```r
12 <- "twelve"
```

```
## Error in 12 <- "twelve": invalid (do_set) left-hand side to assignment
```

You get an error!

## R object types: vectors

In R there are different kind of objects. We will start with **vectors**. 

What is a vector? A vector is simply a set of elements *of the same class* (typically these classes are: character, numeric, integer, or logical -as in True/False). Vectors are the basic data structure in R. 

Typically you will use the `c()` function (c stands for *concatenate*) to create vectors. The code below exemplifies how to create vectors of different classes (numeric, logical, character, etc.). Notice how the listed elements (to simplify there are two elements in each vector below) are separated by commas `,`:


```r
my_1st_vector <- c(0.5, 0.6) #creates a numeric vector with two elements
my_2nd_vector <- c(1L, 2L) #creates an integer vector ("L" suffix specifies an integer type)
my_3rd_vector <- c(TRUE, FALSE) #creates a logical vector
my_4th_vector <- c(T, F) #creates a logical vector using abbreviations of True and False, but you should avoid this formulation an instead use the full word.
my_5th_vector <- c("a", "b", "c") #creates a character vector
my_6th_vector <- c(1+0i, 2+4i) #creates a complex vector (we won't really use in this class)
```

Cut and paste this code into your script and run it. You will see how all these vectors are added to your global environment and stored there.

The beauty of an object oriented statistical language like R is that one you have these objects you can use them as **inputs** in functions, use them in operations, or to create other objects. This makes R very flexible. See some examples below:


```r
class(my_1st_vector) #a function to figure out the class of the vector
```

```
## [1] "numeric"
```

```r
length(my_1st_vector) #a function to figure out the length of the vector
```

```
## [1] 2
```

```r
my_1st_vector + 2 #Add a constant to each element of the vector
```

```
## [1] 2.5 2.6
```

```r
my_7th_vector <- my_1st_vector + 1 #Create a new vector that contains the elements of my1stvector plus a constant of 1
my_1st_vector + my_7th_vector #Adds the two vectors and auto-print the results (note how the sum was done)
```

```
## [1] 2.0 2.2
```

As indicated earlier, when you create objects you will place them in your working memory or workspace. Each R session will be associated to a workspace (called "global environment" in R Studio). In R Studio you can visualise the objects you have created during a session in the **Global Environment** screen. But if you want to produce a list of what's there you can use the `ls()` function (the results you get my differ from the ones below depending on what you actually have in your global environment).


```r
ls() #list all objects in your global environment
```

```
## [1] "my_1st_vector" "my_2nd_vector" "my_3rd_vector" "my_4th_vector"
## [5] "my_5th_vector" "my_6th_vector" "my_7th_vector" "my_text"      
## [9] "x"
```

If you want to delete a particular object you can do so using the `rm()` function.


```r
rm(x) #remove x from your global environment
```

It is also possibly to remove all objects at once:


```r
rm(list = ls()) #remove all objects from your global environment
```

If you mix in a vector elements that are of a different class (for example numerical and logical), R will **coerce** to the minimum common denominator, so that every element in the vector is of the same class. So, for example, if you input a number and a character, it will coerce the vector to be a character vector -see the example below and notice the use of the `class()` function to identify the class of an object. 


```r
my_8th_vector <- c(0.5, "a")
class(my_8th_vector) #The class() function will tell us the class of the vector
```

```
## [1] "character"
```

## R object types: Data frame

Ok, so now that you understand some of the basic types of objects you can use in R, let's start taking about data frames. One of the most common objects you will work with in this course are **data frames**. Data frames can be created with the `data.frame()` function. 

Data frames are *multiple vectors* of possibly different classes (e.g., numeric, factors, character), but of the same length (e.g., all vectors, or variables, have the same number of rows). This may sound a bit too technical but it is simply a way of saying that a data frame is what in other programmes for data analysis gets represented as data sets, the tabular spreadsheets you have seen when using Excel.

![](imgs/df.PNG){width=80%}

Let's create a data frame with two variables:


```r
#We create a dataframe called mydata_1 with two variables, an integer vector called foo and a logical vector called bar
mydata_1 <- data.frame(foo = 1:4, bar = c(T,T,F,F))
mydata_1
```

```
##   foo   bar
## 1   1  TRUE
## 2   2  TRUE
## 3   3 FALSE
## 4   4 FALSE
```

Or alternatively for the same result:


```r
x <- 1:4
y <- c(T, T, F, F)
mydata_2 <- data.frame (foo = x, bar = y)
mydata_2
```

```
##   foo   bar
## 1   1  TRUE
## 2   2  TRUE
## 3   3 FALSE
## 4   4 FALSE
```

As you can see in R, as in any other language, there are multiple ways of saying the same thing. Programmers aim to produce code that has been optimised: it is short and quick. It is likely that as you develop your R skills you find increasingly more efficient ways of asking R how to do things. What this means too is that when you go for help, from your peers or us, we may teach you slightly different ways of getting the right result. As long as you get the right result that's what at this point really matters.

These are silly toy examples of data frames. In this course, we will use real data. Next week we will learn in greater detail how to read data into R. But you should also know that R comes with pre-installed data sets. Some packages in fact are nothing but collections of data frames.

Let's have a look at some of them. We are going to look at some data that are part of the *fivethirtyeight* package. This package contains data sets and code behind the stories in [this particular online newspaper](http://fivethirtyeight.com/). This package is not part of the base installation of R, so you will need to install it first. I won't give you the code for it. See if you can figure it out by looking at previous examples.

Done? Ok, now we are going to look at the data sets that are included in this package. Remember first we have to **install** and **load** the package if we want to use it:


```r
library(fivethirtyeight)
```

```
## Some larger datasets need to be installed separately, like senators and
## house_district_forecast. To install these, we recommend you install the
## fivethirtyeightdata package by running:
## install.packages('fivethirtyeightdata', repos =
## 'https://fivethirtyeightdata.github.io/drat/', type = 'source')
```

```r
data(package="fivethirtyeight") #This function will return all the data frames that are available in the named package.
```

Notice that this package has some data sets that relate to stories covered in this journal that had a criminological angle. Let's look for example at the hate_crimes data set. How do you that? First we have to load the data frame into our global environment. To do so use the following code:


```r
data("hate_crimes")
```

This function will search among all the *loaded* packages and locate the "hate_crimes" data set. Notice that it now appears in the global environment, although it also says "promise" next to it. To see the data in full you need to do something to it first. So let's do that.

Every object in R can have **attributes**. These are: names; dimensions (for matrices and arrays: number of rows and columns) and dimensions names; class of object (numeric, character, etc.); length (for a vector this will be the number of elements in the vector); and other user-defined. You can access the attributes of an object using the `attributes()` function. Let's query R for the attributes of this data frame.


```r
attributes(hate_crimes)
```

```
## $row.names
##  [1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25
## [26] 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 47 48 49 50
## [51] 51
## 
## $class
## [1] "tbl_df"     "tbl"        "data.frame"
## 
## $names
##  [1] "state"                       "state_abbrev"               
##  [3] "median_house_inc"            "share_unemp_seas"           
##  [5] "share_pop_metro"             "share_pop_hs"               
##  [7] "share_non_citizen"           "share_white_poverty"        
##  [9] "gini_index"                  "share_non_white"            
## [11] "share_vote_trump"            "hate_crimes_per_100k_splc"  
## [13] "avg_hatecrimes_per_100k_fbi"
```

These results printed in the may console may not make too much sense to you at this point. We will return to this next week, so do not worry. 

Go now to the global environment panel and left click on the data frame "hate_crimes". This will open the data viewer in the top left section of R Studio. What you get there is a spreadsheet with 12 variables and 51 observations. Each variable in this case is providing you with information (demographics, voting patterns, and hate crime) about each of the US states.  

![](imgs/dataview.PNG){width=80%}

## Exploring data
Ok, let's now have a quick look at the data. There are so many different ways of producing summary stats for data stored in R that is impossible to cover them all! We will just introduce a few functions that you may find useful for summarising data. Before we do any of that it is important you get a sense for what is available in this data set. Go to the help tab and in the search box input the name of the data frame, this will take you to the documentation for this data frame. Here you can see a list of the available variables.

![](imgs/codebook.PNG){width=80%}

Let's start with the *mean*. This function takes as an argument the numeric variable for which you want to obtain the mean. Because of the way that R works you cannot simply put the name of the variable you have to tell R as well in which data frame is that variable located. To do that you write the name of the data frame, the dollar sign(`$`), and then the name of the variable you want to summarise. If you want to obtain the mean of the variable that gives us the proportion of people that voted for Donald Trump you can use the following expression:


```r
mean(hate_crimes$share_vote_trump)
```

```
## [1] 0.49
```

This code is saying look inside the "hate_crimes" dataset object and find the "share_vote_trump" variable, then print the mean. The `$` is used when you want to find a particular component of an object. In the case of dataframes that component typically will be one of the vectors (variables). But we will see other uses for other kind of objects as we move through the course.

Another function you may want to use with numeric variables is `summary()`:


```r
summary(hate_crimes$share_vote_trump)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   0.040   0.415   0.490   0.490   0.575   0.700
```

This gives you the five number summary (minimum, first quartile, median, third quartile, and maximum, plus the mean and the count of missing values if there are any). 

You don't have to specify a variable you can ask for these summaries from the whole data frame:


```r
summary(hate_crimes)
```

```
##     state           state_abbrev       median_house_inc share_unemp_seas 
##  Length:51          Length:51          Min.   :35521    Min.   :0.02800  
##  Class :character   Class :character   1st Qu.:48657    1st Qu.:0.04200  
##  Mode  :character   Mode  :character   Median :54916    Median :0.05100  
##                                        Mean   :55224    Mean   :0.04957  
##                                        3rd Qu.:60719    3rd Qu.:0.05750  
##                                        Max.   :76165    Max.   :0.07300  
##                                                                          
##  share_pop_metro   share_pop_hs    share_non_citizen share_white_poverty
##  Min.   :0.3100   Min.   :0.7990   Min.   :0.01000   Min.   :0.04000    
##  1st Qu.:0.6300   1st Qu.:0.8405   1st Qu.:0.03000   1st Qu.:0.07500    
##  Median :0.7900   Median :0.8740   Median :0.04500   Median :0.09000    
##  Mean   :0.7502   Mean   :0.8691   Mean   :0.05458   Mean   :0.09176    
##  3rd Qu.:0.8950   3rd Qu.:0.8980   3rd Qu.:0.08000   3rd Qu.:0.10000    
##  Max.   :1.0000   Max.   :0.9180   Max.   :0.13000   Max.   :0.17000    
##                                    NA's   :3                            
##    gini_index     share_non_white  share_vote_trump hate_crimes_per_100k_splc
##  Min.   :0.4190   Min.   :0.0600   Min.   :0.040    Min.   :0.06745          
##  1st Qu.:0.4400   1st Qu.:0.1950   1st Qu.:0.415    1st Qu.:0.14271          
##  Median :0.4540   Median :0.2800   Median :0.490    Median :0.22620          
##  Mean   :0.4538   Mean   :0.3157   Mean   :0.490    Mean   :0.30409          
##  3rd Qu.:0.4665   3rd Qu.:0.4200   3rd Qu.:0.575    3rd Qu.:0.35694          
##  Max.   :0.5320   Max.   :0.8100   Max.   :0.700    Max.   :1.52230          
##                                                     NA's   :4                
##  avg_hatecrimes_per_100k_fbi
##  Min.   : 0.2669            
##  1st Qu.: 1.2931            
##  Median : 1.9871            
##  Mean   : 2.3676            
##  3rd Qu.: 3.1843            
##  Max.   :10.9535            
##  NA's   :1
```

So you see how now we are getting this info for all variables in one go.

There are multiple ways of getting results in R. Particularly for basic and intermediate-level statistical analysis many core functions and packages can give you the answer that you are looking for. For example, there are a variety of packages that allow you to look at summary statistics using functions defined within those packages. You will need to install these packages before you can use them. 

I am only going to introduce one of them here *skimr*. It is neat and is maintained by one of my former stats teachers, the criminologist [Elin Waring](https://www.lehman.edu/academics/sociology/faculty-waring.php), an example of kindness and dedication to her students. 

You will need to install it before anything else. Use the code you have learnt to do so and then load it. I won't be providing you the code for it, by now you should now how to do this.



Once you have loaded the *skimr* package you can use it. Its main function is *skim*. Like *summary* for data frames, skim presents results for all the columns and the statistics will depend on the class of the variable. However, the results are displayed and stored in a nicer way - though we won't get into the details of this right now.


```r
skim(hate_crimes)
```


\begin{tabular}{l|l|r|r|r|r|r|r|r|r|r|r|r|r|r|r|l}
\hline
skim\_type & skim\_variable & n\_missing & complete\_rate & character.min & character.max & character.empty & character.n\_unique & character.whitespace & numeric.mean & numeric.sd & numeric.p0 & numeric.p25 & numeric.p50 & numeric.p75 & numeric.p100 & numeric.hist\\
\hline
character & state & 0 & 1.0000000 & 4 & 20 & 0 & 51 & 0 & NA & NA & NA & NA & NA & NA & NA & NA\\
\hline
character & state\_abbrev & 0 & 1.0000000 & 2 & 2 & 0 & 51 & 0 & NA & NA & NA & NA & NA & NA & NA & NA\\
\hline
numeric & median\_house\_inc & 0 & 1.0000000 & NA & NA & NA & NA & NA & 5.522361e+04 & 9208.4781698 & 3.552100e+04 & 4.865700e+04 & 5.491600e+04 & 6.071900e+04 & 76165.000000 & ▂▆▇▅▂\\
\hline
numeric & share\_unemp\_seas & 0 & 1.0000000 & NA & NA & NA & NA & NA & 4.956860e-02 & 0.0106981 & 2.800000e-02 & 4.200000e-02 & 5.100000e-02 & 5.750000e-02 & 0.073000 & ▅▇▇▇▂\\
\hline
numeric & share\_pop\_metro & 0 & 1.0000000 & NA & NA & NA & NA & NA & 7.501961e-01 & 0.1815873 & 3.100000e-01 & 6.300000e-01 & 7.900000e-01 & 8.950000e-01 & 1.000000 & ▁▂▅▆▇\\
\hline
numeric & share\_pop\_hs & 0 & 1.0000000 & NA & NA & NA & NA & NA & 8.691176e-01 & 0.0340732 & 7.990000e-01 & 8.405000e-01 & 8.740000e-01 & 8.980000e-01 & 0.918000 & ▃▅▃▆▇\\
\hline
numeric & share\_non\_citizen & 3 & 0.9411765 & NA & NA & NA & NA & NA & 5.458330e-02 & 0.0310770 & 1.000000e-02 & 3.000000e-02 & 4.500000e-02 & 8.000000e-02 & 0.130000 & ▇▆▆▂▂\\
\hline
numeric & share\_white\_poverty & 0 & 1.0000000 & NA & NA & NA & NA & NA & 9.176470e-02 & 0.0247148 & 4.000000e-02 & 7.500000e-02 & 9.000000e-02 & 1.000000e-01 & 0.170000 & ▂▇▃▂▁\\
\hline
numeric & gini\_index & 0 & 1.0000000 & NA & NA & NA & NA & NA & 4.537647e-01 & 0.0208908 & 4.190000e-01 & 4.400000e-01 & 4.540000e-01 & 4.665000e-01 & 0.532000 & ▆▇▅▁▁\\
\hline
numeric & share\_non\_white & 0 & 1.0000000 & NA & NA & NA & NA & NA & 3.156863e-01 & 0.1649152 & 6.000000e-02 & 1.950000e-01 & 2.800000e-01 & 4.200000e-01 & 0.810000 & ▇▇▆▂▁\\
\hline
numeric & share\_vote\_trump & 0 & 1.0000000 & NA & NA & NA & NA & NA & 4.900000e-01 & 0.1187097 & 4.000000e-02 & 4.150000e-01 & 4.900000e-01 & 5.750000e-01 & 0.700000 & ▁▁▆▇▇\\
\hline
numeric & hate\_crimes\_per\_100k\_splc & 4 & 0.9215686 & NA & NA & NA & NA & NA & 3.040930e-01 & 0.2527086 & 6.744680e-02 & 1.427066e-01 & 2.261971e-01 & 3.569347e-01 & 1.522302 & ▇▂▁▁▁\\
\hline
numeric & avg\_hatecrimes\_per\_100k\_fbi & 1 & 0.9803922 & NA & NA & NA & NA & NA & 2.367613e+00 & 1.7142450 & 2.669408e-01 & 1.293139e+00 & 1.987068e+00 & 3.184344e+00 & 10.953480 & ▇▅▁▁▁\\
\hline
\end{tabular}

Apart from summary statistics, last semester we discussed a variety of ways to graphically display variables. In week 3 of 'Making Sense of Criminological Data' covered scatterplots, a graphical device to show the relationship between two quantitative variables. I don't know if you remember the amount of point and click you had to do in Excel for getting this done. If not you can review the notes [here](https://maczokni.github.io/MSCD_labs/week3.html).

## R data types: Factors

An important thing to understand in R is that categorical (ordered, also called ordinal, or unordered, also called nominal) data are *typically* encoded as **factors**, which are just a special type of vector.  A factor is simply an integer vector that can contain *only predefined values* (this bit is very important), and is used to store categorical data. Factors are treated specially by many data analytic and visualisation functions. This makes sense because they are essentially different from quantitative variables.

Although you can use numbers to represent categories, *using factors with labels is better than using integers to represent categories* because factors are self-describing (having a variable that has values "Male" and "Female" is better than a variable that has values "1" and "2" to represent male and female). When R reads data in other formats (e.g., comma separated), by default it will automatically convert all character variables into factors. If you rather keep these variables as simple character vectors you need to explicitly ask R to do so. We will come back to this next week with some examples.

Factors can also be created with the `factor()` function concatenating a series of *character* elements. You will notice that is printed differently from a simply character vector and that it tells us the levels of the factor (look at the second printed line).


```r
the_smiths <- factor(c("Morrisey", "Marr", "Rourke", "Joyce")) #create a new factor
the_smiths #auto-print the factor
```

```
## [1] Morrisey Marr     Rourke   Joyce   
## Levels: Joyce Marr Morrisey Rourke
```
Alternatively for similar result using the as.factor() function. Here you will create `the_smiths_char` object and then transform it to a factor variable, `the_smiths_f`.


```r
the_smiths_char <- c("Morrisey", "Marr", "Rourke", "Joyce") #create a character vector
the_smiths_f <- as.factor(the_smiths_char) #create a factor using a character vector
the_smiths_f #auto-print factor
```

```
## [1] Morrisey Marr     Rourke   Joyce   
## Levels: Joyce Marr Morrisey Rourke
```

Factors in R can be seen as vectors with more information added. This extra information consists of a record of the distinct values in that vector, called **levels**. If you want to know the levels in a given factor you can use the `levels()` function:


```r
levels(the_smiths_f)
```

```
## [1] "Joyce"    "Marr"     "Morrisey" "Rourke"
```

Notice that the levels appear printed by alphabetical order (Try `levels(the_smiths_char)` and see what R says. Yes, `the_smiths_char` and `the_smiths_f` are different!). There will be situations when this is not the most convenient order (e.g., *Dec, Jan, Mar (Alphabetical order)* instead of *Jan, Mar, Dec*). Later on we will discuss in these tutorials how to reorder your factor levels when you need to.

Let's look at one more example here. Let's say we are making data about Hogwarts Houses which divided into four houses; Gryffindor, Hufflepuff, Ravenclaw and Slytherin. 


```r
#We create a dataframe called HarryPotter with two variables, a character vector called name and a character vector called house
HarryPotter <- data.frame(name = c("Potter", "Malfoy", "Lovegood", "Chang", "Hagrid", "Diggory"), house = c("Gryffindor", "Slytherin", "Ravenclaw", "Ravenclaw", "Gryffindor", "Hufflepuff"))
HarryPotter
```

```
##       name      house
## 1   Potter Gryffindor
## 2   Malfoy  Slytherin
## 3 Lovegood  Ravenclaw
## 4    Chang  Ravenclaw
## 5   Hagrid Gryffindor
## 6  Diggory Hufflepuff
```

Use `str(HarryPotter$house)` and see what R says. R will list all observations in the variable and says it's a character variable, right? Now we are going to convert `house`, a character variable, into a factor variable `house_f` meaning that R will categorise the variable.


```r
HarryPotter$house_f <- as.factor(HarryPotter$house)
str(HarryPotter$house_f)
```

```
##  Factor w/ 4 levels "Gryffindor","Hufflepuff",..: 1 4 3 3 1 2
```

```r
levels(HarryPotter$house_f) #try 'levels(HarryPotter$house)' and find the difference
```

```
## [1] "Gryffindor" "Hufflepuff" "Ravenclaw"  "Slytherin"
```

Now can you clearly understand what **factor** means in R? Factors are used to represent categorical data. Once created, factors can contain pre-defined set values, known as `levels`. Like we just converted 6 character data (`house`) into 4 factor data! (`house_f`).

![](imgs/as_factor.png){width=80%}

## How to import data

Programmers are lazy, and the whole point of using code-based interfaces is that we get to avoid doing unneccessary work, like point-and-click downloading of files. And when data exists online in a suitable format, we can tell R to read the data in from the web directly, and cut out the middle man (that being ourseves in our pointing-and-clicking activity). 

How can we do this? Well think about what we do when we read in a file. We say, hello R, i would like to create a new object please and I will call this new object `my_dataframe`. We do this by typing the name we are giving the object and the assignment function `<-`(assignment operator), Right? Then on the right hand side of the assignment function, there is the value that we are assigning the variable. So it could be a bit of text (such as when you're creating a `urlfile` object and you pass it the string `"path to my file"`), or it could be some function, for example when you read a csv file with the `read_csv()` function. 

So if we're reading a csv, we also need to specify *where* to read the csv from. Where should R look to find this data? This is where normally you are putting in the path to your file, right? Something like: 


```r
my_dataframe <- read_csv('PATH_OR_URL_TO_CSV_FILE')
```

Well what if your data does not live on your laptop or PC? Well, if there is a way that R can still access this data just by following a path, then this approach will still work! So how can we apply this to getting the Licensed Premises data from the web? 

You know when you right click on the link, and select "Save As..." or whatever you click on to save? You could, also select "Copy Link Address". This just copies the webpage where this data is stored. Give it a go! Copy the address, and then paste it into your browser. It will take you to a blank page where a forced download of the data will begin. So what if you pasted this into the `read_csv()` function? 


```r
my_dataframe <- read_csv("www.data.com/data you want to import.csv")
#file.choose() brings up a file explorer window that allows you to interactively choose a file path to work with.
my_dataframe <- read_csv(file.choose())
```

Well in this case, the my_data object would be assigned the value returned from the read.csv() function reading in the file from the 'urlfile' you provided. File path is no mysterious thing, file path is simply the *path* to the *file* you want to read. If this is a website, then so be it. 

R also can read Stata (.dta) files using the `read_dta()` function in the Haven package, SPSS (.sav) files using the `read_spss()` function also in the Haven Package. There are so many different ways, codes we can use to import data into R. In this course, you will learn one by one! 

## How to use 'comment'
In the bits of code above, you will have noticed parts that were grayed out. See for example in the last example provided. You can see that after the hashtag, all the text is being grayed out. What is this? What's going on? 

These are **comments**. Comments are simply annotations that R will know is not code (and therefore doesn't attempt to understand and execute). We use the hash-tag symbol to specify to R that what comes after is not programming code, but simply bits of notes that we write to remind ourselves what the code is actually doing. Including these comments will help you to understand your code when you come back to it.

To create a comment you use the hashtag/ number sign `#` followed by some text. Whenever the R engine sees the number sign it knows that what follows is not code to be executed. You can use this sign to include *annotations* when you are coding. These annotations are a helpful reminder to yourself (and others reading your code) of **what** the code is doing and (even more important) **why** you are doing it. 

It is good practice to often use annotations. You can use these annotations in your code to explain your reasoning and to create "scannable" headings in your code. That way after you save your script you will be able to share it with others or return to it at a later point and understand what you were doing when you first created it -see [here for further details on annotations and in how to save a script when working with the basic R interface](http://mercury.webster.edu/aleshunas/R_learning_infrastructure/R%20scripts.html).

Just keep in mind: 

+ You need one `#` per line, and anything after that is a comment that is not executed by R.

+ You can use spaces after (its not like a hashtag on twitter). 

## How to Quit RStudio
At some point, you will quit your R/R Studio session. I know, hard to visualise, right? Why would you want to do that? Anyhow, when that happens R Studio will ask you a hard question: "Save work space image to bla bla bla/.RData?" What to do? What does that even mean?

If you say "yes" what will happen is that all the objects you have in your environment will be preserved, alongside the *History* (which you can access in the top right set of windows) listing all the functions you have run within your session. So, next time you open this project all will be there. If you think that what is *real* is those objects and that history, well then you may think that's what you want to do.

Truth is what is real is your scripts and the data that your scripts use as inputs. You don't need anything that is in your environment, because you can recreate those things by re-running your scripts. I like keeping things tidy, so when I am asked whether I want to save the image, my answer is always no. Most long time users of R never save the workspace, nor care about saving the history either. Remember what is real is your scripts and the data.

Keep in mind though that you should not then panic if you open your next R Studio session and you don't see any objects in your environment. The good news is you can generate them quickly enough (if you really need them) by re-running your scripts. I would suggest that at this point it may be helpful for you to get into this habit as well. I suspect otherwise you will be in week 9 of the semester and have an environment full of garbage you don't really need.

What is more. I would suggest you go to the Tools drop down menu, select Global Options, and make sure you select "Never" where it says "Save workspace". Then click "Apply". This way you will never be asked to save what is in your global environment when you terminate a session.

<img src="https://user-images.githubusercontent.com/98951792/215292052-cbb36812-e7a7-4a7f-b2e4-57ea93918274.png"> 

## Summary: exercise for this week
Once you finish your lab session, don't forget to do this [Exercise](https://eonk.shinyapps.io/MCD_ex) and have a chance to sum-up this week's R codes.

<!--chapter:end:01-intro.Rmd-->

# Getting to know your data

## Causality in social sciences

In today's session we will refresh themes you have explored in previous research methods courses, specifically causality. This is a central concept in empirical research. We often do research because we want to make causal inferences. We want to be in a position where we establish whether an intervention or a social process is causally linked to crime or some other relevant criminological outcome.

Making causal inferences often involves making comparisons. For example, between cases that have been subject to an intervention and cases that have not being subject to the causal process we are trying to investigate. But you should already know that not all kind of research comparisons are the same. In previous methods courses you must have discussed the differences between experimental and observational studies. This different kinds of research designs have a bearing on your ability to make causal inference.

Let's think about a specific case so that this makes more sense. Is there discrimination against former offenders in the labor market? In other words, are offenders less likely to find employment after release because of prejudice among employers? Or can we say that the fact that former offenders are less likely to be in employment may be due to other factors? Perhaps, they are less skilled. Perhaps they have less social capital, people they know that can help them to get jobs or to learn about job opportunities. Perhaps, they are less interested in finding employment? 

Only in comparisons when other things are equal you can make causal inferences. It would only be fair to compare John, an ex-offender with a high school degree and X number of personal connections and Y numbers of professional experience, with Peter, a non-ex offender, with the same educational and professional credentials than John (and everything else that matters when getting jobs also being equal between Peter and John). 

How can you do that? How can you create situations when other things are equal? Well, that's what courses in research design are oriented to teach you. What is important for you to remember is that the way data are generated, the way you do your study, will, of course, affect the kind of interpretations that you make from your statistical comparisons. And not all studies are created equal. Some research designs put you in a better position than others to make causal inference.

You should have learnt by now that the ["bronze" standard](https://link.springer.com/article/10.1007/s11292-005-3538-2) for establishing causality in the social sciences is the randomised experiment. In a randomised trial, the researchers change the causal variable of interest for a group using something like a coin toss. As Angrist and Pischke (2015: xiii) highlight:

*"By changing circumstances randomly, we make it highly likely that the variable of interest is unrelated to the many other factors determining the outcomes we mean to study... Random manipulation makes other things equal hold on average across the groups that did and did not experience manipulation"*

So, say you want to establish whether arresting a perpetrator may have a deterrent effect on subsequent domestic abuse. You could randomise, basically use the equivalent of a lottery, to decide whether the police officer is going to arrest the perpetrator or not and then compare those you arrest with those you don't arrest. Because you are randomising your treatment (the arrest) on average the treatment and the control group on the long run should be fairly similar and any differences you observe between them in the outcome of interest (domestic abuse recidivism) you could link it to your intervention -if you are interested in the answer to this you can read about it [here](https://www.ojp.gov/pdffiles1/nij/188199.pdf).

In this session we will look at data from a randomised trial that tried to establish whether there is discrimination in the labour market against former offenders. In doing so, we will also learn various functions used in R to read data, transform data, and to obtain summary statistics for groups. We will also very quickly introduce a plotting function used in R to generate graphics.

## Getting data thanks to reproducibility

Last week we introduced the notion of reproducible research and said that using and publishing code (particularly if using open source tools like R) is the way that [many researchers](https://osf.io/?gclid=EAIaIQobChMIq-jM6MuY2QIV7Z3tCh04vAycEAAYASAAEgLptPD_BwE) around the world think that science ought to be done. This way of operating makes research more open, more credible, and more legitimate. It also means that we can more easily access the data used in published research. For this session we are going to use the data from [this](https://academic.oup.com/qje/article/133/1/191/4060073) and [this paper](https://pubs.aeaweb.org/doi/pdfplus/10.1257/aer.p20171003) study. In this research project, the authors tried to answer the question of whether criminal antecedents and other personal characteristics have an impact on access to employment. You can find more details about this work in [episode 8](https://www.probablecausation.com/podcasts/episode-8-amanda-agan) of *Probable Causation*, the criminology podcast.

If you want to know more about 'Ban the Box' to encourage ‘fair chance recruitment’ practices in the UK, you can find more information [here](https://recruit.unlock.org.uk/fair-chance-recruitment/ban-the-box/) and also can watch a video from Leo Burnett who helped promote the importance of giving people a chance to explain their past.

<iframe src="https://www.youtube.com/embed/eM1nVA6hwlI" width="100%" height="400px" data-external="1"></iframe>

[Amanda Agan](http://economics.rutgers.edu/people/626-amanda-agan) and [Sonja Starr](https://www.law.umich.edu/FacultyBio/Pages/FacultyBio.aspx?FacID=sbstarr) developed a randomised experiment in which they created 15,220 fake resumes randomly generating these critical characteristics (such as having a criminal record) and used these resumes to send online job applications to low-skill, entry level job openings in New Jersey and New York City. All the fictitious applicants were male and about 21 to 22 years old. These kind of experiments are very common among researchers that want to explore through these "audits" whether some personal characteristics are discriminated against in the labor market.

Because Amanda Agan and Sonja Starr conformed to reproducible standards when doing their research we can access this data from the *Harvard Dataverse* (a repository for open research data). Click [here](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VPHMNT) to locate the data.

![](imgs/harvarddataverse.PNG) 

In this page you can see a download section and some files that can be accessed. One of them contains analytic code pertaining to the study and the other contains the data. You also see a link called **metadata**. Metadata is data about data, it simply provides you with some information about the data. If you clink in metadata you will see at the bottom a reference to the software the authors used (STATA). So we know these files are in [STATA](https://www.stata.com/) proprietary format. Let's download the data file and then read the data into R.

You could just click "download" and then place the file in your project directory. Alternatively, and preferably, you may want to use code to make your whole work more reproducible. Think of it this way, every time you click or use drop down menus you are doing things that others cannot reproduce because there won't be a written record of your steps. You will need though to do some clicking for finding out the required url you will use for writing your code. The file we want is the `AganStarrQJEData.dta`. Click in the name of this file. You will be taken to another webpage. On it you will see the download url. Copy and paste this url in your code below.


```r
#First, let's create an object with the link, paste the copied address here:
urlfile <- "https://dataverse.harvard.edu/api/access/datafile/3036350"
```

This  data file is a STATA.dta file in our working directory. To read STATA files we will need the *haven* package. This is a package developed for importing different kind of data files into R. If you don't have it you will need to install it. And then load it.


```r
library(haven)
#Now we can use the 'read_dta' function, within this function we will
#pass an argument, urlfile, specifying to the read_dta function the need to
#make a url connection. The url function takes as an argument the url
#we are using and that we encoded in the urlfile object in our case.
banbox <- read_dta(urlfile)
```

You will need to pay attention to the file extension, to find the appropriate function to read in your file. For example, if something has the extension `.sav` that is a file used by the software SPSS. To read this, you would use the `read_spss()` function, also in the haven package. 

Some other file types need other packages. For example, to read in comma separated values or `.csv` files, you can use the `read_csv()` function from the `readr` package. To read in excel files, you would use the appropriate function from the `readxl` package, which might be `read_xls()` or `read_xlsx()` depending on the file extension. 

## Getting a sense for your data

### First steps

What is the first thing you need to ask yourself when you look at a dataset? Data are often too big to look at the whole thing. It is almost always impossible to eyeball the entire dataset and see what you have in terms of interesting patterns or potential problems. It is often a case of information overload and we want to be able to extract what is relevant and important about it. But where do you start?  You can find a brief but very useful overview put together by Steph de Silva in the image below. Read it before we carry on.

![](imgs/firstlookatdata.jpg)<!-- --> 

As Mara Averick (somebody you want to follow in twitter at @dataanndme if you want to be in top of R related resources) suggests this also makes for good relationship advice!

<img src="https://user-images.githubusercontent.com/98951792/215890363-7911fbd7-e020-41a3-991f-3e2863a94170.PNG">

Here we are going to introduce a few functions that will help you to start making sense for what you have just downloaded. Summarising the data is the first step in any analysis and it is also used for finding out potential problems with the data. Regarding the latter you want to look out for: missing values; values outside the expected range (e.g., someone aged 200 years); values that seem to be in the wrong units; mislabeled variables; or variables that seem to be the wrong class (e.g., a quantitative variable encoded as a factor). 

Lets start by the basic things you always look first in a datasets. You can see in the Environment window that banbox has 14813 observations (rows) of 62 variables (columns). You can also obtain this information using code. Here you want the  **DIM**ensions of the dataframe (the number of rows and columns) so you use the `dim()` function:


```r
dim(banbox)
```

```
## [1] 14813    62
```

Looking at this information will help you to diagnose whether there was any trouble getting your data into R (e.g., imagine you know there should be more cases or more variables). You may also want to have a look at the names of the columns using the `names()` function. We will see the names of the variables.


```r
names(banbox)
```

```
##  [1] "nj"                   "nyc"                  "app_date_d"          
##  [4] "pre"                  "post"                 "storeid"             
##  [7] "chain_id"             "center"               "crimbox"             
## [10] "crime"                "drugcrime"            "propertycrime"       
## [13] "ged"                  "empgap"               "white"               
## [16] "black"                "remover"              "noncomplier_store"   
## [19] "balanced"             "response"             "response_date_d"     
## [22] "daystoresponse"       "interview"            "cogroup_comb"        
## [25] "cogroup_njnyc"        "post_cogroup_njnyc"   "white_cogroup_njnyc" 
## [28] "ged_cogroup_njnyc"    "empgap_cogroup_njnyc" "box_white"           
## [31] "pre_white"            "post_white"           "white_nj"            
## [34] "post_remover_ged"     "post_ged"             "remover_ged"         
## [37] "post_remover_empgap"  "post_empgap"          "remover_empgap"      
## [40] "post_remover_white"   "post_remover"         "remover_white"       
## [43] "raerror"              "retail"               "num_stores"          
## [46] "avg_salesvolume"      "avg_num_employees"    "retail_white"        
## [49] "retail_post"          "retail_post_white"    "percblack"           
## [52] "percwhite"            "tot_crime_rate"       "nocrimbox"           
## [55] "nocrime_box"          "nocrime_pre"          "response_white"      
## [58] "response_black"       "response_ged"         "response_hsd"        
## [61] "response_empgap"      "response_noempgap"
```

As you may notice, these names may be hard to interpret. If you open the dataset in the data viewer of RStudio (using `View`) you will see that each column has a variable name and underneath a longer and more meaningful **variable label** that tells you what each variable means. 


```r
View(banbox)
```

### On tibbles and labelled vectors

You also want to understand what the banbox object actually is. You can do that using the `class()` function:


```r
class(banbox)
```

```
## [1] "tbl_df"     "tbl"        "data.frame"
```

What does `tbl` stands for? It refers to **tibbles**. This is essentially a new type of data structure introduced into R. Tibbles *are* data frames, but a particular type. Not all data frames we encounter in R are tibbles.

The R language has been around for a while and sometimes things that made sense a couple of decades ago, make less sense now. A number of programmers are trying to create code that is more modern and more useful today. They are doing this by introducing a set of packages that speak to each other in order to modernise R without breaking existing code. You can think of it as an easier and more efficient modern dialect of R. This set of packages is called the **tidyverse**. Tibbles are dataframes that have been optimised to be used with this new set of packages. You can read a bit more about tibbles [here](http://r4ds.had.co.nz/tibbles.html).

You can also look at the class of each individual column. As discussed, class of the variable lets us know, for example, if its an integer (number), character, or factor. 

To get the class of one variable, you pass it to the `class()` function. For example:


```r
class(banbox$crime)
```

```
## [1] "haven_labelled" "vctrs_vctr"     "double"
```

```r
class(banbox$num_stores)
```

```
## [1] "numeric"
```

We talked about numeric vectors in week one. It is simply a collection of numbers. But what is a labelled vector? This is a new type of vector introduced by the *haven* package. **Labelled vectors** are categorical variables that have labels. Go to the *Environment* panel and left click in the banbox object. This should open the data browser in the top left quadrant of RStudio.

<img src="https://user-images.githubusercontent.com/98951792/215890726-b8a9ca15-b889-4fb6-a4be-62463bdfba93.PNG">

If you look carefully you will see that the various columns that include categorical variables only contain numbers. In many statistical environments, such as STATA or SPSS, this is a common standard. The variables have a numeric value for each observation and then each of these numeric values is associated with a label. This kind of made sense when computer memory was an issue - for this was an efficient way of saving resources. It also made manual data input quicker. These days it makes perhaps less sense. But labelled vectors give you a chance to reproduce data from other statistical environments without losing any fidelity in the import process. See what happens if we try to summarise this labelled vector. We will use the `table()` to provide a count of observations on the various valid values of the *crime* variable. It is a function to obtain your frequency distribution.


```r
table(banbox$crime)
```

```
## 
##    0    1 
## 7323 7490
```

So, we see that we have 7490 observations classed as 1 and 7323 classed as 2. If only we knew what those numbers represent! Well, we actually do. We will use the `attributes()` function to see the different "compartments" within your "box", your object.


```r
attributes(banbox$crime)
```

```
## $label
## [1] "Applicant has Criminal Record"
## 
## $format.stata
## [1] "%9.0g"
## 
## $class
## [1] "haven_labelled" "vctrs_vctr"     "double"        
## 
## $labels
## No Crime    Crime 
##        0        1
```

So this object has different compartments. The first one is called label and it provides a description of what the variable measures. This is what you saw in the RStudio data viewer earlier. The second compartment explains the original format in which it was. The third one identifies the class of the vector. Whereas the final one, *labels*, provides the labels that allows us to identify what the meaning of 0 and 1 mean in this context.
 
### Turning variables into factors and changing the labels

Last week we said that many R functions expect factors when you have categorical data, so typically after you import data into R you may want to coerce your labelled vectors into factors. To do that you need to use the `as_factor()` function of the *haven* package. Let's see how we do that.


```r
#This code asks R to create a new column in your banbox tibble
#that is going to be called crime_f. Typically, when you alter
#variables you can to create a new one so that the original gets
#preserved in case you do something wrong. Then we use the
#as_factor() function to explain to R that what we want to do
#is to get the original crime variable and mutate it into 
#a factor, this resulting factor is what will be stored in
#the new column.
banbox$crime_f <- as_factor(banbox$crime)
```

You will see now that you have 63 variables in your dataset, look at the environment to check. Let's explore the new variable we have created (you can also look for the new variable in the data browser and see how it looks different to the original crime variable):


```r
class(banbox$crime_f)
```

```
## [1] "factor"
```

```r
table(banbox$crime_f)
```

```
## 
## No Crime    Crime 
##     7323     7490
```

```r
attributes(banbox$crime_f)
```

```
## $levels
## [1] "No Crime" "Crime"   
## 
## $class
## [1] "factor"
## 
## $label
## [1] "Applicant has Criminal Record"
```

So far we have a looked at single columns in your dataframe one at the time. But there is a way that you can apply a function to all elements of a vector (list or dataframe). You can use the functions `sapply()`, `lapply()`, and `mapply()`  . To find out more about when to use each one see [here](https://www.r-bloggers.com/using-apply-sapply-lapply-in-r/). 

For example, we can use the `lapply()` function to look at each column and get its class. To do so, we have to pass two arguments to the `lapply()` function, the first is the name of the dataframe, to tell it what to look through, and the second is the function we want it to apply to every column of that function. 

So we want to type `lapply('name of dataframe', 'name of function')` 

Which is: 

```r
lapply(banbox, class)
```

As you can see many variables are classed as 'labelled'. This is common with survey data. Many of the questions in social surveys measure the answers as categorical variables (e.g., these are nominal or ordinal level measures). In fact, with this dataset there are many variables that are encoded as numeric that really aren't. Welcome to real world data, where things can be a bit messy and need tidying!

See for example the variable black:


```r
class(banbox$black)
```

```
## [1] "numeric"
```

```r
table(banbox$black)
```

```
## 
##    0    1 
## 7406 7407
```

We know that this variable measures whether someone is black or not. When people use 0 and 1 to code binary responses, typically they use a 1 to denote a positive response, a yes. So, I think it is fair to assume that a 1 here means the respondent is black. Because this variable is of class numeric we cannot simply use `as_factor()` to assign the pre-existing labels and create a new factor. In this case we don't have preexisting labels, since this is not a labelled vector. So what can we do to tidy this variable? We'll we need to do some further work.


```r
#We will use a slightly different function as.factor()
banbox$black_f <- as.factor(banbox$black)
#You can check that the resulting column is a factor
class(banbox$black_f)
```

```
## [1] "factor"
```

```r
#But if you print the frequency distribution you will see the data are still presented in relation to 0 and 1
table(banbox$black_f)
```

```
## 
##    0    1 
## 7406 7407
```

```r
#You can use the levels function to see the levels, the categories, in your factor
levels(banbox$black_f)
```

```
## [1] "0" "1"
```

So, all we have done is create a new column that is a factor but still refers to 0 and 1. If we assume (rightly) that 1 mean black we have 7407 black applicants. Of course, it makes sense we only get 0 and 1 here. What else could R do? This is not a labelled vector, so there is no way for R to know that 0 and 1 mean anything other than 0 and 1, which is why those are the levels is using. But now that we have the factor we can rename those levels. We can use the following code to do just that:


```r
#We are using the levels function to access them and change
#them to the levels we specify with the c() function. Be
#careful here, because the order we specify here will map 
#out to the order of the existing levels. 
#So given that 1 is black and black is the second level 
#(as shown when printing the results above) you want to make sure that in the c()
#you write black as the second level.
levels(banbox$black_f) <- c("non-Black", "Black")
table(banbox$black_f)
```

```
## 
## non-Black     Black 
##      7406      7407
```

This gives you an idea of the kind of transformations you often want to perform to make your data more useful for your purposes. But let's keep looking at functions you can use to explore your dataset. 

### Looking for missing data and other anomalies

You can, for example, use the `head()` function if you just want to visualise the values for the first few cases in your dataset. The next code for example ask for the values for the first two cases. If you want a different number to be shown you just need to change the number you are passing as an argument.


```r
head(banbox, 2)
```

In the same way you could look at the last two cases in your dataset using `tail()`:


```r
tail(banbox, 2)
```

It is good practice to do this to ensure R has read the data correctly and there's nothing terribly wrong with your dataset. If you have access to STATA you can open the original file in STATA and check if there are any discrepancies, for example. Glimpsing your data in this way can also give you a first impression for what the data looks like.

One thing you may also want to do is to see if there are any **missing values**. For that we can use the `is.na()` function. Missing values in R are coded as NA. The code below, for example, asks for NA values for the variable *response_black* in the *banbox* object for observations 1 to 10:


```r
is.na(banbox$response_black[1:10])
```

```
##  [1] FALSE  TRUE  TRUE FALSE FALSE  TRUE  TRUE  TRUE FALSE  TRUE
```

The result is a logical vector that tells us if it is true that there is missing (NA) data for each of those first ten observations. You can see that there are 6 observations out of those 10 that have missing values for this variable.



```r
sum(is.na(banbox$response_black)) 
```

```
## [1] 7406
```

This is asking R to sum how many cases are TRUE NA in this variable. When reading a logical vector as the one we are creating, R will treat the FALSE elements as 0s and the TRUE elements as 1s. So basically the sum() function will count the number of TRUE cases returned by the is.na() function.

You can use a bit of a hack to get the proportion of missing cases instead of the count:


```r
mean(is.na(banbox$response_black))
```

```
## [1] 0.4999662
```

This code is exploiting the mathematical fact that the mean of binary outcomes (0 or 1) gives you the proportion of ones in your data. As a rule of thumb, if you see more than 5% of the cases declared as NA, you need to start thinking about the implications of this. Beware of formulaic application of rules of thumb such as this though! In this case, we know that 49%% of the observations have missing values in this variable. When you see things like this the first thing to do is to look at the codebook or documentation to try to get some clues as to why there are so many missing cases. With survey data you often have questions that are simply not asked to everybody, so it's not necessarily that something went very wrong with the data collection, but simply that the variable in question was only used with a subset of the sample. And that, therefore, any analysis you do using this question will only relate to that particular subset of cases.

There is a whole field of statistics devoted to doing analysis when missing data is a problem. R has extensive capabilities for dealing with missing data -see for example [here](https://www.routledge.com/Flexible-Imputation-of-Missing-Data-Second-Edition/Buuren/p/book/9781032178639). For the purpose of this introductory course, however, we only explain how to do analysis that ignore missing data. This is often referred to a **full/complete case analysis**, because you only use observations for which you have full information in all the variables you employ. You would cover techniques for dealing with this sort of issues in more advanced courses.

## Data wrangling with dplyr

The data analysis workflow has a number of stages. The diagram below (produced by Hadley Wickham) is a nice illustration of this process:

![](imgs/data-science-explore.png)

We have started to see different ways of bringing data into R. And we have also started to see how we can explore our data. It is now time we start discussing one of the following stages, **transform**. A good deal of time and effort in data analysis is devoted to this. You get your data and then you have to do some transformations to it so that you can answer the questions you want to address in your research. We have already seen, for example, how to turn variables into factors, but there are other things you may want to do.

R offers a great deal of flexibility in how to transform your data, Here we are going to illustrate some of the functionality of the *dplyr* package for data carpentry (a term people use to refer to this kind of operations). This package is part of the tydiverse and it aims to provide a friendly and modern take on how to work with dataframes (or tibbles) in R. It offers, as the authors of the package put it, "a flexible grammar of data manipulation". 

Dplyr aims to provide a function for each basic verbs of data manipulation:

+ `filter()` to select cases based on their values.
+ `arrange()` to reorder the cases.
+ `select()` and `rename()` to select variables based on their names.
+ `mutate()` and `transmute()` to add new variables that are functions of existing variables.
+ `summarise()` to condense multiple values to a single value.
+ `sample_n()` and `sample_frac()` to take random samples.

In this session we will introduce and practice some of these. But we won't have time to cover everything. There is, however, a very nice set of vignettes for this package in the help files, so you can try to go through those if you want a greater degree of detail or more practice. 

Now let's load the package:


```r
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
```

```
## The following objects are masked from 'package:stats':
## 
##     filter, lag
```

```
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

Notice that when you run this package you get a series of warnings in the console. It is telling us that some functions from certain packages are being "masked". One the things with a language like R is that sometimes packages introduce functions that have the same name than others that are already loaded into your session. When that happens the newly loaded ones will over-ride the previous ones. You can still use them but you will have to refer to them explicitly. Otherwise R will assume you are using the function most recently loaded:


```r
#Example:
#If you use load dplyr and then invoke the *filter()* function
#R will assume you are using the filter function from dplyr
#rather than the *filter()* function that exist in the *stats*
#package, which is part of the basic installation of R. If 
#after loading dplyr you want to use the filter function from
#the stats package you will have to invoke it like this:
stats::filter()
#Notice the grammar, first you write the name of the package,
#then colon twice, and then the name of the function. Don't 
#run this code. You would need to pass some valid arguments
#for this to produce meaningful results.
```

## Using dplyr single verbs

One of the first operations you may want to carry out when working with dataframes is to subset them based on values of particular variables. Say we want to replicate the results reported by Agan and Starr in 2017. In this earlier paper, these researchers only used data from the period prior to the introduction of Ban the Box legislation and only used data from businesses that asked about criminal records in their online applications. How can we recreate this dataset?

For this kind of operations we use the `filter()` function. Like all single verbs in dplyr, the first argument is the tibble (or data frame). The second and subsequent arguments refer to variables within that data frame, selecting rows where the expression is TRUE. 

Ok, let's filter out some information we are interested in from `bandbox`. If we look at the dataset we can see that there is a variable called "crimbox" that identifies 'applications that require information about criminal antecedents' and there is a variable called "pre" that identifies 'whether the application was sent before the legislation was introduced'. In this dataset, the value 1 is being used to denote positive responses. Therefore, if we want to create the 2017 dataset, we would start by selecting only data where the value in these two variables equals 1 as shown below.


```r
#We will store the results of filtering the data in a new object that I am calling aer  
#(short for the name of the journal in which the paper was published)

aer2017<- filter(banbox, crimbox == 1, pre == 1)
```

Notice that the number of cases equals the number of cases reported by the authors in their 2017 paper. That's cool! So far we are replicating with same results.

You may have noticed in the code above that I wrote "`==`" instead of "`=`". Logical operators in R are not written exactly the same way than in normal practice. Keep this in mind when you get error messages from running your code. Often the source of your error may be that you are writing the logical operators the wrong way (as far as R is concerned). Look [here](https://www.statmethods.net/management/operators.html) for valid logic operators in R.

Earlier we said that real life data may have hundreds of variables and only a few of those may be relevant for your analysis. For this week's analysis, we want to select only a few variables that might be highly related with 'Discrimination in Employment'. Say you only want "crime", "ged" (a ged is a high school equivalence diploma rather than a proper high school diploma and is sometimes seen as inferior), "empgap" (a gap year on employment), "black_f", "response", and "daystoresponse" from this dataset. For this kind of operations you use the `select()` function.

The syntax of this function is easy. First we name the dataframe object ("aer2017") and then we list the variables. The order in which we list the variables within the select function will determine the order in which those columns appear in the new dataframe we are creating. So this is a handy function to use if you want to change the order of your columns for some reason. Since I am pretty confident I am not making a mistake I will transform the original "aer2017" tibble rather than creating an entirely new object.


```r
aer2017 <- select(aer2017, crime, ged, empgap, black_f, response, daystoresponse)
```

If you now look at the global environment you will see that the "aer2017" tibble has reduced in size and now only has 6 columns. If you view the data you will see these are the 6 variables we selected.

## Using dplyr for grouped operations

So far we have used `dplyr` single verbs for ungrouped operations. But we can also use some of the functionality of `dplyr` for obtaining answers to questions that relate to groups of cases within our dataframe. Imagine that you want to know if applicants with a criminal record are less likely to receive a positive response from employers. How could you figure that one out? For answering this kind of questions we can use the `group_by()` function in conjunction with other `dplyr` functions. In particular we are going to look at the `summarise` function.

First we group the observations by criminal record in a new object, "by_antecedents", by using `as_factor()` in the call to the crime variable the results will be labelled later on (even though we are not changing the crime variable in the aer2017 dataframe). Keep in mind we are using `as_factor()` because the column crime is a labelled vector rather than a factor or a character vector, and we do this to aid interpretation (it is easier to
interpret labels than 0 and 1).


```r
aer2017_by_antecedent <- group_by(aer2017, as_factor(crime))

#Then we run the summarise function to provide some useful
#summaries of the groups we are using: the number of cases
#and the mean of the response variable
results_1 <- summarise(aer2017_by_antecedent,
  count = n(),
  outcome = mean(response, na.rm = TRUE))

results_1 #auto-print the results stored in the newly created object
```

```
## # A tibble: 2 x 3
##   `as_factor(crime)` count outcome
##   <fct>              <int>   <dbl>
## 1 No Crime            1319  0.136 
## 2 Crime               1336  0.0846
```

Let's look at the code in the `summarise` function above. First we are asking R to place the results in an object we are calling "results". Then we are specifying that we want to group the data in the way we specified in our `group_by()` function before, that is by criminal record. Then we pass two arguments. Each of these arguments is creating a new variable in the resulting object called "results". The first variable we are creating is called "*count*" by saying this equals "n()" we are specifying to R that this new variable simply counts the number of cases in each of the grouping categories. The second variable we are creating is called "*outcome*" and to compute this variable we are asking R to compute the mean of the variable response for each of the two groups of applicants defined in "by_antecedents" (those with records, those without). Remember that the variable response in the "aer2017" dataframe was coded as numeric variable, even though in truth is categorical in nature (there was a response, or not, from the employers). It doesn't really matter. Taking the mean of a binary variable in this case is mathematically equivalent to computing a proportion as we discussed earlier.

So, what we see here is that about 13.6% of applicants with no criminal record received a positive response from the employers, whereas only 8% of those with criminal records did receive such a response. Given that the assignation of a criminal record was randomised to the applicants, there's a pretty good chance that no other [**confounders**](https://en.wikipedia.org/wiki/Confounding) are influencing this outcome. And that is the beauty of randomised experiments. You may be in a position to make stronger claims about your results.





## Making comparisons with numerical outcomes

We have been looking at relationships so far between categorical variables, specifically between having a criminal record (yes or no), race (black or white), and receiving a positive response from employers (yes or no). Often we may be interested in looking at the impact of a factor on a numerical outcome. In the banbox object we have such an outcome measured by the researchers. The variable "daystoresponse" tells us how long it took the employers to provide a positive response. Let's look at this variable:


```r
summary(banbox$daystoresponse)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
##    0.00    3.00   10.00   19.48   28.00  153.00   14361
```

The `summary()` function provides some useful stats for numerical variables. We obtain the minimum and maximum value, the 25th percentile, the median, the mean, the 75th percentile, and the number of missing data (NA). You can see the number of missing data here is massive. Most cases have missing data on this variable. Clearly this is a function of, first and foremost, the fact that the number of days to receive a positive response will only be collected in cases where there was a positive response! But even accounting for that, it is clear that this information is also missing in many cases that received a positive response. So given all of this, we need to be very careful when interpreting this variable. Yet, because it is the only numeric variable here we will use it to illustrate some handy functions.

We could do as before and get results by groups. Let's look at the impact of race on days to response:


```r
banbox_by_race <- group_by(banbox, black_f)
results_2 <- summarise(banbox_by_race,
  avg_delay = mean(daystoresponse, na.rm = TRUE))
results_2
```

```
## # A tibble: 2 x 2
##   black_f   avg_delay
##   <fct>         <dbl>
## 1 non-Black      18.7
## 2 Black          20.4
```

We can see that the average delay seems to be longer for 'Black' applicants than 'White' applicants. 

But we could also try to represent these differences graphically. The problem with comparing groups on quantitative variables using numerical summaries such as the mean, is that these comparisons hide more than they show. We want to see the full distribution, not just the mean. For this we are going to use `ggplot2` the main graphical package we will use this semester. We won't get into the details of this package or what the code below means, but just try to run it. We will cover graphics in R in the next section. This is just a taster for it.


```r
library(ggplot2)
ggplot(banbox, aes(y = daystoresponse, x = black_f)) + 
  geom_boxplot() 
```

![](02-causality_files/figure-latex/unnamed-chunk-30-1.pdf)<!-- --> 

Watch [this video](https://www.khanacademy.org/math/probability/data-distributions-a1/box--whisker-plots-a1/v/reading-box-and-whisker-plots) and see if you can interpret the results portrayed here. What do you think?

Overall the outcomes are worse for 'Black' applicants, and in fact, the authors find that employers substantially increase discrimination on the basis of race after ban the box goes into effect.You can now replicate these findings with the data provided. by applying the new skills you've learned this week!

## Summary: exercise for this week

Once you finish your lab session, don't forget to do this [Exercise](https://eonk.shinyapps.io/MCD_ex) and have a chance to sum-up this week's R codes.

<!--chapter:end:02-causality.Rmd-->

# Data visualisation with R

## Introduction

A picture is worth a thousand words; when presenting and interpreting data this basic idea also applies. There has been, indeed, a growing shift in data analysis toward more visual approaches to both interpretation and dissemination of numerical analysis. Part of the new data revolution consists in the mixing of ideas from visualisation of statistical analysis and visual design. Indeed data visualisation is one of the most interesting areas of development in the field.

Good graphics not only help researchers to make their data easier to understand by the general public. They are also a useful way for understanding the data ourselves. In many ways it is very often a more intuitive way to understand patterns in our data than trying to look at numerical results presented in a tabular form. 

Recent research has revealed that papers which have good graphics are perceived as overall more clear and more interesting, and their authors perceived as smarter (see [this presentation](https://vimeo.com/181771433))

The preparation for this session includes many great resources on visualising quantitative information, and if you have not had time to go through them, we recommend that you take some time to do so. 

As with other aspects of R, there are a number of core functions that can be used to produced graphics. However these offer limited possibilities for building graphs. 

The package we will be using throughout this tutorial is `ggplot2`. The aim of `ggplot2` is to implement the [grammar of graphics](http://www.springer.com/statistics/computational+statistics/book/978-0-387-24544-7). The `ggplot2` package has excellent online [documentation](https://ggplot2.tidyverse.org/) and is becoming an industry standard in some sectors. [Here](https://medium.com/bbc-visual-and-data-journalism/how-the-bbc-visual-and-data-journalism-team-works-with-graphics-in-r-ed0b35693535) for example you can read about how the BBC uses as part of their News service.

If you don't already have the package installed (check you do), you will need to do so using the `install.packages()` function. 
 
 You will then need to load up the package
 

```r
library(ggplot2)                                  
```

The grammar of graphics upon which this package is based on defines various components of a graphic. Some of the most important are:

-**The data**: For using `ggplot2` the data has to be stored as a data frame or tibble.

-**The geoms**: They describe the objects that represent the data (e.g., points, lines, polygons, etc..). This is what gets drawn. And you can have various different types layered over each other in the same visualisation.

-**The aesthetics**: They describe the visual characteristics that represent data (e.g., position, size, colour, shape, transparency).

-**Facets**: They describe how data is split into subsets and displayed as multiple small graphs.

-**Stats**: They describe statistical transformations that typically summarise data.

Let's take it one step at the time.

## Anatomy of a plot

Essentially the philosophy behind this is that all graphics are made up of layers. The package `ggplot2` is based on the grammar of graphics, the idea that you can build every graph from the same few components: a data set, a set of geoms—visual marks that represent data points, and a coordinate system.

Take this example (all taken from *Wickham, H. (2010). A layered grammar of graphics. Journal of Computational and Graphical Statistics, 19(1), 3-28.*)

You have a table such as: 

![](imgs/table.png)

You then want to plot this. To do so, you want to create a plot that combines the following layers: 

![](imgs/layers.png)

This will result in a final plot: 

![](imgs/combined.png)

Let's have a look at what this looks like for a graph. 

Let's have a look at some data about [banning orders](https://www.gov.uk/government/publications/football-related-arrests-and-banning-orders-england-and-wales-season-2016-to-2017/football-related-arrests-and-banning-order-statistics-england-and-wales-2016-to-2017-season) for different football clubs. 

First you need to read the data. We keep this data in a website and you can download it with the following code:


```r
# load readr library and import the data using read_csv() function
library(readr)
fbo <- read_csv("https://raw.githubusercontent.com/eonk/dar_book/main/datasets/FootbalBanningOrders.csv")
```

```
## New names:
## Rows: 119 Columns: 4
## -- Column specification
## -------------------------------------------------------- Delimiter: "," chr
## (2): Club.Supported, League.of.the.Club.Supported dbl (2): ...1, Banning.Orders
## i Use `spec()` to retrieve the full column specification for this data. i
## Specify the column types or set `show_col_types = FALSE` to quiet this message.
## * `` -> `...1`
```

You can also find this on the Blackboard page for this week's learning materials. If you download from there, make sure to save this file in your project directory, possibly in a subfolder called "Datasets". Then you can read in from there.

One thing from the first lab we mentioned is conventions in the naming ob objects. This also applies to the names of your variables (i.e. your column names) within your data. If you look at the fbo dataframe, either with the `View()` function, or by printing the names of the columns with the `names()` function, you can see, this dataset violates that requirement: 


```r
names(fbo)
```

```
## [1] "...1"                         "Club.Supported"              
## [3] "Banning.Orders"               "League.of.the.Club.Supported"
```

To address this, we can use a function called `clean_names()` which lives inside the `janitor` package. This will replace any spaces with an underscore, and also turn any capital letters into lowercase. Much more tidy!


```r
library(janitor)
fbo <- clean_names(fbo)
```

Now let's explore the question of number of banning orders for clubs in different leagues. But as a first step, let's just plot the number of banning orders for each club. Let's build this plot:


```r
ggplot(data = fbo, aes(x = club_supported, y=banning_orders)) + #data
   geom_point() +                 #geometry
  theme_bw()                     #backgroud coordinate system
```

![](03-visualisation_files/figure-latex/unnamed-chunk-5-1.pdf)<!-- --> 

The first line above begins a plot by calling the `ggplot()` function, and putting the data into it. You have to name your dataframe with the `data` argument, and then, within the `aes()` command you pass the specific variables which you want to plot. In this case, we only want to see the distribution of one variable, banning orders, in the y axis and we will plot the club supported in the x axis. 

The second line is where we add the *geometry*. This is where we tell R what we want the graph to be. Here we say we want it to be points by using `geom_points`. You can see a list of all possible geoms [here](https://ggplot2.tidyverse.org/reference/). 

The third line is where we can tweak the display of the graph. Here I used `theme_bw()` which is a nice clean theme. You can try with other themes. To get a list of themes you can also see the resource [here](https://ggplot2.tidyverse.org/reference/ggtheme.html). If you want more variety you can explore the package [`ggthemes`](https://yutannihilation.github.io/allYourFigureAreBelongToUs/ggthemes/). 


```r
ggplot(data = fbo, aes(x = club_supported, y=banning_orders)) +     #data
   geom_point() +                                                   #geometry
  theme_dark()                                                      #backgroud coordinate system
```

![](03-visualisation_files/figure-latex/unnamed-chunk-6-1.pdf)<!-- --> 

Changing the theme is not all you can do with the third element. For example here you can't really read the axis labels, because they're all overlapping. One solution would be to rotate your axis labels 90 degrees, with the following code: `axis.text.x = element_text(angle = 90, hjust = 1)`. You pass this code to the `theme` argument. 


```r
ggplot(data = fbo, aes(x = club_supported, y=banning_orders)) + 
  geom_point() + 
  theme(axis.text.x = element_text(angle = 90, hjust = 1))                                   
```

![](03-visualisation_files/figure-latex/unnamed-chunk-7-1.pdf)<!-- --> 

OK what if we don't want it to be points, but instead we wanted it to be a bar graph?


```r
ggplot(data = fbo, aes(x = club_supported, y=banning_orders)) +   #data
  geom_bar(stat = "identity") +                                   #geometry
  theme(axis.text.x = element_text(angle = 90, hjust = 1))        #backgroud coordinate system
```

![](03-visualisation_files/figure-latex/unnamed-chunk-8-1.pdf)<!-- --> 

You might notice here we pass an argument `stat = "identity"` to `geo_bar()` function. This is because you can have a bar graph where the height of the bar shows frequency (`stat = "count"`), or where the height is taken from a variable in your dataframe (`stat = "identity"`). Here we specified a y-value (height) as the banning_orders variable. 

So this is cool! But what if I like both?

Well this is the beauty of the layering approach of `ggplot2`. You can layer on as many geoms as your little heart desires! XD


```r
ggplot(data = fbo, aes(x = club_supported, y=banning_orders)) + #data
  geom_bar(stat = "identity") +                                 #geometry 1 
  geom_point() +                                                #geometry 2
  theme(axis.text.x = element_text(angle = 90, hjust = 1))      #backgroud coordinate system
```

![](03-visualisation_files/figure-latex/unnamed-chunk-9-1.pdf)<!-- --> 

You can add other things too. For example you can add the mean number of *banning_orders*:


```r
ggplot(data = fbo, aes(x = club_supported, y=banning_orders)) +  #data
  geom_bar(stat = "identity") +                                  #geometry 1 
  geom_point() +                                                 #geometry 2
  geom_hline(yintercept = mean(fbo$banning_orders)) +            #mean line
  theme(axis.text.x = element_text(angle = 90, hjust = 1))       #backgroud coordinate system
```

![](03-visualisation_files/figure-latex/unnamed-chunk-10-1.pdf)<!-- --> 

This is basically all you need to know to build a graph! So far we have introduced a lot of code some of which you may not fully understand. Don't worry too much, we just wanted to give you a quick introduction to some of the possibilities. Later in the session we will go back to some of these functions in a slower way. The take away from this section is to understand the basic elements of the grammar of graphics.

## What graph should I use?

There are a lot of points to consider when you are choosing what graph to use to visually represent your data. There are some best practice guidelines, but at the end of the day, you need to consider what is best for your data. What do you want to show? What graph will best communicate your message? Is it a comparison between groups? Is it the frequency distribution of 1 variable? 

As some guidance, you can use the below [cheatsheet, taken from Nathan Yau's blog Flowingdata](https://flowingdata.com/2009/01/15/flow-chart-shows-you-what-chart-to-use/):

![](imgs/chart-chart.jpg)

However, keep in mind that this is more of a guideline, aimed to nudge you in the right direction. There are many ways to visualise the same data, and sometimes you might want to experiment with some of these, see what the differences are. 

There is also a vast amount of research into what works in displaying quantitative information. The classic book is by Edward Tufte [^1], but since him there are many other researchers as well who focus on approaches to displaying data. Two useful books you may want to consider are Few (2012) [^2] and Cairo (2016) [^3]. Claus Wilke is also producing a textbook freely available [in the internet](https://serialmentor.com/dataviz/).
These authors tend to produce recommendations on what to use (and not use) in certain contexts.  

For example, most data visualisation experts agree that you should not use 3D graphics unless there is a meaning to the third dimension. So using 3D graphics just for decoration, as in [this case](https://mir-s3-cdn-cf.behance.net/project_modules/disp/2505dd10837923.56030acd2ef20.jpg) is normally frowned upon. However there are cases when including a third dimension is vital to communicating your findings. See this [example](http://www.visualisingdata.com/2015/03/when-3d-works/).

Also often certain chart types are vilified. For example, the [*pie chart*](https://en.wikipedia.org/wiki/Pie_chart) is one such example. A lot of people (including your course leader) really dislike pie charts, e.g. see [here](http://www.storytellingwithdata.com/blog/2011/07/death-to-pie-charts) or [here](http://www.businessinsider.com/pie-charts-are-the-worst-2013-6?IR=T). If you want to display proportion, research indicates that a square pie chart is more likely to be interpreted correctly by viewers see [here](https://eagereyes.org/blog/2016/a-reanalysis-of-a-study-about-square-pie-charts-from-2009).

Also, in some cases bar plots (if used to visualise quantitative variables) can hide important features of your data, and might not be the most appropriate means for comparison: 

![](imgs/barbarplots.jpg)

This has lead to a [kickstarter campaign](https://www.kickstarter.com/projects/1474588473/barbarplots/description) around actually banning bar plots...!

So choosing the right plot and how to design the different elements of a plot is somehow of an art that requires practice and a good understanding of the data visualisation literature. Here we can only provide you with an introduction to some of these issues. At the end of the chapter we will also highlight additional resources you may want to explore on your own.

An important consideration is that the plot that you use depends on the data you are plotting, as well as the message you want to convey with the plot, the audience that is intended for, and even the format in which it will be presented (a website, a printed report, a power point presentation, etc.). So for example, returning again to the difference between number of banning orders between clubs in different leagues, what are some ways of plotting these?

One suggestion is to make a histogram for each one. You can use ggplot's `facet_wrap()` option to split graphs by a grouping variable. For example, to create a histogram of banning orders you write: 


```r
ggplot(data = fbo, aes(x = banning_orders)) + 
  geom_histogram()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-11-1.pdf)<!-- --> 

Now to split this by *league_of_the_club_supported*, you use `facet_wrap()` in the coordinate layer of the plot.


```r
ggplot(data = fbo, aes(x = banning_orders)) + 
  geom_histogram() + 
  facet_wrap(~league_of_the_club_supported)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-12-1.pdf)<!-- --> 

Well you can see there's different distribution in each league. But is this easy to compare? Maybe another approach would make it easier? 
Personally I like boxplots (we will explain them in greater detail below) for showing distribution. So let's try:


```r
ggplot(data = fbo, aes(x = league_of_the_club_supported, y = banning_orders)) + 
  geom_boxplot() 
```

![](03-visualisation_files/figure-latex/unnamed-chunk-13-1.pdf)<!-- --> 

This makes the comparison significantly easier, right? But the order is strange! Remember we talked about factors in previous weeks? Well the good thing about factors is that we can arrange them in their natural order. If we don't describe an order, then R uses the alphabetical order. So let's reorder our factor. To do that we are specifying the levels in the order in which we want to be embedded within the factor. We use code we introduced last week to do this.


```r
fbo$league_of_the_club_supported <- factor(fbo$league_of_the_club_supported, levels = c("Premier League", "Championship", "League One", "League Two", "Other clubs"))
```

And now create the plot again!


```r
ggplot(data = fbo, aes(x = league_of_the_club_supported, y = banning_orders)) + 
  geom_boxplot() 
```

![](03-visualisation_files/figure-latex/unnamed-chunk-15-1.pdf)<!-- --> 

Now this is great! We can see that the higher the league the more banning orders they have. Any ideas why?

We'll now go through some examples of making graphs using `ggplot2` package stopping a bit more on each of them. 

## Visualising numerical variables: Histograms

Histograms are useful ways of representing quantitative variables visually. 

As mentioned earlier, we will emphasise in this course the use of the `ggplot()` function. With `ggplot()` you start with a blank canvass and keep adding specific layers. The `ggplot()` function can specify the dataset and the aesthetics (the visual characteristics that represent the data). 

To get the data we're going to use here, load up the package `MASS` and then call the *Boston* data into your environment.


```r
library(MASS)
data(Boston)
```

This package has a dataframe called *Boston*. This has data about Housing Values in suburbs of Boston (USA). To access the codebook (how you find out what variables are) use the "?". 

OK so let's make a graph about the variable which represents the per capita crime rate by town (*crim*).

If you want to produce a histogram with the `ggplot` function you would use the following code:



```r
ggplot(Boston, aes(x = crim)) + 
  geom_histogram()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-17-1.pdf)<!-- --> 

So you can see that `ggplot` works in a way that you can add a series of additional specifications (layers, annotations). In this simple plot the `ggplot` function simply maps *crim* as the variable to be displayed (as one of the **aesthetics**) and the dataset. Then you add the `geom_histogram` to tell R that you want this variable to be represented as a histogram. Later we will see what other things you can add.

A histogram is simply putting cases in "bins" and then creates a bar for each bin. You can think of it as a *visual grouped frequency distribution*. The code we have used so far has used a bin-width of size range/30 as R kindly reminded us in the output. But you can modify this parameter if you want to get a rougher or a more granular picture. In fact, you should *always* play around with different specifications of the bin-width until you find one that tells the full story in a parsimonious way.


```r
ggplot(Boston, aes(x = crim)) +
  geom_histogram(binwidth = 1) 
```

![](03-visualisation_files/figure-latex/unnamed-chunk-18-1.pdf)<!-- --> 

We can pass arguments to the the geoms, as you see. Here we are changing the size of the bins (for further details on other arguments you can check the help files). Using bin-width of 1 we are essentially creating a bar for every one unit increase in the percent rate of crime. We can still see that most towns have a very low level of crime.

Let's sum the number of towns with a value lower than 1 in the per capita crime rate. We use the sum function for this, specifying we are only interested in adding cases where the value of the variable *crim* is lower than 1.


```r
sum(Boston$crim < 1)
```

```
## [1] 332
```

We can see that the large majority of towns, 332 out of 506, have a per capita crime rate below 1%. But we can also see that there are some towns that have a high concentration of crime. This is a spatial feature of crime; it tends to concentrate in particular areas and places. You can see how we can use visualisations to show the data and get a first feeling for how it may be distributed.

When plotting a continuous variable we are interested in the following features:

+ **Asymmetry**: whether the distribution is skewed to the right or to the left, or follows a more symmetrical shape.
+ **Outliers**: Are there one or more values that seem very unlike the others?
+ **Multimodality**: How many peaks has the distribution? More than one peak may indicate that the variable is measuring different groups.
+ **Impossibilities or other anomalies**: Values that are simply unrealistic given what we are measuring (e.g., somebody with an age of a 1000 years). Sometimes you may come across a distribution of data with a very high (and implausible) frequency count for a particular value. Maybe you measure age and you have a large number of cases aged 99 (which is often a code used for missing data).
+ **Spread**: this gives us an idea of variability in our data.

Often we visualise data because we want to compare distributions. **Most of data analysis is about making comparisons**. We are going to explore whether the distribution of crime in this dataset is different for less affluent areas. The variable *medv* measures in the Boston dataset the median value of owner-occupied homes. For the purposes of this illustration I want to dichotomise[^4] this variable, to create a group of towns with particularly low values versus all the others. For further details in how to recode variables with R you may want to read the relevant sections in [Quick R](http://www.statmethods.net/management/variables.html) or the [R Cookbook](http://www.cookbook-r.com/Manipulating_data/Recoding_data/). We will learn more about recoding and transforming variables in R soon.

How can we create a categorical variable based on information from a quantitative variable? Let's see the following code and pay attention to it and the explanation below.


```r
Boston$lowval[Boston$medv <= 17.02] <- "Low value" 
Boston$lowval[Boston$medv > 17.02] <- "Higher value"
```

First we tell R to create a new vector (*lowval*) in the Boston data frame. This vector will be assigned the character value "Low value" when the condition within the square brackets is met. That is, we are saying that whenever the value in *medv* is below 17.02 then the new variable *lowval* will equal "Low value". I have chosen 17.02 as this is the first quartile for *medv*. Then we tell R that when the value is greater than 17.02 we will assign those cases to a new textual category called "Higher Value".

The variable we created was a character vector (as we can see if we run the `class` function). so we are going to transform it into a factor using the `as.factor` function (many functions designed to work with categorical variables expect a factor as an input, not just a character vector). If we rerun the `class` function we will see we changed the original variable


```r
class(Boston$lowval)
```

```
## [1] "character"
```

```r
Boston$lowval <- as.factor(Boston$lowval)
class(Boston$lowval)
```

```
## [1] "factor"
```

Now we can produce the plot. We will do this using **facets**. Facets are another element of the grammar of graphics, we use it to define subsets of the data to be represented as multiple groups, here we are asking R to produce two plots defined by the two levels of the factor we just created.


```r
ggplot(Boston, aes(x = crim)) +
  geom_histogram(binwidth = 1) +
  facet_grid(lowval ~ .) 
```

![](03-visualisation_files/figure-latex/unnamed-chunk-22-1.pdf)<!-- --> 

Visually this may not look great, but it begins to tell a story. We can see that there is a considerable lower proportion of towns with low levels of crime in the group of towns that have cheaper homes. It is a flatter, less skewed distribution. You can see how the `facet_grid()` expression is telling R to create the histogram of the variable mentioned in the `ggplot` function for the groups defined by the categorical input of interest (the factor *lowval*).

We could do a few things that may perhaps help to emphasise the comparison like, for example, adding colour to each of the groups.


```r
ggplot(Boston, aes(x = crim, fill = lowval)) +
  geom_histogram(binwidth = 1) +
  facet_grid(lowval ~ .) +
  theme(legend.position = "none")
```

![](03-visualisation_files/figure-latex/unnamed-chunk-23-1.pdf)<!-- --> 

The `fill` argument within the `aes` is telling R what variable to assign colours. Now each of the levels (groups) defined by the *lowval* variable will have a different colour. The `theme` statement that we add is telling R not to place a legend in the graphic explaining that red is higher value and the greenish colour is low value. We can already see that without a label.

Instead of using facets, we could overlay the histograms with a bit of transparency. Transparencies work better when projecting in screens than in printed document, so keep in mind this when deciding whether to use them instead of facets. The code is as follows:


```r
ggplot(Boston, aes(x = crim, fill = lowval)) + 
  geom_histogram(position = "identity", alpha = 0.4)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-24-1.pdf)<!-- --> 

In the code above, the `fill` argument identifies again the factor variable in the dataset grouping the cases. Also, `position = identity` tells R to overlay the distributions and `alpha` asks for the degree of transparency, a lower value (e.g., 0.2) will be more transparent.

In this case, part of the problem we have is that the skew can make it difficult to appreciate the differences. When you are dealing with skewed distributions such as this, it is sometimes convenient to use a transformation [^5]. We will come back to this later this semester. For now suffice to say, that taking the logarithm of a skewed variable helps to reduce the skew and to see patterns more clearly. In order to visualise the differences here a bit better we could ask for the logarithm of the crime per capita rate. Notice how I also add a constant of 1 to the variable *crim*, this is to avoid NA values in the newly created variable if the value in *crim* is zero (you cannot take the log of 0).


```r
ggplot(Boston, aes(x = log10(crim + 1), fill = lowval)) +
  geom_histogram(position = "identity", alpha = 0.4)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-25-1.pdf)<!-- --> 

The plot now is a bit clearer. It seems pretty evident that the distribution of crime is quite different between these two types of towns.

## Visualising numerical variables: Density plots

For smoother distributions, you can use density plot. You should have a healthy amount of data to use these or you could end up with a lot of unwanted noise. Let's first look at the single density plot for all cases. Notice all we are doing is invoking a different kind of geom:


```r
ggplot(Boston, aes(x = crim)) +
  geom_density() 
```

![](03-visualisation_files/figure-latex/unnamed-chunk-26-1.pdf)<!-- --> 

In a density plot, we attempt to visualize the underlying probability distribution of the data by drawing an appropriate continuous curve. So in a density plot then the area under the lines sum to 1 and the Y, vertical, axis now gives you the estimated (guessed) probability for the different values in the X, horizontal, axis. This curve is guessed from the data and the method we use for this guessing or estimation is called kernel density estimation. You can read more about density plots [here](https://serialmentor.com/dataviz/histograms-density-plots.html).

In this plot we can see that there is a high estimated probability of observing a town with near zero per capita crime rate and a low estimated probability of seeing towns with large per capita crime rates. As you can observe it provides a smoother representation of the distribution (as compared to the histograms).

You can also use this to compare the distribution of a quantitative variable across the levels in a categorical variable (factor) and, as before, is possibly better to take the log of skewed variables such as crime:


```r
#We are mapping "lowval" as the variable colouring the lines 
ggplot(Boston, aes(x = log10(crim + 1), colour = lowval)) + 
  geom_density() 
```

![](03-visualisation_files/figure-latex/unnamed-chunk-27-1.pdf)<!-- --> 

Or you could use transparencies:


```r
ggplot(Boston, aes(x = log10(crim + 1), fill = lowval)) + 
  geom_density(alpha = .3)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-28-1.pdf)<!-- --> 

Did you notice the difference with the comparative histograms? By using density plots we are rescaling to ensure the same area for each of the levels in our grouping variable. This makes it easier to compare two groups that have different frequencies. The areas under the curve add up to 1 for both of the groups, whereas in the histogram the area within the bars represent the number of cases in each of the groups. If you have many more cases in one group than the other it may be difficult to make comparisons or to clearly see the distribution for the group with fewer cases. So, this is one of the reasons why you may want to use density plots.

Density plots are a good choice when you want to compare up to three groups. If you have many more groups you may want to consider other alternatives. One such alternative is the **ridgeline plot**, also often called the Joy Division plot (since it was immortalised in the cover of one of their albums):

![](imgs/joydivision.png)

They can be produced with the `ggridges` package. Before we dichotomised the variable *medv* in a manual way, we can use more direct ways of splitting numerical variables into various categories using information already embedded on them. Say we want to split *medv* into deciles. We could use the `mutate` function in `dplyr` for this.


```r
library(dplyr)
Boston <- mutate(Boston, dec_medv = ntile(medv, 10))
```

The `mutate` function adds a new variable to our existing data frame object. We are naming this variable *dec_medv* because we are going to split *medv* into ten groups of equal size (this name is arbitrary, you may call it something else). To do this we will use the `ntile` function as an argument within mutate. We will define the new *dec_medv* variable explaining to R that this variable will be the result of passing the `ntile` function to *medv*. So that `ntile` breaks *medv* into 10 we pass this value as an argument to the function. So that the result of executing `mutate` are stored, we assign this to the *Boston* object.

Check the results:


```r
table(Boston$dec_medv)
```

```
## 
##  1  2  3  4  5  6  7  8  9 10 
## 51 51 51 51 51 51 50 50 50 50
```

We can now use this new variable to illustrate the use of the `ggridge` package. First you will need to install this package and then load it. You will see all this package does is to extend the functionality of `ggplot2` by adding a new type of geom. Here the variable defining the groups needs to be a factor, so we will tell `ggplot` to treat *dec_medv* as a factor using `as.factor`. Using `as.factor` in this way save us from having to create yet another variable that we are going to store as a factor. Here we are not creating a new variable, we are just telling R to treat this numeric variable *as if* it were a factor. Make sure you understand this difference.


```r
library(ggridges)
ggplot(Boston, aes(x = log10(crim + 1), y = as.factor(dec_medv))) + geom_density_ridges()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-31-1.pdf)<!-- --> 

We can see that the distribution of crime is particularly different when we focus in the three deciles with the lowest level of income. For more details on this kind of plot you can read the [vignette](https://cran.r-project.org/web/packages/ggridges/vignettes/introduction.html) for this package.

## Visualising numerical variables: Box plots

[Box plots](http://tomhopper.me/2014/07/04/the-most-useful-data-plot-youve-never-used/) are an interesting way of presenting the 5 number summary (the minimum value, the first quartile, the median, the third quartile, and the maximum value of a set of numbers) in a visual way.  If we want to use `ggplot` for plotting a single numerical variable we need some convoluted code, since `ggplot` assumes you want a boxplot to compare various groups. Therefore we need to set some arbitrary value for the grouping variable and we also may want to remove the x-axis tick markers and label. 

For this illustration, I am going to display the distribution of the median value of property in the various towns instead of crime.


```r
ggplot(Boston, aes(x = 1, y = medv)) + 
  geom_boxplot() +
  scale_x_continuous(breaks = NULL) + #removes the tick markers from the x axis
  theme(axis.title.x = element_blank())
```

![](03-visualisation_files/figure-latex/unnamed-chunk-32-1.pdf)<!-- --> 

Boxplots, however, really come to life when you do use them to compare the distribution of a quantitative variable across various groups. Let's look at the distribution of *log(crime)* across cheaper and more expensive areas:


```r
ggplot(Boston, aes(x = lowval, y=log10(crim + 1))) +
  geom_boxplot()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-33-1.pdf)<!-- --> 

With a boxplot like this you can see straight away that the bulk of cheaper areas are very different from the bulk of more expensive areas. The first quartile of the distribution for low areas about matches the point at which we start to see **outliers** for the more expensive areas.

This can be even more helpful when you have various groups. Let's try an example using the *BCS0708* data frame. This is a dataset from the 2007/08 British Crime Survey.You can use the code below to download it. 


```r
##R in Windows have some problems with https addresses, that's why we need to do this first:
urlfile<-'https://raw.githubusercontent.com/eonk/dar_book/main/datasets/BCS0708.csv'
#We create a data frame object reading the data from the remote .csv file
BCS0708<-read.csv(url(urlfile))
```

This dataset contains a quantitative variable that measures the level of worry for crime (*tcviolent*): high scores represent high levels of worry. We are going to see how the score in this variable changes according to ethnicity (*ethgrp2*).


```r
#A comparative boxplot of ethnicity and worry about violent crime
ggplot(BCS0708, aes(x = ethgrp2, y = tcviolent)) +
  geom_boxplot()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-35-1.pdf)<!-- --> 

Nice. But could be nicer. To start with we could order the groups along the X axis so that the ethnic groups are positioned according to their level of worry. Secondly, we may want to exclude the information for the NA cases on ethnicity (represented by a flat line).


```r
#A nicer comparative boxplot (excluding NA and reordering the X variable)
ggplot(filter(BCS0708, !is.na(ethgrp2) & !is.na(tcviolent)), 
       aes(x = reorder(ethgrp2, tcviolent, FUN = median), y = tcviolent)) +
        geom_boxplot()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-36-1.pdf)<!-- --> 

The `filter` function from `dplyr` is using a logical argument to tell R to only use the cases that do not have NA values in the two variables that we are using. The exclamation mark followed by `is.na` and then the name of a variable is R way of saying "the contrary of is NA for the specified variable". So in essence we are saying to R just look at data that is not NA in these variables. The `reorder` function on the other hand is asking R to reorder the levels in ethnicity according to the median value of worry of violent crime. Since we are using those functions *within* the `ggplot` function this subsetting and this reordering (as with `as.factor` earlier) are not introducing permanent changes in your original dataset. If you prefer to reorder according to the mean you only need to change that parameter after the `FUN` option (e.g, `FUN = mean`).

## Exploring relationships between two quantitative variables: scatterplots

So far we have seen how you can use histograms, density plots and boxplots to plot numerical variables and to compare groups in relation to numerical variables. Another way of saying that is that you can use comparative histograms, density plots, or boxplots to assess the relationship between a numerical variable and a categorical variable (the variable that defines the groups). How do you explore the relationship between two numerical variables?

When looking at the relationship between two quantitative variables nothing beats the **scatterplot**. [This](http://www.datavis.ca/papers/friendly-scat.pdf) is a lovely article in the history of the scatterplot.

A scatterplot plots one variable in the Y axis, and another in the X axis. Typically, if you have a clear outcome or response variable in mind, you place it in the Y axis, and you place the explanatory variable in the X axis. 

This is how you produce a scatterplot with `ggplot()`:


```r
#A scatterplot of crime versus median value of the properties
ggplot(Boston, aes(x = medv, y = crim)) +
  geom_point()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-37-1.pdf)<!-- --> 

Each point represents a case in our dataset and the coordinates attached to it in this two dimensional plane are given by their value in the Y (crime) and X (median value of the properties) variables. 

What do you look for in a scatterplot? You want to assess global and local patterns, as well as deviations. We can see clearly that at low levels of *medv* there is a higher probability in this data that the level of crime is higher. Once the median value of the property hits $30,000 the level of crime is nearly zero for all towns. So far so good, and surely predictable. The first reason why we look at scatterplots is to check our hypothesis (e.g., poorer areas, more crime).

However, something odd seems to be going on when the median property value is around $50,000. All of the sudden the variability for crime goes up. We seem to have some of the more expensive areas also exhibiting some fairly decent level of crime. In fact, there is quite a break in the distribution. What's going on? To be honest I have no clue. But the pattern at the higher level of property value is indeed odd, it is just too abrupt to be natural. 

This is the second reason why you want to plot your data before you do anything else. It helps you to detect apparent anomalies. I say this is an anomaly because the break in pattern is quite noticeable and abrupt. It is hard to think of a natural process that would generate this sudden radical increase in crime once the median property value reaches the 50k dollars mark. If you were analysing this for real, you would want to know what's really driving this pattern (e.g., find out about the original data collection, the codebook, etc.): perhaps the maximum median value was capped at 50K dollars and we are seeing this as a dramatic increase when the picture is more complex? For now we are going to let this rest.

One of the things you may notice with a scatterplot is that even with a smallish dataset such as this, with just about 500 cases, **overplotting** may be a problem. When you have many cases with similar (or even worse the same) value, it is difficult to tell them apart. Imagine there is only 1 case with a particular combination of X and Y values. What you see? A single point. Then imagine you have 500 cases with that same combination of values for X and Y. What do you see? Still a single point. There's a variety of ways for dealing with overplotting. One possibility is to add some **transparency** to the points:


```r
ggplot(Boston, aes(x = medv, y = crim)) +
  geom_point(alpha=.4) #you will have to test different values for alpha
```

![](03-visualisation_files/figure-latex/unnamed-chunk-38-1.pdf)<!-- --> 

Why this is an issue may be more evident with the `BCS0708 data`. Compare the two plots:


```r
ggplot(BCS0708, aes(x = age, y = tcviolent)) +
  geom_point()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-39-1.pdf)<!-- --> 


```r
ggplot(BCS0708, aes(x = age, y = tcviolent)) +
  geom_point(alpha=.2)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-40-1.pdf)<!-- --> 

The second plot gives us a better idea of where the observations seem to concentrate in a way that we could not see with the first.

Overplotting can occur when a continuous measurement is rounded to some convenient unit. This has the effect of changing a continuous variable into a discrete ordinal variable. For example, age is measured in years and body weight is measured in pounds or kilograms. Age is a discrete variable, it only takes integer values. That's why you see the points lined up in parallel vertical lines. This also contributes to the overplotting in this case. 

One way of dealing with this particular problem is by **jittering**. Jittering is the act of adding random noise to data in order to prevent overplotting in statistical graphs. In `ggplot` one way of doing this is by passing an argument to `geom_point` specifying you want to jitter the points. This will introduce some random noise so that *age* looks less discrete.


```r
ggplot(BCS0708, aes(x = age, y = tcviolent)) +
  geom_point(alpha=.2, position="jitter") #Alternatively you could replace geom_point() with geom_jitter() in which case you don't need to specify the position
```

![](03-visualisation_files/figure-latex/unnamed-chunk-41-1.pdf)<!-- --> 

Another alternative for solving overplotting is to **bin the data** into rectangles and map the density of the points to the fill of the colour of the rectangles.


```r
ggplot(BCS0708, aes(x = age, y = tcviolent)) +
  stat_bin2d()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-42-1.pdf)<!-- --> 


```r
#The same but with nicer graphical parameters
ggplot(BCS0708, aes(x = age, y = tcviolent)) +
  stat_bin2d(bins=50) + #by increasing the number of bins we get more granularity
  scale_fill_gradient(low = "lightblue", high = "red") #change colors
```

![](03-visualisation_files/figure-latex/unnamed-chunk-43-1.pdf)<!-- --> 

What this is doing is creating boxes within the two dimensional plane; counting the number of points within those boxes; and attaching a colour to the box in function of the density of points within each of the rectangles.

When looking at scatterplots, sometimes it is useful to summarise the relationships by mean of drawing lines. You could for example add a line representing the **conditional mean**. A conditional mean is simply mean of your Y variable for each value of X. Let's go back to the Boston dataset. We can ask R to plot a line connecting these means using `geom_line()` and specifying you want the conditional means.


```r
ggplot(Boston, aes(x = medv, y = crim)) +
  geom_point(alpha=.4) +
  geom_line(stat='summary', fun.y=mean)
```

```
## Warning: Ignoring unknown parameters: fun.y
```

![](03-visualisation_files/figure-latex/unnamed-chunk-44-1.pdf)<!-- --> 

With only about 500 cases there are loads of ups and downs. If you have many more cases for each level of X the line would look less rough. You can, in any case, produce a smoother line using `geom_smooth` instead. We will discuss later this semester how this line is computed (although you will see the R output tells you, you are using something call the "loess" method). For now just know that is a line that tries to *estimate*, to guess, the typical value for Y for each value of X.


```r
ggplot(Boston, aes(x = medv, y = crim)) +
  geom_point(alpha=.4) +
  geom_smooth(colour="red", size=1, se=FALSE) #We'll explain later this semester what the se argument does, colour is simply asking for a red line instead of blue (which I personally find harder to see. I'm also making the line a bit thicker with size 1)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-45-1.pdf)<!-- --> 

As you can see here you produce a smoother line than with the conditional means. The line, as the scatterplot, seems to be suggesting an overall curvilinear relationship that almost flattens out once property values hit $20k. 

## Scatterplots conditioning in a third variable

There are various ways to plot a third variable in a scatterplot. You could go 3D and in some contexts that may be appropriate. But more often than not it is preferable to use only a two dimensional plot.

If you have a grouping variable you could map it to the colour of the points as one of the aesthetics arguments. Here we return to the *Boston* scatterplot but will add a third variable, that indicates whether the town is located by the river or not.


```r
#Scatterplot with two quantitative variables and a grouping variable, we are telling R to tell "chas", a numeric vector, as a factor. 
ggplot(Boston, aes(x = medv, y = crim, colour = as.factor(chas))) +
  geom_point() 
```

![](03-visualisation_files/figure-latex/unnamed-chunk-46-1.pdf)<!-- --> 

Curiously, we can see that there's quite a few of those expensive areas with high levels of crime that seem to be located by the river. Maybe that is a particularly attractive area?

As before you can add smooth lines to capture the relationship. What happens now, though, is that `ggplot` will produce a line for each of the levels in the categorical variable grouping the cases:


```r
ggplot(Boston, aes(x = medv, y = crim, colour = as.factor(chas))) +
  geom_point(alpha=.4) + #I am doing the points semi-transparent to see the lines better
  geom_smooth(se=FALSE, size=1) #I am doing the lines thicker to see them better
```

![](03-visualisation_files/figure-latex/unnamed-chunk-47-1.pdf)<!-- --> 

You can see how the relationship between crime and property values is more marked for areas not bordering the river, mostly because you have considerably fewer cheaper areas bordering the river. Notice as well the upward trend in the green line at high values of *medv*. As we saw there seems to be quite a few of those particularly more expensive areas that have high crime and seem to be by the river.

We can also map a quantitative variable to the colour aesthetic. When we do that, instead of different colours for each category we have a gradation in colour from darker to lighter depending on the value of the quantitative variable. Below we display the relationship between crime and property values conditioning on the status of the area (high values in *lstat* represent lower status).


```r
ggplot(Boston, aes(x = medv, y = crim, colour = lstat)) +
  geom_point() 
```

![](03-visualisation_files/figure-latex/unnamed-chunk-48-1.pdf)<!-- --> 

As one could predict *lstat* and *medv* seem to be correlated. The areas with low status tend to be the areas with cheaper properties (and more crime) and the areas with higher status tend to be the areas with more expensive properties (and less crime).

You could map the third variable to a different aesthetic (rather than colour). For example, you could map *lstat* to size of the points. This is called a **bubblechart**. The problem with this, however, is that it can make overplotting more acute sometimes.


```r
ggplot(Boston, aes(x = medv, y = crim, size = lstat)) +
  geom_point() #You may want to add alpha for some transparency here.
```

![](03-visualisation_files/figure-latex/unnamed-chunk-49-1.pdf)<!-- --> 

If you have larger samples and the patterns are not clear (as we saw when looking at the relationship between age and worry of violent crime) conditioning in a third variable can produce hard to read scatterplots (even if you use transparencies and jittering). Let's look at the relationship between worry for violent crime and age conditioned on victimisation during the previous year:


```r
ggplot(BCS0708, aes(x = age, y = tcviolent, colour = bcsvictim)) +
  geom_point(alpha=.4, position="jitter")
```

![](03-visualisation_files/figure-latex/unnamed-chunk-50-1.pdf)<!-- --> 

You can possibly notice that there are more green points in the left hand side (since victimisation tend to be more common among youth). But it is hard to read the relationship with age. We could try to use facets instead using `facet_grid`?


```r
ggplot(BCS0708, aes(x = age, y = tcviolent)) +
  geom_point(alpha=.4, position="jitter") +
  facet_grid( .~ bcsvictim)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-51-1.pdf)<!-- --> 

It is still hard to see anything, though perhaps you can notice the lower density the points in the bottom right corner in the facet displaying victims of crime. In a case like this may be helpful to draw a smooth line


```r
ggplot(BCS0708, aes(x = age, y = tcviolent, colour = bcsvictim)) +
  geom_point(alpha=.1, position="jitter") +
  geom_smooth(size=1.5, se=FALSE)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-52-1.pdf)<!-- --> 

What we see here is that for the most part the relationship of age and worry for violent crime looks quite flat, regardless of whether you have been a victim of crime or not. At least, for most people. However, once we get to the 60s things seem to change a bit. Those over 62 that have not been a victim of crime in the past year start to manifest a lower concern with crime as they age (in comparison with those that have been a victim of crime).

## Scatterplot matrix

Sometimes you want to produce many scatterplots simultaneously to have a first peak at the relationship between the various variables in your data frame. The way to do this is by using a scatterplot matrix. There are some packages that are particularly good for this. One of them is `GGally`, basically an extension for `ggplot2`.

Not to overcomplicate things we will only use a few variables from the *Boston* dataset:


```r
#I create a new data frame that only contains 4 variables included in the Boston dataset and I am calling this new data frame object Boston_spm
Boston_spm <- dplyr::select(Boston, crim, medv, lstat)
```

Then we load `ggpairs` and use run the scatterplot matrix using the `ggpairs` function:


```r
library(GGally)
ggpairs(Boston_spm)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-54-1.pdf)<!-- --> 

The diagonal set of boxes that go from the top left to the bottom right gives you the univariate density plot for each of the variables. So, for example, at the very top left you have the density plot for the *crim* variable. If you look underneath this one, you see a scatterplot between *crim* and *medv*. In this case *crim* defines the X axis and *medv* the Y axis, which is why it looks a bit different from the one we saw earlier. The labels in the top and the left tell you what variables are plot in each faceted rectangle. I the top right hand side of this matrix you see that the rectangles say "corr" and the give you a number. These numbers are **correlation coefficients**, which are a metric we use to indicate the strength of a relationship between two quantitative or numeric variables. The close to 1.000 (whether positive or negative) this value is the stronger the relationship is. The closer to zero the weaker the relationship. The stronger relationship here is between *medv* and *istat* (correlation coefficient value: -0.738). The fact that is negative indicates that as the values in one increase, the values in the other tend to decrease. So high values of crime correspond to low values of property prices -as we saw earlier. This coefficient is a summary number of this relationship. We will come back to it later on. For now keep in mind this metric only works well is the relationship should see in the scatterplot is well represented by a straight line. If the relationship is curvilinear it will be a very bad metric that you should not trust.

![](imgs/ggpairs.png){width=80%}

R gives you a lot of flexibility and there are often competing packages that aim to do similar things. So, for example, for a scatterplot matrix you could also use the `spm` function from the `car` package.


```r
library(car)
 #The regLine argument is used to avoid displaying something we will cover in week 8, regression analysis.
spm(Boston_spm, regLine=FALSE)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-55-1.pdf)<!-- --> 

This is a bit different from the one above because rather than displaying the values of correlation coefficient, what you get is another set of scatterplot but with the Y and X axis rotated. You can see the matrix is symmetrical. So the first scatterplot that you see in the top row (second column from the left) shows the relationship between *medv* (in the X axis) and *crim* (in the Y axis). Which is the same relationship shown in the first scatterplot in the second row (first column), only here *crim* defines the X axis and *medv* the Y axis. In this scatterplot you can see, although not very well, that smoothed lines representing the relationship have been added to the plots.


```r
library(car)
spm(Boston_spm, smooth=list(col.smooth="red"), regLine=FALSE)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-56-1.pdf)<!-- --> 

And you can also condition in a third variable. For example, we could condition on whether the areas bound the Charles River (variable *chas*).


```r
Boston_spm <- dplyr::select(Boston, crim, medv, lstat, chas)
spm(~crim+medv+lstat, data=Boston_spm, groups=Boston_spm$chas, by.groups=TRUE, smooth=FALSE, regLine=FALSE)
```

![](03-visualisation_files/figure-latex/unnamed-chunk-57-1.pdf)<!-- --> 

Getting results, once you get the knack of it, is only half of the way. The other, and more important, half is trying to make sense of the results. What are the stories this data is telling us?  R cannot do that for you. For this you need to use a better tool: **your brain** (scepticism, curiosity, creativity, a lifetime of knowledge) and what Kaiser Fung calls ["numbersense"](http://www.amazon.co.uk/Numbersense-How-Data-Your-Advantage/dp/0071799664).

## Titles, legends, and themes in ggplot2

We have introduced a number of various graphical tools, but what if you want to customise the way the produce graphic looks like? Here I am just going to give you some code for how to modify the titles and legends you use. For adding a title for a `ggplot` graph you use `ggtitle()`.


```r
#Notice how here we are using an additional function to ask R to treat the variable chas, which is numeric in our dataset, as if it were a factor (as.factor()). You need to do this if your variable is categorical but is encoded as numeric in your dataframe.
ggplot(Boston, aes(x = medv, y = crim, colour = as.factor(chas))) +
  geom_point() +
  ggtitle("Fig 1.Crime, Property Value and River Proximity of Boston Towns")
```

![](03-visualisation_files/figure-latex/unnamed-chunk-58-1.pdf)<!-- --> 

If you don't like the default background theme for `ggplot` you can use a theme as discussed at the start, for example with creating a black and white background by adding `theme_bw()` as a layer:


```r
ggplot(Boston, aes(x = medv, y = crim, colour = as.factor(chas))) +
  geom_point() +
  ggtitle("Fig 1.Crime, Property Value and River Proximity of Boston Towns") +
  theme_bw()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-59-1.pdf)<!-- --> 

As we said earlier `ggthemes` gives you additional themes you could use. So, for example, you can use the style inspired by *The Economist* magazine.


```r
library(ggthemes)
ggplot(Boston, aes(x = medv, y = crim, colour = as.factor(chas))) +
  geom_point() +
  ggtitle("Fig 1.Crime, Property Value and River Proximity of Boston Towns") +
  theme_economist()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-60-1.pdf)<!-- --> 

Using `labs()` you can change the text of axis labels (and the legend title), which may be handy if your variables have cryptic names. Equally you can manually name the labels in a legend. The value for *chas* are 0 and 1. This is not informative. We can change that.


```r
ggplot(Boston, aes(x = medv, y = crim, colour = as.factor(chas))) +
  geom_point() +
  ggtitle("Fig 1.Crime, Property Value and River Proximity of Boston Towns") +
  labs(x = "Median Property Value (in US Dollars x 1000)",
       y = "Per capita crime rate",
       colour = "Borders the river") +
  scale_colour_discrete(labels = c("No", "Yes"))
```

![](03-visualisation_files/figure-latex/unnamed-chunk-61-1.pdf)<!-- --> 

Sometimes you may want to present several plots together. For this the `gridExtra` package is very good. You will first need to install it and then load it. You can then create several plots and put them all in the same image.


```r
#You may need to install first with install.packages("gridExtra")
library(gridExtra)
#Store your plots in various objects
p1 <- qplot(x=crim, data=Boston)
p2 <- qplot(x=indus, data=Boston)
p3 <- qplot(x=medv, data=Boston)
#Then put them all together using grid.arrange()
grid.arrange(p1, p2, p3, ncol=3) #ncol tells R we want them side by side, if you want them one in top of the other try ncol=1, in this case, however ncol=2 would possibly be the better solution. Try it!
```

![](03-visualisation_files/figure-latex/unnamed-chunk-62-1.pdf)<!-- --> 

We don't have time to get into the detail of all the customisation features available for `ggplot2`. You can find some [additional solutions](https://bbc.github.io/rcookbook/) in the cookbook put together by the data journalists at the BBC or in Kieran Healy free online [book](https://socviz.co/).

## Plotting categorical data: bar charts

You may be wondering what about categorical data? So far we have only discussed various visualisations where at least one of your variables is quantitative. When your variable is categorical you can use bar plots (similar to histograms). We map the factor variable in the aesthetics and then use the `geom_bar()` function to ask for a bar chart.


```r
ggplot(BCS0708, aes(x=walkday)) +
  geom_bar()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-63-1.pdf)<!-- --> 

You can see in the Y axis the label *count*. This is not a variable in your data. When you run a `geom_bar` like this you are invoking as a hidden default a call to the `stat_` function. In this case what is happening is that this function is *counting* the number of cases in each of the levels of *walkday* and this count is what is used to map the height of each of the bars.

The `stat_` function apart from counting the cases in each levels computes their relative frequency, their proportion, and stores this information in a temporal variable called *..prop..*. If we want this variable to be represented in the Y axis we can change the code as shown below:


```r
ggplot(BCS0708, aes(x=walkday)) +
  geom_bar(mapping = aes(y = ..prop..))
```

![](03-visualisation_files/figure-latex/unnamed-chunk-64-1.pdf)<!-- --> 
As Kieran Helay (2018) indicates:

*"The resulting plot is still not right. We no longer have a count on the y-axis, but the proportions of the bars all have a value of 1, so all the bars are the same height. We want them to sum to 1, so that we get the number of observations per" (level) "as a proportion of the total number of observations. This is a grouping issue again...  we need to tell ggplot to ignore the x-categories when calculating denominator of the proportion, and use the total number observations instead. To do so we specify group = 1 inside the `aes()` call. The value of 1 is just a kind of “dummy group” that tells ggplot to use the whole dataset when establishing the denominator for its prop calculations."*


```r
ggplot(BCS0708, aes(x=walkday)) +
  geom_bar(mapping = aes(y = ..prop.., group = 1))
```

![](03-visualisation_files/figure-latex/unnamed-chunk-65-1.pdf)<!-- --> 

Unfortunately, the levels in this factor are ordered by alphabetical order, which is confusing. We can modify this by reordering the factors levels first -click [here](http://www.cookbook-r.com/Manipulating_data/Changing_the_order_of_levels_of_a_factor/) for more details. You could do this within the `ggplot` function (just for the visualisation), but in real life you would want to sort out your factor levels in an appropriate manner more permanently. As discussed last week, this is the sort of thing you do as part of pre-processing your data. And then plot.


```r
#Print the original order
print(levels(BCS0708$walkday))
```

```
## NULL
```


```r
#Reordering the factor levels from very safe to very unsafe (rather than by alphabet). Notice that I am creating a new variable, it is often not unwise to do this to avoid messing up your original data.
BCS0708$walkdayR <- factor(BCS0708$walkday, levels=c('very safe',
  'fairly safe','a bit unsafe','or very unsafe'))
#Plotting the variable again (and subsetting out the NA data)
ggplot(subset(BCS0708, !is.na(walkdayR)), aes(x=walkdayR)) +
  geom_bar(mapping = aes(y = ..prop.., group = 1))
```

![](03-visualisation_files/figure-latex/unnamed-chunk-67-1.pdf)<!-- --> 

We can also map a second variable to the aesthetics, for example, let's look at ethnicity in relation to feelings of safety. For this we produce a **stacked bar chart**.


```r
bcs_bar <-filter(BCS0708, !is.na(walkdayR), !is.na(ethgrp2))
ggplot(data=bcs_bar, aes(x=walkdayR, fill=ethgrp2)) +
  geom_bar()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-68-1.pdf)<!-- --> 

These sort of stacked bar charts are not terribly helpful if you are interested in understanding the relationship between these two variables. It is hard to see if any group is proportionally more likely to feel safe or not.

Instead what you want is a different kind of stacked bar chart, that gives you the proportion of your "explanatory variable" (ethnicity) within each of the levels of your "response variable" (here feelings of safety).


```r
ggplot(data=bcs_bar, aes(x=walkdayR, fill=ethgrp2)) +
  geom_bar(position = "fill")
```

![](03-visualisation_files/figure-latex/unnamed-chunk-69-1.pdf)<!-- --> 

Now we can more easily compare proportions across groups, since all the bars have the same height. But it is more difficult to see how many people there are within each level of the X variable.


```r
p <- ggplot(data=bcs_bar, aes(x=walkdayR, fill=ethgrp2)) + geom_bar(position = "dodge",
             mapping = aes(y = ..prop.., group = ethgrp2))
p
```

![](03-visualisation_files/figure-latex/unnamed-chunk-70-1.pdf)<!-- --> 

Now we have a bar chart where the values of ethnicity are broken down across the levels of fear of crime, with a proportion showing on the y-axis. Looking at the bars you will see that they do not sum to one within each level of fear. Instead, the bars for any particular ethnicity sum to one across all the levels of fear. You can see for example that nearly 75% of the White respondents are in the "Very Safe" level, whereas for example less than 60% of the Black respondents feel "Very Safe".

Sometimes, you may want to flip the axis, so that the bars are displayed horizontally. You can use the `coord_flip()` function for that.


```r
#First we invoke the plot we created and stored earlier and then we add an additional specification with coord_flip()
p + coord_flip()
```

![](03-visualisation_files/figure-latex/unnamed-chunk-71-1.pdf)<!-- --> 

You can also use `coord_flip()` with other `ggplot` plots (e.g., boxplots).

A particular type of bar chart is the divergent stacked bar chart, often used to visualise [**Likert scales**](http://en.wikipedia.org/wiki/Likert_scale). You may want to look at some of the options available for it via the [HH package](http://www.jstatsoft.org/v57/i05/paper), or [sjPlot](http://strengejacke.wordpress.com/2013/07/17/plotting-likert-scales-net-stacked-distributions-with-ggplot-rstats/). But we won't cover them here in detail.

Keep in mind that knowing *how* to get R to produce a particular visualisation is only half the job. The other half is knowing *when* to produce a particular kind of visualisation. [This blog](https://solomonmg.github.io/post/when-to-use-stacked-barcharts/), for example, discusses some of the problems with stacked bar charts and the exceptional circumstances in which you may want to use them.

There are other tools sometimes used for visualising categorical data. Pie charts is one of them. However, as mentioned at the beginning, many people advocate strongly against using pie charts and therefore this is the only pie chart you will see in this course:

![cute pie chart](imgs/piechart.jpg)


What I would use instead are **waffle charts**. They're super easy to make with the "waffle" package but I don't think there's time for them at this point, but look into them [here](https://www.r-bloggers.com/making-waffle-charts-in-r-with-the-new-waffle-package/). 

## Further resources

By now you should know the path to data analysis wisdom will take time. The good news is that we live in a time where there are multiple (very often free) resources to help you along the way. The time where this knowledge was just the preserve of a few is long distant. If you are a motivated and disciplined person there is a lot that you can do to further consolidate and expand your data visualisation skills without spending money. I already recommended you the excellent `ggplot2` online documentation. Here we just want to point you to a a few useful resources that you can pursue in the future. 

First **MOOCS (Massive Online Open Courses)**. There are loads of useful MOOCS that provide training in data visualisation for free (well, you can pay if you want a certificate, but you can also use the resources and learn for free).

+ [Information visualisation](https://www.coursera.org/specializations/information-visualization). This course offers an introduction to some more advanced concepts to those presented in our tutorial. It also covers more advanced software for visualisations in the web.

+ You may also want to keep your eyes open for any new edition of Alberto Cairo's MOOC on ["Data Visualisation for Storytelling and Discovery"](https://journalismcourses.org/data-viz-course-material.html) which covers not the software but the principles and theory of good static and interactive visualisation. But you can find the free materials for the course posted in the linked site (including the videolectures).

Second, **online tutorials**. One of the things you will also soon discover is that R users are keen to write "how to" guides in some of the [750 R devoted blogs](http://www.r-bloggers.com/) or as part of [Rpubs](https://rpubs.com/). Using Google or similar you will often find solutions to almost any problem you will encounter using R. For example, in this blog there are a few tutorials that you may want to look to complement my own:

+ [Cheatsheet for visualising scatterplots](http://rforpublichealth.blogspot.co.uk/2013/11/ggplot2-cheatsheet-for-scatterplots.html)  
+ [Cheatsheet for visualizing distributions](http://rforpublichealth.blogspot.co.uk/2014/02/ggplot2-cheatsheet-for-visualizing.html)  
+ [Cheatsheet for barplots](http://rforpublichealth.blogspot.co.uk/2014_01_01_archive.html)  

Third, *blogs on data visualisation*. If you use [Feedly](https://feedly.com/index.html#discover) or a similar blog aggregator, you should add the following blogs to your reading list. They are written by leading people in the field and are full of useful advice:
+ [Flowing Data](http://flowingdata.com/)
+ [The Functional Art](http://www.thefunctionalart.com/)
+ [Visual Business Intelligence](http://www.perceptualedge.com/blog/)
+ [chartsnthings](https://kpq.github.io/chartsnthings/)
+ [Data Revelations](http://www.datarevelations.com/category/blog)

Fourth, **resources for visualisations we don't have the time to cover**. R is way ahead some of the more popular data analysis programs you may be more familiar with (e.g SPSS or Excel). There's many things you can do. 

For example, if you like maps, **R can also be used to produce visualisations of spatial data**. There are various resources to learn how to do this and we teach this in our *Crime Mapping* module in the third year.



[^1]: Tufte, Edward (2001) *The visual display of quantitative information.* 2nd Edition. Graphic Press.

[^2]: Few, Stephen (2012) *Show me the numbers: designing graphics and tables to enlighten.* 2nd Edition. Analytics Press.

[^3]: Cairo, Alberto (2016) *The truthful art: data, charts, and maps for communication.* New Riders.

[^4]: Split into two groups.

[^5]: [This](http://tomhopper.me/2010/08/30/graphing-highly-skewed-data/) is an interesting blog entry in solutions when you have highly skewed data. 

<!--chapter:end:03-visualisation.Rmd-->

# Refresher on descriptive statistics & data carpentry

## Introduction

We have already introduce the typical workflow of data analysis

![](imgs/data-science-explore.png)

In this figure produced by Hadley Wickham you can see the first stage of data analysis involve importing your data, getting it into a [tidy format](http://vita.had.co.nz/papers/tidy-data.pdf), and then doing some transformations so that you get the data in good shape for analysis. There is a famous and possibly false statistic that says that 80% of an analyst time is often devoted to this kind of operations. Although the statistic is likely made up, the truth is that the experience of many analysts resonates with it. So, you should not underestimate data carpentry or data wrangling (as these processes are often called) as a part of your analysis.

For various decades, social scientists of a quantitative persuasion worked primarily with survey data (for an excelent history of how this come to be you can read [this book](https://global.oup.com/academic/product/identities-and-social-change-in-britain-since-1940-9780199587650?cc=gb&lang=en&#)), which came in rather tidy formats, but often required some transformations. Today we are more likely to rely on "big" and other new forms of data (from the web, administrative sources, or a variety of sensors) that may require more significant processing before we can do any analysis with it. Think, for example, of data from online vendors of drugs available in the Dark Net. Some people talk of the advent of a new [computational social science](http://science.sciencemag.org/content/323/5915/721/tab-pdf) around these new methods. This kind of data, indeed, opens avenues for research we could only dream of in the past as argued by [some of our colleagues](https://www.sciencedirect.com/science/article/pii/S0955395919300313?via%3Dihub). But getting this kind of data requires the development of new skills (e.g, web scrapping) and generally requires more processing before they are tidy and ready for analysis.

R is particularly well suited for this new world. In this module we only work with survey data, which tends to be tidier and easier to work with in the context of an introductory course unit. But even when working with this kind of data you often have to think hard about required tidying and transformations before you can start your analysis. 

In this module we expect you to download a survey dataset for analysis. These datasets are already rather tidy and have been professionally cleaned and prepared for analytical consumption. But you may still have to select cases and variables that are appropriate for your own analysis. Also, you likely will need to generate new variables or change existing ones for various reasons. It’s a rare data set in which every variable you need is measured directly. Examples of things you may need to do include:

* Combine various variables into a new one (eg., computing a rate)
* Reduce the number of levels in a categorical variable
* Format the variable to assign it to a more appropriate class if this is called for (e.g., character into factor). You will need to format date variables as dates, numerical variables as numbers, etc.).
* Recode values identifying missing cases as NA.
* Labelling all variables and categorical values so you don’t have to keep looking them up.
* Change the labels associated with the levels of a categorical variable.

## Getting some data from Eurobarometer

We're going to go ahead and download some data for the session today, specifically data from a *Eurobarometer*. Eurobarometers are opinion polls conducted regularly on behalf of the European Commission since 1973. Some of them ask the same questions over time to evaluate changes in European's views in a variety of subjects (standard Eurobarometers). Others are focused on special topics and are conducted less regularly (special Eurobarometers). They are a useful source of datasets that you could use, for exampple, for your undergraduate dissertation.

The data from these surveys is accessible through the data catalogue of GESIS, a data warehouse at the *Leibniz Institute for the Social Sciences* in Germany. For downloading data from GESIS you have to register with them (following the registration link) [here](https://login.gesis.org/realms/gesis/login-actions/registration?client_id=js-login&tab_id=6knmqH-4kbI). Once you activate your registration you should be able to access the data at GESIS.

![](imgs/register.PNG) 

GESIS has a section of their website devoted to the Eurobarometer survey. You can access that section [here](https://www.gesis.org/eurobarometer-data-service/home/). You could navigate this webpage to find the data we will be using for this tutorial, but to save time I will provide you a direct link to it. We will be using the special Eurobarometer 85.3 form 2016. This survey among other things asked Europeans about their views on gender violence.

![](imgs/eb.PNG) 

You can access the data for this eurobarometer [here](https://search.gesis.org/research_data/ZA6695). 

![](imgs/gesisa.PNG) 

You will see here that there are links to the files with the data in SPSS and STATA format. You can also see a tab where you could obtain the questionnaire for the survey. Once you are registered download the STATA version of the file and also an English version of the questionnaire. Make sure you place the file in your working directory. Once you do this you should be able to use the code we are using in this session.

First, we will load the data into our session. Since the data is in STATA format we will need to read the data into R using the `haven` package. Specifically, we will use the `read_dta()` function for importing STATA data into R. As an argument we need to write the name of the file with the data (and if it is not in your working directory, the appropriate path file).


```r
library(haven)
eb85_3 <- read_dta("datasets/ZA6695_v2-0-0.dta")
dim(eb85_3)
```

```
## [1] 27818   483
```

Alternatively, you can import the file from the webiste where we keep the data:

```r
eb85_3 <- read_dta("https://www.dropbox.com/s/f2s31sva7s8hzfa/ZA6695_v2-0-0.dta?dl=1")
```

We can see there are 27818 cases (survey participants) and 483 variables. 

## Thinking about your data: filtering cases

Imagine that we needed to write a report about attitudes to sexual violence.

First, we would need to think if we wanted to use all cases in the data or only a subset of the cases. For example, when using something like the Eurobarometer we would need to consider if we are interested in exploring the substantive topic across Europe or only for some countries. Or alternatively you may want to focus your analysis only on men attitudes to sexual violence. In a situation like this you would need to filter cases. This decision needs to be guided by your theoretical interests and your driving research question.

So, for example, if we only wanted to work with the UK sample we would need to figure out if there is a variable that identifies the country in the dataset. To know this, we need to look at the *codebook* (sometimes called data dictionary). In this case, we can look at the interactive facility provided for GESIS for online data analysis, which provides an interactive online codebook for this dataset. You can access this facility in the link highlighted in the image below:

![](imgs/linktoonlinea.png) 

Let's explore the online facility for the Eurobarometer. If we expand the menus in the left hand side by clicking in variable description, and then in standard nation id variables, you will see there is a variable that provides a "country code". This must be it. click on it and then you will see in the right hand side some information about this variable. You see the name of this variable (as it will appear in the dataset) *isocntry* and we can see this variable uses [ISO 3166](https://en.wikipedia.org/wiki/ISO_3166) codes to designate the country. This is an international standard set of abbreviations for country names. For the UK these codes are "GB-GBN" and "GB-NIR" (for Northern Ireland).

![](imgs/countrya.png) 

Now that we have this information we can run the code to select only the cases that have these values in the dataset. For doing something like that we would use the `dplyr::filter` function. We used the `filter` function in week 2. You can read more about it in the `dplyr` vignette. 


```r
library(dplyr)
#First, let's see what type of vector isocntry is
class(eb85_3$isocntry)
```

```
## [1] "character"
```

```r
uk_eb85_3 <- filter(eb85_3, isocntry %in% c("GB-GBN", "GB-NIR"))
```

The variable *isocntry* is a character vector with codes for the different participating countries. Here we want to select all the cases in the survey that have either of two values in this vector (GB-GBN or GB-NIR). Since these values are text we need to use quotes to wrap them up. Because we are selecting more than one value we cannot simply say `isocntry == "GB-BGN"`. We also need the cases from Northern Ireland. So, we use a particular operator introduced by `dplyr` called the piping operator (`%in%`). The piping operator is essentially saying to R *"and then"*. Basically, here we are creating a vector with the values we want *and then* asking R to look at those values within tne list (containing the right labels) in the the *isocntry* vector so that we can filter everything else out.

If you run this code you will end up with a new object called `uk_eb85_3` that only has 1306 observations. We have now a dataset that only has the British participants.

## Selecting variables: using `dplyr::select`

Perhaps, for the sake of this example, we decide to do an analysis that focuses on looking at attitudes toward sexual violence for all of Europe and for all participants. Yet, you won't be using 483 variables for certain. Among other reasons because our guidelines for the essay suggest you use fewer variables. But more generally because typically your theoretical model will tell you that some things matter more than others. 

The first thing you need to do is to think about what variables you are going to use. This involves first thinking about what variables are available in the dataset that measure your outcome of interest but then also consider what your theory of attitudes to gender violence say (this generally will include things that are not measured in the survey, such is life!).

For the sake of this exercise we are assuming the thing you are interested in explaining or better understanding is attitudes regarding sexual violence. So, before anything else you would need to spend some time thinking about how this survey measures these attitudes. You would need to screen the questionnaire and the codebook to identify these variables and their names in the dataset. Have a look at the questionnaire. The questions about gender violence start at the bottom of page 7. Which of these questions are questions about attitudes towards sexual violence?

Once you have all of this you would need to think about which of these survey questions and items make more sense for your research question. This is something where you will need to use your common sense but also your understanding of the literature in the topic. Criminologists and survey researchers spend a lot of time thinking about what is the best way of asking questions about topics or concepts of interest. They often debate and write about this. In data analysis measurement is key and is the process of systematically assigning numbers to objects and their properties, to facilitate the use of mathematics in studying and describing objects and their relationships. So, as part of your essay, you will need to consider what do researchers consider are good questions to measure, to tap into, the abstract concepts you are studying.

There are many items in this survey that relate to this topic, but for purposes of continuing our illustration we are going to focus on the answers to question *QB10*. This question asks respondents to identify in what circumstances may be justified to have sexual intercourse without consent. The participants are read a list of items (e.g., "flirting before hand") and they can select various of them if so they wish. 


\includegraphics[width=26.65in]{imgs/qb10a} 

What name is associated with this variable? Well you can see that depending on which thing they asked about, it might be `qb10_1`, `qb10_2`, `qb10_3`, etc etc!

Damn! We have one question but several variables! This is common when the question in the survey allows for multiple responses. Typically when this is read into a dataset, survey researchers create a variable for each of the possible multiple responses. If the respondent identified one of those potential responses they will be assigned a "yes" or a "1" for that column. If they did not they will be assigned a "no" or a "0". Let's see how this was done in this case:


```r
class(eb85_3$qb10_1)
```

```
## [1] "haven_labelled" "vctrs_vctr"     "double"
```

This is a vector labelled by haven. We could see what labels were used using the `attributes` function.


```r
attributes(eb85_3$qb10_1)
```

```
## $label
## [1] "INTERCOURSE W/O CONSENT APPROPRIATE WHEN: WEARING SEXY CLOTHES"
## 
## $format.stata
## [1] "%8.0g"
## 
## $class
## [1] "haven_labelled" "vctrs_vctr"     "double"        
## 
## $labels
## Not mentioned     Mentioned 
##             0             1
```

We can see here that the value 1 corresponds to cases where this circumstance was mentioned. Let's see how many people considered this a valid circumstance to have sex without consent.


```r
table(eb85_3$qb10_1)
```

```
## 
##     0     1 
## 24787  3031
```

Fortunately, only a minority of respondents.

Apart from thinking about the variables we will use to measure our outcome of interest we will need to select some variables that you think may be associated with this outcome. Here we will only do a few. Again, this is something that needs to be informed by the literature (what variables does the literature considers important) and our own interest. 

For the sake of illustration, let's say we are going to look at gender, political background of the respondent, country of origin, age, occupation of the respondents, and type of community they live in. Most of these are demographic variables (not always the more fun or theoretically interesting), but that's all we have in this eurobarometer and so they will have to do. 

The same way you try to identify the names of the variables for your outcome variable, you would need to do this for the variables you use to "explain" your outcome. Once you have done your variable selection you can subset your data to only include these.


```r
df <- select(eb85_3, qb10_1, qb10_2, qb10_3, qb10_4,
             qb10_5, qb10_6, qb10_7, qb10_8, qb10_9,
             qb10_10, qb10_11, qb10_12, d10, d11,
             isocntry, d1, d25, d15a, uniqid)
```

Ta-da! We now have a new object called *df* with only the variables we will be working with. In this format, it is easier to visualise the data. Notice we have also added a variable called `uniqid`. With many datasets like this you will have a unique id value that allows you to identify individuals. This id may be handy later on, so we will preserve it in our object.

If you `View` this object *df* you will notice that the selected variables appear in the order you selected them. If you wanted a different arrangement, for example you may have preferred to have *uniqid* as your first column, you could have modified the code like so:


```r
df <- select(eb85_3, uniqid, qb10_1, qb10_2, qb10_3, qb10_4,
             qb10_5, qb10_6, qb10_7, qb10_8, qb10_9,
             qb10_10, qb10_11, qb10_12, d10, d11,
             isocntry, d1, d25, d15a)
```

Or if you just want to reorder one or few columns (for example you want to also move d1, d25 and d15 a to the front), you could use `everything()` afterwards to save some typing, as below:


```r
df <- select(df, uniqid, d1, d25, d15a, everything())
```

If you want to add a lot of columns, it can save you some typing to have a good look at your data and see whether you can’t get to your selection by using chunks. Since *qb10_1* and the others are one after the other in the dataset we can use the `start.col:end.col` syntax like below:


```r
df <- select(eb85_3, uniqid, qb10_1:qb10_12, d10, d11,
             isocntry, d1, d25, d15a)
```

If you have a lot of columns with a similar structure you can use partial matching by adding `starts_with()`, `ends_with()` or `contains()` in your select statement. So, for example, an alternative to the syntax above we could use the following:


```r
df <- select(eb85_3, uniqid, starts_with("qb10"), d10, d11,
             isocntry, d1, d25, d15a)
```

Notice how the text we pass as an argument goes between double quotes.

An alternative is to deselect columns by adding a minus sign in front of the column name. You can also deselect chunks of columns. **Don't execute the code below for this practical**, but if you wanted, for example to get rid of *uniqid* you could do the following:


```r
df <- select(df, -uniqid)
```

Yes, a lot of these tips are about saving you some typing. Being lazy (productive, efficient) is fine. You can find more tips like this and useful ideas if you want to rename your columns or variables in [this tutorial](https://suzan.rbind.io/2018/01/dplyr-tutorial-1/).

## Creating summated scales

Now comes the next part. What are we going to do with these variables? How are we going to use them? Here you need to do some thinking using your common sense and also considering how other researchers may have used this question about attitudes to sexual violence. There's always many possibilities. 

We could, for example, consider that we are going to split the sample in two: those that consider any of these circumstances valid and those that didn't. We would then end up with a binary indicator that we could use as our outcome variable in our analysis. 

The thing is that doing that implies loosing information. We may think that someone that consider many circumstances as valid is not the same than the person that only considers one as valid. Yet, creating a global binary indicator would treat these two individuals in the same way.

Another alternative could be to see how many of these circumstances are considered valid excuses for each individual and to produce a sum then for every respondent. Since there are 9 "excuses" we could have a sum from 0 to 9. This is a very rough **summated scale**. You can read more about the proper development of summated scales [here](https://pdfs.semanticscholar.org/aa84/dc485a07b920a957e9ef295e8dced8fa025c.pdf). 

Let's do this. We are going to create a new variable that add up the responses to *qb10_1* all the way to *qb10_9*. For this we use the `mutate` function from the `dplyr` package.


```r
df <- mutate(df, 
       at_sexviol = qb10_1 + qb10_2 + qb10_3 + qb10_4 +
         qb10_5 + qb10_6 + qb10_7 + qb10_8 + qb10_9)
table(df$at_sexviol)
```

```
## 
##     0     1     2     3     4     5     6     7     8     9 
## 19681  2529  2117  1643   841   416   255   155    57   124
```

We have a skewed distribution. Most people in the survey consider that none of the identified circumstances are valid excuses for having sexual intercourse without consent. On the other hand, only a minority of individuals (124) consider that all of these 9 circumstances are valid excuses for having sex without consent. A high score in this count variable is telling you the participant is more likely to accept a number of circumstances in which sexual intercourse without consent is acceptable. You may read more about count data of this kind [here](https://en.wikipedia.org/wiki/Count_data).

Hold on for a second, though. There is a variable `qb10_10` that specifies people that answered "none of these" circumstances. In theory the number of people with a "1" in that variable (that is, selected this item) should equal 19681 (the number of zeros in our new variable). Let's check this out:


```r
table(df$qb10_10)
```

```
## 
##     0     1 
##  9400 18418
```

Oops! Something doesn't add up! Only 18418 people said that none of these circumstances were valid. So why when we add all the other items we end up with 19681 rather than 18418? Notice that there is also a qb10_11 and a qb10_12. These two items identify the people that refused to answer this question and those which did not know how to answer it. 


```r
table(df$qb10_11)
```

```
## 
##     0     1 
## 27563   255
```

```r
table(df$qb10_12)
```

```
## 
##     0     1 
## 26810  1008
```

There are 255 people that refused to answer and 1008 that did not know how to answer. If you add 1008, 255, and 18418 you get 19681. So our new variable is actually computing as zeroes people that did not know how to answer this question or refused to answer it. We do not want that. We do not know what these people think, so it would be wrong to assume that they consider that none of these circumstances are valid excuses for sexual intercourse without consent.

There are many ways to deal with this. He could simply filter out cases where we have values of 1 in these two variables (since we don't know their answers we could as well get rid of them). But We could also recode the variable to define this values as what they are NA (missing data, cases for which we have no valid information).


```r
df$at_sexviol[df$qb10_11 == 1 | df$qb10_12 == 1] <- NA
table(df$at_sexviol)
```

```
## 
##     0     1     2     3     4     5     6     7     8     9 
## 18418  2529  2117  1643   841   416   255   155    57   124
```

Pay attention to the code above. When we want to recode based in a condition we use something like that. What we are saying with that code is that we are going to assign as "`NA`" (missing data) the cases for which the condition between the square brackets are met. Those conditions are as defined, when the participants answered don't know *or* (the logical operator for "or" is "|") refused to answer the question (that is when *qb10_11* or *qb10_12* equals 1). You can see other scenarios for recoding using this kind of syntax in the resources we link below. You can see other logical operators used in R [here](https://www.datamentor.io/r-programming/operator/).

Notice that once we do the recoding and rerun the frequency distribution you will see we achieved what we wanted. Now all those missing cases are not counted as zero.

Summated scales like the one we created here are quick and not the most kosher way of combining several questions into a single measure. In research methods you probably learnt that we often work with theoretical constructs that we do not observe directly (e.g., self control, anomie, collective efficacy, etc.). We often call these **latent variables**. In order to study these constructs we create measures or scales that are based in **observed variables** (those we actually include and ask in the survey). [This](https://www.ismanet.org/doctoryourspirit/pdfs/Beck-Depression-Inventory-BDI.pdf) is a famous measure of *depression* often used in research. As you can see we have different questions (our oberved variables) that we think are related to our latent or not observed (directly) variable (*depression*). You can also see there are several items or questions all of which we researchers think are linked to depression in this scale. If you provide positive answers to many of these questions we may think that you have this unobserved thing we call *depression*.

When measuring latent variables it is a good idea to have multiple items that all capture aspects of the unobserved variable we are really interested in measuring. There is a whole field of statistics that focuses in how to analise if your observed variables are good indicators of your unobserved variable (**psychometry** is how we call this field in psychology) and also that focuses on how to best combine the answers to our observed variables in a single score (**latent variable modelling**). Some of the scores in the Crime Survey for England and Wales that you may use for your essay have been created with this more advanced methods (some of the measures on confidence in the police, for example). Summated scales are not really the best way to do this. But these are more advanced topics that are covered in upper level undergraduate or postgraduate courses. So for now, we will use summated scales as a convenient if imperfect way of aggregating observed variables.

<!-- can add cronbach alpha if we want -->

## Collapsing categories in character variables

One of the variables we selected is the country in which the participant lives. Let's have a look at this variable.


```r
table(df$isocntry)
```

```
## 
##     AT     BE     BG     CY     CZ   DE-E   DE-W     DK     EE     ES     FI 
##   1016   1029   1001    501   1060    533   1052   1010   1001   1008   1042 
##     FR GB-GBN GB-NIR     GR     HR     HU     IE     IT     LT     LU     LV 
##   1009   1006    300   1000   1026   1046   1002   1013   1004    508   1010 
##     MT     NL     PL     PT     RO     SE     SI     SK 
##    500   1003   1002   1000   1007   1109   1012   1008
```

There are 30 countries in the sample. You may consider that for the purposes of your analysis maybe that is too much. For the sake of this tutorial, let's say that maybe you are not really interested in national differences but in regional differences across different parts of Europe. Say you may want to explore whether these attitudes are different across Western/Central Europe, Scandinavian countries, Mediterranean countries, and Eastern Europe. You do not have a variable with these categories but since you have a variable that gives you the nations you could create such a variable. How would you do that?

First, you need to consider what the new categories are going to be and how you are going to distribute the countries in your sample across those categories. You may do that in a piece of paper. Then you would need to write the code to have a new variable with this information.

We are going to group the countries in 4 regions: Western (AT, BE, CZ, DE-E, DE-W, FR, GB-GBN, GB-NIR, IE, LU, NL), Eastern (BG, EE, HU, LT, LV, PL, RO, SK), Southern (CY, ES, GR, HR, IT, MT, PT, SI), and Northern Europe (DK, FI, SE).

Then you need to figure out what kind of variable we are dealing with here:


```r
class(df$isocntry)
```

```
## [1] "character"
```

Ok, this is a categorical unordered variable, we know that. But this kind of variables could be encoded into R as either *character* vectors, *factor* variables, or as we have seen as well as *haven_labelled*. How you recode a variable is contingent in how it is encoded. Here we are going to show you how you would do the recoding with a *character* variable such as *isocntry* into another character variable we will call *region*. We will see later examples for how to recode *factors*.

We will have a variable with four new categories (Western, Southern, Eastern, and Northern) whenever the right conditions are met. For this we can use the `case_when()` function, also from the `dplyr` package. What this does, is it goes through every *case*, and does something *when* it is true. We wrap this in the `mutate()` function, which allows us to create a new variable. We'll call this new variable "region". 

First, let's create four lists, which contain the codes for countries we would like to code Western, Eastern, Northern, and Southern: 


```r
western_list <- c("AT", "BE", "CZ", "DE-E", "DE-W", 
                  "FR", "GB-GBN", "GB-NIR", "IE", "LU", "NL")

eastern_list <- c("BG" , "EE", "HU", "LT" , "LV" , "PL" , "RO", "SK")

northern_list <- c("DK", "FI", "SE")

southern_list <- c("CY", "ES", "GR", "HR" , "IT" , "MT", "PT", "SI")
```

Now that we have these lists, our condition will be to evaluate whether the value for each row for the `isocntry` variable falls within one of these, and *when* this is the *case* then code if appropriately: 


```r
df <- df %>% 
    mutate(region = case_when(isocntry %in% western_list ~ "Western", 
                              isocntry %in% eastern_list ~ "Eastern",
                              isocntry %in% northern_list ~ "Northern", 
                              isocntry %in% southern_list ~ "Southern")
           )

table(df$region)
```

```
## 
##  Eastern Northern Southern  Western 
##     8079     3161     7060     9518
```

What we are doing above is initialising a new variable in the *df* object that we are calling *region*. We are then assigning to each of the four categories in this character vector those participants in the survey that have the corresponding values in the *isocntry* variable as defined for each category. So for example if Austria is the value in *isocntry* we are telling R we want this person to be assigned the value of "Western" in the *region* variable. And so on. You can see the list of ISO country codes [here](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes).

Once you have created the variable you could start exploring if there is any association with our outcome variable. For example, using **mosaic plots** from the `vcd` package (if you don't have it installed the code won't run).


```r
library(vcd)
```

```
## Loading required package: grid
```

```r
mosaic(~region + at_sexviol, data = df)
```

![](04-carpentry_files/figure-latex/unnamed-chunk-22-1.pdf)<!-- --> 

In a mosaic plot like this the height of the region levels indicate how big that group is. You can see there are many more observations in our sample that come from Western countries than from Northern countries. Here what we are interested is the length. We see that Northern countries have proportionally more people in the zero category than any other group. On the other hand, Eastern countries have the fewer zeros (so looking as if attitudes more permissive towards sexual violence are more common there, even if still a minority). We will come back to this kind of plots later on this semester.

## Working with apparently cryptic variable names and levels

Let's look at the variable *d10* in our dataset:


```r
table(df$d10)
```

```
## 
##     1     2 
## 12230 15588
```

What is this? Unclear, isn't it? If you look at the questionnaire you will see that this variable measures gender, that values of 1 correspond to men and that values of 2 corresponds to woman. But this is far from straightforward just by looking a the printed table or the name of the variable.

To start with we may want to change the name of the variable. One way to do this is the following:


```r
colnames(data)[colnames(data)=="old_name"] <- "new_name"
```

Of course, we need to change the names for valid ones in our case. So adapting that code we would write as follows:


```r
colnames(df)[colnames(df)=="d10"] <- "gender"
```

If you prefer the *tydiverse* dialect (that aims to save you typing among other things), then you would use the `rename` function as below (beware if you already renamed *d10* using `colnames` there will be no longer a *d10* variable and therefore R will return an error).


```r
df <- rename(df, gender=d10)
```

If you now check the names of the variables (with the `names` function) in `df` you will see what has happened:


```r
names(df)
```

```
##  [1] "uniqid"     "qb10_1"     "qb10_2"     "qb10_3"     "qb10_4"    
##  [6] "qb10_5"     "qb10_6"     "qb10_7"     "qb10_8"     "qb10_9"    
## [11] "qb10_10"    "qb10_11"    "qb10_12"    "gender"     "d11"       
## [16] "isocntry"   "d1"         "d25"        "d15a"       "at_sexviol"
## [21] "region"
```

If you want to change many variable names it may be more efficient doing it all at once. First we are going to select fewer variables and retain only the ones will continue using:


```r
df <- select(df, uniqid, at_sexviol, gender, d11, d1, d25, d15a, region)
```

Now we can change a bunch of names all at once with the following code:


```r
names(df)[4:7] <- c("age", "politics", "urban", "occupation")
names(df)
```

```
## [1] "uniqid"     "at_sexviol" "gender"     "age"        "politics"  
## [6] "urban"      "occupation" "region"
```
 
You may have seen we wrote `[4:7]` above. This square bracket notation is identifying the columns within that particular object. It is indicating to R that we only wanted to change the name of the variables defining column 4 to 7 in the dataframe, those corresponded to d11, d1, d25, and d15a, which respectively (we can see in the questionnaire) correspond to age, politics, whether the respondent live in a urban setting, and occupation. We assign to those columns the names we specify (in the appropriate order) in the list that follows. Now we will be less likely to confuse ourselves, since we have columns with meaningful names (which will appear in any output and plots we produce).

Let's look at occupation:


```r
table(df$occupation)
```

```
## 
##    1    2    3    4    5    6    7    8    9   10   11   12   13   14   15   16 
## 1588 1864 1845 8916  129   14  384  768  517  878  313 1921 2202  856 2062  271 
##   17   18 
## 2471  819
```

There are 18 categories here. And it is not clear what they mean.


```r
class(df$occupation)
```

```
## [1] "haven_labelled" "vctrs_vctr"     "double"
```

Remember that this is `haven_labelled`. If we look at the attributes we can see the correspondence between the numbers above and the labels.


```r
attributes(df$occupation)
```

```
## $label
## [1] "OCCUPATION OF RESPONDENT"
## 
## $format.stata
## [1] "%8.0g"
## 
## $class
## [1] "haven_labelled" "vctrs_vctr"     "double"        
## 
## $labels
##       Responsible for ordinary shopping, etc. 
##                                             1 
##                                       Student 
##                                             2 
##           Unemployed, temporarily not working 
##                                             3 
##                       Retired, unable to work 
##                                             4 
##                                        Farmer 
##                                             5 
##                                     Fisherman 
##                                             6 
##                   Professional (lawyer, etc.) 
##                                             7 
##              Owner of a shop, craftsmen, etc. 
##                                             8 
##                    Business proprietors, etc. 
##                                             9 
## Employed professional (employed doctor, etc.) 
##                                            10 
##                      General management, etc. 
##                                            11 
##                       Middle management, etc. 
##                                            12 
##                    Employed position, at desk 
##                                            13 
##                 Employed position, travelling 
##                                            14 
##                Employed position, service job 
##                                            15 
##                                    Supervisor 
##                                            16 
##                         Skilled manual worker 
##                                            17 
##                 Unskilled manual worker, etc. 
##                                            18
```

Having to look at this every time is not very convenient. You may prefer to simply use the labels directly. For this we can use the `as_factor` function from the `haven` package.


```r
df$f_occup <- as_factor(df$occupation)
class(df$f_occup)
```

```
## [1] "factor"
```

```r
table(df$f_occup)
```

```
## 
##       Responsible for ordinary shopping, etc. 
##                                          1588 
##                                       Student 
##                                          1864 
##           Unemployed, temporarily not working 
##                                          1845 
##                       Retired, unable to work 
##                                          8916 
##                                        Farmer 
##                                           129 
##                                     Fisherman 
##                                            14 
##                   Professional (lawyer, etc.) 
##                                           384 
##              Owner of a shop, craftsmen, etc. 
##                                           768 
##                    Business proprietors, etc. 
##                                           517 
## Employed professional (employed doctor, etc.) 
##                                           878 
##                      General management, etc. 
##                                           313 
##                       Middle management, etc. 
##                                          1921 
##                    Employed position, at desk 
##                                          2202 
##                 Employed position, travelling 
##                                           856 
##                Employed position, service job 
##                                          2062 
##                                    Supervisor 
##                                           271 
##                         Skilled manual worker 
##                                          2471 
##                 Unskilled manual worker, etc. 
##                                           819
```

Now you have easier to interpret output.

## Recoding factors

As we said there are many different types of objects in R and depending on their nature the recoding procedures may vary. You may remember that many times categorical variables will be encoded as factors. Let's go back our newly created *f_occup*. We have 18 categories here. These are possibly too many. Some of them have to few cases, like *fisherman*. Although this is a fairly large dataset we only have 14 fisherman. It would be a bit brave to guess what fishermen across Europe think about sexual violence based in a sample of just 14 of them. 

This is a very common scenario when you analyse data. In these cases is helpful to think of ways of adding the groups with small counts (like fishermen in this case) to a broader but still meaningful category. People often refer to this as *collapsing categories*. You also have to think theoretically, do you have good enough reasons to think that there's ought to be meaningful differences in attitudes to sexual violence among these 18 groups? If you don't you may want to collapse into fewer categories that may make more sense.

As when we created the *region* variable the first thing to do is to come out with a new coding scheme for this variable. We are going to use the following. I'm not making this scheme up, I am just using the scheme that the Eubarometer uses to simplify these categories.

    1	Self-employed (5 to 9 in d15a)	
    2	Managers (10 to 12 in d15a)	
    3	Other white collars (13 or 14 in d15a)	
    4	Manual workers (15 to 18 in d15a)	
    5	House persons (1 in d15a)	
    6	Unemployed (3 in d15a)	
    7	Retired (4 in d15a)	
    8	Students (2 in d15a)
    
It would be quicker to recode from *d15a* into a new variable (there would be less typing when dealing with numbers rather than labels). But here we are going to use this example to show you how to recode from a factor variable, so instead we will recode form *f_occup*. 

As often in R, there are multiple ways of doing this. We could use `dplyr::recode`. But here we will show you how to do this using the `recode` function from the `car` library.


```r
df$occup2 <- df$f_occup
levels(df$occup2) <- list("Self-employed" = 
                            c("Farmer" , "Fisherman" ,
                              "Professional (lawyer, etc.)" ,
                              "Owner of a shop, craftsmen, etc.",
                              "Business proprietors, etc."),
                          "Managers" = 
                            c("Employed professional (employed doctor, etc.)",
                              "General management, etc.", 
                              "Middle management, etc."),
                          "Other white collar" = 
                            c("Employed position, at desk", 
                              "Employed position, travelling"),
                          "Manual workers" = 
                            c("Employed position, service job",
                              "Supervisor",
                              "Skilled manual worker",
                              "Unskilled manual worker, etc."),
                          "House persons" = "Responsible for ordinary shopping, etc.",
                          "Unemployed" = "Unemployed, temporarily not working",
                          "Retired" =  "Retired, unable to work",
                          "Student" = "Student")
```

One of the things you need to be very careful with when recoding factors or character variables is that you need to input the chunk of texts in the existing variables exactly as they appear in the variable. Otherwise you will get into trouble. So, for example, if in the code above you wrote `fishermen` instead of `Fisherman` you would have 14 less cases in the `Self-Employed` level than you should have. When doing this kind of operations is always convenient to check that the categories add up correctly.

For more details in how to recode factors and other potential scenarios you may want to read [this paper](https://peerj.com/preprints/3163/) by Amelia McNamara and Nicholas Horton.

## Understanding missing data

As we have already seen, you will have participants that do not provide you with valid answers for the questions in the survey. In general in any kind of data set you work with, whether it comes from surveys or not, you will have cases for which you won't have valid information for particular variables in your dataframe. Missing data is common. 

Let's look at the *politics* variable.


```r
class(df$politics)
```

```
## [1] "haven_labelled" "vctrs_vctr"     "double"
```

```r
table(df$politics)
```

```
## 
##    1    2    3    4    5    6    7    8    9   10 
## 1433  830 2161 2217 6690 2238 2056 1658  474 1126
```

```r
sum(is.na(df$politics))
```

```
## [1] 6935
```

It looks as if we have no missing data. Right? Well, appearances can be deceiving sometimes.

![](imgs/leftrighta.png) 

This is the question as it was asked from the survey respondents. Notice the difference in the response options and the categories in *politics*. We know that those that see themselves further to the left will have answer 1 and those that see themselves further to the right would have answer 10. What does 97 and 98 then refers to? If you look at the questionnaire you will see that those that refuse or don't know *in the questionnaire* are coded as 11 and 12.

Let's look closer at the `attributes`:


```r
attributes(df$politics)
```

```
## $label
## [1] "LEFT-RIGHT PLACEMENT"
## 
## $format.stata
## [1] "%8.0g"
## 
## $class
## [1] "haven_labelled" "vctrs_vctr"     "double"        
## 
## $labels
##          Box 1 - left                 Box 2                 Box 3 
##                     1                     2                     3 
##                 Box 4                 Box 5                 Box 6 
##                     4                     5                     6 
##                 Box 7                 Box 8                 Box 9 
##                     7                     8                     9 
##        Box 10 - right Refusal (Spontaneous)                    DK 
##                    10                    NA                    NA
```

A tip if you don't want to see as much output. If you want to access directly only some of the attributes you can call them directly modifying the code as below:


```r
attributes(df$politics)$labels
```

```
##          Box 1 - left                 Box 2                 Box 3 
##                     1                     2                     3 
##                 Box 4                 Box 5                 Box 6 
##                     4                     5                     6 
##                 Box 7                 Box 8                 Box 9 
##                     7                     8                     9 
##        Box 10 - right Refusal (Spontaneous)                    DK 
##                    10                    NA                    NA
```

Or we could use the `val_labels` function from the `labelled` package for the same result:


```r
library(labelled)
val_labels(df$politics)
```

```
##          Box 1 - left                 Box 2                 Box 3 
##                     1                     2                     3 
##                 Box 4                 Box 5                 Box 6 
##                     4                     5                     6 
##                 Box 7                 Box 8                 Box 9 
##                     7                     8                     9 
##        Box 10 - right Refusal (Spontaneous)                    DK 
##                    10                    NA                    NA
```


Notice that though the questionnaire assigned a value of 11 to refusal and 12 to "don't know" answers, in the dataset those values are instead 97 and 98. You will see this often - 97, 98, 99, and similar codes are often used to denote missing data.

You may have good theoretical reasons to preserve this in your analysis. Perhaps you think that people that did not answer this question have particular reasons not to do so and those reasons may be associated with their attitudes to violence. In that case you may want to somehow preserve them in your analysis. Absent that rationale you may just want to treat them as they are: missing data. You just have no way of knowing if these people are more or less lefty or conservative. So let's declare them as such for sake of explaining how you would do that:


```r
df$politics[df$politics>=97] <- NA
table(df$politics)
```

```
## 
##    1    2    3    4    5    6    7    8    9   10 
## 1433  830 2161 2217 6690 2238 2056 1658  474 1126
```
The equal or greater operator in R is written as `>=`. What we are saying in the first statement to R is that whenever *politics* has a value equal or greater than 97 we are going to recode those cases as `NA`, as missing data. Since this is a `haven_labelled` vector we can use numbers here rather than characters or factor levels as part of the recoding. That makes things a bit easier in that it saves typing. 
Let's look a the results:


```r
summary(df$politics)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
##   1.000   4.000   5.000   5.196   7.000  10.000    6935
```

Now you see you have 6935 cases with missing data. As always it is good to check the original variable. We had 2766 and 4169 between refusals and "don't know" respondents. These add up to 6935. 

Let's check something else:


```r
library(skimr)
skim(df$politics)
```

Mmmmm. The `summary` function worked, but other functions do not know to treat the values in the `haven_labelled` vector as a numeric. So, to avoid problems we may want to define as such (if we truly believe this is a quantitative rather than a categorical variable or at the very least are willing to treat it as quantitative).


```r
df$politics_n <-as.numeric(df$politics)
```

If you try this now, you will see it works:


```r
skim(df$politics_n)
```

If we want to see what percentage of cases is NA across our dataset we could use `colMeans` combined with `is.na`. This will compute the mean (the proportion) of cases that are NA in each of the columns of the dataframe:


```r
colMeans(is.na(df))
```

```
##       uniqid   at_sexviol       gender          age     politics        urban 
## 0.0000000000 0.0454022575 0.0000000000 0.0000000000 0.2492990150 0.0006470631 
##   occupation       region      f_occup       occup2   politics_n 
## 0.0000000000 0.0000000000 0.0000000000 0.0000000000 0.2492990150
```

This is suspicious. Only the variables we have created and already sorted seem to have NA. This may be a function of the `haven_labelled` vectors behaving like with the original *politics* variable. Let's explore it. We can use the `val_labels` function from the `labelled` package to extract labels from the whole dataframe like this:


```r
val_labels(df)
```

```
## $uniqid
## NULL
## 
## $at_sexviol
## NULL
## 
## $gender
##   Man Woman 
##     1     2 
## 
## $age
##                      15 years                      96 years 
##                            15                            96 
## 99 and older [not documented] 
##                            99 
## 
## $politics
##          Box 1 - left                 Box 2                 Box 3 
##                     1                     2                     3 
##                 Box 4                 Box 5                 Box 6 
##                     4                     5                     6 
##                 Box 7                 Box 8                 Box 9 
##                     7                     8                     9 
##        Box 10 - right Refusal (Spontaneous)                    DK 
##                    10                    NA                    NA 
## 
## $urban
##      Rural area or village Small or middle sized town 
##                          1                          2 
##                 Large town                         DK 
##                          3                         NA 
## 
## $occupation
##       Responsible for ordinary shopping, etc. 
##                                             1 
##                                       Student 
##                                             2 
##           Unemployed, temporarily not working 
##                                             3 
##                       Retired, unable to work 
##                                             4 
##                                        Farmer 
##                                             5 
##                                     Fisherman 
##                                             6 
##                   Professional (lawyer, etc.) 
##                                             7 
##              Owner of a shop, craftsmen, etc. 
##                                             8 
##                    Business proprietors, etc. 
##                                             9 
## Employed professional (employed doctor, etc.) 
##                                            10 
##                      General management, etc. 
##                                            11 
##                       Middle management, etc. 
##                                            12 
##                    Employed position, at desk 
##                                            13 
##                 Employed position, travelling 
##                                            14 
##                Employed position, service job 
##                                            15 
##                                    Supervisor 
##                                            16 
##                         Skilled manual worker 
##                                            17 
##                 Unskilled manual worker, etc. 
##                                            18 
## 
## $region
## NULL
## 
## $f_occup
## NULL
## 
## $occup2
## NULL
## 
## $politics_n
## NULL
```

Notice that in *urban* there are explicit codes for missing data but that these values won't be treated as such, at least we do something. Let's see how many cases we have in this scenario:


```r
table(df$urban)
```

```
## 
##     1     2     3 
##  8563 11881  7356
```

Not too bad. Let's sort this variable:


```r
df$urban[df$urban>=8] <- NA
df$f_urban <- as_factor(df$urban)
table(df$f_urban)
```

```
## 
##      Rural area or village Small or middle sized town 
##                       8563                      11881 
##                 Large town                         DK 
##                       7356                         18
```

```r
mean(is.na(df$f_urban))
```

```
## [1] 0
```

You can see that even though have now no cases with a value of 8 or DK, the label appears printed in the output. This is still a valid level:


```r
levels(df$f_urban)
```

```
## [1] "Rural area or village"      "Small or middle sized town"
## [3] "Large town"                 "DK"
```

So, we may want to remove it explicitly if we don't want output reminding us what we already know, that "there are not" DK cases (since now we call them and treat them as NA). For removing unused levels in a factor we use the `droplevels` function,


```r
df$f_urban <- droplevels(df$f_urban)
table(df$f_urban)
```

```
## 
##      Rural area or village Small or middle sized town 
##                       8563                      11881 
##                 Large town                         DK 
##                       7356                         18
```

Above also saw the codes for *gender* let's use `as_factor` again for this variable:


```r
df$f_gender <- as_factor(df$gender)
```

Let's just keep the variables we will retain for our final analysis:


```r
df_f <- select(df, uniqid, at_sexviol, f_gender, age, politics_n,
               f_urban, f_occup, region)
```

We are going to do some further exploration of NA. Let's create a new variable that identifies the cases that have missing data in at least one of the columns in the data with the final variables for our analysis. For this we can use the `complete.cases` function that creates a logical vector indicating whether any of the cases has missing values in at least one column:


```r
df_f$complete <- complete.cases((df_f))
table(df_f$complete)
```

```
## 
## FALSE  TRUE 
##  7628 20190
```

```r
mean(df_f$complete)
```

```
## [1] 0.7257891
```

So, shocking as this may sound you only have full data in 72% of the participants. Notice how the percentage of missing cases in the variables range:


```r
colMeans(is.na(df_f))
```

```
##     uniqid at_sexviol   f_gender        age politics_n    f_urban    f_occup 
## 0.00000000 0.04540226 0.00000000 0.00000000 0.24929902 0.00000000 0.00000000 
##     region   complete 
## 0.00000000 0.00000000
```

The function `complete.cases` is returning what cases have missing data **in any of** the variables not in a singular one. It is not unusual for this percentage to be high. You may end up with a massive loss of cases even though the individual variables themselves do not look as bad as the end scenario.

Later this term we will cover forms of analysis (e.g., multiple regression) in which you have to work with multiple variables at the same time. This form of analysis require you to have information for all the cases and all the variables. Every case for which there is not information in one of the variables in your analysis is automatically excluded from such analysis. So the actual sample size you use when using these techniques is the sample size for which you have full information. In our example your sample size (when you do multiple regression analysis or any multivariate analysis) will be 20184 rather than 27818.

This being the case it makes sense to exclude from your data all cases that have some missing information in the variables you will be using in your analisis. For this you can use the `na.omit` function. We create a new object (I name it "full_df", you can call it whatever) and put inside it the outcome of running `na.omit` in our original sample ("df_f").


```r
full_df <- na.omit(df_f)
```

Now we have a dataset ready for starting our analysis. 

## Exploring dataframes visually

We have covered now a number of functions you can use to explore your data, such as `skimr::skim()`, `str()`, `summary()`, `table()`, or `dplyr::glimpse()`. But sometimes is useful to get a more panoramic way. For this we can use the `visdat` package for visualising whole dataframes amd its main function `vis_dat()`.


```r
library(visdat)
vis_dat(df_f)
```

```
## Warning: `gather_()` was deprecated in tidyr 1.2.0.
## Please use `gather()` instead.
```

![](04-carpentry_files/figure-latex/unnamed-chunk-55-1.pdf)<!-- --> 

Nice one! You get a visual representations of how your variables are encoded in this dataframe. You have several categorical variables such as region, f_gender, f_urban, and f_occup. We see that region is encoded as a `character` vector, whereas the others are `factors`. For the purposes of this course, it is generally better to have your categorical variables encoded as factors. So one of the next steps in our data prep may be to recode region as a factor. 


```r
df_f$f_region <- as.factor(df_f$region)
```

We can also see we have age, a quantitative variable, *age*, encoded as `haven_labelled`. We could as well encoded as `numeric`.


```r
df_f$age <- as.numeric(df_f$age)
```

What we do with *at_sexviol* depends on how we decide to treat it. But for arguments sake let's say we are going to treat it as numerical.


```r
df_f$at_sexviol <- as.numeric(df_f$at_sexviol)
```
The othe piece of info you get with `vis_dat` is the prevalence of missing data (NA) for each variable (the dark horizontal cases represent a missing case in the variable). We can summarise missing data visually more clearly with `vis_miss`.


```r
vis_miss(df_f)
```

![](04-carpentry_files/figure-latex/unnamed-chunk-59-1.pdf)<!-- --> 

You can find more details about how to explore missing data in the vignette of the `naniar` package [here](http://naniar.njtierney.com/articles/getting-started-w-naniar.html).

## A quick recap on descriptive statistics

You have covered this extensively last semester, and we have also touched on this in the last three weeks, but just as a quick refresher. We can have a review of some descriptive statistics to end the week. 

### Central Tendency

Central tendency refers to a descriptive summary of the centre of the data’s distribution; it takes the form of a single number that is meant to represent the middle or average of the data. The **mean**, **median**, and **mode** are common statistics of the central tendency. 

The *mean* is the average and it is useful when we want to summarise a variable quickly. Its disadvantage is that it is sensitive to extreme values, so the mean can be distorted easily. 

For example, the mean value for our political scale variable is: 


```r
mean(df$politics_n, na.rm = TRUE)
```

```
## [1] 5.195805
```

To address this sensitivity, the *median* is a better measure because it is a robust estimate, which means that it is not easily swayed by extreme values. It is the middle value of the distribution. 


```r
median(df$politics_n, na.rm = TRUE)
```

```
## [1] 5
```

The *mode* helps give an idea of what is the most typical value in the distribution, which is the most frequently occurring case in the data. While mean and median apply to numeric variables, the mode is most useful when describing categorical variables. For example, you may want to know the most frequently occurring category. To query the mode, we use the function `mlv()` (acronym for **m**ost **l**ikely **v**alues) from the `modeest` package to answer this question: 
<br>


```r
library(modeest)
mlv(df$f_occup)
```

```
## [1] Retired, unable to work
## 18 Levels: Responsible for ordinary shopping, etc. ... Unskilled manual worker, etc.
```

<!-- ### **Dispersion in Nominal and Ordinal Variables** -->

<!-- We learn how to conduct two measures of dispersion in `R` for categorical variables: the variation ratio and the index of qualitative variation: -->

<!-- The **variation ratio** (VR) tells us the proportion of cases that are not in the modal category – basically cases not in the most frequent or ‘popular’ category. The formula for the variation ratio (VR) is: -->

<!-- $$VR = 1 – ({\frac {N~modalcat~} {N~total~}})$$ -->

<!-- $N~modalcat$ refers to the frequency of observations in the modal category, and $N~total~$ refers to the total number of observations. This formula states that VR is equal to 1 minus the proportion of observations that are in the modal category, which is the same as saying the proportion of observations that are not in the modal category.  -->

<!-- So let's create objects we need for this calculation. First, how many observations do we have in our modal category? Well, looking back at the occupation variable, the modal category was:  -->

<!-- ```{r} -->

<!-- mlv(df$f_occup) -->

<!-- ``` -->

<!-- To check how many we have, we can create a frequency table:  -->

<!-- ```{r} -->

<!-- table(df$f_occup) -->

<!-- ``` -->

<!-- We can see from that it's 8916. So we could just assign this to our object:  -->

<!-- ```{r} -->

<!-- num_modal_cat <- 8916 -->

<!-- ``` -->

<!-- But with copy and pasting there is always scope f -->

### Dispersion

You always want to talk about dispersion as well. If you have a numeric variable, you might want to consider the **range**, which is the difference between the maximum and minimum value in a given distribution:



```r
max(df$politics_n, na.rm = TRUE) - min(df$politics_n, na.rm = TRUE)
```

```
## [1] 9
```


You also want to talk about the **variance** ( $s^2$ ), which tells you about spread, specifically the sum of the squared deviations from the mean, which is then divided by the total number of observations. You will then also come across **standard deviation** (SD), which is the square root of the variance. You can find these with the `sd()` and the `var()` functions: 


```r
var(df$politics_n, na.rm = TRUE)
```

```
## [1] 4.864302
```

```r
sd(df$politics_n, na.rm = TRUE)
```

```
## [1] 2.205516
```

Visual representations of dispersions such as a histogram are also handy for getting an overview of your data. 

For categorical variables, a frequency table might show distribution, or again a visualisation. You can get quantitative summaries of dispersion for categorical variables, such as variance ratio and the index of qualitative variation, but I'll leave these for now. If you want to know about these, ask us in the labs!

### Bivariate analysis

We've touched on this already in week two, when we looked at using the `group_by()` and `summarise()` functions. Look back at week 2 for more detail. But for example, if we wanted to know what is the mean political score broken down by occupation, we would answer that question using these two functions: 



```r
politics_by_occ <- df %>% 
    group_by(f_occup) %>% 
    summarise(mean_poli_score = mean(politics_n, na.rm = TRUE))

politics_by_occ
```

```
## # A tibble: 18 x 2
##    f_occup                                       mean_poli_score
##    <fct>                                                   <dbl>
##  1 Responsible for ordinary shopping, etc.                  5.23
##  2 Student                                                  4.91
##  3 Unemployed, temporarily not working                      4.96
##  4 Retired, unable to work                                  5.17
##  5 Farmer                                                   5.69
##  6 Fisherman                                                4.82
##  7 Professional (lawyer, etc.)                              5.14
##  8 Owner of a shop, craftsmen, etc.                         5.40
##  9 Business proprietors, etc.                               5.72
## 10 Employed professional (employed doctor, etc.)            5.41
## 11 General management, etc.                                 5.59
## 12 Middle management, etc.                                  5.16
## 13 Employed position, at desk                               5.21
## 14 Employed position, travelling                            5.38
## 15 Employed position, service job                           5.11
## 16 Supervisor                                               5.39
## 17 Skilled manual worker                                    5.25
## 18 Unskilled manual worker, etc.                            5.30
```

We can now begin to hypothesise whether there are differences political leanings between different occupations. Next week we will continue to expand on how we might actually go about generalising our conclusions from these observed descriptive analyses. 

## Further resources

There are many other ways to recode variables and create new variables based in existing ones. Here we only provided some examples. We cannot exhaust all possibilities in this tutorial. You can find additional examples and code for how to do the recoding of variables in the following links. Please make sure that you spend some time looking at these additional resources. They are not optional.

[Wrangling categorical data in R](https://peerj.com/preprints/3163.pdf)

[http://rprogramming.net/recode-data-in-r/](http://rprogramming.net/recode-data-in-r/)

[http://www.cookbook-r.com/Manipulating_data/Recoding_data/](http://www.cookbook-r.com/Manipulating_data/Recoding_data/)

[https://mgimond.github.io/ES218/Week03a.html](https://mgimond.github.io/ES218/Week03a.html)

[https://www.r-bloggers.com/from-continuous-to-categorical/](https://www.r-bloggers.com/from-continuous-to-categorical/)

You should also look for the `dplyr` documentation for the functions mutate() and recode().

If you would like to combine several variables into one for your analysis in more complex ways but do not know how to do that, please do get in touch. Also do not hesitate to approach us if you have any other specific queries.


<!--chapter:end:04-carpentry.Rmd-->

# Foundations of statistical inference: confidence intervals 

## Introduction

Up to now we have introduced a series of concepts and tools that are helpful to describe sample data. But in data analysis we often do not observe full populations. We often only have sample data. 

Think of the following two problems:

You want to know the extent of intimate partner violence in a given country. You could look at police data. But not every instance of intimate partner violence gets reported to, or recorded by, the police. We know there is a large proportion of those instances that are not reflected in police statistics. You could do a survey. But it would not be practical to ask everybody in the country about this. So you select a sample and try to develop an estimate of what the extent of this problem is in the population based on what you observe in the sample. But, how can you be sure your sample guess, your estimate, is any good? Would you get a different estimate if you select a different sample?

You conduct a study to evaluate the impact of a particular crime prevention program. You select a a number of areas as part of the study. Half of it you randomly allocate to your intervention and the other half to your control or comparison group. Imagine that you observe these areas after the intervention is implemented and you notice there is a difference. There is less crime in your intervention areas. How can you reach conclusions about the effectiveness of the intervention based on observations of differences on crime in these areas? What would have happened if your randomisation would have split your sample in different ways, would you still be able to observe an effect?

For this and similar problems we need to apply statistical inference: a set of tools that allows us to draw inferences from sample data. In this session we will cover a set of important concepts that constitute the basis for statistical inference. In particular, we will approach this topic from the **frequentist** tradition. 

It is important you understand this is not the only way of doing data analysis. There is an alternative approach, **bayesian statistics**, which is very important and increasingly popular. Unfortunately, we do not have the time this semester to also cover Bayesian statistics. Typically, you would learn about this approach in more advanced courses. 

Unlike in previous and future sessions, the focus today will be less applied and a bit more theoretical. However, it is important you pay attention since understanding the foundations of statistical inference is essential for a proper understanding of everything else we will discuss in this course. The code we cover in the first few sections this week is much trickier but won't be instrumental for your assignment, so don't worry too much if you don't fully understand it. 

## Generating random data

For the purpose of today's session we are going to generate some fictitious data. We use real data in all other sessions but it is convenient for this session to have some randomly generated fake data (actually technically speaking pseudo-random data)[^1]. 

So that all of us gets the same results (otherwise there would be random differences!), we need to use the `set.seed()` function. Basically your numbers are pseudo random because they're calculated by a number generating algorithm, and setting the *seed* gives it a number to "grow"" these pseudo random numbers out of. If you start with the same seed, you get the same set of random numbers. 

So to guarantee that all of us get the same randomly generated numbers, set your seed to 100:


```r
set.seed(100) 
```

We are going to generate a large object (100,000 cases) with skewed data. We often work with severely skewed data in criminology. For generating this type of data, we are going to use the `rnbinom()` function for something called negative binomial distributions, which is a discrete probability distribution often use as a model for counts.


```r
skewed <- rnbinom(100000, mu = 1, size = 0.3) 
```

The code above creates data that follow a negative binomial distribution, essentially a highly skewed distribution. Don't worry too much about the other parameters we are using as arguments at this stage, but if curious look at `?rnbinom`.

We can also get the mean and standard deviation for this object using `mean` and `sd` respectively:


```r
mean(skewed)
```

```
## [1] 1.00143
```

```r
sd(skewed)
```

```
## [1] 2.083404
```

And we can also see what it looks like:


```r
library(ggplot2)
qplot(skewed)
```

![](05-inference_files/figure-latex/unnamed-chunk-4-1.pdf)<!-- --> 

We are going to pretend this variable measures numbers of crime perpetrated by an individual in the previous year. Let's see how many offenders we have in this fake population.


```r
sum(skewed > 0)
```

```
## [1] 35623
```

We are now going to put this variable in a dataframe and we are also going to create a new categorical variable -identifying whether someone offended over the past year (e.g., anybody with a count of crime higher than 0). Let's start by creating a new dataframe (*"fakepopulation"*) with the skewed variable we created rebaptised as *crimecount*.


```r
fake_population <- data.frame(crimecount = skewed)
```

Then let's define all values above 0 as "Yes" in a variable identifying offenders and everybody else as "No". We use the `ifelse()` function for this.


```r
fake_population$offender <- ifelse(fake_population$crimecount > 0, c("Yes"), c("No"))
#Let's check the results
table(fake_population$offender)
```

```
## 
##    No   Yes 
## 64377 35623
```

We are now going to generate a normally distributed variable (watch [this short video](https://www.youtube.com/watch?v=mtH1fmUVkfE) if you are unclear what a normal distribution is). 

We are going to pretend that this variable measures IQ. We are going to assume that this variable has a mean of 100 in the non-criminal population (pretending there is such a thing) with a standard deviation of 15 and a mean of 92 with a standard deviation of 20 in the criminal population. We are pretty much making up these figures.

The first expression is asking R to generate random values from a normal distribution with mean 100 and standard deviation for every of the 64394 "non-offenders" in our fake population data frame. WARNING: If you run the `table()` function and the number of non-offenders you get is different, you will need to amend the code below accordingly (this will happen if you did not use the seed or generated the original skewed variable more than once).If you get the following message it means you are using the wrong number of people in each category: *number of items to replace is not a multiple of replacement lengthnumber of items to replace is not a multiple of replacement length*.


```r
fake_population$IQ[fake_population$offender == "No"] <- rnorm(64377, mean = 100, sd = 15)
```

And now we are going to artificially create somehow dumber offenders.


```r
fake_population$IQ[fake_population$offender == "Yes"] <- rnorm(35623, mean = 92, sd = 20)
```

We can now have a look at the data. Let's plot the density of IQ for each of the two groups and have a look at the summary statistics. 


```r
##This will give us the mean IQ for the whole population
mean(fake_population$IQ)
```

```
## [1] 97.19921
```

```r
#We will load the plyr package to get the means for IQ for each of the two offending groups
library(plyr)
#We will store this mean in a data frame (IQ_means) after getting them with the ddply function
IQ_means <- ddply(fake_population, "offender", summarise, IQ = mean(IQ))
#You can see the mean value of IQ for each of the two groups, unsurprisingly they are as we defined them
IQ_means
```

```
##   offender       IQ
## 1       No 99.96347
## 2      Yes 92.20370
```
We are going to create a plot with the density estimation for each of the plots (first two lines of code) and then I will add a vertical line at the point of the means (that we saved) for each of the groups


```r
ggplot(fake_population, aes(x = IQ, colour = offender)) + 
  geom_density() +
  geom_vline(data = IQ_means, mapping = aes(xintercept = IQ, colour = offender), linetype = "dashed", size = 1)
```

![](05-inference_files/figure-latex/unnamed-chunk-11-1.pdf)<!-- --> 

So, now we have our fake population data. In this case, because we generated the data ourselves, we know what the "population"" data looks like and we know what the summary statistics for the various attributes (IQ, crime) of the population are. But in real life we don't normally have access to full population data. It is not practical or economic. It is for this reason we rely on samples.

## Sampling data and sampling variability

It is fairly straightforward to sample data with R. The following code shows you how to obtain a random sample of size 10 from our population data above:


```r
#We will use the sample function within the mosaic package. 
library(mosaic) 
sample(fake_population$IQ, 10)
```

```
##  [1] 123.02991 108.10296  94.90335 101.76552 102.96829 100.88919 105.88429
##  [8] 107.06557  90.07606 108.01750
```

First of all notice that `mosaic` masks quite a few functions from various packages. If you want to use them remember to use the `'package_I_need'::'for_function_I_want'` formula we covered in previous sessions. 

You may be getting sample elements that are different from mine, depending on the seed you used and how many times before you tried to obtain a *random* sample. You can compute the mean for a sample generated this way:


```r
mean(sample(fake_population$IQ, 10))
```

```
## [1] 102.9824
```

And every time you do this, you will be getting a slightly different mean. Try to rerun the code several times. This is one of the problems with sample data. Not two samples are going to be exactly the same and as a result, every time you compute the mean you will be getting a slightly different value. Run the function three or four times and notice the different means you get as the elements that make up your sample vary.

We can also use code to automatise the process. The following code will ask R to draw 15 samples of size 10 and obtain the means for each of them.


```r
do(15) * with(sample(fake_population, 10), mean(IQ))
```

```
##         with
## 1   91.83841
## 2   92.54385
## 3   99.13335
## 4  102.72856
## 5  102.78062
## 6   94.71675
## 7   83.25669
## 8   95.69518
## 9   97.58754
## 10 103.38229
## 11  93.91211
## 12 105.36669
## 13  93.90070
## 14  95.85066
## 15  96.46357
```

So here we have the means that we obtain from 15 different samples from this population. Notice how they vary. We can store the results from an exercise such as this as a variable and plot it:


```r
#The following code will create a dataframe with the results
samp_IQ <- do(15) * with(sample(fake_population, 10), mean(IQ))
#You can see the name of the variable designating the means in the create data frame
names(samp_IQ)
```

```
## [1] "with"
```

```r
#We are going to create a data frame with the population mean
IQ_mean <- data.frame(mean(fake_population$IQ))
#Have a look inside the object to see what the variable containing the mean is called (and we can then use this name in our plot function)
names(IQ_mean)
```

```
## [1] "mean.fake_population.IQ."
```

```r
#And we can plot it then
ggplot(samp_IQ, aes(x = with)) + 
  geom_histogram() +
  geom_vline(data = IQ_mean, mapping = aes(xintercept = mean.fake_population.IQ.), 
             linetype = "dashed", size = 1, colour = "red") + #This code will add a red line with the overall mean
  labs(x = "Value of the sample means", y = "Number of samples") +
  annotate("text", x = 99.8, y = 3, label = "Population mean", colour = "red") + #Annotate is used to insert elements in the graphic, in this case text indicating what the red line means, the x and y indicate the position where the annotation will appear in regards to the x and the y axis (this position may not be optimal depending on the means you get when you run this code)
  theme_bw()
```

```
## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.
```

![](05-inference_files/figure-latex/unnamed-chunk-15-1.pdf)<!-- --> 

Your exact results may differ from those shown here, but you can surely see the point. We have a problem with using sample means as a guess for population means. Your guesses will vary. How much of a problem is this? [This excellent piece and demonstration](http://www.nytimes.com/2014/05/02/upshot/how-not-to-be-misled-by-the-jobs-report.html?_r=0) by New York Times reporters illustrate the problem well. We are going to learn that something called the **central limit theorem** is of great assistance here.

## Sampling distributions and sampling experiments

We are going to introduce an important new concept here: **sampling distribution**. A sampling distribution is the probability distribution of a given statistic based on a random sample. It may be considered as *the distribution of the statistic for all possible samples from the same population of a given size*. 

We can have a sense for what the sampling distribution of the means of IQ for samples of size 10 in our example by taking a large number of samples from the population. This is called a **sampling experiment**. Let's do that. We will take 50000 samples (rather than 15 as before) of size 10 (that is, with ten elements each) and compute the means. This may take a bit. Wait until you see the object appear in your environment.


```r
sampd_IQ_10 <- do(50000) * with(sample(fake_population, 10), mean(IQ))
```

So now we have 50000 sample means from samples of size 10 taken from our fake population. We are now going to take the mean of this 50000 sample means and then we are going to compare it to the population mean.


```r
mean(sampd_IQ_10$with) #mean of the sample means
```

```
## [1] 97.17187
```

```r
mean(fake_population$IQ) #mean of the population
```

```
## [1] 97.19921
```


BOOM! They are pretty much the same. What we have observed is part of something called the **central limit theorem**, a concept from probability theory. One of the first things that the central limit theorem tells us is that **the mean of the sampling distribution of the means (also called the expected value) should equal the mean of the population**. It won't be quite the same in this case (to all the decimals) because we only took 50000 samples, but in the very long run (if you take many more samples) they would be the same.

Let's now visually explore the distribution of the sample means.


```r
#Now we plot the means
qplot(sampd_IQ_10$with, xlab = "Distribution of means from samples of size 10")
```

![](05-inference_files/figure-latex/unnamed-chunk-18-1.pdf)<!-- --> 

ta-da, Amazing! isn't it? When you (1) take many random samples from a normally distributed variable; (2) compute the means for each of these samples; and (3) plot the means of each of these samples, you end up with something that is also normally distributed. **The sampling distribution of the means of normally distributed variables in the population is normally distributed**. I want you to think for a few seconds as to what this means and then keep reading.

What this type of distribution for the sample means is telling us is that most of the samples will give us guesses that are clustered around their own mean, as long as the variable is normally distributed in the population (which is something, however, that we may not know). Most of the sample means will cluster around the value of 97.11 (in the long run), which is the population mean in this case. There will be some samples that will give us much larger and much smaller means (look at the right and left tail of the distribution), but most of the samples won't gives us such extreme values.

So although every sample will give us different values to the mean, in the long run, they will tend to be similar to the mean of the population. If you were to take repeated samples from the same population more often than not, the sample mean will be closer rather than far from the population mean. When you take a sample you have no way of knowing if your sample is one of those that got close to the population mean or far from it. But it is somehow reassuring to know the procedure in the long run tends to get it right more often than not.

Another way of saying this is that the means obtained from random samples behave in a predictable way. When we take just one sample and compute the mean we won't we able to tell whether the mean for that sample is close to the centre of its sampling distribution (and thus to the population mean). But we will know the probability of getting an extreme value for the mean is lower than the probability of getting a value closer to the mean. That is, if we can assume that the variable in question is normally distributed in the population.

But it gets better. Let's repeat the exercise with a sample size of 30, 100 and 1000. This code will take some time to run. But compare it with how long it would take you to take 10 pieces of paper from a bag with 100000 pieces of paper 50000 times...


```r
sampd_IQ_30 <- do(50000) * with(sample(fake_population, 30), mean(IQ))
sampd_IQ_100 <- do(50000) * with(sample(fake_population, 100), mean(IQ))
sampd_IQ_1000 <- do(50000) * with(sample(fake_population, 1000), mean(IQ))  

#Let's plot the results, notice how we have changed the aesthetics. 
#We are definig them within each geom because we are using different data stored in different dataframes.
ggplot() + 
  geom_density(data = sampd_IQ_1000, aes(x = with, fill = "1000"), position = "identity", alpha = 0.4) +
   geom_density(data = sampd_IQ_100, aes(x = with, fill = "100"), position = "identity", alpha = 0.4) +
   geom_density(data = sampd_IQ_30, aes(x = with, fill = "30"), position = "identity", alpha = 0.4) +
  labs(fill = "Sample size") + #This will change the title of the legend
  scale_fill_discrete(limits = c("1000", "100", "30")) + #This will ensure the order of the items in the legend is correct
  xlab("Distribution of mean value of IQ")
```

![](05-inference_files/figure-latex/unnamed-chunk-19-1.pdf)<!-- --> 

Pay attention to the aesthetics here. Because essentially we are looking at three different datasets, the variables we plot are identified not in an `aes` statement within the general `ggplot()` function but rather the `aes` are included and specified within each of the geoms we are plotting. 

But back to the substantive point, can you notice the differences between these **sampling distributions**? *As the sample size increases, more and more of the samples tend to cluster closely around the mean of the sampling distribution*. In other words with larger samples the means you get will tend to differ less from the population mean than with smaller samples. You will be more unlikely to get means that are dramatically different from the population mean.

Let's look closer to the summary statistics using `favstats()` from the loaded `mosaic` package:


```r
favstats(~with, data = sampd_IQ_30)
```

```
##       min       Q1   median       Q3      max     mean       sd     n missing
##  84.36391 95.10328 97.23989 99.36223 109.4893 97.22025 3.159672 50000       0
```

```r
favstats(~with, data = sampd_IQ_100)
```

```
##       min       Q1   median       Q3      max     mean       sd     n missing
##  90.40428 96.03429 97.21813 98.38842 103.9214 97.20767 1.743929 50000       0
```

```r
favstats(~with, data = sampd_IQ_1000)
```

```
##       min       Q1   median       Q3     max     mean        sd     n missing
##  94.84451 96.83374 97.20142 97.56903 99.5329 97.19854 0.5469711 50000       0
```


As you can see the mean of the sampling distributions is pretty much the same regardless of sample size, though since we only did 50000 samples there's still some variability. But notice how the **range** (the difference between the smaller and larger value) is much larger when we use smaller samples. When I run this code I get one sample of size 30 with a sample mean as low as 83 and another as high as 110. But when I use a sample size of a 1000 the smallest sample mean I get is 95 and the largest sample size I get is 99. *When the sample size is smaller the range of possible means is wider and you are more likely to get sample means that are wide off from the expected value.*

This variability is also captured by the standard deviation of the sampling distributions, which is smaller the larger the sample size is. The standard deviation of a sampling distribution receives a special name you need to remember: the **standard error**. In our example, with samples of size 30 the standard error is 3.16, whereas with samples of size 1000 the standard error is 0.55.

We can see that the precision of our guess or estimate (that is the sample mean we use to infer the population mean) improves as we increase the sample size. So we can conclude that using the sample mean as a estimate (we call it a **point estimate** because it is a single value, a single guess) of the population mean is not a bad thing to do *if your sample size is large enough and the variable can be assumed to be normally distributed in the population.* As we have illustrated here, more often than not this guess won't be too far off in those circumstances.

But what about variables that are not normally distributed. What about *"crimecount"*? We saw this variable was quite skewed. Let's take numerous samples, compute the mean of *"crimecount"*, and plot its distribution. Let's generate the sampling distributions for sample sizes of 30, 100, and 1000 elements. This will take a minute or so depending in how good your machine is.


```r
sampd_CR_30 <- do(50000) * with(sample(fake_population, 30), mean(crimecount))
sampd_CR_100 <- do(50000) * with(sample(fake_population, 100), mean(crimecount))
sampd_CR_1000 <- do(50000) * with(sample(fake_population, 1000), mean(crimecount))
```

And now let's plot the means from these samples (the sampling distributions).


```r
ggplot() + 
  geom_density(data=sampd_CR_1000, aes(x = with, fill = "1000"), position = "identity", alpha = 0.4) +
   geom_density(data=sampd_CR_100, aes(x = with, fill = "100"), position = "identity", alpha = 0.4) +
   geom_density(data=sampd_CR_30, aes(x = with, fill = "30"), position = "identity", alpha = 0.4) +
  labs(fill = "Sample size") + #This will change the title of the legend
  scale_fill_discrete(limits = c("1000", "100", "30")) #This will ensure the order of the items in the legend is correct
```

![](05-inference_files/figure-latex/unnamed-chunk-22-1.pdf)<!-- --> 

```r
favstats(~with, data = sampd_CR_30)
```

```
##         min        Q1    median       Q3      max     mean        sd     n
##  0.06666667 0.7333333 0.9666667 1.233333 3.166667 1.003719 0.3804143 50000
##  missing
##        0
```

```r
favstats(~with, data = sampd_CR_100)
```

```
##   min   Q1 median   Q3  max     mean        sd     n missing
##  0.36 0.86   0.99 1.13 2.05 1.003114 0.2082509 50000       0
```

```r
favstats(~with, data = sampd_CR_1000)
```

```
##    min    Q1 median    Q3   max     mean         sd     n missing
##  0.751 0.957      1 1.045 1.307 1.001474 0.06548459 50000       0
```

```r
mean(fake_population$crimecount)
```

```
## [1] 1.00143
```

You can see something similar happens. Even though *"crimecount"* itself is not normally distributed. The sampling distribution of the means of *"crimecount"* becomes more normally distributed the larger the sample size gets. Although we are not going to repeat the exercise again, the same would happen even for the variable *"offender"*. With a binary categorical variable such as offender (remember it could take two values: yes or no) the "mean" represents the proportion with one of the outcomes. But essentially the same process applies.

What we have seen in this section is an illustration of various amazing facts associated with the central limit theorem. Most sample means are close to the population mean, very few are far away from the population mean, and on average, we get the right answer (i.e., the mean of the sample means is equal to the population mean).  This is why statisticians say that the sample mean is an **unbiased** estimate of the population mean.

How is this helpful? Well, it tells us we need large samples if we want to use samples to guess population parameters without being too far off. It also shows that although sampling introduces error (**Sampling Error**: the difference between the sample mean and the population mean), this error behaves in predictable ways (in most of the samples the error will be small, but it will be larger in some: following a normal distribution). In the next section, we will see how we can use this to produce something called confidence intervals.

If you want to further consolidate some of these concepts you may find [these videos](https://www.khanacademy.org/math/probability/statistics-inferential/sampling_distribution/v/central-limit-theorem) on sampling distributions from Khan Academy useful.

## The normal distribution and confidence intervals with known standard errors

While the sample mean may be the best single number to use as an estimate of the population mean, particularly with large samples, each sample mean will continue to come with some sample error (with some distance from the population mean). How can we take into account the uncertainty in estimating the population mean that derives from this fact?

The key to solving the problem relies in the fact that the sampling distribution of the means will approach normality with large samples. *If we can assume that the sampling distribution of the means is normally distributed* then we can take advantage of the properties of the **standard normal distribution**. 

One of the peculiarities of the standard normal distribution is that we know the proportion of cases that fall within standard deviation units away from the mean. In the graphic below you can see the percentage of cases that fall within one and two standard deviations from the mean in the standard normal distribution:

![](imgs/nd_1.png)

We know that the sampling distribution of the means can be assumed with large samples to have a shape like this. We saw that when we run our sampling experiment. You can think of the sampling distribution of the means as the distribution of sampling error. Most sample means fall fairly close to the *expected value* (i.e., the population mean) and so have small sampling error; many fall a moderate distance away; and just a few fall in the tails of the sampling distribution, which signals large estimation errors. So although working with sample data we don’t have a precise distance of our sample mean from the population mean, we now have a model that tells us how that distance behaves (i.e., it follows a normal distribution). Let this sink in for a few seconds. 

This is very useful because then we can use this knowledge to generate what we call the **margin of error**. The margin of error is simply *the largest likely sampling error*. In social science we typically choose likely to imply 95%. So that there is a 95% chance that the sampling error is less than the margin of error. By extension this means that there is only a 5% chance that the sampling error will be bigger: that we have been very unlucky and our sample mean falls in one of the tails of the sampling distribution. Again, this may sound a bit abstract but below it will become clearer.

Looking at the theoretical standard normal distribution we know that about 95% of the cases fall within 2 standard deviations on either side of the mean. We know then that 95% of the sample means (95.46% to be more precise) will fall within two standard errors  of the expected value (e.g., the mean of the sampling distribution). So we can say that the margin of error, the largest likely estimation error, equals 2 standard errors. More accurately, the margin of error equals 1.96 standard errors (1.96 corresponds to 95% whereas the value 2 corresponds to 95.46%).

This may be much clearer with an example. Let’s focus in our variable “IQ”. Look at the standard error (the standard deviation of the collection of sample means) for the sampling distribution of “IQ” when we took samples of 100 cases. We produced this earlier on.  


```r
se_sampd_IQ_100 <- favstats(~with, data=sampd_IQ_100)
se_sampd_IQ_100$sd
```

```
## [1] 1.743929
```

The standard error was 1.7439289. If we multiply 1.7439289 times 1.96 we obtain 3.4181007. This means that 95% of the cases in this sampling distribution will have an error that won’t be bigger than that. They will only at most differ from the mean of the sampling distribution by (plus and minus) 3.4181007. However, 5% of the samples will have a margin of error bigger than that (in absolute terms).

The wonderful thing is that we can use the margin of error to provide information about the degree to which our sample estimate may vary from the population mean. We can use it to give a measure of the uncertainty in our estimation. How?

>“We rely on this obvious relation: If M” (our sample mean) “is likely to be close to μ” (the population mean) “-as the last page or two has illustrated- then μ is likely to be close to M. As simple as that. The simulation shows us that, for most samples, M” (the sample mean) “falls pretty close to μ” (the population mean) “, in fact within margin of error of μ. Now, we have only a single M and don’t know μ. But, unless we’ve been unlucky, our M has fallen within the margin of error of μ, and so, if we mark out an interval extending the margin of error on either side of our, most likely we’ve included μ. Indeed, and that interval is the confidence interval (CI)” (Cumming, 2012: 69).

If we have a large random sample, the 95% confidence interval will then be:  
Upper limit= sample mean + 1.96 * standard error  
Lower limit= sample mean - 1.96 * standard error

This will be clearer with a complete example. Let's extract a sample of size 100 from the "fake_population" and look at the distribution of IQ:


```r
sample_1 <- sample(fake_population, 100)
mean(sample_1$IQ)
```

```
## [1] 98.99451
```

When I then take the mean of "IQ" in this sample I get the value of 98.994507. It does not matter if you get a different value. Remember the standard error for the sampling distribution of “IQ” when we took samples of a 100 cases. It was 1.7439289. If we multiply 1.7439289 times 1.96 we obtain 3.4181007.  The upper limit for the confidence interval then will be 98.994507 (my sample mean) plus 3.4181007 (the margin of error) and the lower limit for the confidence interval will be 98.994507 minus 3.4181007. This yields a confidence interval ranging from 95.5764063 to 102.4126077. 

Now, if your sample mean would have been different, your confidence interval would have also been different. If you take 10,000 sample means and compute 10,000 confidence intervals they will be different among themselves. In the long run, that is, if you take a large enough numbers of samples and then compute the confidence interval for each of the samples, *95% of those confidence intervals will capture the population mean and 5% will miss it*. Let’s explore this.

We are first going to select 100 means (from the samples of size 100) out of the 50,000 samples that we created (if you don't understand this code, have a second look at the notes from Chapter 1)


```r
samp_IQ_100 <- sampd_IQ_100[1:100, ]
ci_IQ <- data.frame(meanofIQ = samp_IQ_100)
```

We are now going to create the lower and the upper limit for the confidence interval. First we obtain the margin of error. To do this I will compute the summary statistics for the sampling distribution and then multiply the standard error (e.g., the standard deviation of the sampling distribution) times 1.96.


```r
se_sampd_IQ_100 <- favstats(~with, data=sampd_IQ_100)
me_IQ_100 <- se_sampd_IQ_100$sd * 1.96 #sd is the name of the variable returned from favstats() that includes the information about the standard deviation of the distribution we were exploring. Notice how one of the beauties of R is that it allows you to extract content from the objects it creates so that then you use them for whatever purpose you want. Here we compute the margin of error by multiplying this times 1.96.
```

Then I will create two numerical vectors with the upper and the lower limit and then add them to the data frame we created


```r
ci_IQ$LowerLimit <- samp_IQ_100 - me_IQ_100
ci_IQ$UpperLimit <- samp_IQ_100 + me_IQ_100
```

You may want to use the `View()` function to see inside the `ci_IQ` data frame that we have created. Every row represents a sample and for each sample we have the mean and the limits of the confidence interval. We can now query how many of these confidence intervals include the mean of the variable crime in our fake population data.


```r
ci_IQ$indx <- (ci_IQ$LowerLimit <= mean(fake_population$IQ)) & 
  (ci_IQ$UpperLimit >= mean(fake_population$IQ))
sum(ci_IQ$indx)
```

```
## [1] 95
```
If you look inside the *ci_IQ* object using `View(ci_IQ)` you will see that there is now a logical vector called *indx* telling us whether that particular sample confidence interval includes or not the population mean.

Thus 95 intervals contain the true population mean. If you feel playful (and curious) you may want to modify the code we have use above to check how many of a 100 or of 200 samples for example would contain the true population mean. It should be roughly around 95% of them. Pretty cool, isn't it?

We can also plot these confidence intervals. First We are going to create an ID variable to identify each sample (I will need this as an input in the plot I will create). I will use the row name (that list the samples from 1 to 1 100) as my ID variable.


```r
ci_IQ$id <- rownames(ci_IQ)
```

We are going to use a new `geom` we have not covered so far that allows you to create lines with a point in the middle. You need to tell R where the line begins and ends, as well as where to locate the point in the middle. The point in the middle is our mean and the lines range from the lower limit and upper limit. In this sense each line represents the confidence interval. We will use the ID variable so that R plots one line for each of the samples. Finally We are asking R to use the *"indx"* variable we create so that we can distinguish clearly the confidence intervals that cover the population mean. You are not going to need this code for your homework or assignments, so do not worry if you don't fully get it.


```r
ggplot(ci_IQ, aes(x = id, y = meanofIQ, ymin = LowerLimit, ymax = UpperLimit, group= indx, color = indx)) +
  geom_hline(yintercept  = mean(fake_population$IQ), colour = "red", size = 1) + #This will create a horizontal line representing the population mean, so that we can clearly see it
  geom_pointrange(aes(ymin = LowerLimit, ymax = UpperLimit)) +
  theme_bw() +
  ggtitle("Confidence intervals for the mean (100 samples of size 100)") +
  labs(colour="Covers μ?", x = "", y ="Mean of IQ") +
  scale_x_discrete(breaks = "") + #this ensures that no tick marks and labels are used in the axis defining each sample (try to run the code witout this line to see what happens if you don't include it)
  coord_flip() 
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

```
## Warning in grid.Call.graphics(C_text, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <ce>
```

```
## Warning in grid.Call.graphics(C_text, as.graphicsAnnot(x$label), x$x, x$y, :
## conversion failure on 'Covers μ?' in 'mbcsToSbcs': dot substituted for <bc>
```

![](05-inference_files/figure-latex/unnamed-chunk-30-1.pdf)<!-- --> 

The horizontal lines represent the confidence intervals for the mean for each of the samples. The point in the middle of those lines represent each of the sample means. The colours indicate whether the confidence intervals cross (cover) the population mean (represented by the vertical red line). You can see that 5 (this may vary slightly according to your random samples) are red, and 95 are greenish. Few of the sample means touch the red line, but most confidence intervals include it.

If we know the population mean, then we can see whether a sample confidence interval overlaps with the population mean. But in real life we run samples precisely because we don't know the population parameters. So, unfortunately, when you do a sample you can never be sure whether your estimated confidence interval is one of the red or the green ones!!! 

The truth is we will never know whether our confidence interval captures the population parameter or not, *we can only say that under certain assumptions if we had repeated the procedure many times our confidence interval will include the population mean 95% of the time*. It is important not to get confused about it. We cannot never know in real life applications if our confidence interval actually covers the population mean. This is one of the reasons why in statistics when making inferences we cannot provide definitive answers[^2], there is always an element of uncertainty that is part of any scientific endeavour - and which goes along way towards explaining why we need to replicate studies, to see if theirs findings hold. 

It is generally considered better practice to report your confidence intervals than your point estimates. Why?  

+ First, because you are being explicit about the fact you are just guessing. Point estimates such as the mean create a false impression of precision.  
+ But beware the CI can also be misleading! 95% of the times you may get the true parameter, but that’s not the same than to say that 95% of the time your mean will lie between your upper and lower boundaries for your confidence interval. [This is a common interpretative mistake made by researchers and, even, teachers](http://link.springer.com/article/10.3758%2Fs13423-013-0572-3). Do not make it yourself!!! **A confidence interval can only be used to evaluate the procedure not a specific estimated interval**.  

So to reiterate:  

+ INCORRECT INTERPRETATION: “There is a 95% chance that the mean IQ is between 89.7 and 104.7 minutes”. This is a very common misconception! It seems very close to true, but it isn’t because the population mean value is fixed. So, it is either in the interval or not and you can't possibly know whether that is the case. This is subtle but important.
+ What is correct? **95% of the time, when we calculate a confidence interval in this way, the true mean will be between the two values. 5% of the time, it will not.** Because the true mean (population mean) is an unknown value, we don’t know if we are in the 5% or the 95%. BUT 95% is pretty good. This is the only correct interpretation of our confidence interval, so do not take it any other as valid.
+ Is is not terrible to say something like “We are 95% confident that the mean IQ for all people in our fake population is between 89.7 and 104.7.” This is a common shorthand for the idea that the calculations “work” 95% of the time. But beware in true even this shorthand is incorrect for it seems to imply the particular confidence interval is correct, when all we can do is statements about the procedure not about the specific boundaries of our CI (as the "We are 95% confident" statement does). 
+ Remember that we can’t have a 100% confidence interval. By definition, the population mean is not known . If we could calculate it exactly we would! But that would mean that we need a census of our population with is often not possible or feasible.
+ Finally, because if the range of values that you give me for your CI is smaller or bigger I will know that your estimate is more or less precise respectively. That is, **with the CI you are giving me a measure of your uncertainty.** The bigger the CI the more uncertain we are about the true population parameter.

## Asymptotic confidence intervals for means and proportions using R

You may have spotted a big problem in what came before. How did we compute the confidence interval? We multiplied 1.96 times the standard error. Remember: the standard error is the standard deviation of the sampling distribution of the mean. And… well, at least you are willing to repeat a survey thousands and thousands of times with the same population you won’t know what the standard error is! The population mean is unknown and we want to estimate it. *But the standard error that we need for constructing our confidence interval is also unknown!* 

If you are working with proportions there is an obvious way to estimate the standard error only with sample data (for details see the required reading). But with means this is not possible. There is, however, a solution. You can use **the standard deviation of your sample** as an estimate for the **standard error**. You would also need to make some adjustments to the formula for the confidence interval (you divide the sample standard deviation by the square root of the sample mean). You don't need to worry to much about the mathematics of it. In practice we will rely on R to apply these formulas and compute the confidence intervals. 

It is important, though, that you know that this approach works reasonably well when applying the normal probability model to large samples. But with small samples using the sample standard deviation as an estimate of the standard error (so that we can compute the confidence interval) is problematic. The sample standard deviation also varies from sample to sample and this extra variation in smaller samples will mess up the computation of the margin of errors. William Gosset's suggested we needed to use a different probability distribution for this cases, the *Student's t-distribution*.  

You can learn more about this distribution and the work of Gosset in the suggested reading. The Student's t-distribution and the normal distribution are almost indistinguishable for large samples. In essence that means you will still multiply by 1.96. But with smaller sample sizes that value will be different if you use a normal distribution or Student's t-distribution. Refer to the recommended textbooks for further clarification.

It is fairly straightforward to get the confidence intervals using R. *In order to use the Student's t-distribution we need to assume the data were randomly sampled and that the population distribution is unimodal and symmetric.* We know this is the case in the population and next week we will discuss how you can check this assumption when you don't have the population data.

Earlier we created a sample of 100 cases from our fake population. Let's build the confidence intervals using the sample standard deviation as an estimate for the standard error and assuming we can use the Student's t-distribution:


```r
t.test(sample_1$IQ)
```

```
## 
## 	One Sample t-test
## 
## data:  sample_1$IQ
## t = 58.162, df = 99, p-value < 2.2e-16
## alternative hypothesis: true mean is not equal to 0
## 95 percent confidence interval:
##   95.61727 102.37175
## sample estimates:
## mean of x 
##  98.99451
```

Ignore for now the few first lines of this output. Just focus on the 95% interval. You will see it is not wildly different from the one we derived using the actual standard error.

If you want a different confidence interval, say 99%, you can pass an additional argument to change the default in the `t.test()` function. In this case, when saying `.99` we are saying that if we were to repeat the procedure 99% of the confidence intervals would cover the population parameter.


```r
t.test(sample_1$IQ, conf.level = .99)
```

```
## 
## 	One Sample t-test
## 
## data:  sample_1$IQ
## t = 58.162, df = 99, p-value < 2.2e-16
## alternative hypothesis: true mean is not equal to 0
## 99 percent confidence interval:
##   94.52423 103.46478
## sample estimates:
## mean of x 
##  98.99451
```

What if you have a factor and want to estimate a confidence interval for a proportion. In our data we have a dichotomous variable that identifies cases as offenders.


```r
table(sample_1$offender)
```

```
## 
##  No Yes 
##  66  34
```

We can use the `prop.test()` function in these cases:


```r
prop.test(sample_1$offender=="Yes") #We want to estimate the proportion of respondents who are offenders, which is why we specifically ask for those classified as "Yes"
```

```
## 
## 	1-sample proportions test with continuity correction
## 
## data:  ==  [with success = TRUE]sample_1$offender  [with success = TRUE]Yes  [with success = TRUE]
## X-squared = 9.61, df = 1, p-value = 0.001935
## alternative hypothesis: true p is not equal to 0.5
## 95 percent confidence interval:
##  0.2501177 0.4423445
## sample estimates:
##    p 
## 0.34
```

You can also specify a different confidence level:


```r
prop.test(sample_1$offender=="Yes", conf.level = .99)
```

```
## 
## 	1-sample proportions test with continuity correction
## 
## data:  ==  [with success = TRUE]sample_1$offender  [with success = TRUE]Yes  [with success = TRUE]
## X-squared = 9.61, df = 1, p-value = 0.001935
## alternative hypothesis: true p is not equal to 0.5
## 99 percent confidence interval:
##  0.227086 0.473612
## sample estimates:
##    p 
## 0.34
```

The `prop.test()` function uses a normal approximation to compute the confidence interval. This approximation may not work well when the outcome of interest is rare or uncommon or with small samples. A number of alternative formulas have been proposed for these cases. Check Wikipedia for "binomial proportion confidence interval". To get R to compute these alternative ways you need to install and load the `binom` package.


```r
library(binom)
binom.confint(34, 100) #This function takes as the first argument the count for the outcome of interest and the sample size as the second argument
```

```
##           method  x   n      mean     lower     upper
## 1  agresti-coull 34 100 0.3400000 0.2544306 0.4374073
## 2     asymptotic 34 100 0.3400000 0.2471548 0.4328452
## 3          bayes 34 100 0.3415842 0.2507476 0.4341676
## 4        cloglog 34 100 0.3400000 0.2491861 0.4327669
## 5          exact 34 100 0.3400000 0.2482235 0.4415333
## 6          logit 34 100 0.3400000 0.2540660 0.4379354
## 7         probit 34 100 0.3400000 0.2527521 0.4368062
## 8        profile 34 100 0.3400000 0.2520471 0.4360562
## 9            lrt 34 100 0.3400000 0.2520248 0.4360417
## 10     prop.test 34 100 0.3400000 0.2501177 0.4423445
## 11        wilson 34 100 0.3400000 0.2546152 0.4372227
```

Here you can see 11 different confidence intervals that are computed using different formulas and approaches. You will see that in this case the differences between the Normal approximation and these methods are minimal, but there may be scenarios where this is not the case.

Remember that *confidence intervals may be easy to construct (just one line of code!) but they are easy to misinterpret.* The word confidence in everyday meaning is subjective. Perhaps it would be better to have terms such as "sampling precision interval" (Kaplan, 2012), but we don't. Another common mistake when reading them is to think that you can say that "if you repeat the study and take the mean, the new result will be within the margin of error of the original study", but this is not correct mathematically (remember the plot of the confidence intervals).

## A brief intro to resampling and bootstraping

We have seen how theoretically the sampling distribution reflects variation from random samples. We also discussed how in practice we only have one sample. In the previous sections we also saw how we can some times use theoretical probability distributions (such as the normal or the t distribution) provided we are willing to make some assumptions. And we could then use these distributions to build our confidence intervals. 

Another way of building confidence intervals is called **bootstrapping**. This comes from the phrase: "He pulled himself up by his own trousers", which is said of someone who improves himself without help. Essentially what we are doing is estimating the properties of the sampling distribution from our single sample. How? By means of taking repeated samples (with replacement) *from our own sample*. These samples are called **resamples**. Essentially the sample is "used as a stand-in for the population and new samples are drawn from the sample" (Kaplan, 2012). Notice I said we use sampling *with* replacement. Every time we select a case from the sample, the case is put back so that we can select it again.

First, let's extract a sample of size 10


```r
sample_2 <- sample(fake_population$IQ, 10)
sample_2
```

```
##  [1] 105.93597  97.39249 114.46043 103.15389  81.59962  93.32657  80.87160
##  [8]  78.01179  91.06645  90.89693
```

We can then resample (drawing samples from the set of cases in our sample) with replacement. Notice we are not taking samples from the same population but new samples from our sample.


```r
resample(sample_2)
```

```
##  [1]  93.32657  80.87160 105.93597  91.06645  91.06645  81.59962  81.59962
##  [8]  81.59962 103.15389 105.93597
```

You can see how some elements in this resample are repeated from the original sample. In my resample, I have three with that one value in original sample. In your particular sample the combinations can be slightly different as R samples randomly.

Bootstrapping involves repeating this process many times and examining the variation among the resamples to construct a confidence interval based on the resampling distribution. Bootstraping won't work well with very small samples. The sample size should be one or two dozen or larger (Kaplan, 2012). So let's move to a slightly larger sample and then we will create the resampling distribution.


```r
sample_3 <- sample(fake_population$IQ, 30)
resampling_IQ_30_1 <- do(1000) * mean(resample(sample_3))
```

Then we can use the Mosaic `qdata()` function to extract the 95% coverage intervals:


```r
qdata(~mean, p = c(.025, .975), resampling_IQ_30_1)
```

```
##     2.5%    97.5% 
##  85.6076 100.6655
```

How does this compare to the confidence interval using the Student's t-distribution?


```r
t.test(sample_3)
```

```
## 
## 	One Sample t-test
## 
## data:  sample_3
## t = 23.429, df = 29, p-value < 2.2e-16
## alternative hypothesis: true mean is not equal to 0
## 95 percent confidence interval:
##   84.85121 101.08254
## sample estimates:
## mean of x 
##  92.96687
```

What if the sample size was larger?


```r
sample_4 <- sample(fake_population$IQ, 100)
resampling_IQ_100_1 <- do(1000) * mean(resample(sample_4))
qdata(~mean, p = c(.025, .975), resampling_IQ_100_1)
```

```
##      2.5%     97.5% 
##  95.61095 102.13736
```

```r
t.test(sample_4)
```

```
## 
## 	One Sample t-test
## 
## data:  sample_4
## t = 58.284, df = 99, p-value < 2.2e-16
## alternative hypothesis: true mean is not equal to 0
## 95 percent confidence interval:
##   95.33928 102.05956
## sample estimates:
## mean of x 
##  98.69942
```

As you can see as the sample size grows the differences between the bootstrap confidence interval and the one that relies on the t Student model become more similar.

Before we conclude this section, it is important to remember that the *resampling* distributions won't construct the sampling distribution. What they do is to show you how the sampling distribution may look like *if the population looked like your sample*. The centre of the resampling distribution is generally not aligned with the centre of the sampling distribution, although in practice the width of the re-sampling distribution in practice tends to match the width of the sampling distribution. The following figure shows you how three resampling distributions compare to the sampling distribution of IQ for samples of size 30.


```r
resampling_IQ_30_2 <- do(1000) * mean(resample(sample_3))
```


```r
resampling_IQ_30_3 <- do(1000) * mean(resample(sample_3))
```

![](05-inference_files/figure-latex/unnamed-chunk-45-1.pdf)<!-- --> 


## What about comparisons? Sampling distribution for the difference of two means

So far we have seen how we can use confidence intervals to quantify the unavoidable uncertainty that exists when you use sample data to make inferences about population parameters. In doing this, the focus of our discussion has been *univariate* estimation; that is, we were focusing on the logic involved in estimating single quantities (descriptive values for single variables) such as the mean or the proportion for a given variable (i.e., the proportion of households that suffer a burglary victimisation). 

But statistics is all about comparisons. And making comparisons involves working with several variables or groups at the same time. So most often we need to estimate information about various variables or groups at the same time. When making comparisons we also have to take into account sampling variability. 

Imagine that we want to know whether there is a difference in the level of fear experienced by males and females. Suppose we want to compare the average level of fear of violent crime across the two genders. We could use the data from the British Crime Survey we have been using so far (please load the data if you don't have it in your global environment from previous weeks). But we also need to take into account sampling variability. The estimated mean for fear of crime for males will be subject to some sampling error. The same for females. And the same for the difference between the two means.


```r
##R in Windows have some problems with https addresses, that's why we need to do this first:
urlfile<-'https://raw.githubusercontent.com/eonk/dar_book/main/datasets/BCS0708.csv'
#We create a data frame object reading the data from the remote .csv file
BCS0708<-read.csv(url(urlfile))
```

We are going to use the `describeBy` function of the `psych` package to produce summary statistics by group.


```r
library(psych)
with(BCS0708, describeBy(tcviolent, sex))
```

```
## 
##  Descriptive statistics by group 
## group: female
##    vars    n mean   sd median trimmed  mad   min  max range skew kurtosis   se
## X1    1 4475 0.33 1.04   0.23    0.25 0.96 -2.35 3.56  5.91 0.61     0.02 0.02
## ------------------------------------------------------------ 
## group: male
##    vars    n  mean   sd median trimmed  mad   min  max range skew kurtosis   se
## X1    1 3959 -0.27 0.86  -0.44   -0.36 0.69 -2.35 3.81  6.16  1.1     1.91 0.01
```

```r
ggplot(BCS0708, aes(x = sex, y = tcviolent)) +
  geom_boxplot()
```

![](05-inference_files/figure-latex/unnamed-chunk-47-1.pdf)<!-- --> 

The mean value of fear of violent crime is -0.27 for the males and 0.33 for the females. There is a difference in the mean value of fear of crime of 0.6. Comparing the distributions in the boxplot seems to suggest that the distribution of scores on fear of violent crime tend to be higher than for the males. 

The question we need to ask ourselves is: would we observe similar differences if we were looking at population data (rather than sample data)? The answer to the previous questions, as you can imagine by now, is that here we also have the problem of sampling variability. 

If we were to take a different sample from the same population (1) we would obtain a slightly different mean score of fear for the men; (2) a slightly different mean score of fear for the women; and (3) correspondingly a slightly different difference between those two quantities. So rather than a difference of -0.6 points we may find a slightly different one. 

How do we deal with this? Again,  we can make assumptions about the sampling distributions of the estimated parameters and try to quantify our uncertainty around the observed difference. Earlier we only had to worry about one parameter (the mean or the proportion in the population). We said that thanks to the central limit theorem we can assume that with large samples the sampling distribution of this single parameter follows a normal distribution. Now instead we have two different population parameters (i.e., the mean score of fear for men, µ1, and the mean age of fear for women, µ2) and their difference (µ1 – µ2) . Look at the Figure below:

![](http://simon.cs.vt.edu/SoSci/converted/T-Dist/t-distribution.gif)

Now we are trying to work out two different population parameters (the population mean of fear for males and females), which are unknown, based on our observed sample estimates. If we were to take repeated samples from the same populations these sample-based estimates of the means would vary and so would the difference between them. But we know that if we were to take large repeated samples of men the sampling distribution of the means for fear of crime in the long run would follow a normal distribution. Equally, if we were to take repeated samples of women the same would happen. However, now we are not only interested in these two quantities (the mean for each group) we are also interested in the difference between them, the difference in the mean score of fear for females and males.

In essence, however, the same principles apply.  If we were to plot the distribution of the difference between these two quantities, the means for the men and the women for every single sample of repeated samples, we would also have a sampling distribution: the sampling distribution of the differences of the means as shown in the figure above. 

Here, as earlier, we could invoke the central limit theorem that, in this case, states that with large random samples the sampling distribution of the difference of the means will be normal. We can also apply a variation of this (Gosset’s theorem) that states that with small samples of normally distributed variables we can use the t-student distribution. We could then construct a 95% confidence interval for the difference of the means that would give us the range of plausible values from the same population. 

Remember how we construct confidence intervals for the mean by adding the mean to the standard error of the sampling distribution of the mean. Also remember how we used the standard deviation of the sample mean as a proxy for the standard error. The computation of the confidence interval for the difference of two means works in a similar way but we need to account for the fact that now we have two different variances (i.e., in our example the variance for men and for women). Otherwise, the logic for constructing the confidence interval remains the same. For details on computation and formula see appropriate textbooks.

If you want to compare two samples means you would use the following code to obtain the 95% confidence interval for the difference of the two means:


```r
t.test(tcviolent ~ sex, data = BCS0708)
```

```
## 
## 	Welch Two Sample t-test
## 
## data:  tcviolent by sex
## t = 29.114, df = 8398.3, p-value < 2.2e-16
## alternative hypothesis: true difference in means between group female and group male is not equal to 0
## 95 percent confidence interval:
##  0.5614656 0.6425300
## sample estimates:
## mean in group female   mean in group male 
##            0.3281656           -0.2738322
```

For now, I want you to ignore the first few lines of output and just focus in the bottom part. You see how the mean value of *"tcviolent"* (fear of violent crime) is printed for each of the two groups. If you subtract this two values you obtain around 0.6. Right above you see the confidence interval for the difference between these two means. This confidence ranges from 0.56 to 0.64. We are simply stating that the values in the interval are plausible as true values for the population parameter, and that values outside the interval are relatively implausible (although not impossible). 

Although our point estimate for the difference was 0.6 (=0.33-(-0.27)), the confidence interval gives us more information as to what the true difference may be in the population. In the long run, that is, if you take a large enough numbers of samples and then compute the confidence interval for each of the samples, 95% of those confidence intervals will capture the difference in the population and 5% will miss it. As before, always remember, we may have been unlucky and got one of those 5% confidence intervals.

*Notice that the confidence interval does not include the value zero*. The observed difference that we have between females and males is not consistent with a difference of zero in the population. The fact that our estimated CI for the difference of the means does not include zero invites the suggestion that the difference between males and females is different from zero in the population. If, on the other hand, you were to encounter a confidence interval for the difference of the means including the value of zero then you would be less confident that the difference in the population would not be zero. This makes sense. If zero is a very plausible value for the difference of the means in the population then we cannot on the basis of our sample data pretend otherwise.

## Comparing means visually by using error bars representing confidence intervals: inference by eye

In the previous section we have discussed how you can construct *the confidence interval for the difference between two means*. Another way of looking at whether the means of two groups are different in a population is by visually comparing *the confidence interval for the means of each of the two groups*. Think for a second about the semantic difference. If you don't get it, look back at the figure we represented above.

We can visualise the confidence interval for the sample mean score of fear of crime for the men and the women using `ggplot()`:


```r
#As usual we define the aesthetics first
ggplot(BCS0708, aes(x = sex, y = tcviolent)) +
        stat_summary(fun.data = "mean_cl_normal", geom = "pointrange") 
```

![](05-inference_files/figure-latex/unnamed-chunk-49-1.pdf)<!-- --> 

```r
#this function ask to display summary statistics as pointrange (the point is the mean and the lines end at the upper and lower CI limits). The "mean_cl_normal" uses the CI assuming normality.
#So if you prefer the bootstrapped confidence interval rather than assuming normality, you could use:
ggplot(BCS0708, aes(x = sex, y = tcviolent)) +
       stat_summary(fun.data = "mean_cl_boot", geom = "crossbar") #Here we are using a different geom just to show you the range of options, but you could also have used "pointrange". Or finally, you could also use "errorbars"
```

![](05-inference_files/figure-latex/unnamed-chunk-49-2.pdf)<!-- --> 

```r
ggplot(BCS0708, aes(x = sex, y = tcviolent)) +
       stat_summary(fun.data = "mean_cl_boot", geom = "errorbar") +
        stat_summary(fun.y = mean, geom = "point")
```

![](05-inference_files/figure-latex/unnamed-chunk-49-3.pdf)<!-- --> 

The point in the error bar represents the mean value for fear of crime for each of the groups and the error bars represent the upper and lower bound for the confidence interval for the mean fear of crime score for each of those two groups. Notice how *the confidence intervals do not overlap*. These confidence intervals provide a range of plausible values for the population parameters, the mean score of fear for males and females in the population. The fact that the CI do not overlap is another way of showing that there may be a difference in the population parameters for these two groups. Lack of any overlap is strong suggestion of a significant difference in the population.

If they were overlapping this would be indicating that some of the plausible values for the mean fear of crime score for males in the population would also be plausible values for the mean fear of crime for females in the population. In this case, when there is some overlap, it is less intuitive to interpret the confidence intervals. *You can have some overlap even if there is a real difference across the population means*. However, the greater the overlap the smaller the chance that there is a difference between the two means in the population. In particular, if the overlap is greater than about 50% for the length of the bar either side of the mean then you will be, roughly speaking, "very confident" that there is no real difference in the population. [This](http://www.apastyle.org/manual/related/cumming-and-finch.pdf) is a good guide about how to interpret error bars in this type of scenarios.



[^1]: Although we would like to think of our samples as random, it is in fact very difficult to generate random numbers in a computer. Most of the time someone is telling you they are using random numbers they are most likely using pseudo-random numbers. If this is the kind of thing that gets you excited you may want to read the [wiki entry](http://en.wikipedia.org/wiki/Random_number_generation#.22True.22_random_numbers_vs._pseudo-random_numbers). If you want to know how R generates these numbers you should ask for the help pages for the Random.Seed function.
[^2]: As an aside, you can use [this Java applet](https://digitalfirst.bfwpub.com/stats_applet/stats_applet_4_ci.html) to see what happens when one uses different parameters with confidence intervals. In the right hand side you will see a button that says “Sample”. Press there. This will produce a horizontal line representing the confidence interval. The left hand side end of the line represents the lower limit of the confidence interval and the right hand side end of the line represents the upper limit of the confidence interval. The red point in the middle is your sample mean, your point estimate. If you are lucky the line will be black and it will cross the green vertical line. This means that your CI covers the population mean. There will be a difference with your point estimate (i.e., your red point is unlikely to be just in top of the green vertical line). But, at least, the population parameter will be included within the range of plausible values for it that our confidence interval is estimating. If you keep pressing the “Sample” button (please do 30 or 50 times), you will see that most confidence intervals include the population parameter: most will cross the green line and will be represented by a black line. Sometimes your point estimate (the red point at the centre of the horizontal lines) will be to the right of the population mean (will be higher) or to the left (will be lower), but the confidence interval will include the population mean (and cross the green vertical line). 

<!--chapter:end:05-inference.Rmd-->

# Hypotheses 

## The logic of hypothesis testing

In the last unit we learned how to think about and build confidence intervals. We explained how we could use confidence intervals to deal with uncertainty when estimating population parameters. Confidence intervals as we will see are very commonly used in statistics. The other key inferential tool in data analysis is the hypothesis test. Today we will focus on this second tool. 

Last week we saw how we could use confidence intervals as well to form a view about whether there are differences across groups in the population. And we also saw how we could do "inference by eye" by virtue of visually comparing the confidence interval for the estimated mean value of fear for men and the estimated mean value of fear for women. Now we are going to use a different approach to make inferences about the existence of these differences in the population: hypothesis testing.

Wikipedia defines a statistical hypothesis test as "a method of making decisions using data from a scientific study". The logic of hypothesis testing is based in the work of a number of pioneers in the field of statistics, the British Ronald Fisher and Egon Pearson and the Polish Jerzy Neyman . This work is so important that [some people argue](https://simplystatistics.tumblr.com/post/18903448428/ra-fisher-is-the-most-influential-scientist-ever) that Sir Ronald Fisher is one of the most influential academics in the history of science; not a small feat! 

Hypothesis testing, or null hypothesis testing (NHST) as it is often referred to, proceeds in a number of steps. 

1.**We always start with a research question** 

Our research questions in criminology can vary: Are ethnic minorities more likely to be stopped and searched? Does punishing offenders reduces crime? Is crime going down? Is self-control associated with offending? Here we are asking are women more afraid of violent crime than men?

2.**To answer a research question we have to formulate at least one and sometimes several research hypotheses related to it** 

A research hypothesis is simply a proposed answer to our research question that we can test by carrying out some research. Research hypothesis can be directional and non-directional:

>"When the research hypothesis does not indicate a specific type of outcome, stating only that there is a relationship or a difference, we say that it is a **non-directional hypothesis**. However, in those cases where a researcher has a very clear idea of what to expect -based on prior research evidence and/or theory -the research hypothesis may be more precise. In this case, the researcher may specify the nature of the relationship that is expected. Such a research hypothesis is called a **directional hypothesis**. When a directional hypothesis is used, the researcher states at the outset that he or she is interested in a specific type of outcome -for example, that one group has more arrests than another. Suppose we are interested in comparing the arrest records of drug involved offenders with those of offenders who do not use drugs. Our research hypothesis might be simply that the arrest records of drug involved offenders and offenders who do not use drugs are different (a nondirectional hypothesis). But based on prior knowledge of criminal behaviour among drug-involved offenders, we might want to state a directional hypothesis -that drug-involved offenders have more serious arrest records than do non-drug involved offenders. One problem with choosing the latter option is that if we state our research hypothesis as a directional hypothesis, we are stating that we are not interested in outcomes that fall in the opposite direction. In criminal justice research, we can often be surprised by what we learn in a study. Accordingly, researchers generally are cautious in defining a directional research hypothesis" (Weisburd and Britt, 2010: 120)

In our example, the research hypothesis will be non-directional and simply state that there are differences in the fear of violent crime among men and women.

3. **The following step is to formulate what is called a null hypothesis**

In frequentist statistical inference we test hypothesis not in reference to the research hypothesis but in reference to the **null hypothesis**. The null hypothesis gains its name from the fact that it usually states that there is no relationship or no difference. "We make decisions about hypothesis in relation to the null hypothesis rather than the research hypothesis. This is because the null hypothesis states that the parameter in which we are interested is a particular value" (Weisburd and Britt. 2010: 122). 

In the example that we are using the null hypothesis would be that there is no difference in mean level of fear for males and females. This is the same than saying that the difference on fear for these two groups is zero. So, using the null hypothesis gives us a specific value. Typically this value is zero, whereas the research hypothesis would be consistent with any of many values other than zero.  We will see in a second why working with a precise value such as zero is helpful.

De Veaux et al (2012) explain the logic of hypothesis testing as being similar to the logic of jury trials. In jury trials within the Common Law tradition somebody is innocent until proven guilty:

>"the null hypothesis is that the defendant is innocent... The evidence takes the form of facts that seem to contradict the presumption of innocence. For us" (researchers) "this means collecting data... The next step is to judge the evidence. Evaluating the evidence is the responsibility of the jury in a trial, but if falls on your shoulders in hypothesis testing. The jury considers the evidence in light of the presumption of innocence and judges whether the evidence against the defendant would be plausible if the defendant were in fact innocent. Like the jury, you ask, **'Could these data plausibly have happened by chance if the null hypothesis were true?'** If they are unlikely to have occurred, then the evidence raises a reasonable doubt about the null hypothesis. Ultimately, you must make a decision. The standard of beyond a reasonable doubt is wonderfully ambiguous... But when you ask the same question of your null hypothesis, you have the advantage of being able to quantify exactly how surprising the evidence would be were the null hypothesis true" (De Veaux et al. 2012: 479)

So, in hypothesis testing we look at our observed sample data. In our case, we look at the difference in fear of violent crime for males and females and we ask ourselves the question: is the observed difference likely to have come from a population where the real difference is zero (as our null hypothesis specifies)? As you can see, testing against the null gives us the advantage of testing against a specific value. We can compare the value that we observe with zero, the precise value hypothesised by the null hypothesis. *The downsise of it is that few things are exactly the same in nature*. So to say that the level of fear of crime in men and women is probably not exactly the same (e.g., a difference of zero) is arguably not always going to give us the answer that we want.

4. **The fundamental step in hypothesis testing, therefore, is the question: are the observed data surprising, given the null hypothesis? And the key question is to determine exactly how likely the data we observed would be were the null hypothesis a true model of the world**

So in essence we are after a probability, specifically a conditional probability (i.e, *the probability of our data if the null hypothesis were true*). We are trying to quantify the probability of seeing data like the one we have observed (a difference of 0.79 in our example) if we take as given that the null hypothesis is true (and the value "should be" zero). We call this probability the **p value**. You may have heard this term before. All it means, it bears repeating, is **the probability of observing our data if the null hypothesis were true**.

>"**When the p value is high**, then we can conclude that we have not seeing anything unusual. Events that have a high probability of happening happen often. The data are thus consistent with the model from the null hypothesis, and we have no reason to reject the null hypothesis. But we realize many other similar hypotheses could also account for the data we've seen, so we haven't proven that the null hypothesis is true. The most we can say is that it doesn't appear to be false. Formally, we fail to reject the null hypothesis. That's a pretty weak conclusion, but it's all we're entitled to. **When the p value is low enough**, it says that it's very unlikely we'd observed data like these if our null hypothesis were true. We started with a model. Now the model tells us that the data are unlikely to have happened. The model and the data are at odds with each other, so we have to make a choice. Either the null hypothesis is correct and we've just seen something remarkable, or the null hypothesis is wrong..." (De Veaux et al. 2012: 480)

When is a p value high and when is low? Typically, we use criteria similar to those we use when constructing confidence intervals: we would consider a p value low enough if 95% of the time the observed data was considered to be inconsistent with the model proposed by our null hypothesis. So, we look for p values that are smaller or bigger than 0.05.

That is, we look for differences that happen less than 5% of the time before we tentatively reject the null hypothesis. However, there is nothing sacrosanct about 95% and you could have good reasons to depart from this criterion (read page 123 to 128 of Weisburd and Britt, 2010 for further details). In fact, only last year a number of researchers argued we should use a more stringent p value to address the crisis of reproducibility in science.

You will see that statistics books refer to the threshold we use to define a p value as high or low as our **level of statistical significance** (also often referred to as the **alpha level**). In our example here (and all the others we will use this semester) we will use an alpha level of 0.05. That is we will reject the null hypothesis *only if our p level is below that threshold*.

5. **After defining our research and null hypothesis and having taken a decision of how low our p value ought to be in order to reject the null hypothesis, we need to specify a model for testing this null hypothesis. All models make assumptions, so an important part of specifying a model is stating your assumptions and checking that they are not being violated. **

Through the semester we will cover a number of statistical tests, all with their own assumptions. These tests are appropriate in different circumstances (defined by their assumptions). Basically what we will be doing in the remaining thematic units this semester is to explain what those circumstances are for each test so that you can choose the right one on each occasion. We will see later the assumptions made by the sort of hypothesis tests you use to compare means across groups.

6. **Once we've gone through all those steps comes the calculation of the test statistics and, based on the results, our decision**

Different tests that we will encounter this semester have different formulas. Sometimes I will give you a basic description of what those formulas are doing, because it is good to know what is being computed for conceptual understanding. But the mechanics are handled by the computer. You won't need to memorise those formulas nor calculate anything yourself.

The ultimate goal of these statistical tests for hypothesis testing is to obtain a p value: the probability that the observed statistic (or a more extreme value) occurs if the null model is correct. If the p value is small enough (smaller than our alpha level: such as 0.05) then we will **"reject the null hypothesis"**. If it is not, we will **"fail to reject the null hypothesis"**. The language is important.

Whatever you decide, the *American Psychological Association Statistical Committee* recommends that it is always a good idea to report the p value as an indication of the strength of the evidence. That is, not only report the finding to be significant or not, also report your actual p value.

One final word. P values have attracted a lot of debate over the years. They are often misunderstood and people often read too much into them. They have also been used in a too simplistic way as a yardstic to decide what research findings are "worthy". It is important to know what they are and how they work. It is particularly important not to overinterpret them either. The term statistical **significance** is particularly misleading because in common usage we think of something significant as important. But in our context is basically equivalent to say that we have observed in our sample/study may not be noise. That'ts it. You will find all sorts of reactions to p values. Some people think we should ban them and use alternative approaches to data analysis (like Bayesian statistics). Others think that we should use more stringent thresholds (like p values below .01 or .001). Yet most scientists still rely on them, so it is important that you learn what they are, their limitations, and how to interpret them in a correct manner.

## Comparing means across two groups (the t test)

Let's elaborate with our example. Our research question is whether women are more afraid of crime. We are going to test a non-directional hypothesis and use an alpha level of .05. The test we use in this case is the t test, which relies in the Student's t-distribution introduced last week. This test makes a number of assumptions that we need to check first.

This t test makes a number of assumptions:

1. *We are comparing means or proportions* (that is our original variable is either a quantitative variable OR we have a binary variable with a large sample) across two groups. We are indeed doing so.

2. Population distribution: *normal distribution is assumed in both populations* (but this assumption can be relaxed if both samples are large). We will check this shortly. Because the tests make assumptions about the shape of the distribution we say that the t test is a **parametric test**. Tests that do not make this sort of assumptions are called non-parametric. 

3. Independence assumptions: To use the method *the two groups must be independent of each other*.This assumption would be violated if, for example, one group would consist of husbands and the other group their wives. The values for couples might be related. But this is not the case with the BCS data. Similarly if we compare an individual before and after a treatment, his/her observations would be related. For these situations we would need a different test (the dependent t test, which we won't cover).

4. Sampling method: the data were obtained through *independent random sampling*. The BCS uses a complex survey design which would require the use of special procedures for hypothesis testing. However, those special procedures are well beyond the scope of this course and would typically be covered in more advanced courses. Therefore, for convenience we will proceed as if this assumption is met.

You may also want to check for outliers by plotting the data, for in some cases this may distort your results, particularly with smaller samples. So we are ok with 1 and 2, and are going to proceed as if 4 is met. What about normality? With large samples you can relax this assumption. However, you may want to also check if your sample data are normally distributed.


```r
##R in Windows have some problems with https addresses, that's why we need to do this first:
urlfile<-'https://raw.githubusercontent.com/eonk/dar_book/main/datasets/BCS0708.csv'
#We create a data frame object reading the data from the remote .csv file
BCS0708<-read.csv(url(urlfile))
```


```r
library(ggplot2)
ggplot(BCS0708, aes(x = tcviolent, colour = sex)) + #you will need to load the data as explained in week 1
  geom_density() 
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-2-1.pdf)<!-- --> 

The plotted density provide a visual tool for assessing the unimodality and the symmetry of the distribution. Later we will discuss a more elaborate graphical tool for assessing the normal condition (e.g., the normal probability plot). 

For now let's assume this is good enough. Then we would be ready to compute the t test. 


```r
t.test(tcviolent ~ sex, data = BCS0708)
```

```
## 
## 	Welch Two Sample t-test
## 
## data:  tcviolent by sex
## t = 29.114, df = 8398.3, p-value < 2.2e-16
## alternative hypothesis: true difference in means between group female and group male is not equal to 0
## 95 percent confidence interval:
##  0.5614656 0.6425300
## sample estimates:
## mean in group female   mean in group male 
##            0.3281656           -0.2738322
```

If the code and the results look familiar is because we already saw them last week when producing the confidence interval for the sampling distribution of the difference of two means. Last week we focused on the 95% confidence interval, now we are going to look at the first few lines of printed output.

First we see is the so-called **Welch two sample t-test**. It is a version of the t test that does not assume that the variance of your response variable is the same for your two groups. It is the default version we will always use.  You also see a value for "t" (29.11), this is the test statistic obtained using the formula for the t test and something called df (abbreviation for degrees of freedom).

Farther to the right you see a value for p, this gives the probability associated with observing the difference in our sample if the null hypothesis were true. This value is 2.2e-16. If you are not used to this notation essentially what it means is that you need to move the decimal point 16 times to the left. In other words, the p value here is very close to 0 and therefore we can reject the null hypothesis that the difference in the population is 0. The observed difference in this sample would have been rather implausible if the null hypothesis were true.  Therefore, here we would argue that our evidence suggests that we can reject the null hypothesis. We can say that there is a **statistically significant** difference between fear of violent crime for men and women in England and Wales.

It is important you remember this: **the p value is not the probability that the null hypothesis is true**. Imagine that our p value was 0.04. As tempting as it may be to say that a p value of 0.04 means there is a 4% chance that the null hypothesis is true, that just isn't right.  The only thing that we are in a position to state is: given the null hypothesis, there is a 4% chance of observing the difference that we have actually observed (or one more unlikely).

## What does a significant effect mean?

Before we said that the difference between the mean score of fear of violent crime for males and females is statistically significant. It is of critical importance that you understand what this actually means. Unfortunately, in this context significance does not quite have the same meaning that we give it in normal language. 

When in normal language we say that something is significant we mean to say that it is important. When in statistics we say that something is statistically significant *we don't mean to say that it is important*. All it means is that, if we trust our data and methods, we are in a position to reject the null hypothesis with the threshold (alpha level) that we specified (0.05) a priori. It is something much more specific as you can see. Basically all we are saying is that we are willing to reject the null hypothesis that there is whatsoever no difference (or relationship) in the population.

However, rejecting the null hypothesis is, very often, not terribly "important" in a practical or theoretical sense. Think about our example. All we can say as a result of our t test here is that in the population on average the difference between fear of violent crime for males and females is likely to be different from zero. That's all! The null hypothesis, in this sense, is almost invariably known to be untrue even before you do your study! Is that significant in the normal sense (i.e., important)? Is a difference of -0.6 in these scores important? The fact this variable uses an artificial metric makes it even more difficult to evaluate.

To make statistical significance even more "insignificant" in a practical sense, if you work with large samples almost everything will be statistically significant. It is easier to achieve statistically significant results if your sample size is large enough. Some statisticians therefore are very dismissive of p values as not very informative. They argue that p values may simply be a measure of sample size.

Precisely for these reasons, it is always important to combine the use of p values with some discussion of the **effect size**. That is, you not only want to discuss the probability of a difference in the population but want to say something about the magnitude of the observed difference. 

In the example we are examining the effect size is the observed difference of -0.6. Is this large or small? Interpreting this in raw format, in the original scale, requires some subjective judgement. And I mean subjective in a positive way, it means you have to think about it. Unfortunately, the original scale here uses an artificial metric that is difficult to evaluate on its own.

We can always look at **standardised measure of the effect size**. You will find a number of standardised measures of effect size. They aim to give you a sense of how large these differences are by using a standardised metric. We are just going to use one of them, Cohen's d, for this scenario. We can obtain this measure with the `cohen.d()` function from the `effsize` package, which you will have to install.


```r
library(effsize)
cohen.d(BCS0708$tcviolent ~ BCS0708$sex)
```

```
## 
## Cohen's d
## 
## d estimate: 0.6281126 (medium)
## 95 percent confidence interval:
##     lower     upper 
## 0.5843047 0.6719205
```

The output suggest that the Cohen's d estimate is a medium effect size. Cohen proposed a set of rules of thumb to interpret the d statistic:  an effect size (in absolute value) of 0.2 to 0.3 might be a "small" effect, around 0.5 a "medium" effect and 0.8 to infinity, a "large" effect. However, keep in mind these rules are not absolute. In some fields of research and in relation to some problems the rules of thumb may be slightly different. You need, in professional practice, to be alert to those nuances by being familiar to the rules that other researchers use in your particular area of work.

How do we write our results up? We could say the following (and in case you are wondering, we covered last week how to obtain the standard errors using the psych package):

>"On average, males have a lower score of fear of violent crime (M=-.27, SE=.01) than the female group (M=.33, SE=.02). Using an alpha level of 0.05, this difference was significant (t=-29.11, p=.000) and represented a medium-sized effect (Cohen's d=-0.63)."

This is what you would write in your "Findings" section. In your "Conclusions" you would need to discuss what the theoretical or practical implications of this finding are; connecting it to existing theoretical debates. If your test had been insignificant (a p value greater than 0.05) then you would have to say so: "the difference was insignificant, thus, we failed to reject the null hypothesis".

One important thing to remember is that when doing hypothesis testing there is always the possibility of error. Our statements are probabilistic. We could be rejecting the null hypothesis when we shouldn't (false positive or Type I error), if we are using an alpha level of .05 this may happen 5% of the time, or we may fail to reject the null hypothesis when we should (false negative or Type II error).

![Errors](http://flowingdata.com/wp-content/uploads/2014/05/Type-I-and-II-errors1-625x468.jpg)

## Power analysis

In this section we introduce the `pwr` package for power analysis. In the video lectures you had to watch as preparation for today we introduced the notion of power analysis. In order for a statistical test to be able to be effective, to be able to detect an effect, you need to have sufficient power. Power is related to the magnitude of the effect (it will be easier to detect stronger rather than weaker effects) and sample size (it will be easier to detect effects with large samples than with small samples). A problem with many scientific studies is that they are *underpowered*, the fail to reject the null hypothesis simply because they do not have sufficient power (often because the sample size is not large enough). Power analysis is generally done during the planning of an analysis so that you know what kind of sample you are going to need if you want to be able to run meaningfull hypothesis tests. That is you do your power analysis before you collect your data. 

But we can also check how much power we have after the fact, just to ensure we are not failing to reject the null hypothesis as a consequence of insufficient power. For this purposes we can use the `pwr` package. For computing the power when comparing two sample means we use the `pwr.t2n.test` function. This function expects we provide the sample size of each group (if we are doing the power calculation after we have collated our data) and the effect size we may want to be able to detect. Let's see how many people we have in each of our two groups (male and females) when assessing differences in fear of violent crime.



```r
library(psych)
```

```
## 
## Attaching package: 'psych'
```

```
## The following object is masked from 'package:effsize':
## 
##     cohen.d
```

```
## The following objects are masked from 'package:ggplot2':
## 
##     %+%, alpha
```

```r
describeBy(BCS0708$tcviolent, BCS0708$sex)
```

```
## 
##  Descriptive statistics by group 
## group: female
##    vars    n mean   sd median trimmed  mad   min  max range skew kurtosis   se
## X1    1 4475 0.33 1.04   0.23    0.25 0.96 -2.35 3.56  5.91 0.61     0.02 0.02
## ------------------------------------------------------------ 
## group: male
##    vars    n  mean   sd median trimmed  mad   min  max range skew kurtosis   se
## X1    1 3959 -0.27 0.86  -0.44   -0.36 0.69 -2.35 3.81  6.16  1.1     1.91 0.01
```

Ok, so that is 4475 and 3959. Let's say we want to detect even very small effect sizes. The functions in this package assume a default .05 level of statistical significance, although this is something we could change. So if we go with the default, we would write as follows:


```r
library(pwr)
pwr.t2n.test(n1 = 4475, n2 = 3959, d= 0.2)
```

```
## 
##      t test power calculation 
## 
##              n1 = 4475
##              n2 = 3959
##               d = 0.2
##       sig.level = 0.05
##           power = 1
##     alternative = two.sided
```

The function is telling us that we have a power of 1. The statistical power ranges from 0 to 1, and as statistical power increases, the probability of making a type II error (wrongly failing to reject the null) decreases. So with a power of 1 we are very unlikely indeed to failing to reject the null hypothesis when we should.

With sample sizes this large, you are unlikely to run into problems with power. But these things do matter in particular applications. Think for example of cases when you are trying to evaluate if a particular criminal justice intervention works. If you work with small samples you may wrongly conclude that your intervention didn't make a difference (you fail to reject the null hypothesis) because you did not have sufficient statistical power. This was a common problem in older studies (see [here](https://www.sciencedirect.com/science/article/pii/0047235289900044) for a review) and it is a problem that still persist to some extent (read [this](https://www.tandfonline.com/doi/abs/10.1080/07418825.2018.1495252) more recent review).

## Comparing means across several groups (ANOVA)

### The problem with multiple comparisons

We have used the t test to assess differences in a metric variable across two groups defined by a categorical variable. As we have explained during the class, if you are interested in comparing across more than two groups then you cannot run multiple t tests. Why? Because we would run into the problem of [**multiple comparisons**](http://en.wikipedia.org/wiki/Multiple_comparisons_problem) illustrated below:

![](http://imgs.xkcd.com/comics/significant.png)

By running multiple comparisons you increase the change that you find significant differences by random chance alone. Imagine you throw a six face dice with numbers from 1 to 6. What is the probability of getting a 1? Right, 1/6. Now. Imagine that we throw the dice 6 times. What is the probability of getting a 1 at least once. Well, it would be the probability of getting a one each of the times multiplied by the number of times. 

You can think of a statistical test as equivalent to this. The more times you run the test the higher the probability that something will come out significant. As the number of comparisons (tests) increase, the chances that this will happen increase. So, instead of running multiple t tests, we will run a single ANOVA test that allow us to explore whether there are significant differences across the groups being compared. 

###Visual exploration of differences in the distributions across the groups

We will look at the distribution of scores of fear of violent crime (`tcviolent`) vary across the ethnic groups indexed by the variable `ethgrp2`. Let' visualise these differences:


```r
ggplot(BCS0708, aes(ethgrp2, tcviolent, fill=ethgrp2)) + 
  geom_boxplot(outlier.size=1) + 
  guides(fill=FALSE) 
```

```
## Warning: `guides(<scale> = FALSE)` is deprecated. Please use `guides(<scale> =
## "none")` instead.
```

```
## Warning: Removed 3242 rows containing non-finite values (stat_boxplot).
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-7-1.pdf)<!-- --> 

What you see here is that the boxplot also displays the values of fear for the few individuals in the dataset for which we don't know the ethnicity ("NA" in the X axis). In many occasions this is not what you want. At least you are trying to understand your missing data problem (an advanced topic which we don't cover this semester), you only want a plot that uses information for the individuals with  valid information (that is the ones for which we have data on fear and ethnicity). If you have quite a few NA cases and they seem systematically different from the other groups, you may have some reasons to be concerned.

You can use the following code to modify the display (and also to ensure the boxes are ordered around the x axis not by alphabetical order but by order of the level of fear). The `na.omit()` function ask R to omit from the data all cases with missing information on the specified columns. The `reorder()` function ensure that the x axis is ordered according to the level of fear.


```r
ggplot(na.omit(BCS0708[,c("ethgrp2", "tcviolent")]), aes(x=reorder (ethgrp2, tcviolent), y=tcviolent, fill=ethgrp2)) +
  geom_boxplot() +
  coord_flip() + #We are flipping the coordinates to avoid the overprinting of the factor levels
  guides(fill=FALSE)
```

```
## Warning: `guides(<scale> = FALSE)` is deprecated. Please use `guides(<scale> =
## "none")` instead.
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-8-1.pdf)<!-- --> 

You can see here slightly different distributions of fear for the ethnic groups. Notice for example how 75% of the Asian group has scores on fear of crime that are higher than those of 50% of individuals in the White group.  Let's look at the statistics:


```r
library(psych)
describeBy(BCS0708$tcviolent, BCS0708$ethgrp2)
```

```
## 
##  Descriptive statistics by group 
## group: asian or asian british
##    vars   n mean   sd median trimmed  mad   min  max range skew kurtosis   se
## X1    1 283 0.88 1.17   0.68    0.86 1.32 -2.07 3.32  5.39 0.19    -0.89 0.07
## ------------------------------------------------------------ 
## group: black or black british
##    vars   n mean   sd median trimmed mad   min  max range skew kurtosis  se
## X1    1 120  0.5 1.14    0.3    0.48 1.2 -1.85 2.59  4.44 0.17    -0.92 0.1
## ------------------------------------------------------------ 
## group: chinese or other
##    vars  n mean   sd median trimmed  mad   min  max range skew kurtosis   se
## X1    1 93 0.34 1.14   0.23     0.3 1.33 -1.64 2.81  4.45 0.31    -0.88 0.12
## ------------------------------------------------------------ 
## group: mixed
##    vars  n mean  sd median trimmed  mad   min  max range skew kurtosis   se
## X1    1 35 0.52 1.3   0.39     0.5 1.16 -2.34 2.97   5.3 0.22    -0.68 0.22
## ------------------------------------------------------------ 
## group: white
##    vars    n mean   sd median trimmed  mad   min  max range skew kurtosis   se
## X1    1 7902    0 0.98  -0.15   -0.09 0.88 -2.35 3.81  6.16 0.85     0.72 0.01
```

Looking at the results we can clearly see that there seem to be some differences in the means across groups. The White group has the lowest mean (.00) and the Asian group has the highest mean (.88), this is consistent with the other location measures displayed in the boxplot (quartiles and the median). But how precise are these point estimates for the means as measures of the population parameters? How much trust can we place in them as indicative of the true level of fear of crime in the various ethnic groups in the population? 

I want you to pay attention to the column in that table that provides you with the sample size for each of the ethnic groups. Notice anything worth thinking about here? Do you think that the estimates of fear of crime for each of these ethnic groups will be equally precise? Remember the lecture on sampling variability, sampling distributions, and confidence intervals, do you think that (given the different size of the samples for the various ethnic groups) the confidence interval will be equally wide for each of them? Why? Why not? 

We have now examined the means for fear of crime for the various ethnic groups and have seen how the Asian group seem to have the highest average level of fear. But we have discussed in the class that point estimates are "problematic" because they do not communicate sampling variability - for that we need confidence intervals. Last week we explained how to do confidence intervals for the mean of two groups. I am going to show you here a different way of plotting confidence intervals for means of various groups. 

The simplest way to do this is with the `plotmeans` function in the `gplots` package (not to confuse with the `ggplot2` package). This function uses by default the t Student distribution for computing the confidence intervals (given the small sample size of some of the groups this is appropriate here):


```r
#You will need to install this package first
library(gplots)
plotmeans(tcviolent ~ ethgrp2, data = BCS0708) #if you rather use the normal approximation you could use an additional argument: use.t=FALSE
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-10-1.pdf)<!-- --> 

When you only have two groups you can use these graphs (error bars displaying confidence intervals) in a way equivalent to the way that you use a t test, but when you have multiple groups you need to think about the problem of multiple comparisons.

### ANOVA

So, again, we see some differences in means. Are these differences statistically significant? In other words, can we infer that they exist in the population from which the sample was drawn? For this we can run ANOVA and an F test. 

How does this test work? We run ANOVA because we want to decide if the sample means are different enough for us to be able to reject the null hypothesis that they are different in the population. Clearly, if they are very different between themselves in the sample we will be in a stronger position to do this. That should be clear: if you want to talk abut differences in the population observing big differences across the means in the sample gets you closer to that. 

What ANOVA does is to contrast the variability between the groups with the variability within the groups to produce a ratio: (Variability between the groups)/(Variability within the groups). If there is more variability between the groups than within the groups the more confidence we can have in a conclusion that the population means are not equal. Likewise, if there is more variation within the groups than between the groups, we will be in weaker ground to conclude that the population means are different. This [short video](https://www.youtube.com/watch?v=ITf4vHhyGpc) explains it with an example.

So that's how ANOVA gets the name, it is a ratio of variability, to be more precise a ratio of variances. The observed value is then compared to a probability distribution we haven't covered yet: the [F distribution](http://en.wikipedia.org/wiki/F-distribution). We have talked about the normal and the t distribution, the F distribution is just another family of probability distributions. But the idea remains the same earlier in relation to the t test. If you obtain large absolute values for F, you will be more confident that the observed differences are inconsistent with the null hypothesis. These values will have a low probability of being observed if the null hypothesis is true (if all the population means are equal) and therefore we will be able to reject this null hypothesis.

To run the ANOVA test we use the `aov()` function:


```r
fearmodel.1<- aov(tcviolent ~ ethgrp2, data=BCS0708)
summary(fearmodel.1)
```

```
##               Df Sum Sq Mean Sq F value Pr(>F)    
## ethgrp2        4    253   63.21   64.54 <2e-16 ***
## Residuals   8428   8254    0.98                   
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 3243 observations deleted due to missingness
```

The result is significant suggesting that there are some significant differences across the ethnic groups in fear of violent crime. The probability of observing this data, with the noted differences in means, if the null hypothesis were true is also very low (<2e-16).

Done, right? Well, not quite. Remember the steps in a hypothesis test. Before running the test we need to think and check the assumptions of the test, that should precede running the test. The ANOVA F test makes the following assumptions:  
+ **Independence assumption**: the groups must be be independent of each other (this assumption would be violated if for example we compare a subjects performance before some treatment, again during the treatment, and then after the treatment: for this you would need something called *repeated measures ANOVA* which we don't have the time to cover).  
+ **Randomisation condition**: were the groups created through randomisation or in case of surveys are the data from each group a representative sample of that group? As with the t test, we are assuming simple random selection, which is not the case when the survey uses a complex survey design (but as we said then we will ignore this for convenience).  
+ **Equal variance assumption** (also called the lovely names of homogeneity of variance or homoskedasticity): to check this assumption you need to check that the groups have similar variances (we'll discuss this in greater length next). But it is important you know statisticians have discussed the degree to which this assumption matters, or in other words to what degree ANOVA is *robust*  to violations of this assumptions. Is ANOVA robust (will give us results we can trust) when this assumption is violated? Andy Field and his co-authors (2012) discuss this at length in page 413. His view is that "when sample sizes are unequal, ANOVA is not robust to violations of homogeneity of variance" and we should proceed accordingly.   
+ **Normal population assumption**: like the t test, we need to assume that the normal model is reasonable for the populations underlying each of the treatment groups.

### Checking homogeneity of variance and dealing with unequal spread

Let's start by discussing why we care about the spread of the groups. Remember that ANOVA contrasts variability between the groups with variability within each group. If the variability within the groups varies, we are making this pooled variance larger, reducing the F statistic, and making it less likely that we can reject the null hypothesis. So when you have this problem, the ANOVA test will usually be a conservative test that will reject your null hypothesis less often than it should. 

Look at the boxplots we produced. Does it look as if the spreads change systematically with the centres? Do the boxes with the bigger centres also have the wider spread? This sort of systematic trend may be more concerning than random differences in spread across the groups.


We can also run a test that will check the homogeneity of variance. This is the [Levene Test](http://en.wikipedia.org/wiki/Levene's_test). We can run this test with the `leveneTest()` function of the `car` package.


```r
library(car)
leveneTest(BCS0708$tcviolent, BCS0708$ethgrp2, center = median)
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##         Df F value    Pr(>F)    
## group    4  13.433 6.476e-11 ***
##       8428                      
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```


In this case, the test is significant suggesting that the variances are different in the population. However, you need to keep in mind that with the large samples of some of the groups this result is unsurprising.

We can further explore this assumption plotting the results from the ANOVA model we already run. Plotting the results of this ANOVA model allows us to inspect some plots that are useful for diagnosing problems.


```r
plot(fearmodel.1) #Running this would result in four consecutive plots.
#Alternatively if you don't want to run ANOVA first and store the results in an object
plot(aov(tcviolent ~ ethgrp2, data=BCS0708))
```

As Andy Field and his colleagues (2012) suggest the more important of these plots are the first two (to assess equal spread and normality). If you don't want to print the four diagnostic plots you need to use more specific instructions so that R know which one you want. Let's just get the plot we need for assessing equal spread:


```r
plot(fitted(aov(tcviolent ~ ethgrp2, data=BCS0708)), resid(aov(tcviolent ~ ethgrp2, data=BCS0708)), xlab = "Fitted values", ylab = "Residuals", main = "Residuals vs Fitted")     # plot a diagnostic check for heteroscedasticity in the residuals from the response Y to a factor or numeric A
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-14-1.pdf)<!-- --> 

This plot can be used to further explore homogeneity of variances. It is a plot of residuals versus fitted values (we will return to this later on this semester, for now just focus on interpretation as detailed below). We already know the Levene Test is significant and that the variances cannot be assumed to be the same in the population. In this sort of situations you expect plots such as this in which the vertical lines do not have the same length (longer collection of points suggests more variance and shorter collection of points less variance). We should be particularly concern with any systematic patterning (that is some sort of funnelling visual effect suggesting a systematic shortening or expanding of the lines as we move right to left in the X axis).

It looks as if the larger group (Whites) is the one with more variance. Again, in this sort of scenarios the ANOVA F Test will be more conservative (it may lead you to reject the null hypothesis in more occasions than it is warranted). Despite this we found a significant effect, so in practical terms it does not look as if the homogeneity of variance was such a big deal (it made our test more conservative right, but we still manage to reject the null hypothesis).

In those situations when you are concerned about the violation of this assumption because you have samples for some of the groups, we could run instead of ANOVA the Welch's F test for equality of means:


```r
oneway.test(tcviolent ~ ethgrp2, data=BCS0708)
```

```
## 
## 	One-way analysis of means (not assuming equal variances)
## 
## data:  tcviolent and ethgrp2
## F = 46.663, num df = 4.00, denom df = 155.14, p-value < 2.2e-16
```

In this case, the substantive conclusion is unsurprisingly the same. You reject the null hypothesis given the low p value associated with the observed F value.

### Checking normality and dealing with problems

The F tests require the underlying errors to follow a Normal model. Stricto sensu, we need to check the Normal model is reasonable for the population underlying each group. We should start by looking at the side-by-side boxplots for indications of skewness. If they are all or most skewed in the same direction, the normal condition will fail. We also need to look at outliers within each group (particularly with smaller samples). You may also find it useful to compare the density estimates.


```r
ggplot(na.omit(BCS0708[,c("ethgrp2", "tcviolent")]), aes(x = tcviolent, fill = ethgrp2)) + 
  geom_density(alpha = .3)
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-16-1.pdf)<!-- --> 

We can also use a [**normal probability plot**](http://en.wikipedia.org/wiki/Normal_probability_plot) of the residuals. If we had use `plot(fearmodel.1)`, the second of the four printed plots would be the normal Q-Q plot. Alternatively we can specifically ask for it:


```r
qqnorm(resid(aov(tcviolent ~ ethgrp2, data=BCS0708)), main="Normal Q-Q Plot")
qqline(resid(aov(tcviolent ~ ethgrp2, data=BCS0708)), col = 2)
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-17-1.pdf)<!-- --> 

```r
# normal scores check for skewness, kurtosis and outliers in in the residuals 
```

As before, we are concerned here with clear departures from the red line. How do you interpret a QQ plot? It takes practice and some subjective judgement, it's kind of an art. These are common patterns and possible interpretations:

+ all but a few points fall on a line: *outliers in the data*

+ left end of pattern is below the line and right end of pattern is above the line:*long tails at both ends of the data distribution*

+ left end of pattern is above the line and right end of pattern is below the line: *short tails at both ends of the data distribution*

+ curved pattern with slope increasing from left to right: data distribution is *skewed to the right*

+ curved pattern with slope decreasing from left to right data distribution is *skewed to the left*

+ staircase pattern (plateaus and gaps): data have been rounded or are discrete

You may find [these examples](http://emp.byui.edu/BrownD/Stats-intro/dscrptv/graphs/qq-plot_egs.htm) of interpretation useful. We can see there are some at both ends.

Also this [shiny app](https://xiongge.shinyapps.io/QQplots/) is an interactive way to get your head around interpreting Normal QQ plots. 

The `qqPlot` function of the `car` package assists the interpretation by drawing a confidence interval around the expected values:


```r
qqPlot(fearmodel.1)
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-18-1.pdf)<!-- --> 

```
## [1] 1761 4769
```

We can see that there is some departure from normality.

Sometimes when non-normality is an issue **transforming** your variable may be a way of solving the problem. You create a new transformed variable based on the original one that will now meet the normality requirement. This is something that can also sort issues with extreme observations (outliers). The idea behind transformations is that "you do something to every score to correct for distributional problems, outliers or unequal variances" (Field et al. 2012). There's nothing dodgy about it. It's not like we are cheating, because the same transformation will be applied to all scores. But it changes the units of measurement, which can make interpretation a bit more obscure. 

There are many different potential transformations: log transformations, square root transformations, reciprocal transformations, reverse score transformations, etc. How do you choose? Trial and error. That is, you got to work and work until you find one that solves your problem. And sometimes none of the transformations give you an ideal solution.  

We will illustrate the process of trial and error for normalising `tcviolent` (as much as we can). Let's look again at the distribution of the variable.


```r
ggplot(BCS0708, aes(x = tcviolent)) + 
  geom_density()
```

```
## Warning: Removed 3242 rows containing non-finite values (stat_density).
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-19-1.pdf)<!-- --> 

We can see that the distribution is multimodal and that the tail to the right is longer than the tail to the left, there is a positive skew. We can also see that the values range from negative to positive values. Many of the transformations we use do not work well when we have negative values or zeros. So one way to allow them to work is to add a constant large enough to avoid zeros. I will add three to the variable:


```r
BCS0708$ptcviolent <- BCS0708$tcviolent+3
```

This code creates a new variable `ptcviolent` in the BCS0708 dataframe that is the result of adding 3 to the original variable tcviolent. This ensures that all the values are positive. You will see all we have done is to shift the entire distribution to the positive side of the scale:


```r
ggplot(BCS0708, aes(x = ptcviolent)) + 
  geom_density()
```

```
## Warning: Removed 3242 rows containing non-finite values (stat_density).
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-21-1.pdf)<!-- --> 

Let's see what happens when we apply a logarithmic transformation (often used with skewed data):


```r
ggplot(BCS0708, aes(x = log10(ptcviolent))) + 
  geom_density()
```

```
## Warning: Removed 3242 rows containing non-finite values (stat_density).
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-22-1.pdf)<!-- --> 

Oops... We squashed the right tail a bit too much and stretched it in the left hand side. We'll have to try another transformation. 

Here I will discuss power transformations. We define a simple power transformation as the replacement of a variable X by X^??^. Often powers in the range from -2 to 3 are useful. The power -1 is in fact the reciprocal or inverse transformation. This family of transformations was first used by a seminal paper by Box and Cox in 1964, which is why you will find the literature refers to them as the Box-Cox (BC) transformations in their honour. 

How do you select the right power transformation? Again, trial and error. The `symbox()` function in the `car` package is useful for finding a transformation to approximate symmetry by trial and error. The following code will produce a series of boxplots comparing the distribution of our variable (`ptcviolent`) for various power transformations.


```r
symbox(BCS0708$ptcviolent, data=BCS0708)
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-23-1.pdf)<!-- --> 

We can see that the most symmetrical of all is the 0.5 transformation. Let's create and plot a variable using this power transformation:


```r
BCS0708$bctcviolent <- bcPower(BCS0708$ptcviolent, 0.5)
ggplot(BCS0708, aes(x = bctcviolent)) + 
  geom_density()
```

```
## Warning: Removed 3242 rows containing non-finite values (stat_density).
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-24-1.pdf)<!-- --> 

The new variable to the left hand side has squashed the right tail. It is a bit more symmetrical. We can see this in a normal probability plot:


```r
qqPlot(BCS0708$bctcviolent)
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-25-1.pdf)<!-- --> 

```
## [1] 4388 4701
```

```r
qqPlot(BCS0708$tcviolent)
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-25-2.pdf)<!-- --> 

```
## [1] 1761 4769
```

As we said the normal probability plots using this function display a (red) straight line (which is how a normally distributed probability should look like in these plots) and then the dots (on black here) showing the actual distribution of data. You can see that the variable in which we took the 0.5 power of fear of crime (the first plotted) is a bit closer to the straight red line, but still showing some departure from normality.

If we were happy with our transformations we could then run ANOVA as if the data was normal, only instead of comparing means on fear of violence we would be comparing means on whatever transformation we have made, scores of fear of crime raised to the 0.5 power (which to many mortals may sound rather obscure).

### Robust ANOVA

Wilcox (2005) describes a set of procedures for conducting robust ANOVA: ways of doing ANOVA when there are problems with its assumptions. When everything goes completely wrong with the assumptions, you may want to look at these options.

For this we need to install the package that he has created for implementing these procedures in R. 


```r
install.packages("WRS2")
```

We can now invoke the code. The following code will use ANOVA based on 5% trimmed mean with 599 bootstrap samples:


```r
library(WRS2)
t1waybt(tcviolent ~ ethgrp2, data = BCS0708, tr = .05, nboot = 599)
```

```
## Call:
## t1waybt(formula = tcviolent ~ ethgrp2, data = BCS0708, tr = 0.05, 
##     nboot = 599)
## 
## Effective number of bootstrap samples was 599.
## 
## Test statistic: 45.3591 
## p-value: 0 
## Variance explained: 0.087 
## Effect size: 0.294
```

As with the standard ANOVA and the Welch version, we still get a significant result.

### Post Hoc Comparisons

So we are fairly certain there's bound to be differences in the level of fear of crime across ethnic groups that may be reflective of those we see in our sample. In our sample (see below) the mean value of fear of violent crime across groups is different. The White group (.00) has the lowest level of fear and the Asian group the highest (.88). With the other groups with levels of fear of crime in between these two extremes: Chinese or Other (.34), Black (.50) and Mixed (.52).

However, all the ANOVA test (and the Welch's F test and the robust ANOVA) does is to tell you that there are significant differences across these categories. What it does not do is to tell you which of those differences are significant. In other words, we don't know if, for example, the apparent difference between fear of crime for the White and the Chinese group is significant or not. We know that some of these differences are significant but we don't know which ones. We can however run post hoc (after the fact) comparisons that would give us answers to these -although this would only make sense if the ANOVA (or equivalent) test has already detected some differences.

There are different methods that have been proposed for doing post hoc multiple comparisons (see Field et al 2012 discussion in page 428-432). All of these methods try to take into account the problem of multiple comparisons and the way they modify the probability of finding a significant result, but they do it in a different way. Field et al. (2012) also explain how to compute a few different ones in pp. 447-451. I'm just going to illustrate one of these methods (Bonferroni adjustment) and you can learn about the others from Field et al. (2012).

The `pairwise.t.test()` function asks for multiple t tests adjusting for the fact you are indeed running multiple comparisons. The first variable identifies your metric variable, then you identify the categorical predictor, and then you select the particular multiple comparison adjustment you are choosing. Check Field et al. (2012) for what some of the options are. 


```r
pairwise.t.test(BCS0708$tcviolent, BCS0708$ethgrp2, p.adjust.method="bonferroni") 
```

```
## 
## 	Pairwise comparisons using t tests with pooled SD 
## 
## data:  BCS0708$tcviolent and BCS0708$ethgrp2 
## 
##                        asian or asian british black or black british
## black or black british 0.0041                 -                     
## chinese or other       4.7e-05                1.0000                
## mixed                  0.4025                 1.0000                
## white                  < 2e-16                4.7e-07               
##                        chinese or other mixed 
## black or black british -                -     
## chinese or other       -                -     
## mixed                  1.0000           -     
## white                  0.0111           0.0214
## 
## P value adjustment method: bonferroni
```

What you see printed in this matrix are the p. values for each of the comparisons. Whenever that value is below the alpha level you have set out, say our conventional .05, then you can conclude that this particular comparison/difference is significant. So here we can say that:

+ The White group has significantly lower level of fear of crime than the Mixed group (p. value is .02), than the Asian group (p value is below 2.e-16), than the Black group (p value is 4.7e-07), and that the Chinese or Other group (p value is 0.01).

+ The Mixed group is only significantly different from the White group (the p value is higher than .05 for the other comparisons).

+ The Black group is significantly higher than the White and significantly higher than the Asian but no different from the mixed group or the Chinese/Other.

+ And we can say that the Chinese/Other has more fear than the White group and less than the Asian but does not seem different from the mixed group or the Black.

### Effect size for ANOVA

You can use the following programming code to get what is called as eta squared:


```r
summary.lm(fearmodel.1) 
```

```
## 
## Call:
## aov(formula = tcviolent ~ ethgrp2, data = BCS0708)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -2.9520 -0.7243 -0.1517  0.4958  3.8024 
## 
## Coefficients:
##                               Estimate Std. Error t value Pr(>|t|)    
## (Intercept)                    0.88176    0.05883  14.989  < 2e-16 ***
## ethgrp2black or black british -0.38112    0.10780  -3.535 0.000409 ***
## ethgrp2chinese or other       -0.54197    0.11828  -4.582 4.67e-06 ***
## ethgrp2mixed                  -0.36376    0.17732  -2.051 0.040251 *  
## ethgrp2white                  -0.87864    0.05987 -14.676  < 2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 0.9896 on 8428 degrees of freedom
##   (3243 observations deleted due to missingness)
## Multiple R-squared:  0.02972,	Adjusted R-squared:  0.02926 
## F-statistic: 64.54 on 4 and 8428 DF,  p-value: < 2.2e-16
```

The summary function is simply invoking the results we obtained earlier when we run ANOVA and created the 'fearmodel.1' object. You get loads of numbers there. But the only part you are interested is what the output labels as 'R-Squared' (0.02972). In the context of ANOVA this is usually called **eta squared**. This value is also referred to as the *percent of variance explained*. This is simply the proportion of the total sum of squares that is accounted by the between sum of squares. The larger the proportion of total variance that is accounted for by the between sum of squares, the stronger the relationship between the metric and the categorical variable. When the means of the groups defined by your categorical variable are the same, eta squared will be 0. That would mean no relationship exist between your metric and your categorical variable. The largest value eta squared can take is 1, meaning that all the variability in your metric variable can be explained by your categorical variable. 

Taking the square root of eta squared gives you the correlation between the metric and the categorical variable. Eta or the correlation is a measure of effect size; that is of the substantive impact of your categorical variable. In this case that value (square root of 0.02972) is around .17. That suggests that ethnicity has a small effect on fear of crime in this study (see page 58 of Field et al. 2012 for rules of thumb to interpret eta or r). 

You can also use the `ANOVA` function from the `lessR` package, which is a package designed to facilitate the learning of R.


```r
library(lessR)
ANOVA(tcviolent ~ ethgrp2, data = BCS0708, brief=TRUE) #The brief argument set to TRUE excludes pairwise comparisons and extra text from being printed.
```

![](06-hypothesis_testing_files/figure-latex/unnamed-chunk-30-1.pdf)<!-- --> 

```
## 
##   BACKGROUND 
## 
## Response Variable: tcviolent 
##  
## Factor Variable: ethgrp2 
##   Levels: asian or asian british black or black british chinese or other mixed white 
##  
## Number of cases (rows) of data:  11676 
## Number of cases retained for analysis:  8433 
## 
## 
##   DESCRIPTIVE STATISTICS  
## 
##                            n            mean              sd              min             max 
## asian or asian british   283   0.88175663803   1.16668811073   -2.07022309303   3.31529736519 
## black or black british   120   0.50063411160   1.13798384912   -1.85322141647   2.59109425545 
## chinese or other          93   0.33978925640   1.13861126145   -1.64311027527   2.80809569359 
## mixed                     35   0.51799569013   1.29961704407   -2.33650994301   2.96658897400 
## white                   7902   0.00311507460   0.97682414921   -2.35029053688   3.80547618866 
##  
## Grand Mean: 0.045530510071 
## 
## 
##   ANOVA 
## 
##                      df            Sum Sq         Mean Sq         F-value   p-value 
## ethgrp2               4   252.83066055375  63.20766513844 64.54270257531    0.0000 
## Residuals          8428  8253.67052402441   0.97931543949 
## 
## R Squared: 0.030 
## R Sq Adjusted: 0.029 
## Omega Squared: 0.029 
##  
## Cohen's f: 0.174 
## 
## 
##   TUKEY MULTIPLE COMPARISONS OF MEANS 
## 
## 
##   RESIDUALS
```

You will see this implementation of ANOVA apart from also printing the R Squared also gives you Omega Squared. Omega Squared is particularly helpful with smaller samples. You will also see with this function (although not printed here) a nicely labelled residual plot to assist interpretation of equal spread.

So finally, how to interpret these numbers? Well you could refer to seminal texts which give us guidance on the eternal question "Is that a big number?" Two such texts are: 

- Field, A (2013) Discovering statistics using IBM SPSS Statistics. Fourth Edition. Sage:London.
- Cohen, J. (1992). A power primer. Psychological bulletin, 112(1), 155.

But why do something ourselves, when we can programme R to do it for us? We can ask R to look this up using some functions found in the `effectsize` package. 

Specifically the function `interpret_omega_squared()` interprets the omega squared, and the function `interpret_eta_squared()` helps interpret the..... you guessed it! The eta squared. You just plug in the value, and the text you wish to use to guide you. 

So to interpret our omega square result above using Field (2013): 


```r
library(effectsize)
```

```
## 
## Attaching package: 'effectsize'
```

```
## The following object is masked from 'package:psych':
## 
##     phi
```

```r
interpret_omega_squared(0.03, rules = "field2013")
```

```
## [1] "small"
## (Rules: field2013)
```


Or Cohen (1992): 



```r
interpret_omega_squared(0.03, rules = "cohen1992")
```

```
## [1] "small"
## (Rules: cohen1992)
```



Isn't that something! Soon you'll be learning how to write code that will write your whole essay for you! Alright that's enough for this week, well done for getting to the end!

<!--chapter:end:06-hypothesis_testing.Rmd-->

# Studying relationships between two factors

## Producing cross tabulations

In earlier sessions we have covered how to run frequency distributions using the `table()` function. Cross tabulations, also called **contingency tables**, are essentially crossed frequency distributions, where you plot the frequency distributions of more than one variable simultaneously. This semester we are only going to explore **two-way cross tabulations**, that is contingency tables where we plot the frequency distribution of two variables at the same time. Frequency distributions are a useful way of exploring categorical variables that do not have too many categories. By extension, cross tabulations are a useful way of exploring relationships between two categorical variables that do not have too many levels or categories.

As we learned during the first week we can get results from R in a variety of ways. You can produce basic tables with some of the core functions in R. However, in order to produce the sort of cross-tabs  we will use, I suggest you install and load the package `gmodels`. This package allows you to produce cross tabulations in a format similar to the one used by commercial statistical packages SPSS and SAS. Since some of you may have some previous experience with SPSS we will use the SPSS format. Cross-tabs with this package are more useful for our purposes than the default you may get with the core R `table()` function.

We will begin the session by loading again the BCS 2007/2008 data from previous weeks. 


```r
##R in Windows have some problems with https addresses, that's why we need to do this first:
urlfile<-'https://raw.githubusercontent.com/eonk/dar_book/main/datasets/BCS0708.csv'
#We create a data frame object reading the data from the remote .csv file
BCS0708<-read.csv(url(urlfile))
```


```
## Installing package into '/Users/EonKim/Library/R/x86_64/4.2/library'
## (as 'lib' is unspecified)
```

```
## 
## The downloaded binary packages are in
## 	/var/folders/4l/6cj909957z9b_sp1hsy3vm100000gn/T//RtmpapgOHR/downloaded_packages
```

We will start by producing a cross tabulation of victimisation ("bcsvictim"), a categorical unordered variable, by whether the presence of rubbish in the streets is a problem in the area of residence ("rubbcomm"), another categorical unordered variable. Broken windows theory would argue we should see a relationship. We will use the following code:



```r
library(gmodels)
with(BCS0708, CrossTable(rubbcomm, bcsvictim, prop.chisq = FALSE, format = c("SPSS")))
```

```
## 
##    Cell Contents
## |-------------------------|
## |                   Count |
## |             Row Percent |
## |          Column Percent |
## |           Total Percent |
## |-------------------------|
## 
## Total Observations in Table:  11065 
## 
##                   | bcsvictim 
##          rubbcomm | not a victim of crime  |       victim of crime  |             Row Total | 
## ------------------|-----------------------|-----------------------|-----------------------|
##     fairly common |                  876  |                  368  |                 1244  | 
##                   |               70.418% |               29.582% |               11.243% | 
##                   |                9.950% |               16.276% |                       | 
##                   |                7.917% |                3.326% |                       | 
## ------------------|-----------------------|-----------------------|-----------------------|
## not at all common |                 4614  |                  849  |                 5463  | 
##                   |               84.459% |               15.541% |               49.372% | 
##                   |               52.408% |               37.550% |                       | 
##                   |               41.699% |                7.673% |                       | 
## ------------------|-----------------------|-----------------------|-----------------------|
##   not very common |                 3173  |                  981  |                 4154  | 
##                   |               76.384% |               23.616% |               37.542% | 
##                   |               36.040% |               43.388% |                       | 
##                   |               28.676% |                8.866% |                       | 
## ------------------|-----------------------|-----------------------|-----------------------|
##       very common |                  141  |                   63  |                  204  | 
##                   |               69.118% |               30.882% |                1.844% | 
##                   |                1.602% |                2.786% |                       | 
##                   |                1.274% |                0.569% |                       | 
## ------------------|-----------------------|-----------------------|-----------------------|
##      Column Total |                 8804  |                 2261  |                11065  | 
##                   |               79.566% |               20.434% |                       | 
## ------------------|-----------------------|-----------------------|-----------------------|
## 
## 
```

```r
#In CrossTable() we are using as our first argument the name of the variable defining the rows, and as our second argument the name of the variable defining the columns. We are also telling R we don't want yet any test of statistical significance and that we want the table to look like it would in SPSS.
```

The cells for the central two columns represent the total number of cases in each category, the **row percentages**, the **column percentages**, and the **total percentages**. So you have, for example, 63 people in the category "rubbish is very common" that were victims of a crime, this represents 30.88% of all the people in the "rubbish is very common" category (your row percent), 2.79% of all the people in the "victim of a crime" category (your column percent), and 0.57% of all the people in the sample.

Let's check the level of measurement of the "rubbcomm" variable with the `class()` function:


```r
class(BCS0708$rubbcomm)
```

```
## [1] "character"
```

It is categorical, we know, but note that R consdiers this "character" rather than "factor" which is what we would like. To make sure that R knows this is a factor, we can convert it with the `as.factor()` function. PAY ATTENTION: we are *not* recoding, so we use `as.factor()` with a dot (as.dot.factor), and we are **not using** the `as_factor()` from the haven package which we would use to recode if this were a .dta file (it's not!). 



```r
BCS0708$rubbcomm <- as.factor(BCS0708$rubbcomm)
```

Now in the table above, we notice that although "rubbcomm" is an ordinal variable, the order in which it gets printed does not make logical sense. We can check the order of the encoding using the `levels()` function.


```r
levels(BCS0708$rubbcomm)
```

```
## [1] "fairly common"     "not at all common" "not very common"  
## [4] "very common"
```

As we can see the order makes little sense. We should reorder the factor levels to make them follow a logical order. There are multiple ways of doing this, some of which we have already seen. This is one possible way of doing it.


```r
BCS0708$rubbcomm <- factor(BCS0708$rubbcomm, levels = c("not at all common", "not very common", "fairly common", "very common"))
```

You are only interested in the proportions or percentages that allow you to make meaningful comparisons. Although you can do cross-tabs for variables in which a priori you don't think of one of them as the one doing the explaining (your independent variable) and another to be explained (your dependent variable); most often you will already be thinking of them in this way. Here we think of victimisation as the outcome we want to explain and "rubbish in the area" as the factor that may help us to explain variation in victimisation.

If you have a dependent variable, you need to request only the percentages that allow you to make comparisons across your independent variable (how common rubbish is) for the outcome of interest (victimisation). In this case, with our outcome (victimisation) defining the columns, we would request and compare the row percentages only. On the other hand, if our outcome were the variable defining the rows we would be interested instead in the column percentages. Pay very close attention to this. It is a very common mistake to interpret a cross tab the wrong way if you don't do as explained here. 

To reiterate then, there are two rules to producing and reading cross tabs the right way. The first rule for reading cross tabulations is that **if your dependent variable is defining the rows then you ask for the column percentages. If, on the other hand, you decided that you preferred to have your dependent variable defining the columns (as seen here), then, you would need to ask for the row percentages**. Make sure you remember this.

To avoid confusion when looking at the table, you could as well modify the code to only ask for the relevant percentages. In this case we will ask for the row percentages. We can control what gets printed in the main console using the different options of the `CrossTable()` function. By default this function prints all the percentages, but most of them are not terribly useful for our purposes here. So, we are going to modify the default options by asking R not to print the column nor the total percentages. 


```r
with(BCS0708, CrossTable(rubbcomm, bcsvictim, prop.chisq=FALSE, prop.c=FALSE, prop.t=FALSE, format=c("SPSS")))
```

```
## 
##    Cell Contents
## |-------------------------|
## |                   Count |
## |             Row Percent |
## |-------------------------|
## 
## Total Observations in Table:  11065 
## 
##                   | bcsvictim 
##          rubbcomm | not a victim of crime  |       victim of crime  |             Row Total | 
## ------------------|-----------------------|-----------------------|-----------------------|
## not at all common |                 4614  |                  849  |                 5463  | 
##                   |               84.459% |               15.541% |               49.372% | 
## ------------------|-----------------------|-----------------------|-----------------------|
##   not very common |                 3173  |                  981  |                 4154  | 
##                   |               76.384% |               23.616% |               37.542% | 
## ------------------|-----------------------|-----------------------|-----------------------|
##     fairly common |                  876  |                  368  |                 1244  | 
##                   |               70.418% |               29.582% |               11.243% | 
## ------------------|-----------------------|-----------------------|-----------------------|
##       very common |                  141  |                   63  |                  204  | 
##                   |               69.118% |               30.882% |                1.844% | 
## ------------------|-----------------------|-----------------------|-----------------------|
##      Column Total |                 8804  |                 2261  |                11065  | 
## ------------------|-----------------------|-----------------------|-----------------------|
## 
## 
```

Much less cluttered. Now we only see in the counts and the row percentages. **Marginal frequencies** appear along the right and the bottom. *Row marginals* show the total number of cases in each row: 204 people perceive rubbish as very common in the area they're living in areas where , 1244 perceive rubbish is fairly common in their area, etc. *Column marginals* indicate the total number of cases in each column: 8804 non-victims and 2261 victims.

In the central cells we see the total number for each combination of categories and now only the row percentage. So the total in each of those cells is expressed as the percentage of cases in that row. So, for example, 63 people who perceive rubbish as very common in their area who are a victim of a crime represent 30.88%% of all people in that row (n=204). If we had asked for the column percentages the 63 people who live in areas where rubbish is very common and are victims would be divided by the 2261 victim people in the study. *Changing the denominator when computing the percentage changes the meaning of the percentage*.

This can sound a bit confusing now. But as long as you remember the first rule we gave you before you should be fine: if your dependent defines the rows ask for the column percentages, if your dependent defines the columns ask for the row percentages. There are always students that get this wrong in the assignments and loose points as a result. Don't let it be you.

The second rule for reading cross tabulations the right way is this: **you make the comparisons across the right percentages (see first rule) in the direction where they do not add up to a hundred**. Another way of saying this is that you compare the percentages for each level of your dependent variable across the levels of your independent variable. In this case we would, for example, compare what percentage of people who perceive rubbish as common in their area are victims of crime. We focus in the second column here (being victim of a crime) because typically that's what we want to study, this is our outcome of interest (e.g., victimisation). We can see rubbish seems to matter a bit. For example, 30.88% of people who live in areas where rubbish is very common have been victimised. By contrast only 15.54% of people who live in areas where rubbish is not at all common have been victimised in the previous year.

## Expected frequencies and Chi-Square

So far we are only describing our sample. Can we infer that these differences that we observe in this sample can be generalised to the population from which this sample was drawn? Every time you draw a sample from the same population the results will be slightly different, we will have a different combination of people in these cells. 

In order to assess that possibility we carry out a test of statistical significance. This test allow us to examine the null hypothesis. So our hypothesis is that there is a relationship between the two variables, while our null hypothesis is that there is not a relationship. In this case, the null hypothesis states that in the population from which this sample was drawn victimisation and how common rubbish is in your area are independent events, that is, they are not related to each other. The materials you read as preparation explained the test that is appropriate for this case, the chi square test. You should know what this test does is to contrast the squared average difference between the observed frequencies and the expected frequencies (divided by the expected frequencies). We can see the expected frequencies for each cell modifying the options of the `CrossTable` function in the following manner:


```r
with(BCS0708, CrossTable(rubbcomm, bcsvictim, expected = TRUE, prop.c = FALSE, prop.t = FALSE, format = c("SPSS")))
```

```
## 
##    Cell Contents
## |-------------------------|
## |                   Count |
## |         Expected Values |
## | Chi-square contribution |
## |             Row Percent |
## |-------------------------|
## 
## Total Observations in Table:  11065 
## 
##                   | bcsvictim 
##          rubbcomm | not a victim of crime  |       victim of crime  |             Row Total | 
## ------------------|-----------------------|-----------------------|-----------------------|
## not at all common |                 4614  |                  849  |                 5463  | 
##                   |             4346.701  |             1116.299  |                       | 
##                   |               16.437  |               64.005  |                       | 
##                   |               84.459% |               15.541% |               49.372% | 
## ------------------|-----------------------|-----------------------|-----------------------|
##   not very common |                 3173  |                  981  |                 4154  | 
##                   |             3305.180  |              848.820  |                       | 
##                   |                5.286  |               20.583  |                       | 
##                   |               76.384% |               23.616% |               37.542% | 
## ------------------|-----------------------|-----------------------|-----------------------|
##     fairly common |                  876  |                  368  |                 1244  | 
##                   |              989.804  |              254.196  |                       | 
##                   |               13.085  |               50.950  |                       | 
##                   |               70.418% |               29.582% |               11.243% | 
## ------------------|-----------------------|-----------------------|-----------------------|
##       very common |                  141  |                   63  |                  204  | 
##                   |              162.315  |               41.685  |                       | 
##                   |                2.799  |               10.899  |                       | 
##                   |               69.118% |               30.882% |                1.844% | 
## ------------------|-----------------------|-----------------------|-----------------------|
##      Column Total |                 8804  |                 2261  |                11065  | 
## ------------------|-----------------------|-----------------------|-----------------------|
## 
##  
## Statistics for All Table Factors
## 
## 
## Pearson's Chi-squared test 
## ------------------------------------------------------------
## Chi^2 =  184.0443     d.f. =  3     p =  1.180409e-39 
## 
## 
##  
##        Minimum expected frequency: 41.68495
```

So you can see, for example, that although 63 people lived in areas where rubbish was very common and experienced a victimisation in the past year, under the null hypothesis of no relationship we should expect this value to be 41.69. There are more people in this cell than we would expect under the null hypothesis. 

The Chi Square test 

(1) compares these expected frequencies with the ones we actually observe in each of the cells; 
(2) then averages the differences across the cells; and 
(3) produces a standardised value that 
(4) we look at in a Chi Square distribution to see how probable/improbable it is. 

If this absolute value is large, it will have a small p value associated with and we will be in a position to reject the null hypothesis. We would conclude then that observing such a large chi square is improbable if the null hypothesis is true. In practice we don't actually do any of this. We just run the Chi Square in our software and look at the p value in much the same way we have done for other tests. But it is helpful to know what the test is actually doing.

Asking for the expected frequencies with `CrossTable()` automatically prints the results of the Chi Square test. In this case, you get a Chi Square of 184.04, with 3 degrees of freedom. The probability associated with this particular value is nearly zero (1.180e-39). This value is considerably lower than the standard alpha level of .05. So, these results would lead us to conclude that there is a statistically significant relationship between these two variables. We are able to reject the null hypothesis that these two variables are independent in the population from which this sample was drawn. In other words, this significant Chi Square test means that we can assume that there was indeed a relationship between our indicator of broken windows and victimisation in the population of England and Wales in 2007/2008.

Notice that R is telling us that the minimum expected frequency is 41.68. Why? The Chi-squared test, for it to works, assumes the cell counts are sufficiently large. Precisely what constitutes 'sufficiently large' is a matter of some debate. One rule of thumb is that all expected cell counts should be above 5. If we have small cells one alternative is to rely on the Fisher's Exact Test rather than in the Chi Square. We don't have to request it here. Our cells are large enough for Chi Square to work fine. But if we needed, we could obtain the Fisher's Exact Test with the following code:


```r
fisher.test(BCS0708$rubbcomm, BCS0708$bcsvictim)
```

You will most likely get an error message telling you to increase the size of the workspace. When this happens you may try following the recommendation provided (consider using 'simulate.p.value=TRUE'): 


```r
fisher.test(BCS0708$rubbcomm, BCS0708$bcsvictim, simulate.p.value=TRUE)
```

```
## 
## 	Fisher's Exact Test for Count Data with simulated p-value (based on
## 	2000 replicates)
## 
## data:  BCS0708$rubbcomm and BCS0708$bcsvictim
## p-value = 0.0004998
## alternative hypothesis: two.sided
```

The p value is still considerably lower than our alpha level of .05. So, we can still reach the conclusion that the relationship we observe can be generalised to the population. 

Another less extreme solution (if cells are too small) is to use a p value using Monte Carlo simulation. This is a way of proceeding that is similar in philosophy to resampling techniques. To obtain such a Chi Square test you could use the `chisq.test()` function passing an argument requiring that the p value is obtained via resampling simulation:


```r
mytable.1 <- table(BCS0708$rubbcomm, BCS0708$bcsvictim)
chisq.test(mytable.1, simulate.p.value = TRUE)
```

```
## 
## 	Pearson's Chi-squared test with simulated p-value (based on 2000
## 	replicates)
## 
## data:  mytable.1
## X-squared = 184.04, df = NA, p-value = 0.0004998
```

Remember that we didn't really need the Fisher test or the simulated p values in this case. But there may be occasions when you need it as suggested above.

## Residuals

If we look at the observed and expected frequencies in the previous cross-tabulations we will see that there are differences in pretty much all the cells. You can possibly notice as well that some differences are bigger than others. For example, earlier we saw how there are about 21 more people that live in areas where rubbish is very common and experience victimisation than expected under the null hypothesis. Clearly when you see large differences you should expect that the cell in question may be playing a particularly strong role in driving the relationship. 

But how do you know that large is large? A statistic that helps in this regard is the **adjusted standardised residuals**. These residuals give you an idea of the difference between the expected and the observed counts in a standardised scale. Whenever you see differences that are greater (in absolute value) than 2, that's telling you that the difference between expected and observed frequencies in that particular cell is significant and is driving the results of your Chi Square test. We can requests R to print these residuals with the following code:


```r
with(BCS0708, CrossTable(rubbcomm, bcsvictim, expected = TRUE, prop.chisq = FALSE, prop.c = FALSE,  prop.t = FALSE, asresid = TRUE, format = c("SPSS"))) 
```

```
## 
##    Cell Contents
## |-------------------------|
## |                   Count |
## |         Expected Values |
## |             Row Percent |
## |           Adj Std Resid |
## |-------------------------|
## 
## Total Observations in Table:  11065 
## 
##                   | bcsvictim 
##          rubbcomm | not a victim of crime  |       victim of crime  |             Row Total | 
## ------------------|-----------------------|-----------------------|-----------------------|
## not at all common |                 4614  |                  849  |                 5463  | 
##                   |             4346.701  |             1116.299  |                       | 
##                   |               84.459% |               15.541% |               49.372% | 
##                   |               12.605  |              -12.605  |                       | 
## ------------------|-----------------------|-----------------------|-----------------------|
##   not very common |                 3173  |                  981  |                 4154  | 
##                   |             3305.180  |              848.820  |                       | 
##                   |               76.384% |               23.616% |               37.542% | 
##                   |               -6.436  |                6.436  |                       | 
## ------------------|-----------------------|-----------------------|-----------------------|
##     fairly common |                  876  |                  368  |                 1244  | 
##                   |              989.804  |              254.196  |                       | 
##                   |               70.418% |               29.582% |               11.243% | 
##                   |               -8.494  |                8.494  |                       | 
## ------------------|-----------------------|-----------------------|-----------------------|
##       very common |                  141  |                   63  |                  204  | 
##                   |              162.315  |               41.685  |                       | 
##                   |               69.118% |               30.882% |                1.844% | 
##                   |               -3.736  |                3.736  |                       | 
## ------------------|-----------------------|-----------------------|-----------------------|
##      Column Total |                 8804  |                 2261  |                11065  | 
## ------------------|-----------------------|-----------------------|-----------------------|
## 
##  
## Statistics for All Table Factors
## 
## 
## Pearson's Chi-squared test 
## ------------------------------------------------------------
## Chi^2 =  184.0443     d.f. =  3     p =  1.180409e-39 
## 
## 
##  
##        Minimum expected frequency: 41.68495
```

You can see here, looking at the column identifying the outcome of interest (victimisation) that the adjusted standardised residual is lower than -12 for the "not at all common" category. That is the largest residual for the outcome of interest. The expected count under the null hypothesis here is much higher than the observed count. 

## Gamma

Is this relationship strong? The residuals seem to be suggesting it is not trivial indeed. Apart from looking at the residuals, one of the tests discussed in the required reading as a test for the strength of a relationship is gamma. Gamma is a measure of association that allow us to make a judgement about the strength of this relationship and that we can use with ordinal measures (or as in this case when one variable is ordinal and the other is nominal dichotomous). Gamma is appropriate for testing the relationship between two categorical ordered variables (ordinal-level variables) or between a categorical ordered variable and a categorical unordered variables with only two levels (a dichotomous variable, such as "victimisation": that only has two levels, you have or you haven't experienced a victimisation). How can you obtain gamma with R?

We will use the package `vcdExtra` for it (which you may need to install and load) to compute gamma. We use the following code:


```r
mytable.2<-table(BCS0708$bcsvictim, BCS0708$rubbcomm) ##We first create a new object in tabular form because the function we use to compute Goodman and Kruskal's Gamma needs an object of that nature.
print(mytable.2) ##You can print the content of this object and you will see that it is simply the crosstab with just the counts.
```

```
##                        
##                         not at all common not very common fairly common
##   not a victim of crime              4614            3173           876
##   victim of crime                     849             981           368
##                        
##                         very common
##   not a victim of crime         141
##   victim of crime                63
```

```r
library(vcdExtra) ##This will load the vcdExtra package (assuming it is already installed)
GKgamma(mytable.2) ##This function from the vcdExtra package will compute the Gamma measure of association, between parenthesis you need to identify the object that contains your data.
```

```
## gamma        : 0.266 
## std. error   : 0.019 
## CI           : 0.229 0.302
```

Gamma falls between -1 and +1. The sign indicates whether the association is positive or negative. In this case it is positive: this suggests that the higher order of the categories in the ordinal measure (rubbish) is associated with higher values in the second variable (victimisation). Higher in this context mean the order in which they appear in your table. So the highest in your ordinal measure (how common rubbish is) refers to the last row (very common). And highest in the dichotomous measure refers to the last column (victim of a crime). Keep this in mind when interpreting gamma. 

The larger the absolute value of gamma, the stronger the association. There are not clear rules of thumb in how to interpret Gamma. This value is larger than 0, although closer to 0 than to 1. De Vaus (2002) provides the following rules of thumb:  up to .10 (trivial association), .10 to .29 (low to moderate), .30 to .49 (moderate to substantial), .50 to .69 (substantial to very strong), .70 to .89 (very strong), .9 and above (near perfect). On those bases, I would say this particular Gamma estimated at .226 indicates an association of modest size. Notice that the confidence interval is provided. So the estimated gamma with an alpha level of 0.05 is estimated to be anywhere between 0.302 and 0.229. If this confidence interval overlapped with 0 we could not reject the null hypothesis.

Gamma, however, assumes a "linear" relationship, more in one of the variables, more in the other (for positive relationships), less in one, more in the other (for negative relationships). Here we can see that the percentage of people that experience victimisation is almost the same for those who live in areas where rubbish is fairly common but also for those who live in areas where it is very common. That is, once we reach a certain level of rubbish the risk of victimisation does not go much higher. In situations like this gamma is likely underestimating the strength of the relationship.

## Odds and odd ratios

When you have two dichotomous nominal level variables, that is, two nominal level variables that can take only two possible levels, one of the more commonly used measures to indicate the strength of an association are odd ratios. Odd ratios and relative risk are very commonly used in public health and in criminological research. If you have knowledge of betting, you may already know a thing or two about odds.

They are the statistical equivalent of a tongue twister, so don't worry too much if you need to keep looking at this handout every time you want to interpret them. We are going to look at the relationship between victimisation and living in a rural/urban setting: 

```r
with(BCS0708, CrossTable(rural2, bcsvictim, prop.c = FALSE, prop.t = FALSE, expected = TRUE, format = c("SPSS")))
```

```
## 
##    Cell Contents
## |-------------------------|
## |                   Count |
## |         Expected Values |
## | Chi-square contribution |
## |             Row Percent |
## |-------------------------|
## 
## Total Observations in Table:  11676 
## 
##              | bcsvictim 
##       rural2 | not a victim of crime  |       victim of crime  |             Row Total | 
## -------------|-----------------------|-----------------------|-----------------------|
##        rural |                 2561  |                  413  |                 2974  | 
##              |             2373.393  |              600.607  |                       | 
##              |               14.830  |               58.602  |                       | 
##              |               86.113% |               13.887% |               25.471% | 
## -------------|-----------------------|-----------------------|-----------------------|
##        urban |                 6757  |                 1945  |                 8702  | 
##              |             6944.607  |             1757.393  |                       | 
##              |                5.068  |               20.028  |                       | 
##              |               77.649% |               22.351% |               74.529% | 
## -------------|-----------------------|-----------------------|-----------------------|
## Column Total |                 9318  |                 2358  |                11676  | 
## -------------|-----------------------|-----------------------|-----------------------|
## 
##  
## Statistics for All Table Factors
## 
## 
## Pearson's Chi-squared test 
## ------------------------------------------------------------
## Chi^2 =  98.52709     d.f. =  1     p =  3.206093e-23 
## 
## Pearson's Chi-squared test with Yates' continuity correction 
## ------------------------------------------------------------
## Chi^2 =  98.00261     d.f. =  1     p =  4.178318e-23 
## 
##  
##        Minimum expected frequency: 600.6074
```

So we can see that 22% of urban dwellers by comparison to 14% of those living in rural areas have experienced a victimisation in the previous past year. It looks as if living in an urban environment constitutes a risk factor or is associated with victimisation. The Chi Square we obtain has a low p value suggesting that this association is statistically significant. That is, we can possibly infer that there is an association in the population from which the sample was drawn. But how large is this relationship? 

This is where odd ratios are handy. Before we get to them I will discuss a simple tip in layout.  Risk ratios and odd ratios are very commonly used in the public health tradition. In this tradition researchers place the disease/condition defining the columns and the treatment or risk factor defining the rows and they do so in such a way that the first cell correspond to the intersection of the outcome and the risk factor. And the software that computes odd ratios tends to assume this is how your table is set up. So, whenever you are after the relative risks or odd ratios (that is, whenever you work with a 2X2 table) you should laid the table like this as well. It will help interpretation:

+-------------------+---------------------+-----------------+
|                   | Outcome: Yes        | Outcome: No     |
+-------------------+---------------------+-----------------+
| Risk factor: Yes  |                     |                 |
+-------------------+---------------------+-----------------+
| Risk factor: No   |                     |                 |
+-------------------+---------------------+-----------------+

Our table was set up in such a way that the rows are defined by our "risk factor" and the columns by our outcome. But the first cell represents the intersection of the presence of the risk factor and the absence of the outcome. The easiest way to sort this out is to change the order of the levels in our factor variable identifying the outcome ("bcsvictim"). If we ask R to print the levels of the bcsvictim variable we will see that they are as follow:


```r
print(levels(BCS0708$bcsvictim))
```

```
## NULL
```

```r
print(levels(BCS0708$rural2))
```

```
## NULL
```

We want to reverse this. So that "victim of crime" becomes the first level (appears first in the print out) and "urban" becomes the first level as well. There are various ways of doing that with add-on packages, this is an easy way using base R:


```r
BCS0708$bcsvictimR <- factor(BCS0708$bcsvictim, levels = c('victim of crime','not a victim of crime'))
print(levels(BCS0708$bcsvictimR))
```

```
## [1] "victim of crime"       "not a victim of crime"
```

```r
BCS0708$urban <- factor(BCS0708$rural2, levels = c('urban','rural'))
print(levels(BCS0708$urban))
```

```
## [1] "urban" "rural"
```

We can now rerun the previous cross tabulation (with the newly created reordered factors) and the table will look as below:


```r
with(BCS0708, CrossTable(urban, bcsvictimR, prop.c = FALSE, prop.t = FALSE, expected = TRUE, format = c("SPSS")))
```

```
## 
##    Cell Contents
## |-------------------------|
## |                   Count |
## |         Expected Values |
## | Chi-square contribution |
## |             Row Percent |
## |-------------------------|
## 
## Total Observations in Table:  11676 
## 
##              | bcsvictimR 
##        urban |       victim of crime  | not a victim of crime  |             Row Total | 
## -------------|-----------------------|-----------------------|-----------------------|
##        urban |                 1945  |                 6757  |                 8702  | 
##              |             1757.393  |             6944.607  |                       | 
##              |               20.028  |                5.068  |                       | 
##              |               22.351% |               77.649% |               74.529% | 
## -------------|-----------------------|-----------------------|-----------------------|
##        rural |                  413  |                 2561  |                 2974  | 
##              |              600.607  |             2373.393  |                       | 
##              |               58.602  |               14.830  |                       | 
##              |               13.887% |               86.113% |               25.471% | 
## -------------|-----------------------|-----------------------|-----------------------|
## Column Total |                 2358  |                 9318  |                11676  | 
## -------------|-----------------------|-----------------------|-----------------------|
## 
##  
## Statistics for All Table Factors
## 
## 
## Pearson's Chi-squared test 
## ------------------------------------------------------------
## Chi^2 =  98.52709     d.f. =  1     p =  3.206093e-23 
## 
## Pearson's Chi-squared test with Yates' continuity correction 
## ------------------------------------------------------------
## Chi^2 =  98.00261     d.f. =  1     p =  4.178318e-23 
## 
##  
##        Minimum expected frequency: 600.6074
```

In order to understand odd ratios and relative risk is important to understand risks and odds first. The **risk** is simply the probability of the "outcome" we are concerned about (i.e., victimisation). So the risk of victimisation for urban dwellers is simply the number of victimised urban dwellers (1945) divided by the total number of urban dwellers (8702). This is .2235. Similarly we can look at the risk of victimisation for people living in rural areas: the number of victimised countryside residents (413) divided by the total number of residents in rural areas (2974).  This is .1388. The **relative risk** is simply the ratio of these two risks. In this case this yields 1.60. This suggests that urban dwellers are 1.60 times more likely to be victimised than people who live in rural areas.

The **odds** on the other hand contrast the number of individuals with the outcome with those without the outcome for each of the rows. Notice the difference with the risk. So the odds of victimisation for urban dwellers equal the number of victimised urban dwellers (1945) by the number of non-victimised urban dwellers (6757). This is .2878. There are .2878 victimised urban dwellers for every non-victimised urban dweller. And the odds of victimisation for residents of rural areas equal the number of victimised rural residents (413) by the number of non-victimised rural residents (2561). This is .1612. There are .1612 victimised rural residents for every non-victimised rural resident.

The **odds ratio** is the ratio of these two odds. So the odds ratio of victimisation for urban dwellers to rural residents is the odds of victimisation for urban dwellers (.2878) divided by the odds of victimisation for rural residents (.1612). This yields 1.78. This means that the odds of victimisation are almost 1.78 times higher for urban dwellers than for residents in rural areas. 

You can use R to obtain the odd ratios directly. We can use the `vcd` package we mentioned earlier. As before we first create an object with the table and then ask for the ordinary odds ratio using the following code:


```r
library(vcd)
mytable.3<-table(BCS0708$urban, BCS0708$bcsvictimR)
oddsratio(mytable.3, stratum = NULL, log = FALSE) 
```

```
##  odds ratios for  and  
## 
## [1] 1.784947
```

The  `oddsratio` function here is asking for the oddsratio for the table data in the object called *mytable.3*. The `log=FALSE` requests an ordinary odds ratio and the `stratum` option clarifies your data are not stratified.

What would happen if rather than using the recoded variable ("bcsvictimR") we use the original one?


```r
mytable.4<-table(BCS0708$urban, BCS0708$bcsvictim)
print(mytable.4)
```

```
##        
##         not a victim of crime victim of crime
##   urban                  6757            1945
##   rural                  2561             413
```

```r
oddsratio(mytable.4, stratum = NULL, log = FALSE)
```

```
##  odds ratios for  and  
## 
## [1] 0.5602409
```

What's going on? Why do we have a different value here? If you look at the cross tab you should be able to understand. R is now computing the odd ratio for "not being a victim of a crime" (since this is what defines the first column). When an odds ratio is below 1 is indicating that the odds in the first row ("urban") are lower than in the second row ("rural"). Living in urban areas (as contrasted with living in rural areas) reduces the likelihood of non-victimisation. 

How to interpret odd ratios? Something that is important to keep in mind is that odd ratios (and relative risk) are non-negative values, that is: they cannot take negative values (i.e., -1, -3, etc.). They can go from 1 to infinite but only from 1 to zero. If the value is greater than 1 that means that, as in this case, living in an urban area increases the chances of the event, being a victim in this example. If the value were to be between 0 and 1 that would mean that the factor in question reduces the chances of the event you are trying to predict. Finally, a value of 1 means that there is no relationship between the two variables: it would mean that the odds or the risks are the same for the two groups.

Whenever the odd ratio is between 0 and 1 that means that the odds of whatever it is defining the first column (in the more recent table we printed not being a victim) is lower for the first row (in this case living in an urban area) than in the second row (in this case living in a rural area). To read an odd ratio that is between 0 and 1 you first need to take its inverse, so in this case 1/0.5602 will give you 1.78. What this is telling you is that the odds of not being a victim of victim are 1.78 times less for men than for women, which is the same as to say that the odds of being a victim of assault are 1.78 more for men than for women. That is, odd ratios are reciprocal.

You may be confused by now. Have a look at [this video](https://www.youtube.com/watch?v=nFHL54yOniI), it may help to see an oral presentation of these ideas with a different example.  Repeated practice will make it easier to understand. The fact that the interpretation of these quantities is contingent in the way we have laid out our table makes it particularly advisable to hand calculate them as explained above in relation to the outcome you are interested until you are comfortable with them. This may help you to see more clearly what you are getting and how to interpret it. When looking at the R results for odd ratios just always keep in mind that you are aware of what are the reference categories (what defines the first column and the first row) when reading and interpreting odd ratios. The R function we introduced will always give you the odds ratio for the event defined in the first column and will contrast the odds for the group defined by the first row with the odds defined by the second row. If the odds ratio is between 0 and 1 that would mean the odds are lower for the first row, if the odds is greater than 1 that would mean the odds are higher for the second row.

It is also very important you do not confuse the relative risk (a ratio of probabilities) with the odds ratio (a ratio of odds). Be very careful with the language you use when interpreting these quantities.

Odd ratios are ratios of odds, not probability ratios. You cannot say that urban dwellers are 1.78 more likely to be victimised. All you can say with an odd ratio is that the odds of being victimised are 1.78 times higher for urban dwellers than for residents in rural areas. Odds and probabilities are different things.

It is also very important that you interpret these quantities carefully. You will often see media reports announcing things such as that chocolate consumption will double your risk of some terrible disease. What that means is that the percentage of cases of individuals that take chocolate and present the condition is twice as large as those that do not take chocolate and present the condition. But you also need to know what those percentages are to put it in the right context. If those probabilities are very low to start with, well, does it really matter?

![increased risk](https://www.explainxkcd.com/wiki/images/1/11/increased_risk.png)

<!--chapter:end:07-categorical_associations.Rmd-->

# An introduction to regression

## Introduction: models in scientific research


In science one of our main concerns is to develop models of the world, models that help us to understand the world a bit better or to predict how things will develop better. You can read more about modelling in scientific research [here](https://www.visionlearning.com/en/library/Process-of-Science/49/Modeling-in-Scientific-Research/153). Statistics provides a set of tools that help researchers build and test scientific models.

Our models can be simple. We can think that unemployment is a factor that may help us to understand why cities differ in their level of violent crime. We could express such a model like this:

![](imgs/model1.PNG) 

Surely we know the world is complex and likely there are other things that may help us to understand why some cities have more crime than others. So, we may want to have tools that allow us to examine such models. Like, for example, the one below:

![](imgs/model2.PNG) 

In this session we are going to cover regression analysis or, rather, we are beginning to talk about regression modelling. This form of analysis has been one the main technique of data analysis in the social sciences for many years and it belongs to a family of techniques called generalised linear models. Regression is a flexible model that allows you to "explain" or "predict" a given outcome (Y), variously called your outcome, response or dependent variable, as a function of a number of what is variously called inputs, features or independent, explanatory, or predictive variables (X1, X2, X3, etc.). Following Gelman and Hill (2007), I will try to stick for the most part to the terms outputs and inputs.

Today we will cover something that is called linear regression or ordinary least squares regression (OLS), which is a technique that you use when you are interested in explaining variation in an interval level variable. First we will see how you can use regression analysis when you only have one input, like in our first model, and then we will move to situations when we have several explanatory variables or inputs, like in our second model.

We will use a new dataset today, specifically the data used by Patrick Sharkey and his colleagues to study the effect of non profit organisations in the levels of crime. In [*"Uneasy Peace"*](https://books.wwnorton.com/books/Uneasy-Peace/) Prof Sharkey argues that one of the factors that contributed to the decline of crime from the 90s onwards was the role played by non profit community organisations to bring peace and services to deteriorated neighbourhoods. In this session we will use the replication data from one of the papers that Prof Sharkey published studying this question. We can find this data in the [Harvard Dataverse](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/46WIH0). If you are interested in the specific study analysing this data you can find it [here](https://journals.sagepub.com/doi/abs/10.1177/0003122417736289).


```r
urlfile <- "https://dataverse.harvard.edu/api/access/datafile/:persistentId?persistentId=doi:10.7910/DVN/46WIH0/ARS2VS"
sharkey <- read.table(url(urlfile), sep = '\t',header = T)
```

As before we create an object with the permanent `url` address and then we use a function to read the data into R. The data that can be saved using an `api` is in tab separated format. For this then we use the `read.table` function from base R. We pass two arguments to the function `sep= '\t'` is telling R this file is tab separated. The `header = T` function is telling R that is TRUE (T) that this file has a first row that acts as a header (this row has the name of the variables).

There are many more variables here that we are going to need, so let's do some filtering and selection. Let's just focus on a single year, 2012, the most recent in the dataset and just a few select variables.


```r
library(dplyr)
df <- filter(sharkey, year == "2012")
df <- select(df, place_name, state_name, viol_r, black, lesshs, unemployed, fborn, incarceration, log_incarceraton, swornftime_r, log_viol_r, largest50)
```

So now we have a more manageable data set that we can use for this session. The file includes a sample of 264 US cities (see *place_name*) across 44 of states:


```r
table(df$state_name)
```

```
## 
##              Alabama               Alaska              Arizona 
##                    4                    1                    9 
##             Arkansas           California             Colorado 
##                    1                   65                   10 
##          Connecticut District of Columbia              Florida 
##                    5                    1                   18 
##              Georgia                Idaho             Illinois 
##                    2                    1                    8 
##              Indiana                 Iowa               Kansas 
##                    3                    3                    5 
##            Louisiana             Maryland        Massachusetts 
##                    4                    1                    3 
##             Michigan            Minnesota          Mississippi 
##                    6                    3                    1 
##             Missouri              Montana             Nebraska 
##                    5                    1                    2 
##               Nevada        New Hampshire           New Jersey 
##                    3                    1                    4 
##           New Mexico             New York       North Carolina 
##                    1                    5                    9 
##         North Dakota                 Ohio             Oklahoma 
##                    1                    5                    4 
##               Oregon         Pennsylvania         Rhode Island 
##                    4                    4                    1 
##       South Carolina         South Dakota            Tennessee 
##                    3                    1                    6 
##                Texas                 Utah             Virginia 
##                   30                    4                    7 
##           Washington            Wisconsin 
##                    6                    3
```

The variables we have extracted contain information on the demographic composition of those cities (percent black population, percent without high school degree, percent unemployed, percent foreign born), some criminal justice ones (incarceration rate and the rate of sworn full time police officers). We also have measures of the violence rate and a binary indicator that tell us if the city is one of the 50 largest in the country.

We are going to look at the relationship between violent crime with a variable measuring unemployment (*unemployed*). Let's look at the violence rate:


```r
library(ggplot2)
ggplot(df, aes(x = viol_r)) +
  geom_histogram()
```

![](08-regression_files/figure-latex/unnamed-chunk-4-1.pdf)<!-- --> 

As you can see is skewed. Violence is our target variable, the one we want to better understand. You may remember from when we cover ANOVA that some times we have to make transformations to variables so that the assumptions of the models we use are better respected. We will discuss this a bit in greater depth later. For now, just trust us in that rather than using *viol_r* we are going to use the logarithmic transformation of the violence rate, *log_viol_r*.


```r
library(ggplot2)
ggplot(df, aes(x = log_viol_r)) +
  geom_histogram()
```

![](08-regression_files/figure-latex/unnamed-chunk-5-1.pdf)<!-- --> 

Let's look at the scatterplot between the log of the violence rate and unemployment:


```r
ggplot(df, aes(x = unemployed, y = log_viol_r)) +
  geom_point(alpha=.2, position="jitter") 
```

![](08-regression_files/figure-latex/unnamed-chunk-6-1.pdf)<!-- --> 

What do you think when looking at this scatterplot? Is there a relationship between violence and unemployment? Does it look as if cities that have a high score on the X axis (unemployment) also have a high score on the Y axis (violent crime)? It may be a bit hard to see but I would think there is certainly a trend. 

## Motivating regression

Now, imagine that we play a game. Imagine I have all the names of the cities in a hat, and I randomly take one of names from the hat. You're sitting in the audience, and you have to guess the level of violence (*log_viol_r*) for that city. Imagine that I pay £150 to the student that gets the closest to the right value. What would you guess if you only have one guess and you knew (as we do) how the log of violent crime is distributed? 


```r
ggplot(df, aes(x = log_viol_r)) + 
  geom_density() +
  geom_vline(xintercept = 6.061, linetype = "dashed", size = 1, color="red") +
  ggtitle("Density estimate and mean of log violent crime rate")
```

![](08-regression_files/figure-latex/unnamed-chunk-7-1.pdf)<!-- --> 


```r
summary(df$log_viol_r)
```

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   3.831   5.532   6.149   6.061   6.595   7.634
```

If I only had one shot, I would go for the mean or the median (given the skew). Most of the cities have values clustered around those values, which is another way of saying they are bound to be not too far from them. It would be silly to say 4, for example, since there are very few cities with such low level of violence (as measured by *log_viol_r*).

Imagine, however, that now when I take the name of the city from the hat, you are also told how much unemployment there is in that city - so the value of the *unemployed* variable for the city that has been selected (for example 9). Imagine as well that you have the scatterplot that we produced earlier in front of you. Would you still go for the value of "six" (the mean) as your best guess for the value of the selected city? 

I certainly would not go with the overall mean or median as my prediction any more. If somebody said to me, the value *unemployed* for the selected respondent is 9, I would be more inclined to guess the mean value for the cities *with that level of unemployment* (the conditional mean), rather than the overall mean across all the cities. Wouldn't you? 

If we plot the conditional means we can see that the mean *log_viol_r* for cities that report an unemployment of 9 is around 6.5. So you may be better off guessing that.


```
## Warning: Ignoring unknown parameters: fun.y
```

```
## No summary function supplied, defaulting to `mean_se()`
```

![](08-regression_files/figure-latex/unnamed-chunk-9-1.pdf)<!-- --> 

Linear regression tackles this problem using a slightly different approach. Rather than focusing on the conditional mean (smoothed or not), it draws a straight line that tries to capture the trend in the data. If we focus in the region of the scatterplot that are less sparse we see that this is an upward trend, suggesting that as the level of unemployment increases so does the level of violent crime. 

Simple linear regression draws a single straight line of predicted values **as the model for the data**. This line would be a **model**, a *simplification* of the real world like any other model (e.g., a toy pistol, an architectural drawing, a subway map), that assumes that there is approximately a linear relationship between X and Y. Let's draw the regression line:


```r
ggplot(data = df, aes(x = unemployed, y = log_viol_r)) +
  geom_point(alpha = .2, position = "jitter") +
  geom_smooth(method = "lm", se = FALSE, color = "red", size = 1) 
```

```
## `geom_smooth()` using formula 'y ~ x'
```

![](08-regression_files/figure-latex/unnamed-chunk-10-1.pdf)<!-- --> 

The `geom_smooth` function asks for a geom with the regression line, `method=lm` asks for the linear regression line, `se=FALSE` asks for just the line to be printed, the other arguments specify the colour and thickness of the line.

What that line is doing is giving you guesses (predictions) for the values of violent crime based in the information that we have about the level of unemployment. It gives you one possible guess for the value of violence for every possible value of unemployment and links them all together in a straight line. 

Another way of thinking about this line is as the best possible summary of the cloud of points that are represented in the scatterplot (if we can assume that a straight line would do a good job doing this). If I were to tell you to draw a straight line that best represents this pattern of points the regression line would be the one that best does it (if certain assumptions are met).

The linear model then is a model that takes the form of the equation of a straight line through the data. The line does not go through all the points. In fact, you can see is a slightly less accurate representation than the (smoothed) conditional means:


```
## Warning: Ignoring unknown parameters: fun.y
```

```
## `geom_smooth()` using formula 'y ~ x'
```

```
## No summary function supplied, defaulting to `mean_se()`
```

![](08-regression_files/figure-latex/unnamed-chunk-11-1.pdf)<!-- --> 

As De Veaux et al (2012: 179) highlight: "like all models of the real world, the line will be wrong, wrong in the sense that it can't match reality exactly. But it can help us understand how the variables are associated". A map is never a perfect representation of the world, the same happens with statistical models. Yet, as with maps, models can be helpful.

## Fitting a simple regression model

In order to draw a regression line we need to know two things: 
(1) We need to know where the line begins, what is the value of Y (our dependent variable) when X (our independent variable) is 0, so that we have a point from which to start drawing the line. The technical name for this point is the **intercept**.
(2) And we need to know what is the **slope** of that line, that is, how inclined the line is, the angle of the line.

If you recall from elementary algebra (and you may not), the equation for any straight line is:
 y = mx + b 
In statistics we use a slightly different notation, although the equation remains the same:
y = b0 + b1x

We need the origin of the line (b0) and the slope of the line (b1). How does R get the intercept and the slope for the green line? How does R know where to draw this line? We need to estimate these **parameters** (or **coefficients**) from the data. How? We don't have the time to get into these more mathematical details now. You should study the [required reading](http://link.springer.com/chapter/10.1007/978-1-4614-7138-7_3) to understand this (*required means it is required, it is not optional*)[^1]. For now, suffice to say that for linear regression modes like the one we cover here, when drawing the line, R tries to minimise the distance from every point in the scatterplot to the regression line using a method called **least squares estimation**.

In order to fit the model we use the `lm()` function using the formula specification `(Y ~ X)`. Typically you want to store your regression model in a "variable", let's call it `fit_1`:


```r
fit_1 <- lm(log_viol_r ~ unemployed, data = df)
```

You will see in your R Studio global environment space that there is a new object called `fit_1` with 12 elements on it. We can get a sense for what this object is and includes using the functions we introduced in Week 1:


```r
class(fit_1)
```

```
## [1] "lm"
```

```r
attributes(fit_1)
```

```
## $names
##  [1] "coefficients"  "residuals"     "effects"       "rank"         
##  [5] "fitted.values" "assign"        "qr"            "df.residual"  
##  [9] "xlevels"       "call"          "terms"         "model"        
## 
## $class
## [1] "lm"
```

R is telling us that this is an object of class `lm` and that it includes a number of attributes. One of the beauties of R is that you are producing all the results from running the model, putting them in an object, and then giving you the opportunity for using them later on. If you want to simply see the basic results from running the model you can use the `summary()` function.


```r
summary(fit_1)
```

```
## 
## Call:
## lm(formula = log_viol_r ~ unemployed, data = df)
## 
## Residuals:
##      Min       1Q   Median       3Q      Max 
## -1.81195 -0.44612  0.06817  0.45424  1.50438 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)  4.57817    0.14899   30.73   <2e-16 ***
## unemployed   0.23710    0.02302   10.30   <2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 0.6254 on 262 degrees of freedom
## Multiple R-squared:  0.2882,	Adjusted R-squared:  0.2855 
## F-statistic: 106.1 on 1 and 262 DF,  p-value: < 2.2e-16
```

Or if you prefer more parsimonious presentation you could use the `display()` function of the `arm` package:


```r
arm::display(fit_1)
```

```
## lm(formula = log_viol_r ~ unemployed, data = df)
##             coef.est coef.se
## (Intercept) 4.58     0.15   
## unemployed  0.24     0.02   
## ---
## n = 264, k = 2
## residual sd = 0.63, R-Squared = 0.29
```

For now I just want you to focus on the numbers in the "Estimate" column. The value of 4.58 estimated for the **intercept** is the "predicted" value for Y when X equals zero. This is the predicted value of the violence score *when the level of unemployment is zero*. 

We then need the b1 regression coefficient for for our independent variable, the value that will shape the **slope** in this scenario. This value is 0.24. This estimated regression coefficient for our independent variable has a convenient interpretation. When the value is positive, it tells us that *for every one unit increase in X there is a b1 increase on Y*. If the coefficient is negative then it represents a decrease on Y. Here, we can read it as "for every one unit increase in the percentage of people unemployed, there is a 0.24 unit increase in the logarithm of the violence rate."

Knowing these two parameters not only allows us to draw the line, we can also solve for any given value of X. Let's go back to our guess-the-violence game. Imagine I tell you the level of unemployment is 4. What would be your best bet now? We can simply go back to our regression line equation and insert the estimated parameters:

y = b0 + b1x   
y = 4.58 + 0.24 (4)  
y = .1031

Or if you don't want to do the calculation yourself, you can use the `predict` function (differences are due to rounding error):


```r
predict(fit_1, data.frame(unemployed = c(4))) #First you name your stored model and then you identify the new data (which has to be in a data frame format and with a variable name matching the one in the original data set)
```

```
##        1 
## 5.526564
```

This is the expected value of Y, log of the violence rate, when X, unemployment is 5% of the population *according to our model* (according to our simplification of the real world, our simplification of the whole cloud of points into just one straight line). Look back at the scatterplot we produced earlier with the green line. Does it look as if the green line when X is 4 corresponds to a value of Y of 5.5?

## Residuals revisited: R squared

In the output when we run the model above we saw there was something called the residuals. The residuals (in regression) are the differences between the observed values of Y for each case minus the predicted or expected value of Y, in other words the distances between each point in the dataset and the regression line (see the visual example below). 

![drawing](http://www.shodor.org/media/M/T/l/mYzliZjY4ZDc0NjI3YWQ3YWVlM2MzZmUzN2MwOWY.jpg)

You see that we have our line, which is our predicted values, and then we have the black dots which are our actually observed values. The distance between them is essentially the amount by which we were wrong, and all these distances between observed and predicted values are our residuals. **Least square estimation**, the "machine" we use to build the regression line, essentially aims to reduce the squared average of all these distances: that's how it draws the line.

Why do we have residuals? Well, think about it. The fact that the line is not a perfect representation of the cloud of points makes sense, doesn't it? You cannot predict perfectly what the value of Y is for every city just by looking ONLY at unemployment! This line only uses information regarding unemployment. This means that there's bound to be some difference between our predicted level of violence given our knowledge of unemployment (the regression line) and the actual level of violence (the actual location of the points in the scatterplot). There are other things that matter not being taken into account by our model to predict the values of Y. There are other things that surely matter in terms of understanding violence. And then, of course, we have measurement error and other forms of noise.

We can re-write our equation like this if we want to represent each value of Y (rather than the predicted value of Y) then: 
y = b0 + b1x + residuals

The residuals capture how much variation is unexplained, how much we still have to learn if we want to understand variation in Y. A good model tries to maximise explained variation and reduce the magnitude of the residuals. 

We can use information from the residuals to produce a measure of effect size, of how good our model is in predicting variation in our dependent variables. Remember our game where we try to guess violence (Y)? If we did not have any information about X our best bet for Y would be the mean of Y. The regression line aims to improve that prediction. By knowing the values of X we can build a regression line that aims to get us closer to the actual values of Y. 

![](https://people.richland.edu/james/ictcm/2004/weight2.png)

The distance between the mean (our best guess without any other piece of information) and the observed value of Y is what we call the **total variation**. The residual is the difference between our predicted value of Y  and the observed value of Y. This is what we cannot explain (i.e, variation in Y that is *unexplained*). The difference between the mean value of Y and the expected value of Y (the value given by our regression line) is how much better we are doing with our prediction by using information about X (i.e., in our previous example it would be variation in Y that can be *explained* by knowing about unemployment). How much closer the regression line gets us to the observed values. We can then contrast these two different sources of variation (explained and unexplained) to produce a single measure of how good our model is. The formula is as follows:

![formula](http://docs.oracle.com/cd/E40248_01/epm.1112/cb_statistical_11123500/images/graphics/r_squared_constant.gif)

All this formula is doing is taking a ratio of the explained variation (the squared differences between the regression line and the mean of Y for each observation) by the total variation (the squared differences of the observed values of Y for each observation from the mean of Y). This gives us a measure of the **percentage of variation in Y that is "explained" by X**. If this sounds familiar is because it is a measure similar to eta squared in ANOVA that we cover in an earlier session.

As then we can take this value as a measure of the strength of our model. If you look at the R output you will see that the R2 for our model was .29 (look at the multiple R square value in the output) . We can say that our model explains 29% of the variance in the fear of violent crime measure.


```r
#As an aside, and to continue emphasising your appreciation of the object oriented nature of R, when we run the summary() function we are simply generating a list object of the class summary.lm.
attributes(summary(fit_1))
```

```
## $names
##  [1] "call"          "terms"         "residuals"     "coefficients" 
##  [5] "aliased"       "sigma"         "df"            "r.squared"    
##  [9] "adj.r.squared" "fstatistic"    "cov.unscaled" 
## 
## $class
## [1] "summary.lm"
```

```r
#This means that we can access its elements if so we wish. So, for example, to obtain just the R Squared, we could ask for:
summary(fit_1)$r.squared
```

```
## [1] 0.2881989
```

Knowing how to interpret this is important. R^2 ranges from 0 to 1. The greater it is the more powerful our model is, the more explaining we are doing, the better we are able to account for variation in our outcome Y with our input. In other words, the stronger the relationship is between Y and X. As with all the other measures of effect size interpretation is a matter of judgement. You are advised to see what other researchers report in relation to the particular outcome that you may be exploring.[This](http://blog.minitab.com/blog/adventures-in-statistics/regression-analysis-how-do-i-interpret-r-squared-and-assess-the-goodness-of-fit) is a reasonable explanation of how to interpret R-Squared.

Weisburd and Britt (2009: 437) suggest that in criminal justice you rarely see values for R^2 greater than .40. Thus, if your R^2 is larger than .40, you can assume you have a powerful model. When, on the other hand, R^2 is lower than .15 or .2 the model is likely to be viewed as relatively weak. Our observed r squared here is not too bad. There is considerably room for improvement if we want to develop a better model to explain violence [^2]. In any case, many people would argue that R^2 is a bit overrated. You need to be aware of what it measures and the context in which you are using it. Read [here](http://blog.minitab.com/blog/adventures-in-statistics/how-high-should-r-squared-be-in-regression-analysis) for some additional detail.

## Inference with regression

In real applications, we have access to a set of observations from which we can compute the least squares line, but the population regression line is unobserved. So our regression line is one of many that could be estimated. A different sample would produce a different regression line. The same sort of ideas that we introduced when discussing the estimation of sample means or proportions also apply here. *if we estimate b0 and b1 from a particular sample, then our estimates won't be exactly equal to b0 and b1 in the population*. But if we could average the estimates obtained over a very large number of data sets, the average of these estimates would equal the coefficients of the regression line in the population.

In the same way that we can compute the standard error when estimating the mean and explained in Week 5, we can compute standard errors for the regression coefficients to quantify our uncertainty about these estimates. These standard errors can in turn be used to produce confidence intervals. This would require us to assume that the residuals are normally distributed. As seen in the image, and for a simple regression model, you are assuming that the values of Y are approximately normally distributed for each level of X:

![normalityresiduals](http://reliawiki.org/images/2/28/Doe4.3.png)

In those circumstances we can trust the confidence intervals that we can draw around the regression line as in the image below:

![estimated](http://2.bp.blogspot.com/-5e1_FibUjg4/Uv5BItdZqmI/AAAAAAAAA00/o1EfWZ0fk-g/s1600/SimpleLinearRegressionJags-ICON-FREQ-EST.png "Image taken from John Krushcke blog http://doingbayesiandataanalysis.blogspot.co.uk/")

The dark-blue line marks the best fit. The two dark-pink lines mark the limits of the confidence interval. The light-pink lines show the sampling distributions around each of the confidence-interval limits (the many regression lines that would result from repeated sampling); notice that the best-fit line falls at the extreme of each sampling distribution.

You can also then perform standard hypothesis test on the coefficients. As we saw before when summarising the model, R will compute the standard errors and a **t test** for  each of the coefficients.


```r
summary(fit_1)$coefficients
```

```
##              Estimate Std. Error  t value     Pr(>|t|)
## (Intercept) 4.5781742 0.14898596 30.72890 7.474077e-89
## unemployed  0.2370975 0.02302022 10.29953 4.145166e-21
```

In our example, we can see that the coefficient for our predictor here is statistically significant.

We can also obtain confidence intervals for the estimated coefficients using the `confint()` function:


```r
confint(fit_1)
```

```
##                 2.5 %    97.5 %
## (Intercept) 4.2848120 4.8715365
## unemployed  0.1917693 0.2824257
```

[This blog post](http://www.sumsar.net/blog/2013/12/an-animation-of-the-construction-of-a-confidence-interval/) provides a nice animation of the confidence interval and hypothesis testing.

## Fitting regression with categorical predictors

So far we have explained regression using a numeric input. It turns out we can also use regression with categorical explanatory variables. It is quite straightforward to run it. 

We have one categorical variable in the dataset, *largest50*, identifying whether the city is one of the 50 largest in the country.


```r
table(df$largest50)
```

```
## 
##   0   1 
## 216  48
```

```r
class(df$largest50)
```

```
## [1] "numeric"
```

This variable is however stored in a numeric vector. We may want to change this to reflect the fact it is actually categorical.


```r
df$largest50 <- as.factor(df$largest50)
class(df$largest50)
```

```
## [1] "factor"
```

Let's rename the levels. In previous sessions we have illustrated how to do that with base R functions. Here we introduce a new package `forcats` that is worth considering when doing any work with factor variables. You can read more about it [here](https://forcats.tidyverse.org).


```r
library(forcats)
df$largest50 <- fct_recode(df$largest50, Yes = "1", No = "0")
table(df$largest50)
```

```
## 
##  No Yes 
## 216  48
```

We can explore if particularly large cities have higher rates of violence (remember a rate controls for population size, so if this were to be significant it would be telling us that it's not just because there is more people in them!). This is how you would express the model:


```r
fit_2 <- lm(log_viol_r ~ largest50, data=df)
```

Notice that there is nothing different in how we ask for the model. And see below the regression line:

![](08-regression_files/figure-latex/unnamed-chunk-24-1.pdf)<!-- --> 

Although in the plot we still see a line, what we are really estimating here is the average of *log_viol_r* for each of the two categories. 

Let's have a look at the results:


```r
summary(fit_2)
```

```
## 
## Call:
## lm(formula = log_viol_r ~ largest50, data = df)
## 
## Residuals:
##      Min       1Q   Median       3Q      Max 
## -2.11616 -0.48286  0.02965  0.51523  1.49789 
## 
## Coefficients:
##              Estimate Std. Error t value Pr(>|t|)    
## (Intercept)   5.94763    0.04771 124.661  < 2e-16 ***
## largest50Yes  0.62114    0.11189   5.551 6.94e-08 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 0.7012 on 262 degrees of freedom
## Multiple R-squared:  0.1052,	Adjusted R-squared:  0.1018 
## F-statistic: 30.82 on 1 and 262 DF,  p-value: 6.943e-08
```

As you will see the output does not look too different. But notice that in the print out you see how the row with the coefficient and other values for our input variable *largest50* we see that R is printing `largest50Yes`. What does this mean?

Remember week 6 and t tests? It turns out that a linear regression model with just one dichotomous categorical predictor is just the equivalent of a t test. When you only have one predictor the value of the intercept is the mean value of what we call the **reference category** and the coefficient for the slope tells you how much higher (if it is positive) or how much lower (if it is negative) is the mean value for the other category in your factor.

The reference category is the one for which R does not print the *level* next to the name of the variable for which it gives you the regression coefficient. Here we see that the named level is "Yes" (`largest50Yes`). That's telling you that the reference category here is "No". Therefore the Y intercept in this case is the mean value of violence for cities that are not the largest in the country, whereas the coefficient for the slope is telling you how much higher the mean value is for the largest cities in the country. Don't believe me?


```r
#Compute the mean for the smaller cities
mean(df$log_viol_r[df$largest50 == "No"], na.rm=TRUE)
```

```
## [1] 5.947628
```

```r
#Compute the difference between the two means
mean(df$log_viol_r[df$largest50 == "Yes"], na.rm=TRUE) - mean(df$log_viol_r[df$largest50 == "No"], na.rm=TRUE)
```

```
## [1] 0.6211428
```

So, to reiterate, for a single binary predictor, the coefficient is nothing else than the difference between the mean of the two levels in your factor variable, between the averages in your two groups.

With categorical variables encoded as **factors** you always have a situation like this: a reference category and then as many additional coefficients as there are additional levels in your categorical variable. Each of these additional categories is input into the model as **"dummy" variables**. Here our categorical variable has two levels, thus we have only one dummy variable. There will always be one fewer dummy variable than the number of levels. The level with no dummy variable, females in this example, is known as the **reference category** or the **baseline**.

It turns out then that the regression table is printing out for us a t test of statistical significance for every input in the model. If we look at the table above this t value is 5.55 and the p value associated with it is near 0. This is indeed considerably lower than the conventional significance level of 0.05. So we could conclude that the probability of obtaining this value if the null hypothesis is true is very low. However, the observed r squared is also kind of poor. Read [this](http://blog.minitab.com/blog/adventures-in-statistics/how-to-interpret-a-regression-model-with-low-r-squared-and-low-p-values) to understand a bit more this phenomenon of low p, but also low r-squared.

If rather than a binary explanatory variable, you had a factor with five levels. Then if you were to run a regression model this would result in a model with 4 dummy variables. The coefficient of each of these dummies would be telling you how much higher or lower (if the sign were negative) was the level of violence for each of the levels for which you have a dummy compared to your reference category or baseline. One thing that is important to keep in mind is that R by default will use as the baseline category the first level in your factor. 


```r
levels(df$largest50)
```

```
## [1] "No"  "Yes"
```

In our case you can see "No" is listed first. Keep in mind for your assignment that levels in factors are often alphabetically listed, not in a particularly meaningful or useful way.
If you want to change this you may need to reorder the levels. See [here](https://forcats.tidyverse.org/reference/fct_relevel.html) how to do this.

## Motivating multiple regression

So we have seen that our models with just one predictor are not terribly powerful. Partly that's due to the fact that they are not properly specified, they do not include a solid set of good predictor variables that can help us to explain variation in our response variable. We can build better models by expanding the number of predictors (although keep in mind you should also aim to build models as parsimonious as possible).

Another reason why it is important to think about additional variables in your model is to control for spurious correlations (although here you may also want to use your common sense when selecting your variables!). You must have heard before that correlation does not equal causation. Just because two things are associated we cannot assume that one is the cause for the other. Typically we see how the pilots switch the secure the belt button when there is turbulence. These two things are associated, they tend to come together. But the pilots are not causing the turbulences by pressing a switch! The world is full of **spurious correlations**, associations between two variables that should not be taking too seriously. You can explore a few [here](http://tylervigen.com/). It's funny. 

Looking only at covariation between pair of variables can be misleading. It may lead you to conclude that a relationship is more important than it really is. This is no trivial matter, but one of the most important ones we confront in research and policy[^5]. 

It's not an exaggeration to say that most quantitative explanatory research is about trying to control for the presence of **confounders**, variables that may explain explain away observed associations. Think about any criminology question: Does marriage reduces crime? Or is it that people that get married are different from those that don't (and are those pre-existing differences that are associated with less crime)? Do gangs lead to more crime? Or is it that young people that join gangs are more likely to be offenders to start with? Are the police being racist when they stop and search more members of ethnic minorities? Or is it that there are other factors (i.e., offending, area of residence, time spent in the street) that, once controlled, would mean there is no ethnic dis-proportionality in stop and searches? Does a particular program reduces crime? Or is the observed change due to something else?

These things also matter for policy. Wilson and Kelling, for example, argued that signs of incivility (or antisocial behaviour) in a community lead to more serious forms of crime later on as people withdraw to the safety of their homes when they see those signs of incivilities and this leads to a reduction in informal mechanisms of social control. All the policies to tackle antisocial behaviour in this country are very much informed by this model and were heavily influenced by broken windows theory.

But is the model right? Sampson and Raudenbush argue it is not entirely correct. They argue, and tried to show, that there are other confounding (poverty, collective efficacy) factors that explain the association of signs of incivility and more serious crime. In other words, the reason why you see antisocial behaviour in the same communities that you see crime is because other structural factors explain both of those outcomes. They also argue that perceptions of antisocial behaviour are not just produced by observed antisocial behaviour but also by stereotypes about social class and race. If you believe them, then the policy implications are that only tackling antisocial behaviour won't help you to reduce crime (as Wilson and Kelling have argued) . So as you can see this stuff matters for policy not just for theory. 

Multiple regression is one way of checking the relevance of competing explanations. You could set up a model where you try to predict crime levels with an indicator of broken windows and an indicator of structural disadvantage. If after controlling for structural disadvantage you see that the regression coefficient for broken windows is still significant you may be into something, particularly if the estimated effect is still large. If, on the other hand, the t test for the regression coefficient of your broken windows variable is no longer significant, then you may be tempted to think that perhaps Sampson and Raudenbush were into something. 

## Fitting and interpreting a multiple regression model

It could not be any easier to fit a multiple regression model. You simply modify the formula in the `lm()` function by adding terms for the additional inputs.


```r
fit_3 <- lm(log_viol_r ~ unemployed + largest50, data=df)
summary(fit_3)
```

```
## 
## Call:
## lm(formula = log_viol_r ~ unemployed + largest50, data = df)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -1.7338 -0.4047 -0.0189  0.4531  1.5726 
## 
## Coefficients:
##              Estimate Std. Error t value Pr(>|t|)    
## (Intercept)   4.54871    0.14101  32.258  < 2e-16 ***
## unemployed    0.22625    0.02186  10.351  < 2e-16 ***
## largest50Yes  0.53495    0.09476   5.645 4.29e-08 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 0.5915 on 261 degrees of freedom
## Multiple R-squared:  0.3657,	Adjusted R-squared:  0.3608 
## F-statistic: 75.23 on 2 and 261 DF,  p-value: < 2.2e-16
```

With more than one input, you need to ask yourself whether all of the regression coefficients are zero. This hypothesis is tested with a F test, similar to the one we described when describing ANOVA (in fact ANOVA is just a special case of regression). Again we are assuming the residuals are normally distributed, though with large samples the F statistics approximates the F distribution.

You see the F test printed at the bottom of the summary output and the associated p value, which in this case is way below the conventional .05 that we use to declare statistical significance and reject the null hypothesis. At least one of our inputs must be related to our response variable. 

Notice that the table printed also reports a t test for each of the predictors. These are testing whether each of these predictors is associated with the response variable when adjusting for the other variables in the model. They report the "partial effect of adding that variable to the model" (James et al. 2014: 77). In this case we can see that both variables seem to be significantly associated with the response variable.

If we look at the r squared we can now see that it is higher than before. This quantity, r squared, will always increase as a consequence of adding new variables, even if the new variables added are weakly related to the response variable. But the increase we are observing suggests that adding these two variables results in a substantially improvement to our previous model.

We see that the coefficients for the predictors change very little, it goes down a bit for *unemployed* and it goes down somehow more for *largest50*. **But their interpretation now changes**. A common interpretation is that now the regression for each variable tells you about changes in Y related to that variable **when the other variables in the model are held constant**. So, for example, you could say the coefficient for *unemployed* represents the increase in the log of the violence rate for every one-unit increase in the measure of unemployment *when holding all other variables in the model constant* (in this case that refers to holding constant *largest50*). But this terminology can be a bit misleading.

Other interpretations are also possible and are more generalizable. Gelman and Hill (2007: p. 34) emphasise what they call the *predictive interpretation* that considers how "the outcome variable differs, on average, when comparing two groups of units that differ by 1 in the relevant predictor while being identical in all the other predictors". So [if you're regressing y on u and v, the coefficient of u is the average difference in y per difference in u, comparing pairs of items that differ in u but are identical in v](http://andrewgelman.com/2013/01/05/understanding-regression-models-and-regression-coefficients/).

So, for example, in this case we could say that comparing respondents who have the same level of unemployment but who differed in whether they are one of the largest cities or not, the model predicts a expected difference of .53 in their violent crime measure. And that cities with the same size category, but that differ by one percent point in unemployment, we would expect to see a difference of 0.23 in their violent crime measure. So we are interpreting the regression slopes **as comparisons of observation that differ in one predictor while being at the same levels of the other predictors**.

As you can see, interpreting regression coefficients can be kind of tricky. The relationship between the response y and any one explanatory variable can change greatly depending on what other explanatory variables are present in the model. 

For example, if you contrast this model with the one we run with only *largest50* as a predictor you will notice the intercept has changed. You cannot longer read the intercept as the mean value of violence for smaller cities. *Adding predictors to the model changes their meaning*. Now the intercept index the value of violence for smaller cities *that, in addition, score 0 in unemployed*. In this case you don't have cases that meet this condition (equal zero in all your predictors). More often than not, then, there is not much value in bothering to interpret the intercept because if does not represent a real observation in your sample.

Something you need to be particularly careful about is to interpret the coefficients in a causal manner.  At least your data come from an experiment this is unlikely to be helpful. With observational data regression coefficients should not be read as indexing causal relations. This sort of textbook warning is, however, often neglectfully ignored by professional researchers. Often authors carefully draw sharp distinctions between causal and correlational claims when discussing their data analysis, but then interpret the correlational patterns in a totally causal way in their conclusion section. This is what is called the [causation](http://junkcharts.typepad.com/numbersruleyourworld/2012/07/the-causation-creep.html) or [causal](http://www.carlislerainey.com/2012/12/05/another-example-of-causal-creep/) creep. Beware. Don't do this tempting as it may be.

Comparing the simple models with this more complex model we could say that adjusting for *largest50* does not change much the impact of *unemployed* in violence and almost the same can be said about the effect of *largest50* when holding *unemployed* fixed. 

## Presenting your regression results.

Communicating your results in a clear manner is incredibly important. We have seen the tabular results produced by R. If you want to use them in a paper you may need to do some tidying up of those results. There are a number of packages (`textreg`, `stargazer`) that automatise that process. They take your `lm` objects and produce tables that you can put straight away in your reports or papers. One popular trend in presenting results is the **coefficient plot** as an alternative to the table of regression coefficients. There are various ways of producing coefficient plots with R for a variety of models. See [here](http://www.carlislerainey.com/2012/06/30/coefficient-plots-in-r/) and [here](http://www.carlislerainey.com/2012/07/03/an-improvement-to-coefficient-plots/), for example.

We are going to use instead the `plot_model()` function of the `sjPlot` package, that makes it easier to produce this sort of plots. You can find a more detailed tutorial about this function [here](http://rpubs.com/sjPlot/sjplm). See below for an example:


```r
library(sjPlot)
```

```
## Learn more about sjPlot with 'browseVignettes("sjPlot")'.
```

Let's try with a more complex example:


```r
fit_4 <- lm(log_viol_r ~ unemployed + largest50 + black + fborn + log_incarceraton, data=df)
plot_model(fit_4)
```

![](08-regression_files/figure-latex/unnamed-chunk-30-1.pdf)<!-- --> 

<!-- Be advised to use these plots judiciously. There may be other sort of plots that may be [more appropriate](http://www.carlislerainey.com/2012/07/06/why-i-dont-like-coefficient-plots/) for what you want to communicate to your audience than the coefficient plot.-->

You can further customise this:


```r
plot_model(fit_4, title="Violence across cities")
```

![](08-regression_files/figure-latex/unnamed-chunk-31-1.pdf)<!-- --> 

What you see plotted here is the point estimates (the circles), the confidence intervals around those estimates (the longer the line the less precise the estimate), and the colours represent whether the effect is negative (red) or positive (blue). There are other packages that also provide similar functionality, like the `dotwhisker` package that you may want to explore, see more details [here](https://cran.r-project.org/web/packages/dotwhisker/vignettes/dotwhisker-vignette.html).

The `sjPlot` package also allows you to produce html tables for more professional presentation of your regression tables. For this we use the `tab_model()` function. This kind of tabulation may be particularly helpful for your final assignment.


```r
tab_model(fit_4)
```

<table style="border-collapse:collapse; border:none;">
<tr>
<th style="border-top: double; text-align:center; font-style:normal; font-weight:bold; padding:0.2cm;  text-align:left; ">&nbsp;</th>
<th colspan="3" style="border-top: double; text-align:center; font-style:normal; font-weight:bold; padding:0.2cm; ">log viol r</th>
</tr>
<tr>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  text-align:left; ">Predictors</td>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  ">Estimates</td>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  ">CI</td>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  ">p</td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">(Intercept)</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">5.65</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">4.19&nbsp;&ndash;&nbsp;7.12</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">unemployed</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.17</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.12&nbsp;&ndash;&nbsp;0.22</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">largest50 [Yes]</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.46</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.29&nbsp;&ndash;&nbsp;0.63</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">black</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.02</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.01&nbsp;&ndash;&nbsp;0.02</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">fborn</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.01</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.02&nbsp;&ndash;&nbsp;-0.00</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">log incarceraton</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.13</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.36&nbsp;&ndash;&nbsp;0.10</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.251</td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; padding-top:0.1cm; padding-bottom:0.1cm; border-top:1px solid;">Observations</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; padding-top:0.1cm; padding-bottom:0.1cm; text-align:left; border-top:1px solid;" colspan="3">263</td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; padding-top:0.1cm; padding-bottom:0.1cm;">R<sup>2</sup> / R<sup>2</sup> adjusted</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; padding-top:0.1cm; padding-bottom:0.1cm; text-align:left;" colspan="3">0.508 / 0.499</td>
</tr>

</table>

As before you can further customise this table. Let's change for example the name that is displayed for the dependent variable.


```r
tab_model(fit_4, dv.labels = "Violence rate (log)")
```

<table style="border-collapse:collapse; border:none;">
<tr>
<th style="border-top: double; text-align:center; font-style:normal; font-weight:bold; padding:0.2cm;  text-align:left; ">&nbsp;</th>
<th colspan="3" style="border-top: double; text-align:center; font-style:normal; font-weight:bold; padding:0.2cm; ">Violence rate (log)</th>
</tr>
<tr>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  text-align:left; ">Predictors</td>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  ">Estimates</td>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  ">CI</td>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  ">p</td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">(Intercept)</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">5.65</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">4.19&nbsp;&ndash;&nbsp;7.12</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">unemployed</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.17</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.12&nbsp;&ndash;&nbsp;0.22</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">largest50 [Yes]</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.46</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.29&nbsp;&ndash;&nbsp;0.63</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">black</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.02</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.01&nbsp;&ndash;&nbsp;0.02</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">fborn</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.01</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.02&nbsp;&ndash;&nbsp;-0.00</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">log incarceraton</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.13</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.36&nbsp;&ndash;&nbsp;0.10</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.251</td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; padding-top:0.1cm; padding-bottom:0.1cm; border-top:1px solid;">Observations</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; padding-top:0.1cm; padding-bottom:0.1cm; text-align:left; border-top:1px solid;" colspan="3">263</td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; padding-top:0.1cm; padding-bottom:0.1cm;">R<sup>2</sup> / R<sup>2</sup> adjusted</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; padding-top:0.1cm; padding-bottom:0.1cm; text-align:left;" colspan="3">0.508 / 0.499</td>
</tr>

</table>

Or you could change the labels for the independent variables:


```r
tab_model(fit_4, pred.labels = c("(Intercept)", "Percent unemployment", "Largest cities (Yes)", "Percent black", "Percent foreign born", "Incarceration rate (log)"), dv.labels = "Violence rate (log)")
```

<table style="border-collapse:collapse; border:none;">
<tr>
<th style="border-top: double; text-align:center; font-style:normal; font-weight:bold; padding:0.2cm;  text-align:left; ">&nbsp;</th>
<th colspan="3" style="border-top: double; text-align:center; font-style:normal; font-weight:bold; padding:0.2cm; ">Violence rate (log)</th>
</tr>
<tr>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  text-align:left; ">Predictors</td>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  ">Estimates</td>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  ">CI</td>
<td style=" text-align:center; border-bottom:1px solid; font-style:italic; font-weight:normal;  ">p</td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">(Intercept)</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">5.65</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">4.19&nbsp;&ndash;&nbsp;7.12</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">Percent unemployment</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.17</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.12&nbsp;&ndash;&nbsp;0.22</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">Largest cities (Yes)</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.46</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.29&nbsp;&ndash;&nbsp;0.63</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">Percent black</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.02</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.01&nbsp;&ndash;&nbsp;0.02</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>&lt;0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">Percent foreign born</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.01</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.02&nbsp;&ndash;&nbsp;-0.00</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  "><strong>0.001</strong></td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; ">Incarceration rate (log)</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.13</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">&#45;0.36&nbsp;&ndash;&nbsp;0.10</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:center;  ">0.251</td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; padding-top:0.1cm; padding-bottom:0.1cm; border-top:1px solid;">Observations</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; padding-top:0.1cm; padding-bottom:0.1cm; text-align:left; border-top:1px solid;" colspan="3">263</td>
</tr>
<tr>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; text-align:left; padding-top:0.1cm; padding-bottom:0.1cm;">R<sup>2</sup> / R<sup>2</sup> adjusted</td>
<td style=" padding:0.2cm; text-align:left; vertical-align:top; padding-top:0.1cm; padding-bottom:0.1cm; text-align:left;" colspan="3">0.508 / 0.499</td>
</tr>

</table>

Visual display of the effects of the variables in the model are particularly helpful. The `effects` package allows us to produce plots to visualise these relationships (when adjusting for the other variables in the model). Here's an example going back to our model fit_3 which contained unemployment and the dummy for large cities as predictor variables:


```r
library(effects)
```

```
## Loading required package: carData
```

```
## lattice theme set by effectsTheme()
## See ?effectsTheme for details.
```

```r
plot(allEffects(fit_3), ask=FALSE)
```

![](08-regression_files/figure-latex/unnamed-chunk-35-1.pdf)<!-- --> 

Notice that the line has a confidence interval drawn around it (to reflect the likely impact of sampling variation) and that the predicted means for smaller and largest cities (when controlling for unemployment) also have a confidence interval.

##Rescaling input variables to assist interpretation

The interpretation or regression coefficients is sensitive to the scale of measurement of the predictors. This means one cannot compare the magnitude of the coefficients to compare the relevance of variables to predict the response variable. Let's look at the more recent model, how can we tell what predictors have a stronger effect?


```r
summary(fit_4)
```

```
## 
## Call:
## lm(formula = log_viol_r ~ unemployed + largest50 + black + fborn + 
##     log_incarceraton, data = df)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -1.4546 -0.3523 -0.0009  0.3827  1.5771 
## 
## Coefficients:
##                   Estimate Std. Error t value Pr(>|t|)    
## (Intercept)       5.654459   0.743725   7.603 5.44e-13 ***
## unemployed        0.169895   0.024496   6.936 3.27e-11 ***
## largest50Yes      0.457226   0.085311   5.360 1.86e-07 ***
## black             0.015003   0.002678   5.602 5.44e-08 ***
## fborn            -0.010414   0.003101  -3.358 0.000904 ***
## log_incarceraton -0.133946   0.116461  -1.150 0.251158    
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 0.523 on 257 degrees of freedom
##   (1 observation deleted due to missingness)
## Multiple R-squared:  0.5082,	Adjusted R-squared:  0.4987 
## F-statistic: 53.12 on 5 and 257 DF,  p-value: < 2.2e-16
```

We just cannot. One way of dealing with this is by rescaling the input variables. A common method involves subtracting the mean and dividing by the standard deviation of each numerical input. The coefficients in these models is the expected difference in the response variable, comparing units that differ by one standard deviation in the predictor while adjusting for other predictors in the model. 

Instead, [Gelman (2008)](http://www.stat.columbia.edu/~gelman/research/published/standardizing7.pdf) has proposed dividing each numeric variables *by two times its standard deviation*, so that the generic comparison is with inputs equal to plus/minus one standard deviation. As Gelman explains the resulting coefficients are then comparable to untransformed binary predictors. The implementation of this approach in the `arm` package subtract the mean of each binary input while it subtract the mean and divide by two standard deviations for every numeric input.

The way we would obtain these rescaled inputs uses the `standardize()` function of the `arm` package, that takes as an argument the name of the stored fit model.


```r
library(arm)
standardize(fit_4)
```

```
## 
## Call:
## lm(formula = log_viol_r ~ z.unemployed + c.largest50 + z.black + 
##     z.fborn + z.log_incarceraton, data = df)
## 
## Coefficients:
##        (Intercept)        z.unemployed         c.largest50             z.black  
##            6.06080             0.56923             0.45723             0.49188  
##            z.fborn  z.log_incarceraton  
##           -0.24890            -0.08133
```

Notice the main change affects the numerical predictors. The unstandardised coefficients are influenced by the degree of variability in your predictors, which means that typically they will be larger for your binary inputs. With unstandardised coefficients you are comparing complete change in one variable (whether one is a large city or not) with one-unit changes in your numerical variable, which may not amount to much change. So, by putting in a comparable scale, you avoid this problem.

Standardising in the way described here will help you to make fairer comparisons. This standardised coefficients are comparable in a way that the unstandardised coefficients are not. We can now see what inputs have a comparatively stronger effect. It is very important to realise, though, that one **should not** compare standardised coefficients *across different models*.

## Testing conditional hypothesis: interactions

In the social sciences there is a great interest in what are called conditional hypothesis or interactions. Many of our theories do not assume simply **additive effects** but **multiplicative effects**.For example, [Wikstrom and his colleagues (2011)](http://euc.sagepub.com/content/8/5/401.short) suggest that the threat of punishment only affects the probability of involvement on crime for those that have a propensity to offend but are largely irrelevant for people who do not have this propensity. Or you may think that a particular crime prevention programme may work in some environments but not in others. The interest in this kind of conditional hypothesis is growing.

One of the assumptions of the regression model is that the relationship between the response variable and your predictors is additive. That is, if you have two predictors `x1` and `x2`. Regression assumes that the effect of `x1` on `y` is the same at all levels of `x2`. If that is not the case, you are then violating one of the assumptions of regression. This is in fact one of the most important assumptions of regression, even if researchers often overlook it.

One way of extending our model to accommodate for interaction effects is to add additional terms to our model, a third predictor `x3`, where `x3` is simply the product of multiplying `x1` by `x2`. Notice we keep a term for each of the **main effects** (the original predictors) as well as a new term for the interaction effect. "Analysts should include all constitutive terms when specifying multiplicative interaction models except in very rare circumstances" (Brambor et al., 2006: 66).

How do we do this in R? One way is to use the following notation in the formula argument. Notice how we have added a third term `unemployed:largest50`, which is asking R to test the conditional hypothesis that the perceptions of antisocial behaviour may have a different impact on fear of violent crime for men and women.


```r
fit_5 <- lm(log_viol_r ~ unemployed + largest50 + unemployed:largest50 , data=df)
# which is equivalent to: 
# fit_5 <- lm(log_viol_r ~ unemployed * largest50, data=BCS0708)
summary(fit_5)
```

```
## 
## Call:
## lm(formula = log_viol_r ~ unemployed + largest50 + unemployed:largest50, 
##     data = df)
## 
## Residuals:
##      Min       1Q   Median       3Q      Max 
## -1.71844 -0.41330 -0.02989  0.45583  1.59625 
## 
## Coefficients:
##                         Estimate Std. Error t value Pr(>|t|)    
## (Intercept)              4.49267    0.15636  28.734   <2e-16 ***
## unemployed               0.23532    0.02443   9.630   <2e-16 ***
## largest50Yes             0.83064    0.36794   2.258   0.0248 *  
## unemployed:largest50Yes -0.04557    0.05479  -0.832   0.4063    
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 0.5919 on 260 degrees of freedom
## Multiple R-squared:  0.3673,	Adjusted R-squared:   0.36 
## F-statistic: 50.32 on 3 and 260 DF,  p-value: < 2.2e-16
```

You see here that essentially you have only two inputs (perceptions of the area and sex) but several regression coefficients. Gelman and Hill (2007) suggest reserving the term input for the variables encoding the information and to use the term predictor to refer to each of the terms in the model. So here we have two inputs and four predictors (one for the constant term, one for unemployment, another for the largest 50 dummy, and a final one for the interaction effect).

In this case the test for the interaction effect is non-significant, which suggests there isn't such an interaction. The R squared barely changes. Let's visualise the results with the `effects` package:


```r
plot(allEffects(fit_5), ask=FALSE)
```

![](08-regression_files/figure-latex/unnamed-chunk-39-1.pdf)<!-- --> 

Notice that essentially what we are doing is running two regression lines and testing whether the slope is different for the two groups. The intercept is different, we know that largest cities are more violent, but what we are testing here is whether violence goes up in a steeper fashion (and in the same direction) for one or the other group as unemployment goes up. We see that's not the case here. The estimated lines are almost parallel.

A word of warning, the moment you introduce an interaction effect the meaning of the coefficients for the other predictors changes (what it is often referred as to the "main effects" as opposed to the interaction effect). You cannot retain the interpretation we introduced earlier. Now, for example, the coefficient for the *largest50* variable relates the marginal effect of this variable when *unemployment* equals zero. The typical table of results helps you to understand whether the effects are significant but offers little of interest that will help you to meaningfully interpret what the effects are. For this is better you use some of the graphical displays we have covered.

Essentially what happens is that the regression coefficients that get printed are interpretable only for certain groups. So now:

+ The intercept still represents the predicted score of violence for the smaller cities and have a score of 0 in unemployment (as before).

+ The coefficient of the *largest50Yes* predictor now can be thought of as the difference between the predicted score of violence for small cities *that have a score of 0 in unemployment* and largest cities *that have a score of 0 in unemployment*.

+ The coefficient of *unemployed* now becomes the comparison of mean violence *for small cities* who differ by one point in unemployment.

+ The coefficient for the interaction term represents the difference in the slope for *unemployed* comparing smaller and largest cities, the difference in the slope of the two lines that we visualised above.

Models with interaction terms are too often misinterpreted. I strongly recommend you read this piece by [Brambor et al (2005)](https://files.nyu.edu/mrg217/public/pa_final.pdf) to understand some of the issues involved. When discussing logistic regression we will return to this and will consider tricks to ease the interpretation.

Equally, [John Fox (2003)](http://www.jstatsoft.org/v08/i15/paper) piece on the `effects` package goes to much more detail that we can here to explain the logic and some of the options that are available when producing plots to show interactions with this package. You may also want to have a look at the newer `interactions` package [here](https://interactions.jacob-long.com/index.html).

## Model building and variable selection

How do you construct a good model? This partly depends on your goal, although there are commonalities. You do want to start with theory as a way to select your predictors and when specifying the nature of the relationship to your response variable (e.g., additive, multiplicative). Gelman and Hill (2007) provide a series of general principles. I would like to emphasise at this stage two of them:

+ Include all input variables that, for substantive reasons, might be expected to be important in predicting the outcome.

+ For inputs with large effects, consider including their interactions as well.

It is often the case that for any model, the response variable is only related to a subset of the predictors. There are some scenarios where you may be interested in understanding what is the best subset of predictors. Imagine that you want to develop a risk assessment tool to be used by police officers that respond to a domestic violence incident, so that you could use this tool for forecasting the future risk of violence. There is a cost to adding too many predictors. A police officer time should not be wasted gathering information on predictors that are not associated with future risk. So you may want to identify the predictors that will help in this process.

Ideally, we would like to perform variable selection by trying out a lot of different models, each containing a different subset of the predictors. There are various statistics that help in making comparisons across models. Unfortunately, as the number of potentially relevant predictors increases the number of potential models to compare increases exponentially. So you need methods that help you in this process. There are a number of tools that you can use for **variable selection** but this goes beyond the aims of this introduction. If you are interested you may want to read [this](http://link.springer.com/chapter/10.1007/978-1-4614-7138-7_6).

<!--chapter:end:08-regression.Rmd-->

# Logistic regression

## Introduction

In previous sessions we covered the linear regression model, that you can use when you are modeling variation in a numerical response variable. In this session we are going to introduce logistic regression, which is a technique you may use when your outcome or response (or dependent) variable is categorical and has two possible levels.

In criminology, very often you will be interested in binary outcomes (e.g., victim/no victim, arrested/not arrested, etc.) and want to use a number of predictor variables to study these outcomes. It is then, helpful, to understand how to use these models. Logistic regression is part of a broader family of models called **generalised linear models**. You should read the Wikepedia entry for this concept [here](https://en.wikipedia.org/wiki/Generalized_linear_model).

With logistic regression we are modelling the probability of belonging to one of the levels in the binary outcome. For any combination of values for our predictor variables the model will estimate a probability of presenting the outcome of interest. To fit this model we use maximum likelihood. This handout does not focuses in explaining the mathematics behind the method. Those are important but in this introductory module we only provide an introduction to the technique.

To illustrate logistic regression we are going to use the `Arrests` data from the `effects` package. You can obtain details about this dataset and the variables included by using `help(Arrests, package="effects")`. If you don't have that package you will need to install it and load it.


```r
library(effects)
```

```
## Loading required package: carData
```

```
## lattice theme set by effectsTheme()
## See ?effectsTheme for details.
```

```r
data(Arrests, package="effects")
```

```
## Warning in data(Arrests, package = "effects"): data set 'Arrests' not found
```

This data includes information on police treatment of individuals arrested in Toronto for possession of marihuana. We are going to model variation on `released`, a factor with two levels indicating whether the arrestee was released with a summons.  In this case the police could:

+ Release the arrestee with a summons - like a parking ticket 

+ Bring to police station, hold for bail, etc. - harsher treatment 


```r
table(Arrests$released)
```

```
## 
##   No  Yes 
##  892 4334
```

We can see that for possession of marijuana most arrestees are released with a summons. Let's see if we can develop some understanding of the factors that affect this outcome, in particular let's assume our research goal is to investigate whether race is associated with a harsher treatment. For this we may run a logistic regression model.

## Fitting logistic regression

It is fairly straightforward to run a logistic model. Before you fit it, though, is convenient to check what you are actually modelling. Remember that R orders the levels in a factor alphabetically (unless they have been reordered by the authors of the dataframe). What that means is that when you run logistic regression you will be predicting probabilities associated with the category with a higher alphabetical order.


```r
levels(Arrests$released) #Prints the levels, and you can see that "Yes" comes after "No" in alphabetical order
```

```
## [1] "No"  "Yes"
```

```r
contrasts(Arrests$released) #This function shows you the contrasts associated with a factor. You can see the 1 is associated with "Yes". This is what our model will be predicting, the probability of a "Yes".
```

```
##     Yes
## No    0
## Yes   1
```

If by any chance, the level of interest is not the one that will be selected by R, we will need to reorder the factor levels. In this particular analysis our goal is to check whether being Black predicts harsher treatment. So, let's reorder the factor in such a way that the model is oriented towards predicting this harsher treatment. This will simply chage the sign of the coefficients and, in that way, may enhance interpretation.


```r
#Reverse the order
Arrests$harsher <- relevel(Arrests$released, "Yes")
#Rename the levels so that it is clear we now mean yes to harsher treatment
levels(Arrests$harsher) <- c("No","Yes")
#Check that it matches in reverse the original variable
table(Arrests$harsher)
```

```
## 
##   No  Yes 
## 4334  892
```

```r
#We will also reverse the order of the "colour"" variable so that the dummy uses Whites as the baseline
Arrests$colour <- relevel(Arrests$colour, "White")
```

We use the `glm()` function for fitting the model, specifying as an argument that we will be using a logit model (`family="binomial"`). As stated, we are going to run a model oriented primarily to assess to what degree race/ethnicity seems to matter even when we adjust for other factors (e.g., sex, employment, and previous police contacts (checks: number of police data records of previous arrests, previous convictions, parole status, etc. - 6 in all) on which the arrestee's name appeared; a numeric vector)).


```r
fitl_1 <- glm(harsher ~ checks + colour + sex + employed, data=Arrests, family = "binomial")
summary(fitl_1)
```

```
## 
## Call:
## glm(formula = harsher ~ checks + colour + sex + employed, family = "binomial", 
##     data = Arrests)
## 
## Deviance Residuals: 
##     Min       1Q   Median       3Q      Max  
## -1.5226  -0.6156  -0.4407  -0.3711   2.3449  
## 
## Coefficients:
##             Estimate Std. Error z value Pr(>|z|)    
## (Intercept) -1.90346    0.15999 -11.898  < 2e-16 ***
## checks       0.35796    0.02580  13.875  < 2e-16 ***
## colourBlack  0.49608    0.08264   6.003 1.94e-09 ***
## sexMale      0.04215    0.14965   0.282    0.778    
## employedYes -0.77973    0.08386  -9.298  < 2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## (Dispersion parameter for binomial family taken to be 1)
## 
##     Null deviance: 4776.3  on 5225  degrees of freedom
## Residual deviance: 4330.7  on 5221  degrees of freedom
## AIC: 4340.7
## 
## Number of Fisher Scoring iterations: 5
```

The table, as you will see, is similar to the one you get when running linear regression, but there are some differences we will discuss.

The first thing you see in the output printed in the console is the model we run. Then we see something called **the deviance residuals**, which are a measure of model fit. This part of output shows the distribution of the deviance residuals for individual cases used in the model. Later we discuss how to use summaries of the deviance statistic to assess model fit. 

At the very bottom, below the table of coefficients, are fit indices (including the null and deviance residuals and the Akaike information criterion (AIC)). We discuss this later. 

The part in the middle of the output shows the coefficients, their standard errors, the statistic, and the associated p-values. The z statistic (sometimes called a Wald z-statistic) does a job similar to the t test in the linear regression model. It is a test of statistical significance assessing whether each input in the model is associated with the dependent variable.

If we focus in the table of coefficients, we can see that all the inputs but *sex* were significant in the model. The estimates that get printed when you run logistic regression give you the change in the log odds of the outcome for a one unit increase in the predictor. Here we see that for every one unit increase in the number of previous police contacts (*checks*), the **log odds** of receiving harsher treatment (versus being released) increases by 0.36 adjusting for the other variables in the model. The reminder variables are categorical predictors with two levels. So what we see is the coefficient for the dummy variables indicating the contrast with their respective baseline or reference category. So, for example, being Black increases the log odds of receiving harsher treatment by 0.49, whereas being employed decreases the log odds of being released by 0.77. As mentioned above, the coefficient for gender was not significant. What are log odds? We will discuss this in a bit.

We can also use the `confint()` function to obtain confidence intervals for the estimated coefficients.


```r
confint(fitl_1)
```

```
## Waiting for profiling to be done...
```

```
##                  2.5 %     97.5 %
## (Intercept) -2.2241433 -1.5962775
## checks       0.3075891  0.4087441
## colourBlack  0.3334415  0.6574559
## sexMale     -0.2445467  0.3429244
## employedYes -0.9436356 -0.6148518
```

So what does that actually mean?

Interpreting in the log odds scale is something some people do not find very intuitive. So it is common to use **odd ratios** when interpreting logistic regression. We have already covered odd ratios when discussing cross tabulations. To do this, all we need to do is to exponentiate the coefficients. To get the exponentiated coefficients, you tell R that you want to exponentiate (`exp()`), that the object you want to exponentiate is called coefficients and it is part of the model you just run.


```r
exp(coef(fitl_1))
```

```
## (Intercept)      checks colourBlack     sexMale employedYes 
##   0.1490516   1.4304108   1.6422658   1.0430528   0.4585312
```

You can use the same logic to the confindence intervals.


```r
exp(cbind(OR = coef(fitl_1), confint(fitl_1))) #This will print both the OR and their 95% CI.
```

```
## Waiting for profiling to be done...
```

```
##                    OR     2.5 %    97.5 %
## (Intercept) 0.1490516 0.1081600 0.2026495
## checks      1.4304108 1.3601419 1.5049266
## colourBlack 1.6422658 1.3957633 1.9298763
## sexMale     1.0430528 0.7830594 1.4090622
## employedYes 0.4585312 0.3892103 0.5407210
```

Now we can use the interpretation of odd ratios we introduced in a previous session. When the odd ratio is greater than 1 indicates that the odds of receiving harsher treatment increases when the independent variable increases. We can say, for example, that previous police contacts increases the odds of harsher treatment by 43% whereas being black increases the odds of harsher treatment by 64% (while adjusting for the other variables in the model). 

Employment has an odd ratio of 0.45. When the odd ratio is between 0 and 1 is indicating a negative relationship. So employment reduces the odds of harsher treatment by 1/0.46, that is by a factor of 2.18. For more details interpreting odd ratios in logistic regression you may want to read [this](http://www.ats.ucla.edu/stat/mult_pkg/faq/general/odds_ratio.htm). Some people do not like odd ratios. For other ways of interpreting logistic regression coefficients you may want to consult [chapter 5 of the book](http://www.cambridge.org/gb/academic/subjects/statistics-probability/statistical-theory-and-methods/data-analysis-using-regression-and-multilevelhierarchical-models?format=PB) by Gelman and Hill (2007).

You can read more about how to read odd ratios in logistic regression [here](https://stats.idre.ucla.edu/other/mult-pkg/faq/general/faq-how-do-i-interpret-odds-ratios-in-logistic-regression/).

Another way of getting the results with less typing is to use the `Logit()` function in the `lessR` package (you will need to install it if you do not have it).


```r
library(lessR, quietly= TRUE)
```

```
## 
## lessR 4.2.3                         feedback: gerbing@pdx.edu 
## --------------------------------------------------------------
## > d <- Read("")   Read text, Excel, SPSS, SAS, or R data file
##   d is default data frame, data= in analysis routines optional
## 
## Learn about reading, writing, and manipulating data, graphics,
## testing means and proportions, regression, factor analysis,
## customization, and descriptive statistics from pivot tables.
##   Enter:  browseVignettes("lessR")
## 
## View changes in this and recent versions of lessR.
##   Enter: news(package="lessR")
## 
## **New Feature**: Interactive analysis of your data
##   Enter: interact()
```

```r
Logit(harsher ~ checks + colour + sex + employed, data=Arrests, brief=TRUE)
```

```
## 
## Response Variable:   harsher
## Predictor Variable 1:  checks
## Predictor Variable 2:  colour
## Predictor Variable 3:  sex
## Predictor Variable 4:  employed
## 
## Number of cases (rows) of data:  5226 
## Number of cases retained for analysis:  5226 
## 
## 
##    BASIC ANALYSIS 
## 
## Estimated Model for the Logit of Reference Group Membership
## 
##              Estimate    Std Err  z-value  p-value   Lower 95%   Upper 95%
## (Intercept)   -1.9035     0.1600  -11.898    0.000     -2.2170     -1.5899 
##      checks    0.3580     0.0258   13.875    0.000      0.3074      0.4085 
## colourBlack    0.4961     0.0826    6.003    0.000      0.3341      0.6580 
##     sexMale    0.0422     0.1496    0.282    0.778     -0.2511      0.3355 
## employedYes   -0.7797     0.0839   -9.298    0.000     -0.9441     -0.6154 
## 
## 
## Odds Ratios and Confidence Intervals
## 
##              Odds Ratio   Lower 95%   Upper 95%
## (Intercept)      0.1491      0.1089      0.2039 
##      checks      1.4304      1.3599      1.5046 
## colourBlack      1.6423      1.3967      1.9310 
##     sexMale      1.0431      0.7779      1.3986 
## employedYes      0.4585      0.3890      0.5404 
## 
## 
## Model Fit
## 
##     Null deviance: 4776.258 on 5225 degrees of freedom
## Residual deviance: 4330.699 on 5221 degrees of freedom
## 
## AIC: 4340.699 
## 
## Number of iterations to convergence: 5 
## 
## 
## >>> Note:  colour is not a numeric variable.
## 
## >>> Note:  sex is not a numeric variable.
## 
## >>> Note:  employed is not a numeric variable.
## 
## Collinearity
## 
## 
## >>> No collinearity analysis
##  Not all variables are numeric.
```

As with linear regression, the interpretation of regression coefficients is sensitive to the scale of measurement of the predictors. This means one cannot compare the magnitude of the coefficients to compare the relevance of variables to predict the response variable. The same applies to the odd ratios. Tempting and common as this might be, unless the predictors use the same metric (or maybe if they are all categorical) there is little point in comparing the magnitude of the odd ratios in logistic regression. Like the unstardised logistic regression coefficients odd ratios are **not** a measure of effect size that allows comparisons across inputs (Menard, 2012). 

Finally, you could, in the same way than we did in a previous session, use the `standardize()` function from the `arm` package.


```r
library(arm)
```

```
## Loading required package: MASS
```

```
## Loading required package: Matrix
```

```
## Loading required package: lme4
```

```
## 
## arm (Version 1.13-1, built: 2022-8-25)
```

```
## Working directory is /Users/EonKim/Desktop/Rbooks/mcd_book
```

```
## 
## Attaching package: 'arm'
```

```
## The following object is masked from 'package:lessR':
## 
##     rescale
```

```r
fitl_1_s <- standardize(fitl_1)
display(fitl_1_s)
```

```
## glm(formula = harsher ~ z.checks + c.colour + c.sex + c.employed, 
##     family = "binomial", data = Arrests)
##             coef.est coef.se
## (Intercept) -1.77     0.04  
## z.checks     1.10     0.08  
## c.colour     0.50     0.08  
## c.sex        0.04     0.15  
## c.employed  -0.78     0.08  
## ---
##   n = 5226, k = 5
##   residual deviance = 4330.7, null deviance = 4776.3 (difference = 445.6)
```

We can also use **forest plots** in much the same way than we did for linear regression. One way of doing this is using the `plot.model()` function of the `sjPlot` package. Notice that by default the odd ratios are sorted from higher to lower in this display (and also that in this html file the text in the plot is not fully displayed, I'm still trying to fix that, but if you run this and zoom in you will see it better).


```r
library(sjPlot)
plot_model(fitl_1)
```

![](09-logistic_files/figure-latex/unnamed-chunk-11-1.pdf)<!-- --> 

Equally, we can produce effect plots using the `effects` package:


```r
library(effects)
plot(allEffects(fitl_1), ask=FALSE)
```

![](09-logistic_files/figure-latex/unnamed-chunk-12-1.pdf)<!-- --> 

Effect plots in this context are particularly helpful because they summarise the results using probabilities, which is what you see plotted in the y axis.

We don't have to print them all. When we are primarily concerned with one of them, as in this case, that's the one we want to emphasise when presenting and discussing our results. There isn't much point discussing the results for the variables we simply defined as control (given what our research goal was). So in this case we would ask for the plot for our input measuring race/ethnicity:


```r
plot(effect("colour", fitl_1), multiline = FALSE, ylab = "Probability(harsher)")
```

![](09-logistic_files/figure-latex/unnamed-chunk-13-1.pdf)<!-- --> 

We can use the `predict()` function to generate the predicted probability that the arrestess will be released given what we know about their inputs in the model, given values of the predictors. By default R will compute the probabilities for the dataset we fitted the model to. Here we have printed only the first ten probabilities, but the way we use the `predict()` function here will generate a predicted probability for each case in the dataset.


```r
fitl_1_prob <- predict(fitl_1, type = "response") #If you want to add this to your dataframe you could designate your object as Arrests$fitl_1_prob
fitl_1_prob[1:10]
```

```
##          1          2          3          4          5          6          7 
## 0.17262268 0.25519856 0.17262268 0.14344103 0.13833944 0.10091376 0.13455033 
##          8          9         10 
## 0.08905504 0.32891111 0.17262268
```

It is important to understand that with this type of models we usually generate two types of predictions. One the one hand, we are producing a continuous valued prediction in the form of a probability but we can also generate a predicted class for each case. In many applied settings, the latter will be relevant. A discrete category prediction may be required in order to make a decision. Imagine of a probation officer evaluating the future risk of a client. She/He would want to know whether the case is high risk or not.

## Assessing model fit I: deviance and pseudo r squared

As you may remember when looking at linear models we could use an F test to check the overall fit of the model and we could evaluate R squared. When running logistic regression we cannot obtain the R squared (although there is a collection of pseudo-R^2 measures that have been produced). In linear regression things are a bit simpler. As Menard (2010: 43) explains:

> "there is only one reasonable residual variation criterion for quantitative variables in OLS, the familiar error sum of squares... but there are several possible residual variation criteria (entropy, squared error, qualitative difference) for binary variables. Another hindrance is the existence of numerous mathematical equivalents to R^2 in OLS, which are not necessarily mathematically (same formula) or conceptually (same meaning in the context of the model) equivalent to R^2 in logistic regression... Moreover, in logistic regression, we must choose whether we are more interested in qualitative prediction (whether predicitons are correct or incorrect), quantitative prediction (how close predictions are to being correct), or both, because different measures of explained variation are appropriate for these two different types of prediction"

A common starting point for assessing model fit is to look at the **log-likelihood statistic** and the **deviance** (also referred to as -2LL). 

The log likelihood aims to provide a measure of how much unexplained variation there is after you fit the mode. Large values indicate poor fit. 

The deviance, on the other hand, is simply the log likelihood multiplied by -2 and is generally abbraviated as -2LL. The deviance will be a positive value and *larger values indicate worse prediction* of the response variable. It is analogous to the error sum of squares in linear regression. In the same way that OLS linear regression tries to minimise the error sum of squares, maximim likelihood logistic regression tries to minimise the -2LL.

The difference between the -2LL for the model with no predictors and the -2LL for the model with all the predictors is the closer we get in logistic regression to the regression sum of squares. This difference is often called **model chi squared**. And it provides a test of the null hypothesis that all the regression coefficients equal zero. It is, thus, equivalent to the F test in OLS regression.


```
## 
## Call:
## glm(formula = harsher ~ checks + colour + sex + employed, family = "binomial", 
##     data = Arrests)
## 
## Deviance Residuals: 
##     Min       1Q   Median       3Q      Max  
## -1.5226  -0.6156  -0.4407  -0.3711   2.3449  
## 
## Coefficients:
##             Estimate Std. Error z value             Pr(>|z|)    
## (Intercept) -1.90346    0.15999 -11.898 < 0.0000000000000002 ***
## checks       0.35796    0.02580  13.875 < 0.0000000000000002 ***
## colourBlack  0.49608    0.08264   6.003        0.00000000194 ***
## sexMale      0.04215    0.14965   0.282                0.778    
## employedYes -0.77973    0.08386  -9.298 < 0.0000000000000002 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## (Dispersion parameter for binomial family taken to be 1)
## 
##     Null deviance: 4776.3  on 5225  degrees of freedom
## Residual deviance: 4330.7  on 5221  degrees of freedom
## AIC: 4340.7
## 
## Number of Fisher Scoring iterations: 5
```

In our example, we saw that some measures of fit were printed below the table with the coefficients. The **null deviance** is the deviance of the model with no predictors and the **residual deviance** is simply the deviance for this model. You clearly want the residual deviance to be smaller than the null deviance. The difference between the null and the residual deviance is what we called the model chi squared. In this case this is 4776.3 minus 4330.7. We can ask R to do this for us.

First, notice that the object we created has all the information we need already stored.


```r
names(fitl_1)
```

```
##  [1] "coefficients"      "residuals"         "fitted.values"    
##  [4] "effects"           "R"                 "rank"             
##  [7] "qr"                "family"            "linear.predictors"
## [10] "deviance"          "aic"               "null.deviance"    
## [13] "iter"              "weights"           "prior.weights"    
## [16] "df.residual"       "df.null"           "y"                
## [19] "converged"         "boundary"          "model"            
## [22] "call"              "formula"           "terms"            
## [25] "data"              "offset"            "control"          
## [28] "method"            "contrasts"         "xlevels"
```

So we can use this stored information in our calculations.


```r
with(fitl_1, null.deviance - deviance)
```

```
## [1] 445.5594
```

Is 445.6 small? How much smaller is enough? This value has a chi square distribution and its significance can be easily computed. For this computation we need to know the degrees of freedom for the model (which equal the number of predictors in the model) and can be obtained like this:


```r
with(fitl_1, df.null - df.residual)
```

```
## [1] 4
```

Finally, the p-value can be obtained using the following code to invoke the Chi Square distribution:


```r
#When doing it yourself, this is all you really need (we present the code in separate fashion above to that you understand better what the one here does)
with(fitl_1, pchisq(null.deviance - deviance, df.null - df.residual, lower.tail = FALSE))
```

```
## [1] 3.961177e-95
```

We can see that the model chi square is highly significant. Our model as a whole fits significantly better than a model with no predictors.

Menard (2010) recommends to also look at the likelihood ratio R^2 that can be calculated as the difference between the null deviance and the residual deviance, divided by the null deviance.


```r
#Likelihood ratio R2
with(fitl_1, (null.deviance - deviance)/null.deviance)
```

```
## [1] 0.09328629
```

Some authors refer to this as the Hosmer/Lemeshow R^2. It indicates how much the inclusion of the independent variables in the model reduces variation, as measured by the null deviance. It varies between 0 (when our prediction is catastrophically useless) and 1 (when we predict with total accuracy). There are many other pseudo R^2 measures that have been proposed, but Menard [based on research](http://www.tandfonline.com/doi/pdf/10.1080/00031305.2000.10474502) on the properties of various of these measures recommends the likelihood ratio R^2 because:

+ It is the one with a closer conceptual link to R^2 in OLS regression.

+ It does not appear to be sensitive to the base rate (the proportion of cases that have the attribute of interest) of the phenomenon being studied and therefore will work even in cases with unbalanced probabilities.

+ It varies between 0 and 1

+ And it can be used in other generalised linear models (models for categorical outcomes with more than two levels, which we don't cover here)

## Assessing model fit II: confusion matrix and ROC curves

If we are interested in "qualitative" prediction, we also need to consider other measures of fit. In many applied settings, such as in applied predictive modelling, this can be the case. Imagine you are developing a tool to be used to forecast the probability of a repeat victimisation in cases of domestic violence. This type of prediction may then be used to determine the type of police response to cases defined as high risk. Clearly, you want to make sure the classification you make is accurate as possible. For these and similar applications in which *qualitative prediction* is important, we use other type of measures.

In these contexts is common to start from a **classification table** or [**confusion matrix**](http://en.wikipedia.org/wiki/Confusion_matrix). A confusion matrix is simply a cross tabulation of the observed outcome in relation to the predicted outcome. We saw earlier how the `predict()` function generated a set of predicted probabilities for each of the subjects in the study. In order to produce a classification table in this context we need to define a **cut-off point**, a particular probability that we will use in classifying cases. Anybody above that cut-off we will define as belonging to the level of interest and anybody below we will define as not. We could, for example, say that anybody with a probability larger than .5 should be predicted to receive harsher treatment.

The confusion matrix typically follows this layout:

![confusion](http://3.bp.blogspot.com/_txFWHHNYMJQ/THyADzbutYI/AAAAAAAAAf8/TAXL7lySrko/s1600/Picture+8.png)

The diagonal entries correspond to observations that are classified correctly according to our model and our cut off point whereas the off-diagonal entries are misclassifications. **False negatives** are observations that were classified as zeros but turned out to be ones (the outcome of interest). **False positives** are observations that were classified as ones (the outcome of interest) but turned out to be zeros.

There are various ways of producing a confusion matrix in R. The most basic one is to simply ask for the cross-tabulation of the predicted classes (determined by the cut-off criterion) versus the observed classes.


```r
#First we define the classes according to the cut-off
fitl_1_pred_class <- fitl_1_prob > .5
#This creates a logical vector that returns TRUE when the condition is met (the subject is predicted to be released) and FALSE when the condition is not met (harsher treatment was delivered)
fitl_1_pred_class[1:10]
```

```
##     1     2     3     4     5     6     7     8     9    10 
## FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE FALSE
```

```r
#Let's make this into a factor with the same levels than the original variable
harsher_pred <- as.factor(fitl_1_pred_class)
levels(harsher_pred) <- c("No","Yes")
table(harsher_pred)
```

```
## harsher_pred
##   No  Yes 
## 5113  113
```

```r
#Then we can produce the cross tab
tab0 <- table(harsher_pred, Arrests$harsher)
tab0
```

```
##             
## harsher_pred   No  Yes
##          No  4278  835
##          Yes   56   57
```

From classification tables we can derive various useful measures. Two important ones are the **sensitivity** and the **specificity**. The sensitivity of the model is the rate that the event of interest (e.g., receiving harsher treatment) is predicted correctly for all cases having the event.

Sensitivity = number of cases with the event and predicted to have the event / number of samples actually presenting the event

In this case this amount to 57 divided by 835 plus 57. The sensitivity is sometimes also considered the **true positive rate** since it measures the accuracy in the event populaiton. On the other hand, the specificity is defined as:

Specificity = number of cases without the events and predicted as non-events /  number of cases without the event

In this case this amount to 4278 divided by 4278 plus 56. The **false positive rate** is defined as one minus the specificity.

From the table we produced we can generate these measures automatically. For this sort of things, however, I prefer to go straight to the `confusionMatrix()` function from the `caret` package since it produces a very detailed set of calibration measures that are helpful indicators of how well the model is classifying.


```r
library(caret)
```

```
## Loading required package: ggplot2
```

```
## Loading required package: lattice
```

```r
confusionMatrix(data=harsher_pred, reference=Arrests$harsher, positive="Yes") #The data argument specifies the vector with the predictions and the reference argument the vector with the observed outcome or event. The positive argument identifies the level of interest in the factor.
```

```
## Confusion Matrix and Statistics
## 
##           Reference
## Prediction   No  Yes
##        No  4278  835
##        Yes   56   57
##                                              
##                Accuracy : 0.8295             
##                  95% CI : (0.819, 0.8396)    
##     No Information Rate : 0.8293             
##     P-Value [Acc > NIR] : 0.4943             
##                                              
##                   Kappa : 0.078              
##                                              
##  Mcnemar's Test P-Value : <0.0000000000000002
##                                              
##             Sensitivity : 0.06390            
##             Specificity : 0.98708            
##          Pos Pred Value : 0.50442            
##          Neg Pred Value : 0.83669            
##              Prevalence : 0.17069            
##          Detection Rate : 0.01091            
##    Detection Prevalence : 0.02162            
##       Balanced Accuracy : 0.52549            
##                                              
##        'Positive' Class : Yes                
## 
```

We can see first the **accuracy**. The overall accuracy rate gives us the agreement between the observed and predicted classes. However, the overall accuracy is often not the most useful measure. **Kappa** is also a measure that is often used with values ranging between 0.30 to 0.50 considered to indicate reasonable agreement. But for many applications will be of interest to focus on the sensitivity and the specificity as defined above. In this case, we can see that our sensitivity, or the true positive rate, is very poor. And so it is the Kappa. Clearly the model has problems predicting harsh treatment with the select cut off.

One of the problems with taking this approach is that the choice of the cut off point can be arbitrary and yet, this cut off point will impact the sensitivity and specificity of the model. There is a trade-off between sensitivity and specificity. Given a fixed accuracy, more of one will result in less of the other.

So if we use a different cut off point, say .25, the classification table would look like this:


```r
precision<-function(c) {
tab1 <- table(fitl_1_prob>c, Arrests$harsher)
out <- diag(tab1)/apply(tab1, 2, sum)
names(out) <- c('specificity', 'sensitivity')
list(tab1, out)
}
precision(.25)
```

```
## [[1]]
##        
##           No  Yes
##   FALSE 3627  496
##   TRUE   707  396
## 
## [[2]]
## specificity sensitivity 
##   0.8368713   0.4439462
```

Here we are predicting as receiving harsher treatment anybody with a probability above .25 of doing so according to our model. Our sensitivity goes up significantly, but our specificity goes down. You can see that the cut off point will affect how many false positives and false negatives we have. With this cut off point we will be identifying many more cases as presenting the outcome of interest when in fact they won't present it (707 as oppose to 56 when using a cut off of .5). On the other hand, we have improved the sensitivity and now we are correctly identifying as positives 396 cases as opposed to just 57 cases). The overall accuracy is still the same but we have shifted the balance between sensitivity and specificity. 

Potential trade offs here may be appropriate when there are different penalties or costs associated with each type of error. For example, if you are trying to predict a homicide as part of an intervention or prevention program you may give more importance to not making a false negative error. That is you want to identify as many potential homicide victims as possible, even if that means that you will identify as victims individuals that in the end won't be (false positives). On the other hand, if you have limited resources to attend all the cases that you will predict as positives you also need to factor this into the equation. You don't want to use a cut off point that will lead you to identify more cases as potential homicide victims that you can possibly work with.

Similarly, if you think about the criminal justice system, it is essentially built around the idea of avoiding false positives - that is convicting people who are innocent. You will have heard many phrases like "innovent until proven guilty" or "It is far better that 10 guilty men go free than one innocent man is wrongfully convicted". This approach would incline us to err on the side of false negatives, and avoid false positives (higher sensitivity, lower specificity).

We may want to see what happens to sensitivity and specificity for different cut off points.  For this we can look at **receiver operating characteristics** or simply [ROC curves](http://en.wikipedia.org/wiki/Receiver_operating_characteristic). This is essentially a tool for evaluating the sensitivity/specificity trade off. The ROC curve can be used for investigating alternate cut offs for class probabilities.

We can use the `pROC` package for this. We start by creating an object that contains the relevant information with the `roc()` function form t the `pROC` package.


```r
library(pROC)
```

```
## Type 'citation("pROC")' for a citation.
```

```
## 
## Attaching package: 'pROC'
```

```
## The following objects are masked from 'package:stats':
## 
##     cov, smooth, var
```

```r
rocCURVE <- roc(response = Arrests$harsher, 
                predictor = fitl_1_prob)
```

```
## Setting levels: control = No, case = Yes
```

```
## Setting direction: controls < cases
```

Once we have the object with the information, we can plot the ROC curve.


```r
plot(rocCURVE, legacy.axes = TRUE) #By default the x-axis goes backwards, we can use the specified option legacy.axes=TRUE, to get 1-spec on the x axis moving from 0 to 1.
```

![](09-logistic_files/figure-latex/unnamed-chunk-25-1.pdf)<!-- --> 

We can see the trajectory of the curve is at first steep, suggesting that sensitivity increases at a greater pace than the decrease in specificity. However we then reach a point at which specificity decreases at a greater rate than the sensitivity increases. If you want to select a cut off that gives you the optimal cut off point you can use the `coords()` function of the pROC package. You can pass arguments to this function so that it returns the best sum of sensitivity and speficitity.


```r
alt_cutoff1 <- coords(rocCURVE, x = "best", best.method = "closest.topleft")
#The x argument in this case is selecting the best cut off using the "closest topleft" method (which identifie the point closest to the top-left part of the plot with perfect sensitivity or specificity). Another option is to use the "youden" method in the best.method argument.
alt_cutoff1
```

```
##   threshold specificity sensitivity
## 1 0.1696539   0.6305953   0.7163677
```

Here we can see that with a cut off point of .16 we get a specificity of .63 and a sensitivity of .71. Notice how this is close to the base rate of harsher treatment in the sample (17% of individuals actually received harsher treatment). For a more informed discussion of cut off points and costs of errors in applied predictive problems in criminal justice, I recommend reading [Berk (2012)](http://link.springer.com/book/10.1007%2F978-1-4614-3085-8). Often the selection of cut off may be motivated by practical considerations (e.g., selecting individuals for treatment in a situation where resources to do so is limited).

The ROC curve can also be used to develop a quantitative assessment of the model. The perfect model is one where the curve reaches the top left corner of the plot. This would imply 100% sensitivity and specificity. On the other hand, a useless model would one with a curve alongside the diagonal line splitting the plot in two, from the bottom right corner to the top right corner. You can also look at the **area under the curve** (AUC) and use it to compare models. An AUC of .5 correspond to the situation where our predictors have no predictive utility. For a fuller discussion of how to compare these curves and the AUC I recommend reading Chapter 11 of [Kuhn and Johnson (2014)](http://link.springer.com/book/10.1007/978-1-4614-6849-3).

## Interactions

The data we have been using were obtained by the author of the `effects` package from [Michael Friendly](http://www.datavis.ca/), another prominent contributor to the development of R packages. The data are related to a series of stories revelaed by the Toronto Star and further analysed by Professor Friendly as seen [here](http://www.datavis.ca/courses/VCD/vcd4-handout-2x2.pdf). In these further analysis Friendly proposes a slightly more complex model than then one we have specified so far. This model adds three new predictors (citizenship, age, and year in which the case was processed) and also allows for interactions between race (colour) and year, and race and age.


```r
fitl_2 <- glm(harsher ~ employed + citizen + checks + colour * year + colour * age, family = binomial, data = Arrests) #Notice this different way of including interactions
summary(fitl_2)
```

```
## 
## Call:
## glm(formula = harsher ~ employed + citizen + checks + colour * 
##     year + colour * age, family = binomial, data = Arrests)
## 
## Deviance Residuals: 
##     Min       1Q   Median       3Q      Max  
## -1.7625  -0.6178  -0.4408  -0.3473   2.4496  
## 
## Coefficients:
##                     Estimate  Std. Error z value             Pr(>|z|)    
## (Intercept)      -134.187783   69.287702  -1.937             0.052785 .  
## employedYes        -0.747475    0.084601  -8.835 < 0.0000000000000002 ***
## citizenYes         -0.620159    0.105164  -5.897         0.0000000037 ***
## checks              0.364718    0.025949  14.055 < 0.0000000000000002 ***
## colourBlack       361.668318  115.180289   3.140             0.001689 ** 
## year                0.066318    0.034664   1.913             0.055722 .  
## age                 0.009347    0.005495   1.701             0.088979 .  
## colourBlack:year   -0.180225    0.057604  -3.129             0.001756 ** 
## colourBlack:age    -0.038134    0.010161  -3.753             0.000175 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## (Dispersion parameter for binomial family taken to be 1)
## 
##     Null deviance: 4776.3  on 5225  degrees of freedom
## Residual deviance: 4275.0  on 5217  degrees of freedom
## AIC: 4293
## 
## Number of Fisher Scoring iterations: 5
```

What we see here is that the two interactions included are significant. To assist interpretation of interactions is helpful to look at effect plots.


```r
plot(effect("colour:year", fitl_2))
```

![](09-logistic_files/figure-latex/unnamed-chunk-28-1.pdf)<!-- --> 

First we see that up to 2000, there is strong evidence for differential treatment of blacks and whites. However, we also see evidence to support Police claims of effect of training to reduce racial effects.


```r
plot(effect("colour:age", fitl_2))
```

![](09-logistic_files/figure-latex/unnamed-chunk-29-1.pdf)<!-- --> 

On the other hand, we see a significant interaction between race and age. Young blacks are treated more harshly than young whites. But older blacks treated less harshly than older whites.

We already discussed in a previous session the difficulties of interpreting regression coefficients in models with interactions. Centering and standardising in the way discussed earlier can actually be of help or this purpose.



## Further resources

These are a set of useful external resources that may aid your comprehesion (and I have partly relied upon myself, so credit to them!):

+ A set of [explanatory notes](http://www.unc.edu/courses/2010fall/ecol/563/001/docs/lectures/lecture20.htm#dealing) by Jack Weiss at the University of North Carolina. Check lesson 20 and 21. I really like the look of his whole course.

+ The [UCLA guide](http://www.ats.ucla.edu/stat/r/dae/logit.htm) to using logistic regression with R.

+ A [helpful list of resources](http://www.r-bloggers.com/some-r-resources-for-glms/) for general linear models with R.


<!--chapter:end:09-logistic.Rmd-->

# Wrapping up

Well done all. 
It is the final week, so let me start with some general reflections to wrap up the unit. I know some of you may think, why the hell am I learning code and stats? You may think the contents of this course may ultimately not be of direct benefit to you. But we have designed this experience in such a way that you also acquire a set of skills and tools to learn how to confront tough problems (even those you may think you hate). Life will throw many of those kind of problems at your door. Having survived this module, we believe may have also teach you a thing or two about the importance of task persistence; overcoming your frustration in order to obtain results; dealing with your own insecurites and the understandable emotions they generate; being more organised about your work; collaborate with others in the same situation; the importance of attention to detail; etc. Hopefully we may have also helped you to develop a greater sense of curiosity and to achieve the inmense satisfaction one gets when one cracks a tough problem that may have had us screaming at the computer screen for what may have felt like hours. We know a course like this may get you out of your comfort zone. But we firmly believe that it is worth it. And that you will get something out of it, even if now may not be terribly obvious to you.

And with that, let's move to this final session. We are not going to cover new techniques today. What there may be a few tips about presentation that you may find helpful. The document in Blackboard about how to write your analytical report is quite detailed already. But there a few additional tips you may find helpful. 

##Tips for the assignment

You should all now be familiar with the assignment you have to do. In the Blackboard page for this course unit you can obtain the essay question and additional guidance we have prepared. You can see as well [here](https://github.com/eonk/mcd_book/blob/main/files_docs/STEPS%20IN%20THE%20ANALYSIS%20REQUIRED%20FOR%20THE%20ESSAY.pdf). This guidance aims to answer most of the questions about what you need to do and how. It is very detailed and it has been built with the feedback from the many students that have taken this module before. That guidance aims to provide you a helping hand during the process. It also includes a file in how to think about the writing of your essay -see [here](https://github.com/eonk/mcd_book/blob/main/files_docs/WRITING%20THE%20ESSAY.pdf).

Critically you have never written anything like this before so it is normal to have questions. It may help you to read any article in any of the top journals in our field such as [Criminology](https://onlinelibrary.wiley.com/journal/17459125), the [Journal of Research in Crime and Delinquency](https://journals.sagepub.com/home/jrc), or if you like "hard drugs" the [Journal of Quantitative Criminology](https://link.springer.com/journal/10940) to get an idea of the templates that criminologists follow when writing a research report. **Looking at good templates** such as the ones you will encounter in those journals will give you good ideas about how to tell your story. Keep in mind those journal articles are subject to a more generous word count than you will have here, so you will have to be even more succint and parsimonious. If you are spoiled by choice and hesitant about which paper to choose, have a look at [this one](https://onlinelibrary.wiley.com/doi/10.1111/j.1745-9125.2011.00227.x) by Chris Melde and Finn Esbensen from 2009.

For any additional questions you can follow the sequential 5 "Bs" approach designed to enhance autonomy that primary schools follow these days: brain, book, board, buddy, boss. Start with the first and move to the next one if you get stuck.

![](imgs/fiveb.jpg) 

+ **Brain**: "Do you already know the answer or is this something you can decide for yourself?"
+ **Book**: "Can I look back through my learning materials and find the answer there?"
+ **Board**: "Is the answer in the discussion board?"
+ **Buddy**: "Can one of my peers answer this question?" (if unconvinced by their answer you can move to the next B)
+ **Boss**: "If I have tried all the other Bs, then I can put up my hand but continue working" (and remember here you should first try to ask in the discussion board or the labs, and failing that make an appointment through office hours)



A scientific report, like the one you are tasked to write, needs to be clear, well justified, and very efficient in the use of space. It will be helpful you finish ahead of time and **dedicate some time simply to edit your final essay**. This is, in fact, a general piece of advice for any essay you write. But in this case perhaps matters more. You will have done loads of things as part of your analysis, but will have very limited word count to tell the story of your analysis. Every word and every sentence must be needed. There is always a shorter and more parsimonious way of saying something! And, please, use the spelling editors of whatever app you use to write your essays. It is not cool to send essays with typos and grammar errors that any app can automatically detect these days.

Here I am just going to cover a few things you can do to make this presentation a bit more succint and parsimonious.


##Summarising your variables


The paper by Melde and Esbensen (2009) cited above provides an example of how you may want to describe in the text your variables. As noted you may not have as much space to get into so much detail, but the core idea you need to take home is that the reader needs to know what variables you are using and how they are measured. You will also need to provide a succint summary of the descriptive measures for your variables. Look at [this paper](https://journals.sagepub.com/doi/10.1177/1477370808095123) by Andromachi Tseloni and Christina Zarafonitou (2008). Below I reproduce a table from the pre-print version of this article with a summary of the variables they are using in their analysis:

![](imgs/variabledescription.png) 

This is a very succint way of describing the distribution of your variables when all are categorical. If you happen to have quantitative variables as well you could, for example, add another column with the mean and the standard deviation (the latter enclosed in brackets) -which would only have this information for your quantitative variables.

Notice that this table has minimum amount of ink and only lines separating cells when absolutely necessary. If you are uncertain how to modify the default tables your word editor uses, [this file](https://github.com/eonk/mcd_book/blob/main/files_docs/wordtables.pdf) gives you some tips in how to do with with MS Word. It will be fairly similar with other apps.

Notice as well that information about the total sample size is provided. Remember what we cover in the end of section 4.9!

As we have said we want you to look at whether your variables are associated before you run your multiple regression model. We do this so that we can evaluate if you have learnt how to choose the right tests and measures of effect size. 

![](imgs/tableexample.png) 

Above I am reproducing an example of how you could do this. The example assumes you have a categorical dependent variable with four different categories (non-gang, gang only at T1, etc.). You can see how in this table the categories define the column (there is also one for the total sample, if you have something like this you are essentially providing also the summary descriptives for the whole). You can see that the rows define the levels for two categorical variables (gender and race/ethnicity) and two quantitative variables (age and a score for crime). For the categorical variables we have the appropriate percentages (as discussed in week 7) and for the quantitative variables we have the means and standard deviations. Remember how you set this table may differ depending the nature of your variables, but hopefully you get the idea. You can find a way to summarise the information. You could add a column to a table like this with the p values for your statistical tests (somehow indicating what that test was: chi square, F, etc.). Then you could discuss the more relevant of this in the narrative discussing your table.


##Some final words

So, this is the end. At least for now. What we have done this semester is an introduction to the field of data analysis. But there is so much more to it. If you are planning a scientific career or want to work as an analyst in the private or public sector, the journey is just beginning. You could take some choices in the final year to continue this journey. There are some options within our degree (like Crime Mapping or the Quantitative Seconday Analysis Short Dissertation pathway, one of the possible modalities as the Short Dissertation). You could also take options in other degrees within the School of Social Science, our new home, that also have a focus on quant analysis (we can advise on these). After that you may want to think about our MRes in Criminology (Social Statistics), which focuses on quant analysis as part of the criminology track. You can see details [here](https://www.manchester.ac.uk/study/masters/courses/list/10377/mres-criminology-social-statistics/).

But there are many free courses offered as massive online open courses that you could take to consolidate or further expand what you have learnt this semester. Check out [Coursera](https://www.coursera.org/browse/data-science) or [edX](https://www.edx.org/course/subject/data-science) platforms for these. Many of those courses make you pay for a certificate (and if you want to get feedback), but you can watch the videos and use the materials for free in almost all of them. You may also want to have a look at [datacamp](https://www.datacamp.com). Most of their courses require a paid subscription, but there are many courses for free (particularly those created by the community).

Good luck with the essays!!! And do not hesitate to get in touch if you have any queries.

<!--chapter:end:10-Wrapping_up.Rmd-->
