---
layout: page
title: "R From Scratch"
permalink: /R_From_Scratch
---


# Table of contents

- [Introduction]
- [Definitions]
- [First steps]
    - [Using the console]
    - [Incomplete code]
    - [Didn't work!]
    - [Operations]
    - [Using a script]
    - [Comments]
    - [Cancel a command]
    - [Creating objects]
    - [Functions]
        - [Nested functions]
        - [Generic functions]
- [R objects and their structures]
    - [Vectors]
        - [Creating vectors]
        - [Coercion]
        - [Attributes]
        - [Subsets of an object]
    - [Matrices]
        - [Creating matrices]
        - [Subsetting matrices]
    - [Lists]
        - [Creating lists]
        - [Subsetting lists]
    - [Data frames]
        - [Creating data frames]
        - [Subsetting data frames]
- [Packages]
    - [Installing packages]
    - [The Tidyverse]
- [Paths and directories]
    - [R projects]
- [Importing data]
    - [Using read.table()]
    - [Using read.csv()]
    - [Using read_excel()]
- [Built-in datasets in R]
- [Exploring data in R]
- [Suggested readings]
- [APENDIX]
    - [Functions used in this document]


# Introduction

This is the first of a series of documents design to provide the key skills in R and boost your learning experience. The main aim is to allow the reader to understand the fundamentals of R as a programming language and as a platform for data analysis, following a series of easy and reproducible examples.

This courses are for both, newbies with zero experience in programming, as well as users with some experience that want to refresh their memory, develop a weak area, or experienced users that never had a formal introduction to R or Rstudio.

# Definitions

- Programming language: A formal written language with defined grammar that is used to specify instructions to obtain a specific result.
- Code: Text that is written in a given programming language.
- R: A programming language derived from "S" (an older programming language). S was developed with the explicit goal of analyzing data in an easy and efficient way.
- Rstudio: An integrated development environment (IDE) for R.
- IDE: An integrated development environment is a software application that provides comprehensive facilities to programmers for software development. This includes some kind of graphical user interface (GUI).
- GUI: Allows users to interact with electronic devices (i.e. a computer) through graphical icons, menu, etc., instead of just text. 
- Console: Formally called "command line interface" (CLI). Generally appears as an entry of text that allows to specify instructions to a program ("speak to the computer").
- Command: Code that was entered to the console. If well redacted, indicates the execution of a specific action.
- Script: For the purpose of these courses, is a text editor where you can write code and allows you to 1) edit and format it more easily before sending it to the console, and 2) save your code for future use.
- Global environment: Is the virtual space where your computer saves all the data from an R session.
\newpage

# First steps

Open Rstudio like any other program. You will see 3 panels. The left panel corresponds to the console. In the bottom portion of this panel you will see the symbol ">". This is the command line and is where you write the commands. To run a command, that is, for the computer to execute the command, you must press enter. Once the computer has finish to process the command, the result will be displayed in the console panel.

## Using the console

Look what happens if you write 1 + 1

```{r}
1 + 1

```

If you look closely, the result is not only the number 2, it is preceded by a [1]. This has more sense when the output is a series of elements shown in rows. To clarify this, enter the command 50:100 to the console.

```{r}
50:100
```

Basically, the number in square brackets shows you that a given line starts with the Nth component of the series. The first line starts with the first component, the second line starts with the 20th, and the third with the 39th. You will learn more about this in the section "[Subsets of an object]"

The operator ":" is used to obtain all the integers between two integers. The result is a one by one sequence, from the first to the last integer. 

In the console you can use the up arrow in your keyboard to see commands that were run in the past in your current R session.

## Incomplete code

If you run an incomplete line of code, instead of seeing a ">" in the command line, you will see a "+". This means that R is waiting for you to add more code to complete the line.

## Didn't work!

Executing a command in R may result in the following outcomes:

- Message: A notification that does not intervene in the execution of the command.
- Warning: Something is wrong, but it's not "fatal". Does not interfere with the execution of the command.
- Error: A fatal problam has occurred. The execution of the command is stopped.
- Condition: General concept to indicate that something unespected has occurred.

The majority of the mistakes that one makes as a beginner are due to wrong code syntax. R is particularly picky about correct syntax, the tiniest typo may result in an error.

## Operations

