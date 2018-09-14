# Fragmentary-Notes-for-R
## Data Type and Data Structure in R

- dataset: a rectangular array of data with rows representing observations and columns representing variables.
  > example
    ![example dataset](https://raw.githubusercontent.com/haonen/Fragmentary-Notes-for-R/master/example%20dataset.JPG)
  > different traditions for the name of rows and columns
  
    | traditions | name of rows | name of columns|
    | ---------- | ------------ | -------------- |
    | **Stats**      | observations |    variables   |
    |**database**   | records      |  fields        |
    | **data mining & machine-learning** | examples     |  attributes    |
   
 - R has multiple structures for holding data:
 ![R data sturcture](https://raw.githubusercontent.com/haonen/Fragmentary-Notes-for-R/master/R%20data%20structure.JPG)
 
  >scalars（标量）: one-element vectors. Examples include f <- 3, g <- "US",
and h <- TRUE. They’re used to hold constants.
  
  >vectors: one-dimensional arrays that can hold numeric data, character data, or logical data. Note that
the data in a vector must be only one type or mode (numeric, character, or logical).
You can’t mix modes in the same vector.
```ruby
    c()
```
  
  > matrix: a two-dimensional array in which each element has the same mode
(numeric, character, or logical). 
```ruby
myymatrix <- matrix(vector, nrow=number_of_rows, ncol=number_of_columns,
byrow=logical_value, dimnames=list(
char_vector_rownames, char_vector_colnames))
```
  where vector contains the elements for the matrix, nrow and ncol specify the row and
column dimensions, and dimnames contains optional row and column labels stored in
character vectors. The option byrow indicates whether the matrix should be filled in
by row (byrow=TRUE) or by column (byrow=FALSE). The default is by column. The following listing demonstrates the matrix function.

  You can identify rows, columns, or elements of a matrix by using subscripts and
brackets. X[i,] refers to the ith row of matrix X, X[,j] refers to the j th column, and
X[i, j] refers to the ij th element, respectively. The subscripts i and j can be numeric
vectors in order to select multiple rows or columns, as shown in the following listing.

  Matrices are two-dimensional and, like vectors, can contain only one data type.
When there are more than two dimensions, you use arrays (section 2.2.3). When there
are multiple modes of data, you use data frames (section 2.2.4)
  
  >arrays（数组）:similar to matrices but can have more than two dimensions.
    ```ruby
    myarray <- array(vector, dimensions, dimnames)
    ```
    where vector contains the data for the array, dimensions is a numeric vector giving
the maximal index for each dimension, and dimnames is an optional list of dimension labels.
  
  >data frames（数据框）
  ```ruby
  mydata <- data.frame(col1, col2, col3,...)
  ```
    a)
   an alternative for data frame: [tibble](http://blog.fens.me/r-tibble/) for tidyverse especially
   
  >lists: an ordered collection of objects (components). A list allows you to gather a variety of (possibly unrelated) objects under one name. 
  
 - the data types or modes in R:
  > numeric
  
  >  character
  
  > logical(TRUE/FALSE)
  
  > complex (imaginary numbers)
  
  > raw (bytes)
  
 - some definitions in R
  > objects: anything that can be assigned to a variable. This includes constants,
data structures, functions, and even graphs. An object has a **mode (which describes
how the object is stored)** and a **class (which tells generic functions like print how to
handle it)**.

  > factor: **nominal or ordinal** variables. They’re stored and treated specially in R. Factors are crucial in R because they determine how data is analyzed and presented visually. 
    example:
```ruby
    status <- c("Poor", "Improved", "Excellent", "Poor")
    status <- factor(status, order=TRUE, levels=c("Poor", "Improved", "Excellent"))
```

[an interesting document](https://cran.r-project.org/doc/contrib/Liu-FAQ.pdf)

## dplyr
- mutate()
  > mutate(data, new_column = func(old column))
- filter()
  > for rows
- group_by()
- summarize()
- select()
  > for columns
- left_join()
- gather/spread()


