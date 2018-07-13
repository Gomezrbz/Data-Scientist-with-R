# Lists
## What is a list

A list in R allows you to gather a variety of objects under one name (that is, the name of the list) in an ordered way. These objects can be matrices, vectors, data frames, even other lists, etc. It is not even required that these objects are related to each other in any way.

You could say that a list is some kind super data type: you can store practically any piece of information in it
## Creating a List

Let us create our first list! To construct a list you use the function list():

my_list <- list(comp1, comp2 ...)
The arguments to the list function are the list components. Remember, these components can be matrices, vectors, other lists, ...

**Instructions**
Construct a list, named my_list, that contains the variables my_vector, my_matrix and my_df as list components.

**Answers:**
```
# Vector with numerics from 1 up to 10
my_vector <- 1:10 

# Matrix with numerics from 1 up to 9
my_matrix <- matrix(1:9, ncol = 3)

# First 10 elements of the built-in data frame mtcars
my_df <- mtcars[1:10,]

# Construct list with these different elements:
my_list <- list(my_vector,my_matrix,my_df)
```
## Creating a named list
Well done, you're on a roll!

Just like on your to-do list, you want to avoid not knowing or remembering what the components of your list stand for. That is why you should give names to them:
```
my_list <- list(name1 = your_comp1, 
                name2 = your_comp2)
```
This creates a list with components that are named name1, name2, and so on. If you want to name your lists after you've created them, you can use the names() function as you did with vectors. The following commands are fully equivalent to the assignment above:
```
my_list <- list(your_comp1, your_comp2)
names(my_list) <- c("name1", "name2")
```

**Instructions**
- Change the code of the previous exercise (see editor) by adding names to the components. Use for my_vector the name vec, for my_matrix the name mat and for my_df the name df.
- Print out my_list so you can inspect the output.

**Answers:**
```
# Vector with numerics from 1 up to 10
my_vector <- 1:10 

# Matrix with numerics from 1 up to 9
my_matrix <- matrix(1:9, ncol = 3)

# First 10 elements of the built-in data frame mtcars
my_df <- mtcars[1:10,]

# Adapt list() call to give the components names
my_list <- list(my_vector, my_matrix, my_df)
names(my_list) <- c("vec","mat","df")

# Print out my_list
my_list
```
## Selecting elements from a list
Your list will often be built out of numerous elements and components. Therefore, getting a single element, multiple elements, or a component out of it is not always straightforward.

One way to select a component is using the numbered position of that component. For example, to "grab" the first component of shining_list you type

shining_list[[1]]
A quick way to check this out is typing it in the console. Important to remember: to select elements from vectors, you use single square brackets: [ ]. Don't mix them up!

You can also refer to the names of the components, with [[ ]] or with the $ sign. Both will select the data frame representing the reviews:
```
shining_list[["reviews"]]
shining_list$reviews
```
Besides selecting components, you often need to select specific elements out of these components.

**Instructions**
- Select from shining_list the vector representing the actors. Simply print out this vector.
- Select from shining_list the second element in the vector representing the actors. Do a printout like before.

**Answers:**
```
# Print out the vector representing the actors
shining_list$actors

# Print the second element of the vector representing the actors
shining_list$actors[2]
```
## Adding more movie information to the list

To conveniently add elements to lists you can use the c() function, that you also used to build vectors:
```
ext_list <- c(my_list , my_val)
```
This will simply extend the original list, my_list, with the component my_val. This component gets appended to the end of the list. If you want to give the new list item a name, you just add the name as you did before:
```
ext_list <- c(my_list, my_name = my_val)
```

**Instructions**
- Complete the code below such that an item named year is added to the shining_list with the value 1980. Assign the result to shining_list_full.
- Finally, have a look at the structure of shining_list_full with the str() function.

**Answers:**
```
# We forgot something; add the year to shining_list
shining_list_full <- c(shining_list, year = 1980)

# Have a look at shining_list_full
str(shining_list_full)
```