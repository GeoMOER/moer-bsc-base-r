---
title: "Exercise: Object types in R"
published: true
header:
  image: /assets/images/unit_images/u03/header.png
  caption: "Image created with DALL E"
---


The learning aim of this exercise is to reinforce key concepts related to data structures and data transformation in R.


**1.**  
a) Create a vector named vec1 with even numbers from 40 to 200, in steps of 4.  
b) Determine the length of this vector.  
c) Convert this vector into a matrix with 3 columns named mat1.  
d) Access the last value of this matrix.  

  <details>
   <summary>Solution Task 1</summary>
      <pre><code>
      vec1 <- seq(from=40, to=200, by=4)
      length(vec1)
      mat1 <- matrix(vec1, ncol=3)
      mat1[length(mat1)]
      </code></pre>
  </details>

**2.**  
a) Create a factor vector named vec2 with the letters A, B, and C repeated 3 times each.  
b) Convert the factor into a character vector.  
c) Turn the character vector back into a factor, but in reverse alphabetical order.  

  <details>
   <summary>Solution Task 2</summary>
      <pre><code>
      vec2 <- factor(rep(c("A","B","C"), each=3))
      vec2 <- as.character(vec2)
      vec2 <- factor(vec2, levels=rev(LETTERS[1:3]))
      </code></pre>
  </details>

**3.**  
You have two separate data frames, each representing a different set of cities with population data. Combine the two data frames.

```
cities1 <- data.frame(
  City = c("City A", "City B"),
  Population = c(500000, 700000)
)

cities2 <- data.frame(
  City = c("City C", "City D"),
  Population = c(1200000, 900000)
)
```
  <details>
   <summary>Solution Task 3</summary>
      <pre><code>
      cities1 <- data.frame(City = c("City A", "City B"),
                            Population = c(500000, 700000))
      cities2 <- data.frame(City = c("City C", "City D"),
                            Population = c(1200000, 900000))
      cities <- rbind(cities1, cities2)
      </code></pre>
  </details>

**Vectorization - this task will be developed together**

You have current population figures for multiple cities called "A", "B", "C", "D", "E" and "F".

| city | current population |
|------|--------------------|
|  A   |            500,000 |
|  B   |            700,000 |
|  C   |            900,000 |
|  D   |          1,200,000 |
|  E   |             20,000 |
|  F   |            100,000 |

Cities A, C, and E have a growth rate of 1.5% per year.

Cities B, D, and F experience a population decline of 1% per year.

Calculate the projected population for each city after 6 years using the formula:

<p>Future Population = Current Population × (1 + Growth Rate)<sup>6</sup></p>


Use vectorization and vector recycling.

What problems could arise?

  <details>
   <summary>Solution Task 4</summary>
      <pre><code>
      population <- data.frame(Cityname = c("A","B","C","D","E","F"),
                               current = c(500000, 700000, 900000, 1200000, 20000, 100000))
      population$future <- population$current*(1+c(0.015,-0.001))^6
      # If the cities are not ordered accordingly, the vectorization/recycling will cause issues!
      </code></pre>
  </details>


> “Thou shalt never assume that simply because the computer code ran and spit out data of the right shape you have the right answer.” — [Brian McGill](https://dynamicecology.wordpress.com/2016/08/22/ten-commandments-for-good-data-management/)
