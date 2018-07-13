# Data Frame
## What's a data frame?
You may remember from the chapter about matrices that all the elements that you put in a matrix should be of the same type. Back then, your data set on Star Wars only contained numeric elements.

When doing a market research survey, however, you often have questions such as:

'Are your married?' or 'yes/no' questions (logical)
'How old are you?' (numeric)
'What is your opinion on this product?' or other 'open-ended' questions (character)
...
The output, namely the respondents' answers to the questions formulated above, is a data set of different data types. You will often find yourself working with data sets that contain different data types instead of only one.

A data frame has the variables of a data set as columns and the observations as rows. This will be a familiar concept for those coming from different statistical software packages such as SAS or SPSS.

Working with large data sets is not uncommon in data analysis. When you work with (extremely) large data sets and data frames, your first task as a data analyst is to develop a clear understanding of its structure and main elements. Therefore, it is often useful to show only a small part of the entire data set.

So how to do this in R? Well, the function head() enables you to show the first observations of a data frame. Similarly, the function tail() prints out the last observations in your data set.

Both head() and tail() print a top line called the 'header', which contains the names of the different variables in your data set.

**Instructions**
Call head() on the mtcars data set to have a look at the header and the first observations.

**Answers:**
```
# Call head() on mtcars
head(mtcars)
```
## Have a look at the structure
Another method that is often used to get a rapid overview of your data is the function str(). The function str() shows you the structure of your data set. For a data frame it tells you:

The total number of observations (e.g. 32 car types)
The total number of variables (e.g. 11 car features)
A full list of the variables names (e.g. mpg, cyl ... )
The data type of each variable (e.g. num)
The first observations
Applying the str() function will often be the first thing that you do when receiving a new data set or data frame. It is a great way to get more insight in your data set before diving into the real analysis.

As a first goal, you want to construct a data frame that describes the main characteristics of eight planets in our solar system. According to your good friend Buzz, the main features of a planet are:

- The type of planet (Terrestrial or Gas Giant).
- The planet's diameter relative to the diameter of the Earth.
- The planet's rotation across the sun relative to that of the Earth.
- If the planet has rings or not (TRUE or FALSE).

After doing some high-quality research on Wikipedia, you feel confident enough to create the necessary vectors: name, type, diameter, rotation and rings; these vectors have already been coded up on the right. The first element in each of these vectors correspond to the first observation.

You construct a data frame with the data.frame() function. As arguments, you pass the vectors from before: they will become the different columns of your data frame. Because every column has the same length, the vectors you pass should also have the same length. But don't forget that it is possible (and likely) that they contain different types of data.

**Instructions**

Use the function data.frame() to construct a data frame. Pass the vectors name, type, diameter, rotation and rings as arguments to data.frame(), in this order. Call the resulting data frame planets_df.

**Answers:**
```
# Definition of vectors
name <- c("Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune")
type <- c("Terrestrial planet", "Terrestrial planet", "Terrestrial planet", 
          "Terrestrial planet", "Gas giant", "Gas giant", "Gas giant", "Gas giant")
diameter <- c(0.382, 0.949, 1, 0.532, 11.209, 9.449, 4.007, 3.883)
rotation <- c(58.64, -243.02, 1, 1.03, 0.41, 0.43, -0.72, 0.67)
rings <- c(FALSE, FALSE, FALSE, FALSE, TRUE, TRUE, TRUE, TRUE)

# Create a data frame from the vectors
planets_df <- data.frame(name, type, diameter, rotation, rings)

planets_df
```
## Selection of data frame elements
Similar to vectors and matrices, you select elements from a data frame with the help of square brackets [ ]. By using a comma, you can indicate what to select from the rows and the columns respectively. For example:

- my_df[1,2] selects the value at the first row and second column in my_df.
- my_df[1:3,2:4] selects rows 1, 2, 3 and columns 2, 3, 4 in my_df.

Sometimes you want to select all elements of a row or column. For example, my_df[1, ] selects all elements of the first row.

Instead of using numerics to select elements of a data frame, you can also use the variable names to select columns of a data frame.

Suppose you want to select the first three elements of the type column. One way to do this is
```
planets_df[1:3,2]
```
A possible disadvantage of this approach is that you have to know (or look up) the column number of type, which gets hard if you have a lot of variables. It is often easier to just make use of the variable name:
```
planets_df[1:3,"type"]
```
**Instructions**

- From planets_df, select the diameter of Mercury: this is the value at the first row and the third column. Simply print out the result.
- From planets_df, select all data on Mars (the fourth row). Simply print out the result.
- Select and print out the first 5 values in the "diameter" column of planets_df.

**Answers:**
```
# Print out diameter of Mercury (row 1, column 3)
planets_df[1,3]

# Print out data for Mars (entire fourth row)
planets_df[4,]

# Select first 5 values of diameter column
planets_df[1:5, "diameter"]
```
## Selecting of data frame elements (2)
You will often want to select an entire column, namely one specific variable from a data frame. If you want to select all elements of the variable diameter, for example, both of these will do the trick:
```
planets_df[,3]
planets_df[,"diameter"]
```
However, there is a short-cut. If your columns have names, you can use the $ sign:
```
planets_df$diameter
```
**Instructions**
- Use the $ sign to select the rings variable from planets_df. Store the vector that results as rings_vector.
- Print out rings_vector to see if you got it right.
**Answers:**
```
# Select the rings variable from planets_df
rings_vector <-  planets_df$rings
  
# Print out rings_vector
rings_vector
```
## Subset
```
ubset(my_df, subset = some_condition)
```
The first argument of subset() specifies the data set for which you want a subset. By adding the second argument, you give R the necessary information and conditions to select the correct subset.

The code below will give the exact same result as you got in the previous exercise, but this time, you didn't need the rings_vector!
```
subset(planets_df, subset = rings)
```
**Instructions**
Use subset() on planets_df to select planets that have a diameter smaller than Earth. Because the diameter variable is a relative measure of the planet's diameter w.r.t that of planet Earth, your condition is diameter < 1.

**Answers:**
```
# Select planets with diameter < 1
subset(planets_df, diameter < 1)
```
## Sorting
In data analysis you can sort your data according to a certain variable in the data set. In R, this is done with the help of the function order().

order() is a function that gives you the ranked position of each element when it is applied on a variable, such as a vector for example:
```
> a <- c(100, 10, 1000)
> order(a)
[1] 2 1 3
```
10, which is the second element in a, is the smallest element, so 2 comes first in the output of order(a). 100, which is the first element in a is the second smallest element, so 1 comes second in the output of order(a).

This means we can use the output of order(a) to reshuffle a:
```
> a[order(a)]
[1]   10  100 1000
```
Call order() on planets_df$diameter (the diameter column of planets_df). Store the result as positions.
Now reshuffle planets_df with the positions vector as row indexes inside square brackets. Keep all columns. Simply print out the result.
**Instructions**
- Experiment with the order() function in the console. Click 'Submit Answer' when you are ready to continue.
- Call order() on planets_df$diameter (the diameter column of planets_df). Store the result as positions.
- Now reshuffle planets_df with the positions vector as row indexes inside square brackets. Keep all columns. Simply print out the result.

**Answers:**
```
# Elements
b <- c(1,8,5,6,7,4,3,2,9)

# Print the indexes ordered
order <- c(order(b))

# Print the elements ordered.
b[order]

# Use order() to create positions
positions <-  order(planets_df$diameter)

# Use positions to sort planets_df
planets_df[positions,]
```