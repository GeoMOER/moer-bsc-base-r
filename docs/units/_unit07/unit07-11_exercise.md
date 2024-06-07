---
title: "Exercise: Data Visualization in R"
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

1. <br/>
    a) Download the dataset "eu_election_forecast" and read it into R. Convert the Column "Quelle" to "Source". Make sure that each column as the correct data type. <br/>
    b) What Sources of the forecasts are present in the dataset? Perform adjustments such as converting uppercase to lowercase, etc., so that there is only one way of spelling for each source (e.g convert all "insa" to "INSA"). Convert the "Source" column to factor. <br/>
    c) Record the frequency of forecasts of the different sources. <br/>
    d) Now calculate the frequency of each party's mentions across all forecasts (Tip: You can use the is.na() function to exclude any NA values.)<br/>
    e) Create a bar chart displaying the frequency of the parties over all forecasts.<br/>
    f) Calculate the mean forecast for each party for the year 2024. Create a pie chart to display the average forecasts of the elections for 2024.<br/>
    g) Create a histogram to show the distribution of percentages of SPD in 2024.<br/>
    h) Create a boxplot to compare the distribution of percentages of CDU/CSU between all forecasts of 2024.<br/>
<br/>
2. First, create a simple scatter plot where you plot percentage of AFD votes (Y-axis) against time (X-axis) in 2024. Then change the plot type to a plot where the points are sensibly connected with lines. What step is essential in this process?