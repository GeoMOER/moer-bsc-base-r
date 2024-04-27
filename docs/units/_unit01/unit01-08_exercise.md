---
title: "Exercise: Introduction and Basic Functions in R"
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---


In this exercise, we'll start with the basics of R, focusing on installation and fundamental arithmetic operations. But first we need to install R and RStudio.


**1.** Please follow the instructions at [Course Unit 01: Installation](https://geomoer.github.io/moer-base-r/unit01/unit01-02_Installation.html) and install both R and RStudio.

**2.** Use R to <br/>
  a) calculate the sum and product of the numbers 3, 7, 9, 12, and 21. Explore R's help features to find an alternative solutions. <br/>
  b) Calculate the square root of 2025.<br/>

<details>
  <summary>Solution Task 2</summary>
  
  ```r
  # a)
  # Define the vector of numbers
  numbers <- c(3, 7, 9, 12, 21)

  # Calculate sum
  sum_result <- sum(numbers)

  # Calculate product
  product_result <- prod(numbers)

  # Print results
  print(paste("Sum:", sum_result))
  print(paste("Product:", product_result))

  # b)
  # Calculate square root
  sqrt_result <- sqrt(2025)

  # Print result
  print(paste("Square root of 2025:", sqrt_result))
  ```
</details>


Please save your file as "FirstName_LastName_Task_Day1_Unit1.R" and upload it to the "Upload/Unit 1"-Folder in Ilias

**3.** Then <br/>
  a) calculate the Shannon Index for a community of 4 species (A, B, C, D), where species A has 30 individuals, species B has 25 individuals, species C has 15 individuals, and species D has 10 individuals. The Shannon Index is calculated as follows: <br/>
  <img src="https://latex.codecogs.com/svg.image?H=-\sum_{i=1}^{S}p_i\ln(p_i)"/>&nbsp;&nbsp;&nbsp;with
  <img src="https://latex.codecogs.com/svg.image?p_i=\frac{n_i}{N}"/> <br/>
  where <img src="https://latex.codecogs.com/svg.image?n_i\;"> is the frequency of each species and <img src="https://latex.codecogs.com/svg.image?N\;"/> is the total number of individuals across all species. Compare this with a community of 4 species, each having 12 individuals.<br/>
  b) compare the result with a community of 4 species, each having 22 individuals.

<details>
  <summary>Solutions Task 3</summary>

  ```r
  # a)
  N1 <- c(30, 25, 15, 10)
  N2 <- rep(12, 4)
  H1=-sum(N1/sum(N1)*log(N1/sum(N1)))
  H2=-sum(N2/sum(N2)*log(N2/sum(N2)))
  print(H1)
  print(H2)

  # b)
  N3 <- rep(22, 4)
  H3=-sum(N3/sum(N3)*log(N3/sum(N3)))
  print(H3)
  ```
</details>
