---
title: "Exercise: Indexing in R"
published: true
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

**1)**  

given this vector

```
numbers <- c(rep(c(1,4,5), each=4), seq(8,30,2))
```

extract the 6 to 10th and the 15th element

try to extract the 25th element

**2)**  

given the dataframe:

```
df <- data.frame(
  City = c("City A", "City B", "City C"),
  Population = c(500000, 700000, 1200000),
  Area = c(450, 700, 1000)
)
```

a) Extract the data for the second row of df using indexing by position.
b) Extract the value in the third row and second column of df.


**3)**

Given the matrix "scores":

```
scores <- matrix(c(85, 90, 78, 92, 88, 95), nrow = 2, ncol = 3, byrow = TRUE)
colnames(scores) <- c("Math", "Science", "History")
rownames(scores) <- c("Student1", "Student2")
```
Extract the Science score for Student 2 using row and column positions.

**4)**
Given this list:

```
person_info <- list(
  name = "Alice",
  age = 25,
  hobbies = c("Reading", "Hiking", "Cooking"),
  scores = c(Math = 85, Science = 90, History = 88),
  contact_info = list(
    email = "alice@example.com",
    phone = "123-456-7890"
  ),
  favorite_books = list(
    Fiction = c("Pride and Prejudice", "To Kill a Mockingbird"),
    Non_Fiction = c("Sapiens", "Educated")
  )
)
```

Extract Alice’s hobbies from the person_info list using name indexing, and then retrieve her second hobby from the result.
Retrieve Alice’s Science score from the scores element by name.
Retrieve the first book from her favourite fiction list


