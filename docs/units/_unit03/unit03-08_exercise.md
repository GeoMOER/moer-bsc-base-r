---
title: "Assignment: Vector Operations and Data Types in R"
toc: true
toc_label: "In this example"
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

In this exercise, we'll delve into vector creation, manipulation, and data type conversion in R, essential skills for data analysis.

1. Create a vector named `Jahre_var1` using the `c()` function with even numbers from 1983 to 2012. Then, do the same using the `seq()` function, but name this vector `Jahre_var2`.

2. Determine the data type of each vector. Convert them if necessary to match the appropriate data type for their contents. <br/>

3. <br/>
   a) Convert the `Jahre_var1` vector to a character type. <br/>
   b) After conversion, create two new vectors: `Massenzunahme` with values 4.52, 2, 12.04, 0, 8.432 and `AnzahlWochen` with values from 0 to 4. <br/>
   c) Divide `Massenzunahme` by `AnzahlWochen` and observe the results.


4. Then <br/>
  a) calculate the Shannon Index for a community of 4 species (A, B, C, D), where species A has 30 individuals, species B has 25 individuals, species C has 15 individuals, and species D has 10 individuals. The Shannon Index is calculated as follows: <br/>
  <img src="https://latex.codecogs.com/svg.image?H=-\sum_{i=1}^{S}p_i\ln(p_i)"/>&nbsp;&nbsp;&nbsp;with
  <img src="https://latex.codecogs.com/svg.image?p_i=\frac{n_i}{N}"/> <br/>
  where <img src="https://latex.codecogs.com/svg.image?n_i\;"> is the frequency of each species and <img src="https://latex.codecogs.com/svg.image?N\;"/> is the total number of individuals across all species. Compare this with a community of 4 species, each having 12 individuals.<br/>
  b) compare the result with a community of 4 species, each having 22 individuals.

Please save your file as "FirstName_LastName_Task_Day2_Unit03.R".
