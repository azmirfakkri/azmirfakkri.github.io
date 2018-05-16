---
layout: post
title: "Data Science with R, Part 1: Introduction to R"
output: 
  html_document:
    keep_md: true
    toc: true
    toc_float: true
---



This post is the first part of Data Science with R series.  
All codes are implemented in RStudio. If you are not familiar with R and RStudio, I posted an article on [R and RStudio](https://azmirfakkri.github.io/2018/05/11/R-and-RStudio.html).  

# Introduction to Basics

At the most basic level, you can treat R like a calculator. Let's do a few simple calculations.  

**Addition and Subtraction**

```r
# Addition 
2 + 2
```

```
## [1] 4
```

```r
# Subtraction 
5 - 2
```

```
## [1] 3
```

When you run the two lines, you will get an output for each. Easy. Now that we have touched on simple calculations, these are the operators for multiplication, division and exponentiation.  

**Multiplication - `*`**  

```r
# Example for multiplication
3 * 5
```

```
## [1] 15
```

**Division - `/`**  

```r
# Example for division
10 / 5
```

```
## [1] 2
```

**Exponentiation - `^` or `**`**  

```r
# Example for exponentiation
2 ^ 2
```

```
## [1] 4
```

```r
2 ** 2
```

```
## [1] 4
```

Both operators for exponentiation gave us the same answer.  

However, R is more than just a simple calculator. You can assign this calculations to a variable. Let's use the addition example and assign its value to a variable.  

```r
# Assigning a variable
x <- 2 + 2

# Print value
x
```

```
## [1] 4
```

From this example `x` is a variable that contains the value of the addition which is 4. To print the value of x, simply type `x` in r and it will print the value for you.  

Please note that in R, to assign a variable, we use this sign `<-`. You can also use `=`, but I always prefer to use `<-` in R because when you learn another language like Python, assigning a variable uses `=`. This to me makes a clear distinction of what language I am writing in. But the preference is yours.  
The name of variables can be almost anything but avoid variable names that are reserved for functions in R, to avoid confusion.   

You can also do operations on variables that you have saved. For example adding two variables together.

```r
# Assigning variables
car <- 5 + 5
bike <- 10

# Adding variables 
transport <- car + bike

# Print value of transport
transport
```

```
## [1] 20
```

So far in our examples, we have only dealt with one type of data structure in R, called vectors. There are other types of data structures that R can handle. But first let's learn a little bit more about vectors.  

# Vectors  

## Definition  

Vector is a 1-dimensional array and it is the basic data structure in R. Vector allows you to store data in R and it can take data types including numerics, characters and logical. There are two types of vectors: atomic vectors and lists.  

### Atomic Vectors  

There are four common data types of atomic vectors:  

1. **Integers** - e.g. 5, it is a whole number and not a fraction  
2. **Numerics** - e.g. 5.2, it is also known as double  
3. **Characters** - e.g. "eat", it is referred to as string or text  
4. **Logical** - e.g. `TRUE` or `FALSE`, these are Boolean values  

<span style="color:#FF0000">Important:</span> An atomic vector can only store one type of atomic vector. For example, if you create a vector consisting of numerics and characters, the numerics will be coerced into characters.  

Coercion changes the data types to the most flexible type in the vector created. Types from the least to the most flexible:  
(least flexible) logical < integer < double < character (most flexible)  


```r
# Create vector with numerics and characters
a <- c("dogs", "spaniels", 1, 2)

# Print vector
a
```

```
## [1] "dogs"     "spaniels" "1"        "2"
```

In vector `a`, dogs and spaniels are characters while 1 and 2 are integers. Since character is more flexible than integer, 1 and 2 are coerced into characters. We can confirm this by the quotation marks around 1 and 2 when we print vector `a` and by checking its class.  

Note that in R, characters are wrapped in `"quotation marks"` and R is case sensitive, so always spell your `TRUE` and `FALSE` in capital letters or just `T` or `F` and R will understand you.  
To check data type in R, we use a function called `class()`.  

```r
# Assigning variables
intgr <- 5

num <- 5.2

chr <- "eat"

lgcl <- TRUE

# Check data types
class(intgr)
```

```
## [1] "numeric"
```

```r
class(num)
```

```
## [1] "numeric"
```

```r
class(chr)
```

```
## [1] "character"
```

```r
class(lgcl)
```

```
## [1] "logical"
```

### Lists  

We will dicuss list in details in the next section.

## Creating Atomic Vector  

`c()` is a function in R that combine values into a vector or list.  
Let's create a vector consisting of the month number from January to May.

```r
# Create vector of month number
month_num <- c(1, 2, 3, 4, 5)
```

## Name a Vector  

Now, we want to name these months.

```r
# Naming a vector
names(month_num) <- c("Jan", "Feb", "March", "Apr", "May")

# Print month_num
month_num
```

```
##   Jan   Feb March   Apr   May 
##     1     2     3     4     5
```

## Vector Selection  

Selecting element(s) in a vector is really simple, using a bracket `[]`. Let's use the `month_num` vector that we have created earlier and we want to select the first element, Jan.

```r
# Select the first element, Jan
month_num[1]
```

```
## Jan 
##   1
```

In R, the first element starts at 1 and not 0 (like in Python).  
We can also select more than one element at a time. To do this, we use `vector[start:end]`. 

```r
# Select the first, second, third and fourth element
month_num[1:4]
```

```
##   Jan   Feb March   Apr 
##     1     2     3     4
```

# Lists  

## Definition

Just like atomic vector, list is a 1-dimensional array. But unlike atomic vector, a list can contain element of different type i.e. a list can consist of numerics, logical and character at the same time.  
A list is sometimes called a recursive vector because it can also store list!  

## Create a List

We will use the `list()` function to create a list. 

```r
# Create vector and matrix to make a list 
vect1 <- 1:10
mtrx1 <- matrix(c("a", "b", "c", "d", "e", "f", "g", "h", "i"), 3, 3)

# Create list
list1 <- list(vect1, mtrx1)

# View list
list1
```

```
## [[1]]
##  [1]  1  2  3  4  5  6  7  8  9 10
## 
## [[2]]
##      [,1] [,2] [,3]
## [1,] "a"  "d"  "g" 
## [2,] "b"  "e"  "h" 
## [3,] "c"  "f"  "i"
```

```r
# Check structure of list 
str(list1)
```

```
## List of 2
##  $ : int [1:10] 1 2 3 4 5 6 7 8 9 10
##  $ : chr [1:3, 1:3] "a" "b" "c" "d" ...
```

Always use `list()` to create a list even if the list contains another list. If you use `c()`, it will combine all the lists to become just one list.

```r
# Create list using list() and c()
list_using_list <- list(list(1, 2), list(3, 4, 5))
list_using_c <- c(list(1, 2), list(3, 4, 5))

# Check structure of list_using_list
str(list_using_list)
```

```
## List of 2
##  $ :List of 2
##   ..$ : num 1
##   ..$ : num 2
##  $ :List of 3
##   ..$ : num 3
##   ..$ : num 4
##   ..$ : num 5
```

```r
# Check structure of list_using_c
str(list_using_c)
```

```
## List of 5
##  $ : num 1
##  $ : num 2
##  $ : num 3
##  $ : num 4
##  $ : num 5
```

## Naming a List


```r
# Name a list 
list1 <- list(number_vector = vect1, alphabet_matrix = mtrx1)

# View list 
list1
```

```
## $number_vector
##  [1]  1  2  3  4  5  6  7  8  9 10
## 
## $alphabet_matrix
##      [,1] [,2] [,3]
## [1,] "a"  "d"  "g" 
## [2,] "b"  "e"  "h" 
## [3,] "c"  "f"  "i"
```

## Selecting Elements from a List  

To select element from a list we will use double bracket `[[]]`, unlike the single bracket `[]` used in selecting element in an atomic vector. When you use a single bracket in list, you are selecting the vector or the matrix that you store in the list instead of the elements in the vector or the matrix you selected.

```r
# Selecting the first component in the list
list1[1]
```

```
## $number_vector
##  [1]  1  2  3  4  5  6  7  8  9 10
```

```r
# Selecting the elements in the first component of the list 
list1[[1]]
```

```
##  [1]  1  2  3  4  5  6  7  8  9 10
```

```r
# Selecting the 5th element in the first component of the list
list1[[1]][5]
```

```
## [1] 5
```

```r
# Selecting the second component in the list
list1[2]
```

```
## $alphabet_matrix
##      [,1] [,2] [,3]
## [1,] "a"  "d"  "g" 
## [2,] "b"  "e"  "h" 
## [3,] "c"  "f"  "i"
```

```r
# Selecting the 6th element in the second component of the list
list1[[2]][6]
```

```
## [1] "f"
```

Another alternative to selecting element of a list is using the `$` sign. 

```r
# Selecting the 5th element in the first component of the list
list1$number_vector[5]
```

```
## [1] 5
```

```r
# Selecting the 6th element in the second component of the list
list1$alphabet_matrix[6]
```

```
## [1] "f"
```

# Matrices  

## Definition  

In vector, we are dealing with a 1-dimensional array. Let's extend that into 2-dimensional array, consisting of rows and columns, what we get here is a matrix. Just like an atomic vector, a matrix can only consist of one data type. For example, a matrix consisting of numerics.  

## Creating a Matrix 

To create a matrix, we can simply use the `matrix()` function. Before we create our first matrix, let's look at the arguments that can be passed in this function.  

`matrix(data, nrow = 1, ncol = 1, byrow = FALSE)`

* The first argument is data, for example a vector of numerics from 1 to 9.  
* The second argument is nrow, which corresponds to the number of row in the matrix.  
* The third argument is ncol, which corresponds to the number of column in the matrix.  
* The fourth argument is byrow, which tells the function to put your data by row or not. The default setting is `FALSE` which means that if you do not specify it, R will insert the data into the matrix by column. So, if you set it to `byrow = TRUE`, only then R will do it by row.  

Now, let's create a matrix.

```r
# Create a matrix, fill by column
first_matrix <- matrix(1:9, 3, 3)

# Create a matrix, fill by row
second_matrix <- matrix(1:9, 3, 3, byrow = TRUE)

# Print matrices
first_matrix
```

```
##      [,1] [,2] [,3]
## [1,]    1    4    7
## [2,]    2    5    8
## [3,]    3    6    9
```

```r
second_matrix
```

```
##      [,1] [,2] [,3]
## [1,]    1    2    3
## [2,]    4    5    6
## [3,]    7    8    9
```

The `1:9` specify that we want number 1 to number 9. Notice the difference between the first and the second matrix.  

## Naming a Matrix  

Let's take the `first_matrix` that we created above and name its columns and rows. To do this, we use a similar method as naming a vector, `names(vector) <- c("a", "b", "c")`.  

But as we have discussed before, a vector is a 1-dimensional array and matrix is a 2-dimensional array. So, for a matrix, we want to name the columns and the rows.


```r
# Name the columns for first_matrix
colnames(first_matrix) <- c("Col 1", "Col 2", "Col 3")

# Name the rows for first_matrix
rownames(first_matrix) <- c("Row 1", "Row 2", "Row 3")

# Print first_matrix
first_matrix
```

```
##       Col 1 Col 2 Col 3
## Row 1     1     4     7
## Row 2     2     5     8
## Row 3     3     6     9
```

We can see that columns and rows of first_matrix are now labelled.  

## Matrix Calculations  

Let's say we want to calculate the sum of the matrix by rows and by columns. We can do this in R using these functions `colSums()` (for sum of each column) and `rowSums()` (for sum of each row).

```r
# Calculate sum for each column
colSums(first_matrix)
```

```
## Col 1 Col 2 Col 3 
##     6    15    24
```

```r
# Calculate sum for each row
rowSums(first_matrix)
```

```
## Row 1 Row 2 Row 3 
##    12    15    18
```

## Adding Columns and Rows

Now that we have the sums for the columns and rows, we want to add these results to the `first_matrix`.  
For this purpose, we use `cbind()` (add column) and `rbind()` (add row).

```r
# Assign variables
column_sum <- colSums(first_matrix)
row_sum <- rowSums(first_matrix)

# Add column_sum as an extra row
first_matrix_csum <- rbind(first_matrix, column_sum)

# Add row_sum as an extra column
first_matrix_rsum <- cbind(first_matrix, row_sum)

# Print first_matrix_csum
first_matrix_csum
```

```
##            Col 1 Col 2 Col 3
## Row 1          1     4     7
## Row 2          2     5     8
## Row 3          3     6     9
## column_sum     6    15    24
```

```r
# Print first_matrix_rsum
first_matrix_rsum
```

```
##       Col 1 Col 2 Col 3 row_sum
## Row 1     1     4     7      12
## Row 2     2     5     8      15
## Row 3     3     6     9      18
```

We can also join two matrices into one. Let's use the original `first_matrix` and `second_matrix` as one matrix.

```r
# Add two matrices using cbind()
cbind(first_matrix, second_matrix)
```

```
##       Col 1 Col 2 Col 3      
## Row 1     1     4     7 1 2 3
## Row 2     2     5     8 4 5 6
## Row 3     3     6     9 7 8 9
```

```r
# Add two matrices using rbind()
rbind(first_matrix, second_matrix)
```

```
##       Col 1 Col 2 Col 3
## Row 1     1     4     7
## Row 2     2     5     8
## Row 3     3     6     9
##           1     2     3
##           4     5     6
##           7     8     9
```

## Matrix Selection

Selecting element(s) in matrix is done similar to vector selection. And again, because matrix is a 2-dimensional array, we need to specify the row number and the column number `matrix[row number, column number]`.

Let's use a combined `first_matrix` and `second_matrix` as an example.

```r
# Add two matrices using rbind() and assign to a new variable
joined_matrix <- rbind(first_matrix, second_matrix)

# Name all rows in joined_matrix 
rownames(joined_matrix) <- c("Row 1", "Row 2", "Row 3", "Row 4", "Row 5", "Row 6")

# Print joined_matrix
joined_matrix
```

```
##       Col 1 Col 2 Col 3
## Row 1     1     4     7
## Row 2     2     5     8
## Row 3     3     6     9
## Row 4     1     2     3
## Row 5     4     5     6
## Row 6     7     8     9
```

This is how we do matrix selection, `matrix[row number, column number]`.

```r
# Select element in Row 3, Col 2
joined_matrix[3, 2]
```

```
## [1] 6
```

```r
# Select element in Row 3, Col 1 and Col 2
joined_matrix[3, 1:2]
```

```
## Col 1 Col 2 
##     3     6
```

```r
# Select all elements in Row 3 (leave column empty)
joined_matrix[3, ]
```

```
## Col 1 Col 2 Col 3 
##     3     6     9
```

```r
# Select all elements in Col 2 (leave row empty)
joined_matrix[, 2]
```

```
## Row 1 Row 2 Row 3 Row 4 Row 5 Row 6 
##     4     5     6     2     5     8
```

# Factor

## Definition  

A factor is a vector that has a limited set of values. It is used to store categorical data.  
Two examples of categorical data:  
1. Sex - "male" and "female"  
2. Race - "Asian" and "African" or "Ginger" (joking!)  

Factor is developed on top of integer vector. What does this mean? It means that storing factor in R involves a vector of integer values and these integer values have an associated set of character values. These character values are used to display the factor.

## Creating a Factor  

The function that function that we will use to create a factor is `factor()`. Let's create one. 

```r
# Create an education level vector
edu_vector <- c("degree", "degree", "degree", "masters", "phd", "phd", "diploma")

# Create factor
edu_factor <- factor(edu_vector)

# Print factor
edu_factor
```

```
## [1] degree  degree  degree  masters phd     phd     diploma
## Levels: degree diploma masters phd
```

Note that we have four levels in our factor, degree, diploma, masters and phd.  

I have mentioned about categorical data, let's expand our understanding on it. Categorical data can be further divided into two sets:  

* **Nominal** categorical data - it has no implied order, one value does not worth more or less than the other value.  
* **Ordinal** categorical data - it has natural ordering  

## Factor Levels and Level Ordering

Using our `edu_factor` example, which type of categorical data will it be? Ordinal, because there is an order, a degree is a level higher than a diploma.  
Let's set the order of the levels in our factor. We need to specify `order = TRUE` and provide the vector for `levels` (the order is from lowest to highest), the order of this vector is important.

```r
# Set order for edu_factor
edu_factor2 <- factor(edu_vector, order = TRUE, levels = c("diploma", "degree", "masters", "phd"))

# Print edu_factor2
edu_factor2
```

```
## [1] degree  degree  degree  masters phd     phd     diploma
## Levels: diploma < degree < masters < phd
```

Note the difference of the levels between `edu_factor` and `edu_factor2`. We specified the order and levels for `edu_factor2` but not `edu_factor`.  

You can change the name of the levels.

```r
# Rename levels
levels(edu_factor2) <- c("diploma", "undergraduate", "masters", "PhD")

# Print edu_factor2 with new levels name
edu_factor2
```

```
## [1] undergraduate undergraduate undergraduate masters       PhD          
## [6] PhD           diploma      
## Levels: diploma < undergraduate < masters < PhD
```

Note that when you change the name of factor levels, it will re-name the factor as well.

## Factor Summary  

To get an overview of the content of our `edu_factor2`, we can use the `summary()` function.  

```r
# Summary of edu_factor2
summary(edu_factor2)
```

```
##       diploma undergraduate       masters           PhD 
##             1             3             1             2
```

# Data Frame

## Definition

We now know that a matrix can consist only one data type, e.g. numerics or characters. However, in the real world, the type of data you want to store are of different types. We can store this information in a data frame.  

Just like a matrix, a data frame is 2-dimensional, it has a set of columns and rows are called observations. Data frame allows you to store data of different types. <span style="color:#FF0000">It is basically a list of vectors of equal lengths.</span> The previous sentence basically said that data frame can behave like a list (1-dimensional) or matix (2-dimensional).

## Quick Glance of Data Frame  

After reading in your dataset in R, the first thing that you need to know is to understand your dataset, get a feel of what it is that you are dealing with. For that purpose, let me introduce you to three functions that will help you in the initial stages of your data analysis.  

* `str()` - show the structure of your data frame  
* `head()` - show the first few rows in your data frame  
* `tail()` - show the last few rows in your data frame  

Let's use a built-in `Orange` dataset in R to demonstrate what these functions do.  

```r
# See the structure
str(Orange)
```

```
## Classes 'nfnGroupedData', 'nfGroupedData', 'groupedData' and 'data.frame':	35 obs. of  3 variables:
##  $ Tree         : Ord.factor w/ 5 levels "3"<"1"<"5"<"2"<..: 2 2 2 2 2 2 2 4 4 4 ...
##  $ age          : num  118 484 664 1004 1231 ...
##  $ circumference: num  30 58 87 115 120 142 145 33 69 111 ...
##  - attr(*, "formula")=Class 'formula'  language circumference ~ age | Tree
##   .. ..- attr(*, ".Environment")=<environment: R_EmptyEnv> 
##  - attr(*, "labels")=List of 2
##   ..$ x: chr "Time since December 31, 1968"
##   ..$ y: chr "Trunk circumference"
##  - attr(*, "units")=List of 2
##   ..$ x: chr "(days)"
##   ..$ y: chr "(mm)"
```

```r
# See the first few rows
head(Orange)
```

```
##   Tree  age circumference
## 1    1  118            30
## 2    1  484            58
## 3    1  664            87
## 4    1 1004           115
## 5    1 1231           120
## 6    1 1372           142
```

```r
# See the last few rows
tail(Orange)
```

```
##    Tree  age circumference
## 30    5  484            49
## 31    5  664            81
## 32    5 1004           125
## 33    5 1231           142
## 34    5 1372           174
## 35    5 1582           177
```

By looking at the result from `str(Orange)`:  

* It has 35 observations (rows) with 3 variables (columns)  
* Variable `Tree` is an ordered factor with 5 levels, while `age` and `circumference` are numerics

The default number of rows for `head()` and `tail()` is 6, but you can specify a different number like this.

```r
# Specify number of rows
head(Orange, n = 10)
```

```
##    Tree  age circumference
## 1     1  118            30
## 2     1  484            58
## 3     1  664            87
## 4     1 1004           115
## 5     1 1231           120
## 6     1 1372           142
## 7     1 1582           145
## 8     2  118            33
## 9     2  484            69
## 10    2  664           111
```

## Creating a Data Frame

Creating a data frame is really simple. We will use `data.frame()` function.

```r
# Create numeric vector
number <- c(1, 2, 3, 4, 5)

# Create character vector
alphabet <- c("a", "b", "c", "d", "e")

# Create data frame
df1 <- data.frame(number, alphabet)

# View data frame
df1
```

```
##   number alphabet
## 1      1        a
## 2      2        b
## 3      3        c
## 4      4        d
## 5      5        e
```

```r
# View structure of data frame
str(df1)
```

```
## 'data.frame':	5 obs. of  2 variables:
##  $ number  : num  1 2 3 4 5
##  $ alphabet: Factor w/ 5 levels "a","b","c","d",..: 1 2 3 4 5
```

Take a closer look at the result `str(df1)`, alphabet is listed as a factor, but we created a character vector instead of a factor. This happens due to `data.frame()` behaviour, it turns character into factor. We can suppress this behaviour by passing this argument `stringsAsFactors = FALSE`. 

```r
# Specify stringsAsFactors = FALSE
df2 <- data.frame(number, alphabet, stringsAsFactors = FALSE)

# View structure of data frame
str(df2)
```

```
## 'data.frame':	5 obs. of  2 variables:
##  $ number  : num  1 2 3 4 5
##  $ alphabet: chr  "a" "b" "c" "d" ...
```

We can see that alphabet is now a character instead of factor.

One point to note in creating a data frame is, combining vectors using `cbind()` does not produce a data frame. Let's see an example. 

```r
# Combine vectors column-wise
df3 <- cbind(number, alphabet)

# Check class 
class(df3)
```

```
## [1] "matrix"
```

One quick way to transform this matrix into a data frame is by using `as.data.frame()`.

```r
# Coerce matrix into a data frame
df3_dataframed <- as.data.frame(df3)

# Check class
class(df3_dataframed)
```

```
## [1] "data.frame"
```

## Combining a Data Frame  

We can combine data frames using `cbind()` and `rbind()`. Let's use `df2` and create another data frame and combine them.

```r
# Create data frame
df4 <- data.frame(number2 = 6:10, alphabet2 = c("f", "g", "h", "i", "j"), stringsAsFactors = FALSE)

# View data frame
df4
```

```
##   number2 alphabet2
## 1       6         f
## 2       7         g
## 3       8         h
## 4       9         i
## 5      10         j
```

First, let's combine it column-wise using `cbind()`.  
Note that in column-wise combination:  

1. The number of rows must be the same between data frames, both `df2` and `df4` have 5 rows  
2. Column names can be different  
3. Row names are ignored

```r
cbind(df2, df4)
```

```
##   number alphabet number2 alphabet2
## 1      1        a       6         f
## 2      2        b       7         g
## 3      3        c       8         h
## 4      4        d       9         i
## 5      5        e      10         j
```

Now, let's combine it row-wise using `rbind()`.  
Note that in row-wise combination:  

1. The number of columns must be the same between data frames, both `df2` and `df4` have 2 columns  
2. Column names must match  

Let's fix `df4` and assign it to `df5` so we can combine it row-wise

```r
# Create df5
df5 <- data.frame(number = 6:10, alphabet = c("f", "g", "h", "i", "j"), stringsAsFactors = FALSE)

rbind(df2, df5)
```

```
##    number alphabet
## 1       1        a
## 2       2        b
## 3       3        c
## 4       4        d
## 5       5        e
## 6       6        f
## 7       7        g
## 8       8        h
## 9       9        i
## 10     10        j
```

## Selecting Elements in a Data Frame  

Selecting element(s) in a data frame is similar to selecting elements in vector and matrix, using `[]`.

```r
# Create a data frame
df6 <- cbind(df2, df4)

# View data frame
df6 
```

```
##   number alphabet number2 alphabet2
## 1      1        a       6         f
## 2      2        b       7         g
## 3      3        c       8         h
## 4      4        d       9         i
## 5      5        e      10         j
```

Let's select some elements.

```r
# Select element in the 2nd row, 3rd column
df6[2, 3]
```

```
## [1] 7
```

```r
# Select elements in the 4th row, from 1st to 3rd column
df6[4, 1:3]
```

```
##   number alphabet number2
## 4      4        d       9
```

```r
# Select elements in the 2nd to 4th row, 4th column
df6[2:4, 4]
```

```
## [1] "g" "h" "i"
```

```r
# Select elements in the 2nd to 4th row, from 1st to 3rd column
df6[2:4, 1:3]
```

```
##   number alphabet number2
## 2      2        b       7
## 3      3        c       8
## 4      4        d       9
```

```r
# Select all elements in the 5th row (leave column empty)
df6[5, ]
```

```
##   number alphabet number2 alphabet2
## 5      5        e      10         j
```

```r
# Select all elements in the 1st column (leave row empty)
df6[, 1]
```

```
## [1] 1 2 3 4 5
```

An alternative to column number, you can use column name to do the selection. This is useful when you have a dataset with many columns. Remember to wrap the column name with quotation marks.

```r
# Select all elements in the 1st column (leave row empty)
df6[, "number"]
```

```
## [1] 1 2 3 4 5
```

And there's also a shortcut to the above code! You can use the `$` sign. This time, you don't need to wrap it in quotation marks.

```r
df6$number
```

```
## [1] 1 2 3 4 5
```

## Subset a Data Frame

Let's say we want to get observations in our dataset that meets a certain condition, we can do this by using `subset()`. Let's use `Orange` dataset in R to demonstrate this function, the syntax is like this `subset(dataframe, condition)`.

```r
# Select all number 2 trees
subset(Orange, Tree == 2)
```

```
##    Tree  age circumference
## 8     2  118            33
## 9     2  484            69
## 10    2  664           111
## 11    2 1004           156
## 12    2 1231           172
## 13    2 1372           203
## 14    2 1582           203
```

What if we only want Tree and circumference to be selected? We can pass `select` argument. 

```r
# Select all number 2 trees, showing Tree and circumference columns only
subset(Orange, Tree == 2, select = c(Tree, circumference))
```

```
##    Tree circumference
## 8     2            33
## 9     2            69
## 10    2           111
## 11    2           156
## 12    2           172
## 13    2           203
## 14    2           203
```

## Sorting

Let's focus on the circumference column of Orange dataset. We would like to see the circumference ordered from the smallest to the biggest circumference. This is how we do it in R, using `order()`

```r
# Create circ vector
circ <- Orange$circumference

# Find the new order of the elements
order(circ)
```

```
##  [1]  1 15 29 22  8 30 16  2 23  9 17 31  3 18 10 24  4 19  5 32 20 21  6
## [24] 33  7 11 25 12 34 35 26 13 14 27 28
```

```r
# Use the result above to find the new ordered circ
circ[order(circ)]
```

```
##  [1]  30  30  30  32  33  49  51  58  62  69  75  81  87 108 111 112 115
## [18] 115 120 125 139 140 142 142 145 156 167 172 174 177 179 203 203 209
## [35] 214
```
