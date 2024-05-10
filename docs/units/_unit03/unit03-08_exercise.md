---
title: "Exercise: Object types in R"
toc: true
toc_label: "In this example"
header:
  image: /assets/images/unit_images/u03/header.png
  caption: "Image created with DALL E"
---

**1.** <br/>
   a) Create a vector named `vec1` with even numbers from 40 to 450, in steps of 4.<br/>
   b) How long is this vector? <br/>
   c) Access the last element in the vector. <br/>
   d) Extend the vector `vec1` by values from 450 to 494.<br/>
   e) Calculate the sum of `vec1`.

<details>
   <summary>Solution Task 1</summary>
      <code>
      # a) <br>
      vec1 <- seq(40,450, by = 4)<br>
      # b) <br>
      length(vec1)<br>
      # c) <br>
      vec1[length(vec1)]<br>
      # d) <br>
      vec1 <- c(vec1, 450:494)<br>
      # e) <br>
      sum(vec1)<br>
      </code>
</details>
<br>

**2.** <br/>
   a) Create a matrix (named `mat1`) from `vec1` with 2 columns.<br/>
   b) Calculate the sum of `mat1`.<br/>
   c) Now create a matrix (named `mat2`) with 4 columns.<br/>
   d) Calculate the sum of `mat2`.<br/>
   e) What happened?<br/>
   f) Calculate the length of `vec1` divided by 5.<br/>
   g) Access the value at the 33rd row, 4th column of `mat2`.

<details>
   <summary>Solution Task 2</summary>
      <code>
      # a) <br>
      mat1 <- matrix(vec1, ncol = 2)<br>
      # b) <br>
      sum_mat1 <- sum(mat1)<br>
      # c) <br>
      mat2 <- matrix(vec1, ncol = 4)<br>
      # d) <br>
      sum_mat2 <- sum(mat2)<br>
      # e) <br>
      Different sums because vector doesn't fit perfectly inside the matrix.<br>
      # f) <br>
      length(vec1) / 5<br>
      # g) <br>
      value_33_4 <- mat2[33, 4]<br>
      </code>
</details>
<br>

**3.** <br/>
   a) Create a vector (`vec2`) with the first 10 letters of the alphabet (capitalized), each occurring 4 times. The class of this vector should be a factor. The factor levels should be in reverse order to the sequence in the alphabet (i.e., `A` should be listed as the last factor level when, for example, viewing the structure of the vector).<br/>
   b) Reverse the levels of `vec2`.

<details>
   <summary>Solution Task 3</summary>
      <code>
      # a) <br>
      vec2 <- factor(rep(LETTERS[1:10], each = 4), levels = rev(LETTERS[1:10]))<br>
      # b) <br>
      vec2 <- factor(vec2, levels = rev(levels(vec2)))
      </code>
</details>
<br>

**4.** Create a list named “list1” from `vec1`, `mat1`, `mat2`, and `vec2`. Assign appropriate names to the elements of the list. Access the 32th row, 3rd column, of the 3rd element of this list.

<details>
   <summary>Solution Task 4</summary>
      <code>
      list1 <- list(vec1 = vec1, mat1 = mat1, mat2 = mat2, vec2 = vec2)
      value <- list1$mat2[32, 3]
      </code>
</details>
<br>


**5.** <br/>
    a) Create a matrix that has as many columns and rows as the length of `vec2` and name it `Dist`. It should be filled row-wise with values starting at 20.5, in steps of 1.<br/>
    b) In the lower half of the matrix, for odd columns, divide the individual values by 2, and for even columns, subtract 100. Name the result Dist2.

<details>
   <summary>Solution Task 5</summary>
      <code>
      # a) <br>
      Dist <- matrix(seq(20.5, by = 1, length.out = length(vec2) * length(vec2)), 
               nrow = length(vec2), 
               ncol = length(vec2), 
               byrow = TRUE)
      <br/>
      <br/>
      # b)<br>
      Dist2 <- Dist<br/>
      rows <- nrow(Dist2)<br/>
      cols <- ncol(Dist2)<br/>
      <br/>
      lower_half_rows <- (rows/2 + 1):rows<br/>
      <br/>
      # For odd columns in the lower half, divide values by 2<br/>
      Dist2[lower_half_rows, seq(1, cols, 2)] <- Dist2[lower_half_rows, seq(1, cols, 2)] / 2<br/>
      <br/>
      # For even columns in the lower half, subtract 100 <br/>
      Dist2[lower_half_rows, seq(2, cols, 2)] <- Dist2[lower_half_rows, seq(2, cols, 2)] - 100
      </code>
</details>
<br>

Please save your file as “FirstName_LastName_Task_Day3_Unit03.R”.
