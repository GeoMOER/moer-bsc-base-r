---
title: "Exercise: apply"
published: false
toc: true
header:
  image: /assets/images/unit_images/u08/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---

# Exercise 1

Use *apply()* to calculate the total precipitation per location

```{r}
rainfall <- matrix(sample(50:200, 25, replace = TRUE), nrow = 5)
```

<!--
solution:
```{r}
total_rainfall <- apply(rainfall, MARGIN = 1, FUN = sum)
```
-->


# Exercise 2
Use *sapply* to find the height of the tallest tree in each plot
```{r}
tree_heights <- list(
  Plot_A = c(15, 22, 19, 30),
  Plot_B = c(10, 14, 25, 18),
  Plot_C = c(5, 12, 15, 20)
)
```

<!--

```{r}
max_height <- sapply(tree_heights, max)
```

-->

# Exercise 3
Use *tapply* to calculate the average bird count per habitat

```{r}
bird_counts <- c(10, 20, 15, 50, 25, 30, 40, 45, 35, 60)
habitats <- c("Forest", "Forest", "Forest", "Wetland", "Wetland", 
              "Grassland", "Grassland", "Grassland", "Forest", "Wetland")
```

<!--

```{r}
mean_birds <- tapply(bird_counts, habitats, FUN = mean)
```
-->


# Exercise 4


Redo the list of data frames created in the previous exercise:

```{r}
df1 <- data.frame(X = c(1, 2, 3, 4, 5), Y = c(10, 12, 8, 15, 20))
df2 <- data.frame(X = c(2, 3, 4, 5, 6), Y = c(5, 8, 10, 12, 15))
df3 <- data.frame(X = c(3, 4, 5, 6, 7), Y = c(8, 10, 12, 15, 18))
```

This time, name the elements "df1", "df2" and "df3"

Now, create a function "niceplot" that attractively plots Y against X as a point plot and execute this function using lapply to plot all three dataframes at once. 
This function should also automatically change the plot title.
Add an option which allows you to colour points red if they are larger than a value of choice, though the default should be 10.


<!--
```{r}

niceplot <- function(x, threshold=14) {
  
  data <- df.list[[x]]  # Extract the dataframe from the list
  
  # Define colors: Red if Y > threshold, otherwise black
  colours <- ifelse(data$Y > threshold, "red", "black")
  
  # Create the plot
  plot(Y ~ X, data = data, ylim = c(2, 22), xlim = c(1, 7), 
       main = x, pch = 19, col = colours)
}

lapply(names(df.list), function(x)niceplot(x,threshold=10))
```

-->