Now that you know how the console works, you can start doing useful stuff. As beginner, one of the first qualities that you will learn from R is that it is considered a "glorified" calculator. You can do all the basic operations, and much more!

```{r}
6*4

10 - 4

125/(2 + 3)
```

## Using a script

When you open Rstudio for the first time, none of the panels corresponds to a script, you must open one yourself. You can do this in three different ways.

1) Go to "File...New File...R Script"
2) Press the button in the top-left corner that shows a white sheet with a plus sign.
3) Press "ctrl...shift...n" if you have Windows, or "command...shift...n" if you have a Mac.

Now that you have 4 panels in Rstudio, the script corresponds to the top left panel. This is just a text editor that you can use to write your code. To run your code, you must click over the line you want to run and press ctrl + enter (Windows) or cmd + enter (Mac) to run the code. Alternatively, you can press the button that says "Run" in the top right corner of the script. Note that you can highlight several lines of code and run them all at once (actually, they will be run one by one in the order they are written).


## Comments

Working in the script is very useful, because:

- It allows you to reuse your code in the future.
- You can focus on getting your code to a tidy and readable form.
- It's easier to track the things you have done in the past.

To get full advantage of this qualities, it is highly recommended that you annotate your code with plenty of comments. Your future self will highly appreciate this. To write a comment in the script, you just have to start a line with a "#". This tells R that what's next is not code, so it will be ignored. 

The effect of the "#" affects the entire line, but only that line. If you want to continue your comment in the next line, just add another "#".

Tip: If you want to comment out several lines at once, highlight the relevant lines and press cmd + shift + c if you are mac, or ctrl + shift + c if you are Windows.


## Cancel a command

Sometimes, when you run code that uses a lot of data, and thus, a lot of memory and resources from your computer, it may take a while to get to the result. To avoid an unnecessary waste of time, you can cancel a command by pressing ctrl + c (or cmnd + c). Alternatively, you can click the red stop sign in the top right corner of the console panel. This sign appears only when a command is running, in most cases you wont notice it because most commands are executed very quickly. Cancelling a command can also take a while.


## Creating objects

To perform all sorts of calculations in R is not very useful if you don't save your outputs in "objects" to use those results for further calculations. For example, we know that running 1 + 1 will result in a 2 being printed in the console. But how can I store the result of an operation? To achieve this, you must use a new operator, which is known as the "assigner". This operator is just an arrow drawn from two consecutive signs, a "<" and a "-". In the next example, I'm going to assign the result of 1 + 1 to an object symbolized by the letter x.

```{r}
x <- 1 + 1

x
```

You will see that it is common to also use a "=" to assign values to an object. Although this won't make a difference in most cases, these two symbols are slightly different and should not be used interchangeably. I recommend sticking with the "<-" for now.

Once you assign a value to an object, you can use that object in other lines of code where R is going to replace it with the corresponding value.

```{r}
x + x
```

When you create objects, these are displayed in the environment panel. This panel usually displays the "global environment" where all your objects are usually saved since you opened R and shows their names and values. 

As a general rule, the name of an object must start with a letter. Do not use special characters like @, ^, $, !, +, -, / o * at all.

When you assign a new value to an object that already exists, the old value is replaced by the new one.

```{r}
x <- 3

x
```

Additionally, R is case-sensitive.

```{r}
X <- 4

x + 1
```

SUGGESTION: I recommend you to never save the objects of the environment, that is, to erase them when you end the R session. To make sure this happens, follow these steps:

1. In the toolbar, click on "Tools" and select "Global Options".
2. A window will appear in the "General" section. Select the "Workspace" section instead. There, untick the "Restore .RData into workspace at startup" statement.
3. For the "Save workspace to .RData on exit" statement, select "Never".

In general, saving the script plus the original data is more than enough to reproduce your work. Following the steps above will force you to generate a more detailed script.

## Functions

In a programming language, functions are like the verbs because functions perform actions. This includes transforming, ordering, calculating, plotting, etc. In R, a function is like any other object, but if you want to use it you must follow a well defined syntax. In your learning journey you will see two types of functions, "primitives" or functions that are part of base R and that usually take the form of certain operators like ":", and "named" functions that usually can be called by their name followed by a parenthesis (e.g. function()).

All functions (non-primitives) have these components:

