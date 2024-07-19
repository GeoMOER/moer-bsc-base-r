---
title: "Project 3: Insects decline and Landuse"
published: true
---

## Project 3: Insects decline and Landuse

#### Background:
Recent studies have highlighted declines in various insect groups. However, limited time-series data and narrow taxonomic focus have left questions about whether these declines are widespread and share common causes across different land-use types and taxa. Human land use, particularly farming practices such as insecticide application, mowing, soil disturbance, and changes in plant communities through herbicide or fertilizer use, is believed to be a major driver of these declines. Let’s test it!

#### Task:
Insects have been recorded since 2008 as part of the Biodiversity Exploratories. The insects from the first 10 years have now also been identified by entomologists, who’ve sent your supervisor the data  as csv. In addition, ATKIS was used to calculate the proportion of land use types within certain distances around the plots.

Download your assigned .csv from the “Insects” folder. Download the zip 226007_3, which contains the % of arable land.


##### Your supervisor is now asking you to do the following:

1. Prepare a general overview over the data and to document your steps
2. Calculate the average abundance and species richness per year and plot
3. **For each plot**, extract the decline in the number of individuals and species per year, aka the slope of a simple linear model as shown in this code for the number of individuals:

```{r}
# Log-transform the individual counts
data$log_Individuals <- log(data$Individuals + 1)
# Fit a linear model to the log-transformed data
model <- lm(log_Individuals ~ Year, data = data)
summary(model)
# Extract the slope (Year coefficient) from the model
slope <- coef(model)["Year"]
decline_abundance <-  exp(slope) - 1
```

Alternatively, if you can't get that to work,  calculate for each plot the difference in mean abundance and species richness between 2008 and 2018.

4. Now plot the decline against the proportion of arable field in the nearest environment.  
5. Create a map of the plots using the dataset 1000_9, which contains the coordinates of the plot (Longitude on the X axis, latitude on the Y axis). Make it as informative as possible, i.e. by scaling the size of the points according to species richness. Feel free to use packages and help from the internet to gain an extra point.  

Remember, 
For your upcoming meeting with your supervisor, you have two main deliverables to prepare:

- Commented R-Project:
Develop a well-structured R-Project that includes all the necessary code, comments, and annotations. Ensure that your R-Project is organized into clear sections and that the code is well-documented.

- Short Report:
    - Write a concise report that describes the data you are working with, how you handled the data, and provides essential summary statistics. Detail the data, the time frame it covers, and any data quality considerations.
    - Summarize the data handling steps you took, such as addressing missing values and handling outliers. Present summary statistics for the variables of interest. 
    - Create the desired graphs thabd ensure that these graphs are properly labeled and easy to interpret.
    - You can integrate the short report in your R-Project by using Markdown. Otherwise, write it in doc/x format.

Please refer to the project guidelines for detailed instructions and criteria for evaluation.
