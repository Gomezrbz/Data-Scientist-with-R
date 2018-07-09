#Introduction to R 

## How it works 

R makes use of the # sign to add comments, so that you and others can understand what the R code is about. Just like Twitter! Comments are not run as R code, so they will not influence your result. For example, Calculate 3 + 4 in the editor on the right is a comment. 
 
**Intructions**: 

In the editor on the right there is already some sample code. Can you see which lines are actual R code and which are comments? 

Add a line of code that calculates the sum of 6 and 12. 

**Answer**: 

'#' Calculate 3 + 4 

3 + 4 

'#' Calculate 6 + 12 

6 + 12 

## Arithmetic with R 

In its most basic form, R can be used as a simple calculator. Consider the following arithmetic operators: 

Addition: + 

Subtraction: - 

Multiplication: * 

Division: / 

Exponentiation: ^ 

Modulo: %% 

The last two might need some explaining: 

The ^ operator raises the number to its left to the power of the number to its right: for example 3^2 is 9. 

The modulo returns the remainder of the division of the number to the left by the number on its right, for example 5 modulo 3 or 5 %% 3 is 2. 

 

**Intructions**: 

Type 2^5 in the editor to calculate 2 to the power 5. 

Type 28 %% 6 to calculate 28 modulo 6. 

Note how the # symbol is used to add comments on the R code. 

 

**Answer**: 

'#' An addition 

5 + 5  

'#' A subtraction 

5 - 5  

'#' A multiplication 

3 * 5 

'#' A division 

(5 + 5) / 2  

'#' Exponentiation 

2^5 

'#' Modulo 

28 %% 6 

## Variable assignment 

A basic concept in (statistical) programming is called a variable. 

A variable allows you to store a value (e.g. 4) or an object (e.g. a function description) in R. You can then later use this variable's name to easily access the value or the object that is stored within this variable. 

You can assign a value 4 to a variable my_var with the command 

my_var <- 4 

 

**Intructions**: 

Over to you: complete the code in the editor such that it assigns the value 42 to the variable x in the editor. Click 'Submit Answer'. Notice that when you ask R to print x, the value 42 appears. 

 

**Answer**: 

'#' Assign the value 42 to x 

x <- 42  

'#' Print out the value of the variable x 

X 

## Basic data types in R 

R works with numerous data types. Some of the most basic types to get started are: 

Decimals values like 4.5 are called **numerics**. 

Natural numbers like 4 are called **integers**. Integers are also numerics. 

Boolean values (TRUE or FALSE) are called **logical**. 

Text (or string) values are called **characters**. 

Note how the quotation marks on the right indicate that "some text" is a character. 

 

**Intructions**: 

Change the value of the: 

my_numeric variable to 42. 

my_character variable to "universe". Note that the quotation marks indicate that "universe" is a character. 

my_logical variable to FALSE. 

 

**Answer**: 

'#' Change my_numeric to be 42 

my_numeric <- 42 

'#' Change my_character to be "universe" 

my_character <- "universe" 

'#' Change my_logical to be FALSE 

my_logical <- FALSE 

 

## What's that data type? 

Do you remember that when you added 5 + "six", you got an error due to a mismatch in data types? You can avoid such embarrassing situations by checking the data type of a variable beforehand. You can do this with the class() function, as the code on the right shows. 

 

**Intructions**: 

Complete the code in the editor and also print out the classes of my_character and my_logical. 

 

**Answer**: 

'#' Declare variables of different types 

my_numeric <- 42 

my_character <- "universe" 

my_logical <- FALSE  

'#' Check class of my_numeric 

class(my_numeric) 

'#' Check class of my_character 

class(my_character) 

'#' Check class of my_logical 

class(my_logical) 

 
