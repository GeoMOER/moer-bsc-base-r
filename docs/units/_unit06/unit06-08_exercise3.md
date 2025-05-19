---
title: "Exercise: binding and merging"
published: true
toc: true
toc_label: "In this example"
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---
<!--more-->


1.  load the data called "SO2_measures.txt" which is located in the data-folder in Ilias.
2.  Find all entries from "StationA". 
3.   Replace all occurrences of "CO2" with "CarbonDioxide".  
3) Separate the strings into their components: stationname, date, hour, CO2, and SO2 using `strsplit()`   function. Use the results to create a dataframe with the help of `do.call(rbind, x)` and `as.data.frame()`. 

Make sure that every column has a suitable data type.


1. <br/>
    a) Create a project folder. Download and extract the .zip file "DataUnit06" into this folder.
    <!--<details>
    <summary>Solution Task 1a)</summary>
      <code>
      dir.create("../gesammelteWerke/ProjectFolder")   <br>
      unzip("../gesammelteWerke/DataDay04.zip", exdir = "../gesammelteWerke/ProjectFolder")
      </code>
    </details>
    <br>
    -->
    
    b) Load the two datasets "specdat" and "envdat" into your environment. Name them accordingly as "specdat" and "envdat".
    <!--<details>
    <summary>Solution Task 1c)</summary>
      <code>
      specdat <- read.csv("../gesammelteWerke/ProjectFolder/DataDay04/specdat.csv") <br>
      envdat  <- read.table("../gesammelteWerke/ProjectFolder/DataDay04/envdat.csv", sep =";", dec = ",", header = TRUE)
      </code>
    </details>
    <br>
    -->
    c) Transform "specdat" into a long format (named "speclong") so that the species (columns from the third column onwards) are in one column, and the corresponding coverage degrees are in a column named "CoverageDegrees".
    <!--<details>
    <summary>Solution Task 1d)</summary>
      <code>
      library(tidyr)  # Load tidyr for data transformation <br>
      speclong <- pivot_longer(specdat, cols = -c(1:3), names_to = "Species", values_to = "CoverageDegrees")
      </code>
    </details>
    <br>
    -->
    d) Calculate the mean, sum, and standard deviation per plot.
  <!--  <details>
    <summary>Solution Task 1e)</summary>
      <code>
      library(dplyr)  # Load dplyr for data manipulation <br>
      statistics <- speclong %>% <br>
      group_by(Plot) %>% <br>
        summarise( <br>
          Mean = mean(CoverageDegrees, na.rm = TRUE), <br>
          Sum = sum(CoverageDegrees, na.rm = TRUE), <br>
          SD = sd(CoverageDegrees, na.rm = TRUE)<br>
        )
      </code>
    </details>
    <br>

2. Merge "speclong" with "envdat" into "mergedat" without any information loss ;).
<!--
<details>
    <summary>Solution Task 2)</summary>
      <code>
      unique(speclong$Plot)<br>
      speclong$Plot[speclong$Plot == "PlotA"] <- "A"<br>
      unique(envdat$Plot)<br>
      envdat$Plot[envdat$Plot == "c"] <- "C"<br>
      colnames(speclong)[3] <-  "Runde"<br>
      mergedat <- merge(speclong, envdat, by = c("Plot", "Runde"))
      </code>
    </details>
<!--
<details>
   <summary>TIP</summary>
use %in% to see whether all plots of one data frame occur in the other e.g. Plots1[Plots1%in%Plots2]
</details>      
-->