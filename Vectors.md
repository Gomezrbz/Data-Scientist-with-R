# Vectors

## Create a vector 

On your way from rags to riches, you will make extensive use of vectors. Vectors are one-dimension arrays that can hold numeric data, character data, or logical data. In other words, a vector is a simple tool to store data. For example, you can store your daily gains and losses in the casinos. 

In R, you create a vector with the combine function** c()**. You place the vector elements separated by a comma between the parentheses. For example: 

numeric_vector <- c(1, 2, 3)character_vector <- c("a", "b", "c") 

Once you have created these vectors in R, you can use them to do calculations. 

**Intructions**: 

Complete the code such that boolean_vector contains the three elements: TRUE, FALSE and TRUE (in that order). 

**Answer**: 
```
numeric_vector <- c(1, 10, 49) 

character_vector <- c("a", "b", "c") 

# Complete the code for boolean_vector 

boolean_vector <-c(TRUE,FALSE,TRUE) 
```
## Naming a vectorNaming a vector 

As a data analyst, it is important to have a clear view on the data that you are using. Understanding what each element refers to is therefore essential. 

You can give a name to the elements of a vector with the names() function. Have a look at this example: 

some_vector <- c("John Doe", "poker player")names(some_vector) <- c("Name", "Profession") 

This code first creates a vector some_vector and then gives the two elements a name. The first element is assigned the name Name, while the second element is labeled Profession. Printing the contents to the console yields following output: 

        > Name     Profession     "John Doe" "poker player"  

**Intructions**: 

The code names the elements in poker_vectorwith the days of the week. Add code to do the same thing for roulette_vector. 

**Answer**: 
```
# Poker winnings from Monday to Friday 

poker_vector <- c(140, -50, 20, -120, 240) 

# Roulette winnings from Monday to Friday 

roulette_vector <- c(-24, -50, 100, -350, 10) 

# Assign days as names of poker_vector 

names(poker_vector) <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday") 

# Assign days as names of roulette_vectors 

names(roulette_vector)<- c("Monday", "Tuesday","Wednesday","Thursday","Friday") 
```
## How to easily name a variable 

If you want to become a good statistician, you have to become lazy. (If you are already lazy, chances are high you are one of those exceptional, natural-born statistical talents.) 

In the previous exercises you probably experienced that it is boring and frustrating to type and retype information such as the days of the week. However, when you look at it from a higher perspective, there is a more efficient way to do this, namely, to assign the days of the week vector to a **variable**! 

Just like you did with your poker and roulette returns, you can also create a variable that contains the days of the week. This way you can use and re-use it. 

**Intructions**: 

- A variable days_vector that contains the days of the week has already been created for you. 
- Use days_vector to set the names of poker_vector and roulette_vector. 

 
**Answer**: 
```
# Poker winnings from Monday to Friday 

poker_vector <- c(140, -50, 20, -120, 240) 

# Roulette winnings from Monday to Friday 

roulette_vector <- c(-24, -50, 100, -350, 10) 

# The variable days_vector 

days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday") 

# Assign the names of the day to roulette_vector and poker_vector 

names(poker_vector) <- days_vector 

names(roulette_vector) <- days_vector 
```
## Calculating totals 

Now that you have the poker and roulette winnings nicely as named vectors, you can start doing some data analytical magic. 

You want to find out the following type of information: 

- How much has been your overall profit or loss per day of the week? 
- Have you lost money over the week in total? 
- Are you winning/losing money on poker or on roulette? 
- To get the answers, you have to do arithmetic calculations on vectors. 

It is important to know that if you sum two vectors in R, it takes the element-wise sum. For example, the following three statements are completely equivalent: 

c(1, 2, 3) + c(4, 5, 6)c(1 + 4, 2 + 5, 3 + 6)c(5, 7, 9) 

You can also do the calculations with variables that represent vectors: 

a <- c(1, 2, 3) b <- c(4, 5, 6)c <- a + b 

 

**Intructions**: 
- Take the sum of the variables A_vector and B_vector and it assign to total_vector. 
- Inspect the result by printing out total_vector. 

**Answer**: 
```
A_vector <- c(1, 2, 3) 

B_vector <- c(4, 5, 6) 

# Take the sum of A_vector and B_vector 

total_vector <- A_vector + B_vector 

# Print out total_vector 

total_vector 
```
## Vector selection 

To select elements of a vector (and later matrices, data frames, ...), you can use square brackets. Between the square brackets, you indicate what elements to select. For example, to select the first element of the vector, you type poker_vector[1]. To select the second element of the vector, you type poker_vector[2], etc. Notice that the first element in a vector has index 1, not 0 as in many other programming languages. 

**Intructions**: 

Assign the poker results of Wednesday to the variable poker_wednesday. 

**Answer**: 
```
#Poker and roulette winnings from Monday to Friday: 

poker_vector <- c(140, -50, 20, -120, 240) 

roulette_vector <- c(-24, -50, 100, -350, 10) 

days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday") 

names(poker_vector) <- days_vector 

names(roulette_vector) <- days_vector 

# Define a new variable based on a selection 

poker_wednesday <- poker_vector[3] 
```
 ## Select Multiple elements of a Vector
 To select multiple elements from a vector, you can add square brackets at the end of it. You can indicate between the brackets what elements should be selected. For example: suppose you want to select the first and the fifth day of the week: use the vector c(1, 5) between the square brackets. For example, the code below selects the first and fifth element of poker_vector:
