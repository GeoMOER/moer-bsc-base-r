---
title: "Exercise: Object types in R"
toc: true
toc_label: "In this example"
header:
  image: /assets/images/unit_images/u03/header.png
  caption: "Image created with DALL E"
---

1. <br/>
   a) Create a vector named `vec1` with even numbers from 40 to 450, in steps of 4.<br/>
   b) How long is this vector? <br/>
   c) Access the last element in the vector. <br/>
   d) Extend the vector `vec1` by values from 450 to 494.<br/>
   e) Calculate the sum of `vec1`.

2. <br/>
   a) Create a matrix (named `mat1`) from `vec1` with 2 columns.<br/>
   b) Calculate the sum of `mat1`.<br/>
   c) Now create a matrix (named `mat2`) with 4 columns.<br/>
   d) Calculate the sum of `mat2`.<br/>
   e) What happened?<br/>
   f) Calculate the length of `vec1` divided by 5.<br/>
   g) Access the value at the 33rd row, 4th column of `mat2`.

3. <br/>
   a) Create a vector (`vec2`) with the first 10 letters of the alphabet (capitalized), each occurring 4 times. The class of this vector should be a factor. The factor levels should be in reverse order to the sequence in the alphabet (i.e., `A` should be listed as the last factor level when, for example, viewing the structure of the vector).<br/>
   b) Reverse the levels of `vec2`.

4. Create a list named “list1” from `vec1`, `mat1`, `mat2`, and `vec2`. Assign appropriate names to the elements of the list. Access the 32th row, 3rd column, of the 3rd element of this list.

5. <br/>
    a) Create a matrix that has as many columns and rows as `vec2` and name it `Dist`. It should be filled row-wise with values starting at 20.5, in steps of 1.<br/>
    b) In the lower half of the matrix, for odd columns, divide the individual values by 2, and for even columns, subtract 100. Name the result Dist2.