1. Body: The code of a function that determines its function. When you call a function, the body is not shown. To see the body of a function, you can use the function body().
2. Arguments: A functions needs an input and possibly other instructions that determine its behavior in different contexts. For these, you have arguments, which are usually a list of words that go inside the parenthesis when you call a function (e.g. function(argument1, argument2)). Some functions have default values for some of their arguments, which means that if you don't specify those arguments, R will use the default values.
3. Environment: The distribution of the variables of a function in your computer. This is advanced topic and is not necessary to understand it to survive in R, but I might explain it better in future documents for writing your own functions.

If you are not clear with how a specific function is used, or you forgot the arguments, etc., you can write the name of the function in the console preceded by a "?" (e.g. ?function). In the bottom right panel of Rstudio a tab will display showing the help page of that function with all the details about it. This page is generally part of the R documentation, that is, the official information about that function. 

### Nested functions

A function can use other function as an argument. This means that functions can be nested one inside the other. You must always have present that when you nest functions, R will process them from the innermost to the outermost (e.g. function2(function1())).

### Generic functions

A special type of functions are the so called "generic functions". Unlike other functions, generic functions are able to adjust their behavior depending on the class of object they are dealing with. For a specific example you can go to the section "[Exploring data in R]" and see how I use the summary() function.
\newpage

# R objects and their structures

In R, objects can have a variety of structures, but there are 4 structures which are the most common and make the core of R:

- Vector
- Matrix
- List
- Data frame

## Vectors

 A vector is the most basic object in R. The object X previously saved in the section "[Creating objects]" corresponds to a vector of length 1 because it has only one component. The only rule that determines the nature of a vector is that all its components must be objects of the same class. The five main classes of objects are:

- Character: R considers as a character any symbol represented in quotes. Accordingly, "1" would be a character, and not a number.
- Numeric: Any real number
- Integer: Any integer number (must be specified, for example 2L. Also, the output of the function ":" is of class integer).
- Logical: TRUE or FALSE. NA (not available)
- Complex: Complex numbers are represented as an addition between their real part and their imaginary part (e.g. 1 + 2i).

The function class() can be used to determine the class of an object.

### Creating vectors

There are many ways to create a vector. We have already seen the first one, which is using the ":" operator. A more general way to create a vector is to concatenate several vectors of length 1 in a new vector of length "n". For this, you can use the function c(). Moreover, to know the length of a vector, you can use the function length().

Below are some examples of vectors of different classes.
```{r}
# "a", "b" y "c" are vectors of length 1
#  To concatenate them, I use c() and then assign the result to an object called a.

a <- c("a", "b", "c")

class(a)

length(a)

# Creating vectors of other classes

a <- c(0.5, 0.4)      # Numeric
a <- c(TRUE, FALSE)   # Logical
a <- c(T, F)          # Logical
a <- c(1+0i, 2+4i)    # Complex

```

Lastly, the function vector() is also used to create vectors. An advantage of this function is that allows to create empty vectors. We will see in future applications of this convenient option.

```{r}

# Creating a numeric vector of length 5
vector("numeric", length = 5)

# Creating an empty vector, which is logical by default
vector()

# Creating a numeric empty vector
vector("numeric")

```

### Coercion

Because vectors must be made of components of the same class, if you concatenate elements of different classes, these will be coerced to a single class. For this, R follows coercion rules.

```{r}
b <- c(5, "c")
class(b)

b <- c(TRUE, 2)
class(b)

b <- c("x", FALSE)
class(b)


```

As you can see, R coerces objects to a single class in a logical way. In the first case, it makes sense to coerce 5 into a character, but not to coerce "c" into a number.

In general, TRUE and FALSE are equivalent to 1 and 0 respectively in cases in which is necessary to convert them into numbers (and vice versa).

Coercion can be explicit. For this, you can use the functions of the "as." family.

```{r}
c <- 0:10

as.character(c)
as.logical(c)
as.numeric(c)

# When R doesn't know how to coerce objects, it introduces NAs

c <- c("a", "b", "c")

as.numeric(c)
```

### Attributes

The attributes of an object correspond to additional information apart from the content of the object. You may call this the "metadata" of an object. We have already seen some attributes of a vector, like its class and length. Below I show a series of examples of attributes:

- Names
- Dimension names
- Dimensions
- Class
- Length
- Attributes defined by the user

Not all objects contain attributes, but if they do you can see them with the function attributes(). Likewise, you can obtain specific attributes, like the names of an object, using specific functions, in this case, the function names().

