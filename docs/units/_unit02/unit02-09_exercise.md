---
title: "Exercise: Vector Operations and Data Types in R"
published: false
header:
  image: "/assets/images/unit_images/u02/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/arielrobin-2483349/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1509707">Ariel</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1509707">Pixabay</a>'
---

In this exercise, we'll delve into vector creation and data type conversion in R, essential skills for data analysis.

**1.** Apply this command:  
```{r}
set.seed(1234)
```

**2.** Now, create a vector named "precipitation", measured as mm with 10 random values using the **runif**-function. Values should lie between 0 and 250. 

**3.** Look up the code table for [precipitatiopn type](https://codes.ecmwf.int/grib/format/grib2/ctables/4/201/) provided by the European Centre for Medium-Range Weather Forecasts (ECMWF) and generate a vector called "p_type"

**4.** Create a vector called "years", with  **even** numbers from 1990 to 2012.

**5.** What classes do the vectors have? Which classes should they have?




<!--
WiSe 24
**1.** Create a vector named Temperatures using the c() function with five random temperature values between 10 and 30 (you can choose the values). 


  <details>
   <summary>Solution Task 1</summary>
      <code>
      Temperatures <- c(10,14,16,18,20)
      </code>
  </details>
  

**2.** Create a new vector named Days containing the day numbers from 1 to 5 using the `seq()` function


 <details>
   <summary>Solution Task 2</summary>
      <code>
      Days <- seq(from=1,to=5)
      </code>
  </details>


**3.** Determine the data type of each vector.


 <details>
   <summary>Solution Task 3 </summary>
      <pre><code>
      class(Temperatures)  
      class(Days)
      </code></pre>
  </details>



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