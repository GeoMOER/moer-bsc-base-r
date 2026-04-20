---
title: Unmarked Assignment 02 
published: true
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---

The data for this assignment was provided by the city of Marburg, which installed a sensor network across the city to get information about temperature and humidity hot spots.

a) Download the file "MarburgTemperature.RData" from "Data / Exercises and Assignments". When you click on the folder icon in your Environment and navigate to this file, you can load the `MarburgTemperature` dataset into your workspace. 
{% include figure image_path="/assets/images/unit_images/u10/loaddata.png" caption="You need to click here" %}

b) find the hottest temperture and the date when it has been measured over all three data sets.






<!-- WiSe 2025
The data for this exercise was downloaded from [Ourworldindata](https://ourworldindata.org/co2-and-greenhouse-gas-emissions),   
Friedlingstein et al.: Global Carbon Budget 2023, Earth Syst. Sci. Data, 15, 5301-5369, https://doi.org/10.5194/essd-15-5301-2023 

Download the file "Emission" from "Data / Exercises and Assignments". When you click on the folder icon in your Environment and navigate to this file, you can load the `emission` dataset into your workspace. 
{% include figure image_path="/assets/images/unit_images/u10/loaddata.png" caption="You need to click here" %}


a) The dataset comprises information on the entity (e.g. country or continent), it's respective code, the year, the annual CO2 emission per capita and the source of the emission. First, use the vector given below to remove some non-country entities.

```
exclude <- c(
  "High-income countries", "Low-income countries", "Lower-middle-income countries", "Upper-middle-income countries",
  "World",
  "European Union (27)","European Union (28)", "Europe (excl. EU-27)",  "Europe (excl. EU-28)","Europe", 
 "Africa", 
 "Asia", "Asia (excl. China and India)", 
"North America", "North America (excl. USA)", "South America")
```

(if you can't make it work, continue without removing them)

<!--
 <details>
   <summary>Hint </summary>
     read [this chapter](/moer-bsc-base-r/unit04/unit04-03_subsetting.html) carefully
  </details>

    
b) Which country produced the highest gas and the highest oil CO2 emissions in 2020? Answer by using R code, not sorting or filtering the table!


Upload this assignment, together with your code for exercise 3 and 4, by 06.11.25 under the "Submission/A02" folder in Ilias in the following format:
A02_Lastname_Firstname.R

-->