```{r}
# Assigning names to a vector

x <- 1:3

names(x) <- c("Los Angeles", "San Diego", "Irvine")

x

names(x)

attributes(x)


```

### Subsets of an object

Sometimes you would like to see just a portion of an object instead of its entirety. For that we use the "[" operator. To obtain a specific element of an object you need to provide an index that specifies the position of the element inside the object. For vectors, the index is any integer between 1 and the length of the vector. I have already shown an example of this in the section "[Using the console]", but now I will show you how to subset using this operator.

```{r}
x      # The vector x
x[2]   # Obtaining the second element of the vector x

# If you repeat an index, you obtain the same value repeatedly
x[c(2, 2, 2)]

# If the index is negative, you obtain all the elements, except the one specified
x[-2]
```
Instead of using indexes, you can use technique called "logical subsetting". For this you need to generate a logical vector of length equal to your object.
```{r}
L <- c(FALSE, TRUE, FALSE)
x[L]

# You can create the logical vector in a smarter way.
x == 2
L.2 <- x == 2
x[L.2]
```
You can also use the name of an element.
```{r}
x["Irvine"]
```
Lastly, you can also use the "$" operator, but this is only valid for lists and data frames that have names as attributes.

## Matrices

Matrices are vectors with one additional dimension as an attribute. The dimension is a numeric vector of length 2, the first value corresponds to the number of rows, and the second to the number of columns.

### Creating matrices

There are several ways to create a matrix. Below I show some examples.

```{r}

# 1) Using the function matrix() to create a matrix and assign it to the object m

m <- matrix(ncol = 3, nrow = 2)

     # What are the dimensions of this matrix?
dim(m)

     # What are the attributes of this matrix?
attributes(m)

# 2) Creating two numerical vectors and then binding them together...

v1 <- c(1, 2, 3)
v2 <- c(4, 5, 6)

#    a. As columns

m1 <- cbind(v1, v2)
m1

#    b. As rows

m2 <- rbind(v1, v2)
m2


# 3) Creating a single vector and adding a second dimension as an attribute.

v3 <- 1:6

dim(v3) <- c(3, 2)

v3

```

As you may have noticed, matrices are filled by columns, not rows. You can change this with the argument "by.rows = TRUE" in the matrix() function.

You can also add names to the rows and columns of a matrix with the functions rownames() and colnames() respectively.

```{r}

colnames(m) <- c("a", "b", "c")
rownames(m) <- c("d", "f")

m

```

### Subsetting matrices

Matrices are subsetted in a similar way was vectors, but because they have an additional dimension you must add two indexes separated by a comma. The left index specifies the row, while the right one specifies the column.
```{r}
v3[1, 2]

# Adding names for subsetting
colnames(v3) <- c("a", "b")

v3[, "b"]

# Using logical values to select rows
v3[c(T, T, F),"b"]
```

## Lists

Lists are a special kind of vector, which main characteristic is that you can add elements of different classes. Lists are like bags where you can add whatever you want. They may be difficult to manipulate, but they are one of the most useful objects in R.

### Creating lists

You can create a list explicitly with he function list().

```{r}
# Creating a list with objects of different classes
my.list <- list(13, "hello", FALSE, 3 + 4i)
my.list

# You can also create an empty list of specified length using the funciton vector()

list2 <- vector("list", length = 5)
list2

# To facilitate the use of a list, you can add names

names(my.list) <- c("number", "greeting", 
                     "logical", "complex")
my.list
```
### Subsetting lists

With lists you can subset using both, the "[" operator and the "$" operator.
```{r}
# Subseting the first element of a list
my.list[1] # Notice that the output is also a list

class(my.list[1])

# To simplify the output, use double square brackets

my.list[[1]]
class(my.list[[1]])

# Using the dollar sign

my.list$logical  # The output is already simplified


# Lists can be nested

list2
list2[[1]] <- my.list
list2

# Subsetting the second element of the first element in the list
list2[[1]][2]

```


## Data Frames

Data frames are one of the objects that you are going to use the most because they are the way in which R saves data in table format. Despite its similarity with matrices, is indeed a special kind of list where each element has the same length. These elements correspond to columns and their length is the number of rows. Because they are modified list, columns can be of different classes.

Data frames have both, column names and row names as attributes. The latter are usually numbers.

