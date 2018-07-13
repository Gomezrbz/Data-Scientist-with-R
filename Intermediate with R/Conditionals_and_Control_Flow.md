# Conditionals and Control Flow
## Relational Operators

Relational Operators are operators which help you to see the relation between one object and other.

- Check if two objects are equal(==) or inequal(!=).
    - Strings
    - Numbers
    - logicals
    - others
- Check if it is greater, lower with < and >
    - In string for deafault is by alphabetical order.
    - In logic it is True > False.
 **NOTE** Remember you can also review if and object is greater than or equal to (>=) or less than or equal to(<=) 
- Compare a value to all the values of a vector is also possible or vector VS vector.
## Equality
The most basic form of comparison is equality.
``` 
3 == (2 + 1)
"intermediate" != "r"
TRUE != FALSE
"Rchitect" != "rchitect"
```

** Instructions**
- Write R code to see if TRUE equals FALSE.
- Check if -6 * 14 is not equal to 17 - 101.
- Comparison of character strings. Ask R whether the strings "useR" and "user" are equal.
- Find out what happens if you compare logicals to numerics: are TRUE and 1 equal?

** Answers**
```
# Comparison of logicals
TRUE == FALSE

# Comparison of numerics
-6*14 != 17-101

# Comparison of character strings
"useR" == "user"

# Compare a logical with a numeric
TRUE == 1
```
## Greater and less than

Apart from equality operators,there are the less than and greater than operators: < and >. You can also add an equal sign to express less than or equal to or greater than or equal to, respectively. Have a look at the following R expressions, that all evaluate to FALSE:

```
(1 + 2) > 4
"dog" < "Cats"
TRUE <= FALSE
```

Remember that for string comparison, R determines the greater than relationship based on alphabetical order. Also, keep in mind that TRUE corresponds to 1 in R, and FALSE coerces to 0 behind the scenes. Therefore, FALSE < TRUE is TRUE.

** Instructions**
1- What is the result of the following scenarios?

- -6 * 5 + 2 is greater than or equal to -10 + 1.
- "raining" is less than or equal to "raining dogs".
- TRUE is greater than FALSE.

2- Using relational operators, find a logical answer, i.e. TRUE or FALSE, for the following questions:

- On which days did the number of LinkedIn profile views exceed 15?
- When was your LinkedIn profile viewed only 5 times or fewer?
- When was your LinkedIn profile visited more often than your Facebook profile?

** Answers**
```
# 1
# Comparison of numerics
-6*5+2 >= -10 + 1

# Comparison of character strings
"raining" <= "raining dogs"

# Comparison of logicals
TRUE > FALSE

# 2
# The linkedin and facebook vectors have already been created for you
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)

# Popular days
linkedin > 15

# Quiet days
linkedin <= 5

# LinkedIn more popular than Facebook
linkedin > facebook
```
## Compare matrices
R's ability to deal with different data structures for comparisons does not stop at vectors. Matrices and relational operators also work together seamlessly!

Instead of in vectors (as in the previous exercise), the LinkedIn and Facebook data is now stored in a matrix called views. The first row contains the LinkedIn information; the second row the Facebook information. The original vectors facebook and linkedin are still available as well.

** Instructions**

Using the relational operators you've learned so far, try to discover the following:

- When were the views exactly equal to 13? Use the views matrix to return a logical matrix.
- For which days were the number of views less than or equal to 14? Again, have R return a logical matrix.
** Answers**
```
# The social data has been created for you
linkedin <- c(16, 9, 13, 5, 2, 17, 14)
facebook <- c(17, 7, 5, 16, 8, 13, 14)
views <- matrix(c(linkedin, facebook), nrow = 2, byrow = TRUE)

# When does views equal 13?
views == 13

# When is views less than or equal to 14?
views <= 14
```
## Logical Operators

This are used to change or combine the results of comparisons.

- AND operator &
    - Returns two logical values and returns TRUE only if both logical values are TRUE
- OR operator |
    - Returns two logical values and returns TRUE when at least one of them is TRUE.
- NOT operator !
    - Negates the logical value that has as the entry.
## & and |
Before you work your way through the next exercises, have a look at the following R expressions. All of them will evaluate to TRUE:

TRUE & TRUE
FALSE | TRUE
5 <= 5 & 2 < 3
3 < 4 | 7 < 6
Watch out: 3 < x < 7 to check if x is between 3 and 7 will not work; you'll need 3 < x & x < 7 for that.

