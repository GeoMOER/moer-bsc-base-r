---
title: "Exercise: binding and merging"
toc: true
toc_label: "In this example"
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

1. <br/>
    a) Create a project folder. Download and extract the .zip file "DataUnit06" into this folder.<br/>
    b) Download and load the "vegan" package.<br/>
    c) Load the two datasets "specdat" and "envdat" into your environment. Name them accordingly as "specdat" and "envdat".<br/>
    d) Transform "specdat" into a long format (named "speclong") so that the species (columns from the third column onwards) are in one column, and the corresponding coverage degrees are in a column named "CoverageDegrees".<br/>
    e) Calculate the mean, sum, and standard deviation per plot.

2. Merge "speclong" with "envdat" into "mergedat" without any information loss ;).

<details>
   <summary>TIP</summary>
use %in% to see whether all plots of one data frame occur in the other e.g. Plots1[Plots1%in%Plots2]
</details>      