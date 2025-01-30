---
title: "The apply-family"
published: true
toc: false
header:
  image: /assets/images/unit_images/u08/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---


The **apply()** family of functions in R provides a  way to apply a function to elements of matrices, lists, data frames, or grouped data. These functions are vectorized alternatives to loops (for or while), often making code more efficient and readable.

The main functions in the apply() family include:

| Function  | Works on                     | Returns               | Used for                                       |
|-----------|-----------------------------|------------------------|------------------------------------------------|
| `apply()`  | Matrices, data frames        | Vector, list, matrix   | Apply function over rows/columns               |
| `sapply()` | Vectors, lists               | Vector, matrix, list   | Simplified output version of `lapply()`        |
| `lapply()` | Lists, vectors               | Always a list          | Apply function to list elements                |
| `tapply()` | Vectors with grouping factor | Vector or list         | Apply function to subsets of data              |
| `mapply()` | Multiple vectors/lists       | Vector or list         | Apply function to multiple inputs              |


The **apply()** function is used when working with matrices or data frames to apply a function to rows (MARGIN=1) or columns (MARGIN=2).
```
apply(X, MARGIN, FUN, ...)
```

The **sapply()** function is a simplified version of **lapply()**, which we will discuss in detail [here]((/moer-bsc-base-r/unit09/unit09-05_lapply.html)), returning a vector or matrix instead of a list whenever possible.

```
sapply(X, FUN, ...)
```

The **tapply()** function is used when you have *grouped* data and need to apply a function to each group separately. This grouping variable is given by **INDEX**, 	
a list of one or more factors, each of same length as X.

```
tapply(X, INDEX, FUN, ...)
```

The **mapply()** function applies a function to multiple vectors or lists simultaneously.

