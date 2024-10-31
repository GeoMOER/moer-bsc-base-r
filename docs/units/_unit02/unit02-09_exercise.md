---
title: "Exercise: Vector Operations and Data Types in R"
header:
  image: "/assets/images/unit_images/u02/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/arielrobin-2483349/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1509707">Ariel</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1509707">Pixabay</a>'
---

In this exercise, we'll delve into vector creation, manipulation, and data type conversion in R, essential skills for data analysis.


**1.** Create a vector named Temperatures using the c() function with five random temperature values between 10 and 30 (you can choose the values). 

**2.** Create a new vector named Days containing the day numbers from 1 to 5 using the `seq()` function

**3.** Determine the data type of each vector.



<!-- 
Sose24

**1.** Create a vector named `Jahre_var1` using the `c()` function with even numbers from 1983 to 2012. Then, do the same using the `seq()` function, but name this vector `Jahre_var2`.

 <details>
   <summary>Solution Task 1</summary>
      <code>
      Jahre_var1 <- c(1983:2012)<br>
      Jahre_var1 <- Jahre_var1[Jahre_var1 %% 2 == 0]<br>
      <br>
      Jahre_var2 <- seq(1984, 2012, by = 2)<br>
      </code>
  </details>
<br>
**2.** Determine the data type of each vector. Convert them if necessary to match the appropriate data type for their contents. <br/>

 <details>
   <summary>Solution Task 2</summary>
      <code>
      is.integer(Jahre_var1)<br>
      is.integer(Jahre_var2)<br>
      Jahre_var2 <- as.integer(Jahre_var2)
      </code>
  </details>
<br>
**3.** <br/>
   a) Convert the `Jahre_var1` vector to a character type. <br/>
   b) After conversion, create two new vectors: `Massenzunahme` with values 4.52, 2, 12.04, 0, 8.432 and `AnzahlWochen` with values from 0 to 4. <br/>
   c) Divide `Massenzunahme` by `AnzahlWochen` and observe the results.

  <details>
   <summary>Solution Task 3</summary>
      <code>
      # a) <br>
      Jahre_var1 <- as.character(Jahre_var1)<br>
      # b) <br>
      Massenzunahme <- c(4.52, 2, 12.04, 0, 8.432)<br>
      AnzahlWochen  <- seq(0, 4, 1)<br>
      # c) <br>
      Massenzunahme/AnzahlWochen
      </code>
  </details>
<br>

 -->