---
title: "First steps in R"
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---


## #Hashtag and Run!

R treats the hashtag character, **#**, in a special way. It will not compile anything that follows a # on a line. This makes hashtags very useful for adding comments and annotations to your code. You will be able to read the comments, but your computer will pass over them.

```r
# This is a comment. Comments are very helpful
# when you want to describe what's going on in your code.
# Use them often!
This is not a comment anymore. Be careful.

hello <- "Welcome to R" #the variable "hello" is storing the information "Welcome to R"
```

To run a chunk, you can hit the "Run" arrow to the right in the first Window (following picture, red box), or put your cursor inside the chunk and then hit `CTRL + ENTER` on Windows/Linux or `CMD + ENTER` on a Mac.

{% include figure image_path="/assets/images/unit_images/u01/gui_rstudio_exp2.png" caption="Hit the Run-Button." %}

The code and the output of the code will print below the chunk in the second Window (Console).
It looks like this:

```r
> hello <- "Welcome to R"
> hello
[1] "Welcome to R"
>
```

Here, you’ll also see on the left hand side the “>” symbol which means that R is ready to receive a new command. If there's a “+” is visible instead, this means that the command has not yet been completed, e.g. a parenthesis has not been closed.


## Creating scalar objects and simple arithmetic operations

The basic arithmetic operations are addition, subtraction, multiplication and division. Further, more complex operations include square roots, exponentiation and some other. To  control the order of operations, use parentheses "()". Note, that square brackets "[]" cannot be used, because they are reserved for subsetting or indexing data structures like vectors, lists, data frames, and matrices, as you will see in Unit 04.

Examples of mathematic operations in R. This is using R like a calculator.


| Operator  | Description                          | Example   |
|-----------|--------------------------------------|-----------|
| **Arithmetic Operators** ||
| +         | Addition                             | `x + y` |
| -         | Subtraction                          | `x - y` |
| *         | Multiplication                       | `x * y` |
| /         | Division                             | `x / y` |
| ^ or **   | Exponentiation                       |  `x^y`  |
| x %% y    | Modulus (x mod y)                    | `x %% y` |
| %/%       | Integer division                     | `x %/% y`|
| **Math Functions** ||
| sum()     | Sum                                  | `sum()`
| log()     | Logarithms, by default natural       | `log(x)` |
| exp()     | Exponential function                 | `exp(x)` |
| sqrt()    | Square-root                          | `sqrt(x)`|
| ^(1/n)    | nth roots                            | `x^(1/n)`|
| abs()     | Absolute value                       | `abs(x)` |
| sin()     | Sine                                 | `sin(x)` |
| cos()     | Cosinus                              | `cos(x)` |
| tan()     | Tangent                              | `tan(x)` |

This is what it looks like in R:

```r
> 1 + 2
[1] 3
```
```r
> 2 - 1
[1] 1
```
```r
> 2 * 3
[1] 6
```
```r
> 2 / 3
[1] 0,6666666666666667‬
```
```r
> 2 ^ 3
[1] 8
```
```r
> cos(2 ^ (3+2))
[1] 0.8342234
```


That [1] next to your result is a reminder that this line begins with the first value in your result. Some commands return more than one value, and their results may fill up multiple lines.



### Assigning values to objects

And now you have reached the core concept of every object-based programming language: assigning objects. This fundamental operation is remarkably straightforward. You type in the name of the object-to-be, an assignment operator, and the content you'd like to assign. In R, there are two assignment operators: <- and =. The <- operator is the more common and recommended way to assign objects in R. It's considered good practice because it makes your code more readable and is less likely to be confused with the equality operator ==, which is used for comparison.


```r
> # Assign values to objects
> a <- 1+2 # addition/allocation, calculation is stored in object "a"
> a        # show the result
[1] 3
```

```r
> # adding another object
> b <- 2-1
> b
[1] 1
>
> a + b # apply operators to objects
[1] 4
>
> c <- (a + b) * 2 # brackets
> c
[1] 8
```

If you want to store more than one value to an object you need a vector. It is a basic data structure and contains elements of the same type.
When you want to create a **vector**, the basic data structure which contains elements of the same type with more than one element, you need to use the `c()` function which means to combine the elements into a vector (c for combine).

```r
> d <- c(1,2,3)
```

And that is how information is stored in objects in an object-oriented programming language.