### Creating data frames

To create a data frame explicitly, you can use the function data.frame().
```{r}
Data <- data.frame(x = c("a", "e", "i", "o", "u"), 
                   y = 1:5, 
                   z = as.logical(c(0, 1, 1, 0, 0)))

Data

```
### Subsetting data frames

You can use both, the square brackets and the dollar sign.
```{r}
Data[, "x"]

Data$x


# Logical subsetting

Data[Data$y == 5, ]
```

Another popular way of generating data frames is to import data into R that usually are already in table form (see section [Importing data]).
\newpage

# Packages

R has a very active community of users. This is not trivial, since one of the biggest strengths of R is that the entire community of users can contribute to R by sharing code written with a specific application in mind. For example, a couple of decades ago R was gaining a lot of users in ecology and some users started to create their own functions to perform calculations specific to the discipline. The set of tools generated by these ecologists was shared in the form of "packages" which any user can download and use.

Packages contain code that is not part of "base R", that is, the functions and characteristics that are already included when your first download R. Downloading and installing a package, you are actually adding new functions which means you are now capable of doing things that other people figured out for you. You can perform tasks that otherwise would be too tedious or difficult without that specific package.

## Installing packages

To install a package, you can use the function install.packages(). To try it yourself, you can install the package "plyr".

```{r}
# install.packages("plyr")
```

Once a package has been downloaded and installed, their functionalities are not immediately available. To be able to use the new functions provided by the package, you must load the package into R. You can do this with the function library().

```{r}
library(plyr)

```

While loading a package, you will not always see something printed on the console. To make sure that the package was loaded correctly, you can check the bottom right panel in R. You will see a tab called "Packages". In this tab you will find a list of the packages that you have already installed. Those that have been loaded have a tick in the check box left to the name of the package.

Another intuitive way to confirm a package has been loaded correctly is to write the name of a function of the package, but keeping it incomplete. Usually, Rstudio will suggest possible functions that are available when you are writing the name of a function. If you don't see the function's name offered as a suggestion, it is possible that the package was not loaded, or that the installation was unsuccessful.

## The Tidyverse

There is a group of packages that acquired such relevance that became a fundamental part of R. This group of packages are commonly known as the "tidyverse" and they were developed by the New Zealander statistician Hadley Wickham, one of the most relevant figures when it comes to R.

On the next sections, I will show some examples using the tidyverse, so I recommend you install those packages.

```{r, results = "hide"}
# install.packages("tidyverse")

```

It is possible that R will ask you a couple of questions about installing things that need compilation. Just say no. Once installed, remember to load the packages. I always recommend to load the tidyverse in every R session.

```{r}
library(tidyverse)
```
\newpage

# Paths and Directories

Before beginning to work with external files, is better to first understand how to work with directories, that is, the places of your computer where your files are stored (e.g. your desktop). It is highly recommended to have an entire folder exclusively for a specific project with a relevant name. On the other hand, a path is just the way you refer to a specific place in your computer. There are a few differences between Mac/Linux and Windows that you should have in mind:

- The most important difference is how to separate the elements of a path. In Mac and Linux you use slashes (e.g. plots/plot1.pdf) while Windows uses backslashes (e.g. "plots\\plot1.pdf"). In R you can use both independently of your platform, so I recommend you to just use regular slashes because backslashes mean something special for R so when specifying the path you must put two (so annoying!).
- Absolute paths: They indicate the same place regardless of your current working directory. In Windows absolute paths begin with the letter of one of your hard drives (e.g. C:) or two backslashes (e.g. \\\\servername), while in Mac/Linux they begin with a slash (e.g. /users/JM). I suggest to NEVER use absolute paths in your scripts because they make reproducibility difficult. No one will have the same directory as yours.
- A minor detail is that the "~" symbol indicates the home directory in Mac/Linux, while in Windows it indicates the Documents folder.

To know what's your current working directory you can use the function getwd(). This will print an absolute path in the console.

```{r}
getwd()
```

If you want to specify a different working directory from your current one you can use the function setwd(). I suggest using a relative path.
```{r}
setwd("/Users/josemanuel/Documents/R Workshop") # This is an absolute path
```

Personally, I recommend to use R projects instead of setting the working directory explicitly. In the next section I explain how to create an R project.

## R projects

The easiest way to have your files well organized is to create an "R project". Creating one through Rstudio is quite simple, just follow these steps:

1. Click on "File".
2. Select "New Project".
3. Indicate that you want a new directory. A folder for your new project will be created.
4. Select that you want an empty project.
5. Name your directory and specify its path.

Once created, use getwd() to verify that your current directory is the one you specified. In this directory, a ".Rproj" file will be saved. This will allow you to resume your work with the same command history. On the other hand, your global environment should be clean thanks to the advice I have you in the section "[Creating objects]".
\newpage


# Importing data

There is a great variety of functions to use for importing data into R. For practical purposes I will focus in importing tabular data (e.g. spreadsheets). I'll present four main functions for this:

- read.table()
- read.delim()
- read.csv() 
- read_excel()

## Using read.table()

You can use read.table() to import a great variety of files, including text files (i.e. ".txt"). This is one of the most basic ways to get data into R. Despite being archaic, is still one of the most used methods thanks to its interoperability (i.e., any computer can use text files). The output of the function is a data frame.

To use this function you must specify the path to the file. The other arguments have default values. In the next example, I change the default values according to the file I want to import.

```{r}
read.table("Example.txt",    # Path to the file
           header = TRUE,    # Do my columns have names? In this case, yes
           sep = ";",        # Rows are separated by a ";"
           dec = ",")        # Decimals are designed by ","
```

I highly recommend opening the file with your notes app or your equivalent program beforehand to see for yourself what separator is being used, how decimals are specified, and whether columns have names. Also, be sure to check the help page of this function to see the default values for the arguments. You can access the help page by running the command ?read.table()

REMEMBER to always put the format of your file in the path to the file (e.g., "file.txt").

Additional arguments: You may want to specify some non-numeric columns to be read as factors. You can do this in two ways.

- The "stringsAsFactors" argument: If TRUE, reads all character vectors as factors.
- The "colClasses" argument: You can specify the classes of your columns in the form of a character vector.

The next two functions are essentially identical to read.table(), but they have other default values for some of the arguments.

## Using read.delim()

It is ideal for reading text files in which fields are separated by tabs. Moreover, in this function the default value for header is TRUE.

```{r}
read.delim("Example2.txt")
```

## Using read.csv()

As its name says, this function was meant to import "comma delimited files" (i.e., comma separated values, or csv). A spreadsheet could be easily saved as a csv file, being a very useful way to get data into R. Header is TRUE by default and the separator is "," by default.

```{r}
read.csv("capitals.csv",   # Path to the file
         sep = ";",        # Rows are separated by a ";"
         dec = ",")        # Decimals are designed by a ","
```

To save a spreadsheet as a csv (e.g., using Microsoft Excel) you can specify it in: "File", "Save as", and specifying the relevant CSV format (comma delimited). Only one sheet at a time can be saved in csv files. If your spreadsheet has more than one sheet, you will need to copy the one you want to save in a new file to save it as a csv. Alternatively, you can use the next function.

If by this point you have already checked the help page of read.table(), you may have notice the existence of read.csv2() and read.delim2(). These two functions differ from the ones we just saw mainly in the default decimal separator they use (i.e., the "dec" argument). These functions expect a comma for decimal points instead of a point. In the case of read.csv2(), this forces the separator of columns to be a semicolon instead of a comma.

## Using read_excel()

This function is part of the package readxl. In general, is not a good practice to import data from excel files (i.e. .xlsx or .xls) for reproducibility reasons, but it could be very useful to let your original data untouched and avoid having to save each sheet as a separate csv file.

To use this function, you must specify the name of the file, the sheet you want to read, and the range of cells you want to read.

```{r}
library(readxl)

read_excel("data2.xlsx",             # Path to the file
           sheet = 1,                # Sheet to read (you can also put the name on quotes)
           range = "A2:E7")          # Range of cells to read

```

You may notice that the result has a peculiar format. This is because the output is not a data frame, instead, is a new class of object named "tibble". A tibble is a modified data frame with certain advantages. Most functions from the tidyverse use tibbles as the default data object (whether as an input or an output), so this function is a good match with the tidyverse.
\newpage

# Built-in datasets in R

R comes by default with a series of datasets that you can use. This datasets are part of a base R package called "datasets". To obtain a complete list of the datasets you can run this code: library(help = "datasets"). A new tab will appear in the script panel of Rstudio showing the list of datasets along with a brief description of each of them. These datasets can be called by their names. As an example, I will show you the data contained in the "cars" dataset.

