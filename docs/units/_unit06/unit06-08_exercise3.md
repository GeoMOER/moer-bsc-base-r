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

<!--
1.  load the data called "SO2_measures.txt" which is located in the data-folder in Ilias.
2.  Find all entries from "StationA". 
3.   Replace all occurrences of "CO2" with "CarbonDioxide".  
3) Separate the strings into their components: stationname, date, hour, CO2, and SO2 using `strsplit()`   function. Use the results to create a dataframe with the help of `do.call(rbind, x)` and `as.data.frame()`. 

Make sure that every column has a suitable data type.
-->

1. 
    a) Create a project folder. Download and extract the .zip file "DataUnit06" into this folder.
    
    b) Load the two datasets "specdat" and "envdat" into your environment. Name them accordingly as "specdat" and "envdat".
   
    c) Transform "specdat" into a long format (named "speclong") so that the species (columns from the third column onwards) are in one column, and the corresponding coverage degrees are in a column named "CoverageDegrees".
  
    d) Calculate the mean, sum, and standard deviation per plot.
 
2. Merge "speclong" with "envdat" into "mergedat" without any information loss ;).
