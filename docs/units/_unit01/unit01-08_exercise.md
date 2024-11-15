---
title: "Exercise: Introduction and Basic Functions in R"
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---


In this exercise, we'll start with the basics of R, focusing on arithmetic operations.


Use R to   
  a)  Define a vector containing the numbers 4, 8, 15, 16, and 23. Calculate the sum and the product of these numbers. Additionally, use R’s help features to explore different methods for calculating these values.  
  b) Find the square root of 1444.   
  b) Calculate the population density for two different regions. The formula for population density is:  
<img src="https://latex.codecogs.com/svg.image?\text{Population&space;Density}&space;=&space;\frac{\text{Population}}{\text{Area}}"/>

<details> 
  <summary> Solution </summary>
    <pre><code>
    # a) Define a vector containing the numbers 4, 8, 15, 16, and 23  
    numbers <- c(4, 8, 15, 16, 23)
    # Calculate the sum of the numbers  
    sum(numbers)  
    # Calculate the product of the numbers  
    prod(numbers)  
    # b) Find the square root of 1444    
    sqrt(1444)
    <br>
    # c) Calculate the population density for two different regions 
    # The formula for population density is: Population Density = Population / Area  <
    # Define the population and area for Region A and Region B  
    population_A <- 1500000  # Population of Region A 
    area_A <- 2500           # Area of Region A in square kilometers 
    population_B <- 800000    # Population of Region B  
    area_B <- 1200           # Area of Region B in square kilometers
    # Calculate the population density for Region A and Region B  
    density_A <- population_A / area_A  
    density_B <- population_B / area_B  
    </code></pre>
</details> 



<!-- 
# Tasks of SoSe24

**1.** Please follow the instructions at [Course Unit 01: Installation](https://geomoer.github.io/moer-base-r/unit01/unit01-02_Installation.html) and install both R and RStudio.

**2.** Use R to <br/>
  a) calculate the sum and product of the numbers 3, 7, 9, 12, and 21. Explore R's help features to find an alternative solutions. <br/>
  b) Calculate the square root of 2025.<br/>

<details>
  <summary>Solution Task 2</summary>
    <code>
    # a) <br>
    # Define the vector of numbers <br>
    numbers <- c(3, 7, 9, 12, 21) <br>
    <br>
    # Calculate sum <br>
    sum_result <- sum(numbers) <br>
    <br>
    # Calculate product <br>
    product_result <- prod(numbers) <br>
    <br>
    # Print results <br>
    print(paste("Sum:", sum_result)) <br>
    print(paste("Product:", product_result)) <br>
    <br>
    # b) <br>
    # Calculate square root <br>
    sqrt_result <- sqrt(2025) <br>
    <br>
    # Print result <br>
    print(paste("Square root of 2025:", sqrt_result))
    </code>
</details>
<br>

Please save your file as "FirstName_LastName_Task_Day1_Unit1.R" and upload it to the "Upload/Unit 1"-Folder in Ilias

**3.** Then <br/>
  a) calculate the Shannon Index for a community of 4 species (A, B, C, D), where species A has 30 individuals, species B has 25 individuals, species C has 15 individuals, and species D has 10 individuals. The Shannon Index is calculated as follows: <br/>
  <img src="https://latex.codecogs.com/svg.image?H=-\sum_{i=1}^{S}p_i\ln(p_i)"/>&nbsp;&nbsp;&nbsp;with
  <img src="https://latex.codecogs.com/svg.image?p_i=\frac{n_i}{N}"/> <br/>
  where <img src="https://latex.codecogs.com/svg.image?n_i\;"> is the frequency of each species and <img src="https://latex.codecogs.com/svg.image?N\;"/> is the total number of individuals across all species. Compare this with a community of 4 species, each having 12 individuals.<br/>
  b) compare the result with a community of 4 species, each having 22 individuals.

<details>
  <summary>Solution Task 3</summary>
    <code>
    # a) <br>
    N1 <- c(30, 25, 15, 10) <br>
    N2 <- rep(12, 4) <br>
    H1=-sum(N1/sum(N1)*log(N1/sum(N1))) <br>
    H2=-sum(N2/sum(N2)*log(N2/sum(N2))) <br>
    print(H1) <br>
    print(H2) <br>
    <br>
    # b) <br>
    N3 <- rep(22, 4) <br>
    H3=-sum(N3/sum(N3)*log(N3/sum(N3))) <br>
    print(H3)
    </code>
</details> -->
