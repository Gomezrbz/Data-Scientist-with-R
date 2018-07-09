# Vectors

## Create a vector 

On your way from rags to riches, you will make extensive use of vectors. Vectors are one-dimension arrays that can hold numeric data, character data, or logical data. In other words, a vector is a simple tool to store data. For example, you can store your daily gains and losses in the casinos. 

In R, you create a vector with the combine function** c()**. You place the vector elements separated by a comma between the parentheses. For example: 

numeric_vector <- c(1, 2, 3)character_vector <- c("a", "b", "c") 

Once you have created these vectors in R, you can use them to do calculations. 

**Intructions**: 

Complete the code such that boolean_vector contains the three elements: TRUE, FALSE and TRUE (in that order). 

**Answer**: 

numeric_vector <- c(1, 10, 49) 

character_vector <- c("a", "b", "c") 

'#' Complete the code for boolean_vector 

boolean_vector <-c(TRUE,FALSE,TRUE) 

## Naming a vectorNaming a vector 

As a data analyst, it is important to have a clear view on the data that you are using. Understanding what each element refers to is therefore essential. 

You can give a name to the elements of a vector with the names() function. Have a look at this example: 

some_vector <- c("John Doe", "poker player")names(some_vector) <- c("Name", "Profession") 

This code first creates a vector some_vector and then gives the two elements a name. The first element is assigned the name Name, while the second element is labeled Profession. Printing the contents to the console yields following output: 

         Name     Profession     "John Doe" "poker player"  

**Intructions**: 

The code names the elements in poker_vectorwith the days of the week. Add code to do the same thing for roulette_vector. 

**Answer**: 

'#' Poker winnings from Monday to Friday 

poker_vector <- c(140, -50, 20, -120, 240) 

'#' Roulette winnings from Monday to Friday 

roulette_vector <- c(-24, -50, 100, -350, 10) 

'#' Assign days as names of poker_vector 

names(poker_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday") 

'#' Assign days as names of roulette_vectors 

names(roulette_vector)<- c("Monday", "Tuesday","Wednesday","Thursday","Friday") 


## How to easily name a variable 

If you want to become a good statistician, you have to become lazy. (If you are already lazy, chances are high you are one of those exceptional, natural-born statistical talents.) 

In the previous exercises you probably experienced that it is boring and frustrating to type and retype information such as the days of the week. However, when you look at it from a higher perspective, there is a more efficient way to do this, namely, to assign the days of the week vector to a **variable**! 

Just like you did with your poker and roulette returns, you can also create a variable that contains the days of the week. This way you can use and re-use it. 

**Intructions**: 

A variable days_vector that contains the days of the week has already been created for you. 

Use days_vector to set the names of poker_vector and roulette_vector. 

 
**Answer**: 

'#' Poker winnings from Monday to Friday 

poker_vector <- c(140, -50, 20, -120, 240) 

'#' Roulette winnings from Monday to Friday 

roulette_vector <- c(-24, -50, 100, -350, 10) 

'#' The variable days_vector 

days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday") 

'#' Assign the names of the day to roulette_vector and poker_vector 

names(poker_vector) <- days_vector 

names(roulette_vector) <- days_vector 

 

## Calculating totals 

Now that you have the poker and roulette winnings nicely as named vectors, you can start doing some data analytical magic. 

You want to find out the following type of information: 

How much has been your overall profit or loss per day of the week? 

Have you lost money over the week in total? 

Are you winning/losing money on poker or on roulette? 

To get the answers, you have to do arithmetic calculations on vectors. 

It is important to know that if you sum two vectors in R, it takes the element-wise sum. For example, the following three statements are completely equivalent: 

c(1, 2, 3) + c(4, 5, 6)c(1 + 4, 2 + 5, 3 + 6)c(5, 7, 9) 

You can also do the calculations with variables that represent vectors: 

a <- c(1, 2, 3) b <- c(4, 5, 6)c <- a + b 

 

**Intructions**: 

Take the sum of the variables A_vector and B_vector and it assign to total_vector. 

Inspect the result by printing out total_vector. 

**Answer**: 

A_vector <- c(1, 2, 3) 

B_vector <- c(4, 5, 6) 

'#' Take the sum of A_vector and B_vector 

total_vector <- A_vector + B_vector 

'#' Print out total_vector 

total_vector 

## Vector selection 

To select elements of a vector (and later matrices, data frames, ...), you can use square brackets. Between the square brackets, you indicate what elements to select. For example, to select the first element of the vector, you type poker_vector[1]. To select the second element of the vector, you type poker_vector[2], etc. Notice that the first element in a vector has index 1, not 0 as in many other programming languages. 

**Intructions**: 

Assign the poker results of Wednesday to the variable poker_wednesday. 

**Answer**: 

'#' Poker and roulette winnings from Monday to Friday: 

poker_vector <- c(140, -50, 20, -120, 240) 

roulette_vector <- c(-24, -50, 100, -350, 10) 

days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday") 

names(poker_vector) <- days_vector 

names(roulette_vector) <- days_vector 

'#' Define a new variable based on a selection 

poker_wednesday <- poker_vector[3] 

 