```
poker_vector[c(1, 5)]
```
**Intructions**: 
Assign the poker results of Tuesday, Wednesday and Thursday to the variable poker_midweek.

**Answer**: 
```
# Poker and roulette winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Define a new variable based on a selection
poker_midweek <- poker_vector[c(1,2)]
```

## Select Multiple elements of a Vector(Lazy way)
Selecting multiple elements of poker_vector with c(2, 3, 4) is not very convenient. Many statisticians are lazy people by nature, so they created an easier way to do this: c(2, 3, 4) can be abbreviated to2:4, which generates a vector with all natural numbers from 2 up to 4.

So, another way to find the mid-week results is poker_vector[2:4]. Notice how the vector 2:4 is placed between the square brackets to select element 2 up to 4.

**Intructions**: 
Assign to roulette_selection_vector the roulette results from Tuesday up to Friday; make use of : if it makes things easier for you.

**Answer**: 
```
# Poker and roulette winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Define a new variable based on a selection
roulette_selection_vector <- poker_vector[2:4]
```
## Select Multiple elements of a Vector(with names)
Another way to tackle the previous exercise is by using the names of the vector elements (Monday, Tuesday, ...) instead of their numeric positions. For example,
```
poker_vector["Monday"]
```
will select the first element of poker_vector since "Monday" is the name of that first element.

Just like you did in the previous exercise with numerics, you can also use the element names to select multiple elements, for example:
```
poker_vector[c("Monday","Tuesday")]
```

**Intructions**: 
- Select the first three elements in poker_vector by using their names: "Monday", "Tuesday" and "Wednesday". Assign the result of the selection to poker_start.
- Calculate the average of the values in poker_start with the mean() function. Simply print out the result so you can inspect it.

**Answer**: 
```
# Poker and roulette winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Select poker results for Monday, Tuesday and Wednesday
poker_start <- poker_vector[c("Monday","Tuesday","Wednesday")]
  
# Calculate the average of the elements in poker_start
mean(poker_start)
```

## Selection by Comparison
By making use of comparison operators, we can approach the previous question in a more proactive way.

The (logical) comparison operators known to R are:

- < for less than
- > for greater than
- <= for less than or equal to
- >= for greater than or equal to
- == for equal to each other
- != not equal to each other
As seen in the previous chapter, stating 6 > 5 returns TRUE. The nice thing about R is that you can use these comparison operators also on vectors. For example:
```
> c(4, 5, 6) > 5
[1] FALSE FALSE TRUE
```
This command tests for every element of the vector if the condition stated by the comparison operator is TRUE or FALSE
**Intructions**: 
- Check which elements in poker_vector are positive (i.e. > 0) and assign this to selection_vector.
- Print out selection_vector so you can inspect it. The printout tells you whether you won (TRUE) or lost (FALSE) any money for each day.

**Answer**: 
```
# Poker and roulette winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Which days did you make money on poker?
selection_vector <- poker_vector > 0
  
# Print out selection_vector
selection_vector
```

## Selection Comparison(only true vectors)

Working with comparisons will make your data analytical life easier. Instead of selecting a subset of days to investigate yourself (like before), you can simply ask R to return only those days where you realized a positive return for poker.

In the previous exercises you used selection_vector <- poker_vector > 0 to find the days on which you had a positive poker return. Now, you would like to know not only the days on which you won, but also how much you won on those days.

You can select the desired elements, by putting selection_vector between the square brackets that follow poker_vector:
```
poker_vector[selection_vector]
```
R knows what to do when you pass a logical vector in square brackets: it will only select the elements that correspond to TRUE in selection_vector.

**Intructions**: 
Use selection_vector in square brackets to assign the amounts that you won on the profitable days to the variable poker_winning_days.
**Answer**: 
```
# Poker and roulette winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Which days did you make money on poker?
selection_vector <- poker_vector > 0

# Select from poker_vector these days
poker_winning_days <- poker_vector[selection_vector]
```

## Advanced selection
Just like you did for poker, you also want to know those days where you realized a positive return for roulette.

**Intructions**: 
- Create the variable selection_vector, this time to see if you made profit with roulette for different days.
- Assign the amounts that you made on the days that you ended positively for roulette to the variable roulette_winning_days. This vector thus contains the positive winnings of roulette_vector.
**Answer**: 
```
# Poker and roulette winnings from Monday to Friday:
poker_vector <- c(140, -50, 20, -120, 240)
roulette_vector <- c(-24, -50, 100, -350, 10)
days_vector <- c("Monday", "Tuesday", "Wednesday", "Thursday", "Friday")
names(poker_vector) <- days_vector
names(roulette_vector) <- days_vector

# Which days did you make money on roulette?
selection_vector <- roulette_vector > 0

# Select from roulette_vector these days
roulette_winning_days <- roulette_vector[selection_vector]

# Print the result
roulette_winning_days
```