```{r}
head(cars)  # Using the function head() to show only the first 6 rows and save space
```

To learn more about a specific dataset, you can do the same as with functions, write its name preceded by a "?" (e.g. ?cars).
\newpage

# Exploring data in R

A lot of times we need to use data that was not generated by us and, therefore, that we are not familiar with. Before performing any kind of analysis it's critical to have a very clear notion of how the data is organized. I'm going to introduce you to a series of very useful functions when it comes to exploring datasets. As an example, I'm going to use a very classic dataset called "iris".

```{r}
head(iris)     # The first 6 rows 
tail(iris)     # The last 6 rows
dim(iris)      # The number of rows and columns, respectively
names(iris)    # The column names
```

A very useful function that you will use all the time is summary(). As you may guess, it gives you a summary of the object that you give as an argument. You can use any kind of object with summary() since it is a generic function. If you use it with a dataset, it will give you a little summary for each of the variables that make the dataset (i.e. each column). This is because, in general, variables may be of different classes (i.e. numerical, categorical, ordinal, etc.).

```{r}
summary(iris)  # Summary of the dataset by column
```

In the case of iris, the first 4 columns are numerical. By default, summary() gives you the minimum, maximum, the mean, the median, the first quintile, and the third quintile. On the other hand, for the last column, which is categorical, it gives you the number of observations of each category (similar to the output of table()).

Another very useful function is str(), which details the structure of an object. This function is also a generic function. In the case of iris, it shows the dimensions of the dataset, the class of each of the columns (4 numerical and 1 factor), and its components.

```{r}
str(iris)      # A more detailed summary
```

Finally, the function table() is useful to quantify the number of observations of a categorical variable. In iris, we see how many times each species is replicated in the dataset. This is a very efficient way of figuring out whether the experimental design is balanced or not (i.e. if each level has exactly the same number of replicates). 

```{r}
table(iris$Species, useNA = "ifany")    # Number of observations for each species
                                        # useNA reports the number of NAs

```
\newpage

# Suggested readings

I strongly recommend that you check some of these titles. I focused on those that have personally helped me the most. I excluded those related with statistical analyses since that topic will be discussed on a different document.

1) Hands-On Programming with R: Write your own functions and simulations. Garret Grolemund (2014): Excellent introduction for learning how to "truly" program in R. Very friendly with inexperienced users, increasing significantly the pace of learning. Garret was a Ph.D. student of Hadley Wickham, he works in Rstudio and is author of several packages.

2) Data Wrangling with R. Bradley C. Boehmke (2016): 90% of the time that we spend in R is just data manipulation. This book makes life easier being an excellent guide to solve questions and get you unstucked. Also useful to strengthen the basics of R.

3) R Programming for Data Science. Roger Peng (2019): A bible when it comes to learning R. Topics are treated with more depth and with an exceptional clarity. Roger Peng is a veteran in R being a user since the 90s. He is Professor in statistical sciences at John Hopkin's University.
\newpage

# APENDIX

## Functions used in this document

```{r, echo=FALSE}
primitives <- data.frame(action = c("sum", "subtraction", "product", "division", "power", "sequence of integers", "assign", "subset", "subset with simplification", "subset by name in lists and data frames"))

rownames(primitives) <- c("+", "-", "*", "/", "^", ":", "<-", "[", "[[", "$")

knitr::kable(primitives, booktabs = TRUE, caption = "Primitives")
```

```{r, echo = FALSE}
l.tests <- data.frame(action = c("equality test", "inequality test", "greater than", "lesser than", "greater or equal than", "lesser or equal than", "belonging test"))

rownames(l.tests) <- c("==", "!=", ">", "<", ">=", "<=", "%in%")

knitr::kable(l.tests, booktabs = TRUE, caption = "Logical tests")
```



Named functions

- class() 
- c()
- length()
- vector()
- as.character()
- as.logical()
- as.numeric()
- attributes()
- names()
- vector()
- matrix()
- dim()
- cbind()
- rbind()
- rownames()
- colnames()
- list()
- data.frame()
- install.packages()
- library()
- getwd()
- setwd()
- read.table()
- read.delim()
- read.csv()
- read_excel()
- head()
- tail()
- summary()
- str()
- table()






