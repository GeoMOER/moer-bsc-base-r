---
title: "Exercise: Recap"
toc: true
toc_label: "In this example"
---

This test is voluntary. The grade is only for feedback and will not be included in the overall grade.
- Important note: If you get stuck on a task, you can load the backup at any time: `load("backup200422.RData")`. Reload it before each task where you need to use it to avoid errors.

**Task 1a (5 Points):**
 - Load the datasets `ellenberg.txt`, `plants.csv`, and `PlotInfo.txt`. Name them Ewert, Comm, and PlotInfo, respectively. Specify the correct delimiter for each dataset, and for PlotInfo, also specify the decimal symbol—either by including it in the read command or as a comment after the read command. Note that `plants.csv` originally had row names. Restore these.<br/>

**Task 1b (5 Points):**
 - Create a new dataset named "DivEnv". The row names from "Comm" should form the "Plot" column. Additional columns should be calculated from Comm: for each row of Comm (i.e., each plot), calculate the number of individuals (new column name: "Ind") and the number of species (new column name: "Div").
  - Add two more columns, one for the meadow number (column "NoMeadow") and one for the survey square (column "NoQuad"). "NoMeadow" is found between "Meadow" and the underscore in the plot name, "NoQuad" is after the underscore in the plot name. Any functioning solution is acceptable; one approach involves clever use of the "rep" command.

**Task 2a (2 Points):**
  - For future calculations, the species lists from "Comm" and "Ewert" (column: Name) must match. Unfortunately, Ellenberg indicator values could not be determined for all species. Additionally, the delimiter used when writing names was not consistent. Correct the names in "Ewert". How many species still have no entries even after the correction? Use R to answer this question.

**Task 2b (3 Points):**
  - The following steps have been taken for you:
      ```r
      DivEnv2 <- DivEnv
      # Comm2 <- Comm[, Ewert$Name[Ewert$Name %in% colnames(Comm)]]
      # Ewert <- Ewert[Ewert$Name %in% colnames(Comm)]
      Comm2 <- Comm / rowSums(Comm)

      for (j in 2:4) {
        cat(j)
        DivEnv2[, ncol(DivEnv2) + 1] <- NA
        colnames(DivEnv2)[ncol(DivEnv2)] <- colnames(Ewert)[j]

        Ewert2 <- Ewert[match(Ewert$Name, colnames(Comm2)), ]
        Ewert2 <- Ewert2[!is.na(Ewert2$Name), ]

        matchV <- match(colnames(Comm2), Ewert2$Name)
        Comm3 <- Comm2[, matchV[!is.na(matchV)]]

        if (is.numeric(Ewert[, j]) == FALSE) {
          cat(paste0("Warning, extra information in column ", j, "! Data gets split"))
          ellen <- as.numeric(substr(Ewert2[, j], 1, 1))
        } else {
          ellen <- Ewert2[, j]
        }

        for (i in 1:nrow(Comm3)) {
          DivEnv2[i, ncol(DivEnv2)] <- weighted.mean(ellen, Comm3[i, ], na.rm = TRUE)
        }
      }
      ## 234 Warning, extra information in column 4! Data gets split
      ```
  - Questions about the code snippet:
    - A warning is issued if any of the values from Comm2 are not numeric.
    - The entries from the columns of Comm2 serve as weights in the calculation of weighted.mean.
    - Columns 2-4 from the dataset "Ewert" are used as values in the calculation of weighted.mean.
    - The for(i in 1:nrow(Comm2)) loop is executed before the for(j in 2:4) loop.
    - The results of the calculation are written into the rows of "DivEnv2".
    - A warning is generated when calculating column "F".

**Task 3 (2 Points):**
  - Convert "Comm" into a long format and name this new format "comm.long".

**Task 4 (3 Points):**
  - Merge the "PlotInfo" and "DivEnv2" datasets into a final dataset named "Datafinal" without losing any data.

**Task 5 (10 Points):**
  - Create three boxplots from the "Datafinal" dataset, each displaying the values of "L", "T", and "F" per meadow. The boxplots should be displayed side by side. Change a total of 5 aspects of the presentation, i.e., use 5 different commands.
  - Calculate the mean value for "L" per meadow, round it to two decimal places, and display these values under the corresponding boxes. Formulate a function or loop that could automate these steps for "T" and "F".

## Grading Scale

| Points min | Points max | Grade |
|------------|------------|------|
| 29.0       | 30.0       | 15   |
| 27.0       | 28.5       | 14   |
| 25.0       | 26.5       | 13   |
| 22.5       | 24.5       | 12   |
| 20.5       | 22.0       | 11   |
| 18.5       | 20.0       | 10   |
| 16.0       | 18.0       | 9    |
| 14.0       | 15.5       | 8    |
| 11.5       | 13.5       | 7    |
| 9.5        | 11.0       | 6    |
| 7.5        | 9.0        | 5    |
| 6.0        | 7.0        | 4    |
| 4.5        | 5.5        | 3    |
| 2.5        | 4.0        | 2    |
| 1.0        | 2.0        | 1    |
| 0.0        | 0.5        | 0    |