** Instructions**
1- Write R expressions to solve the following questions concerning the variable last:

- Is last under 5 or above 10?
- Is last between 15 and 20, excluding 15 but including 20?

2- Write R expressions to solve the following questions:
- Select the entire second column, named day2, from the li_df data frame as a vector and assign it to second.
- Use second to create a logical vector, that contains TRUE if the corresponding number of views is strictly greater than 25 or strictly lower than 5 and FALSE otherwise. Store this logical vector as extremes.
- Use sum() on the extremes vector to calculate the number of TRUEs in extremes (i.e. to calculate the number of employees that are either very popular or very low-profile). Simply print this number to the console.

** Answers**
```
# 1
# The linkedin and last variable are already defined for you
linkedin <- c(16, 9, 13, 5, 2, 17, 14)

# tail(vector, number of values)
last <- tail(linkedin, 1)
last

# Is last under 5 or above 10?
last < 5 | last > 10

# Is last between 15 (exclusive) and 20 (inclusive)?
last > 15 & last <= 20

#2

# Select the second column, named day2, from li_df: second
second <- li_df$day2

# Build a logical vector, TRUE if value in second is extreme: extremes
extremes <- second > 25 | second < 5

# Count the number of TRUEs in extremes
sum(extremes)

# Solve it with a one-liner
sum(second > 25 | second < 5)
```
## The if statement

Syntax:
```
if (condition) {
  expr
}
```

** Instructions**
- Examine the if statement that prints out "Showing LinkedIn information" if the medium variable equals "LinkedIn".
- Code an if statement that prints "You're popular!" to the console if the num_views variable exceeds 15.

** Answers**
```
# Variables related to your last day of recordings
medium <- "LinkedIn"
num_views <- 14

# Examine the if statement for medium
if (medium == "LinkedIn") {
  print("Showing LinkedIn information")
}

# Write the if statement for num_views
if (num_views > 15) {
  print("You're popular!")
}
```
## Add an else
You can only use an else statement in combination with an if statement. The else statement does not require a condition; its corresponding code is simply run if all of the preceding conditions in the control structure are FALSE. Here's a recipe for its usage:
```
if (condition) {
  expr1
} else {
  expr2
}
```
**Note** It's important that the else keyword comes on the same line as the closing bracket of the if part!

** Instructions**
Add an else statement to both control structures, such that
- "Unknown medium" gets printed out to the console when the if-condition on medium does not hold.
- R prints out "Try to be more visible!" when the if-condition on num_views is not met.

** Answers**
```
# Variables related to your last day of recordings
medium <- "LinkedIn"
num_views <- 14

# Control structure for medium
if (medium == "LinkedIn") {
  print("Showing LinkedIn information")
} else {
  print("Unknown medium")
}

# Control structure for num_views
if (num_views > 15) {
  print("You're popular!")
} else {
  print("Try to be more visible!")
```
## else if
The else if statement allows you to further customize your control structure. You can add as many else if statements as you like. Keep in mind that R ignores the remainder of the control structure once a condition has been found that is TRUE and the corresponding expressions have been executed. Here's an overview of the syntax to freshen your memory:
```
if (condition1) {
  expr1
} else if (condition2) {
  expr2
} else if (condition3) {
  expr3
} else {
  expr4
}
```
**Note** Again, It's important that the else if keywords comes on the same line as the closing bracket of the previous part of the control construct!

** Instructions**
Add code to both control structures such that:

- R prints out "Showing Facebook information" if medium is equal to "Facebook". Remember that R is case sensitive!
- "Your number of views is average" is printed if num_views is between 15 (inclusive) and 10 (exclusive). Feel free to change the variables medium and num_views to see how the control structure respond. In both cases, the existing code should be extended in the else if statement. No existing code should be modified.
** Answers**
```
# Variables related to your last day of recordings
medium <- "LinkedIn"
num_views <- 14

# Control structure for medium
if (medium == "LinkedIn") {
  print("Showing LinkedIn information")
} else if (medium == "Facebook") {
  # Add code to print correct string when condition is TRUE
  print("Showing Facebook Information")
} else {
  print("Unknown medium")
}

# Control structure for num_views
if (num_views > 15) {
  print("You're popular!")
} else if (num_views <= 15 & num_views > 10) {
  # Add code to print correct string when condition is TRUE
  print("Your number of views is average")
} else {
  print("Try to be more visible!")
}
```