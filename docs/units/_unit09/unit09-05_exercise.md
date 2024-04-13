---
title: "Exercise: Loops and if/else"
toc: true
toc_label: "In this example"
---
## Part 1
1. - Copy the following lines:
      ```
      df1 <- data.frame(X = c(1, 2, 3, 4, 5), Y = c(10, 12, 8, 15, 20))
      df2 <- data.frame(X = c(2, 3, 4, 5, 6), Y = c(5, 8, 10, 12, 15))
      df3 <- data.frame(X = c(3, 4, 5, 6, 7), Y = c(8, 10, 12, 15, 18))
      ```
   - Create a list from these lines.
   - Use this list to generate a loop that plots X against Y for each dataset.
   - Color the points red if the sum of X is greater than 20.

## Part2
1. Background: Within the project "Nature 4.0", an "Automated Moth Trap" (AMT) was tested, which attracts moths using UV light and photographs them at regular intervals. Ideally, the resulting images are analyzed by AI, which requires considerable training. The annotations (bounding boxes) made by the AI are stored in .yaml files. <br/>
<br/>
   Dataset "df" includes: Each image made along with its timestamp and the number of bounding boxes. Coordinates of the bounding boxes, if drawn, are stored under BB.X1, BB.X2, BB.Y1, BB.Y2.
   - Your Tasks: The provided script might be applicable to your data. To determine its usefulness, you need to understand the script. Imagine the people who evaluated the data via AI did not comment on the script and over time, have forgotten what exactly was going on. Unfortunately, ChatGPT is also overloaded. Now its your turn!

2. Engage in teams of two with your respective code snippets and answer the questions:<br/>
      **Team 1:**
      ```
      if (nrow(countsM) == 0) {
          mothcount <- 0
      } else {
          countsM <- countsM[countsM$Class_Model == "moth", ]
          if (nrow(countsM) == 0) {
              mothcount <- 0
          } else if (nrow(countsM) == 1) {
              mothcount <- 1
          }
      }
      ```
      Questions:<br/>
      **a)** How many elements does “mothcount” have?<br/>
      **b)** Under what condition is “countsM” filtered to include only moths?<br/>
      **c)** Why is the number of rows checked twice?<br/>
      **d)** If "countsM" contained 4 rows with moths, what would "mothcount" be?<br/>
      **e)** What condition should be added to count multiple moths?

      **Team 2:**
      ```
      start <- as.POSIXct("2021-07-06 23:00:12 CEST")
      hourly <- data.frame(CST=unique(df$CST)[1],
                           Startdate=df[df$Time>"21:59:59"&df$Time<"22:02:00","Date"][1],
                           Hour=c("22","23","00","01","02","03","04","05"))
      for (h in 1:nrow(hourly)) {
          cat(h, "\n")
          start.n <- start + (h - 1) * 60 * 60
          end <- start.n + 1 * 59 * 60
          hIDat <- df[df$timeDate >= start.n & df$timeDate <= end, ]
          if (nrow(hIDat[!is.na(hIDat$BB.X1), ]) == 0) {
              mothcount <- NA
          } else {
              countsM <- aggregate(BB.X1 ~ Date + Time + CST + Class_Model, hIDat, length)
          }
          hourly[h, "Model_count"] <- mothcount
      }
      ```
      Questions:<br/>
      **a)** What data type is h?<br/>
      **b)** What is the maximum value h can take?<br/>
      **c)** Which time spans rows are stored in "hIDat"?<br/>
      **d)** Is "countsM" created if no insects or moths are detected?<br/>
      **e)** What does the aggregate command do?<br/>
      **f)** Where is “mothcount” stored?

      **Team 3:**
      ```
      else {
          mothcount <- 0
          for (i in 1:(nrow(countsM) - 1)) {
            if (countsM[i + 1, "BB.X1"] > countsM[i, "BB.X1"]) {
              mothcount <- mothcount + countsM[i + 1, "BB.X1"] - countsM[i, "BB.X1"]
            }
          }
      }
      ```
      Questions:<br/>
      **a)** What data type is i?<br/>
      **b)** What is the maximum value i can take?<br/>
      **c)** What value would mothcount receive if there were previously 3 moths counted, in the 5th row of countsM at BB.X1 the value was 5, and at BB.X1 in the 6th row a value of 7?<br/>
      **d)** What value would mothcount receive if there were previously 3 moths counted, in the 5th row of countsM at BB.X1 the value was 5, and at BB.X1 in the 6th row a value of 5?<br/>
      **e)** What value would mothcount receive if there were previously 3 moths counted, in the 5th row of countsM at BB.X1 the value was 5, and at BB.X1 in the 6th row a value of 3?

4. After discussing in groups, explain to other teams what your snippets do. Now try to integrate the code at the appropriate places.

5. - With the code, you can now calculate the number of moths for a single plot for a day.
   - Modify it so that the number of insects is also stored.

## Part 3
1. **Task 1:**
    - Load the data "ArtMatrixFalter.RData" (object called moth_wide0). In it, each plot (row) lists the number of each species (column).
    - Create a function that calculates the Shannon Index (Hint: refer back to the materials from the first day of the course).
    - Now calculate the Shannon Index for each plot. Do not use the vegan package for this task!

2. **Task 2:**
    - Create a function "niceplot" that attractively plots the number of individuals (y-axis) against the elevation (x-axis) as a point plot and execute this function using lapply over the data.list (mothlist.RData).
    - Include as a possible specification in this function whether a line should be drawn through the points: niceplot(x, line=TRUE) or niceplot(x, line=FALSE).