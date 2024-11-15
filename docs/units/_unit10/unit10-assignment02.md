---
title: Unmarked Assignment 02 - indexing and subsetting
published: true
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---

The data for this exercise was downloaded from [Ourworldindata](https://ourworldindata.org/co2-and-greenhouse-gas-emissions),   
Friedlingstein et al.: Global Carbon Budget 2023, Earth Syst. Sci. Data, 15, 5301-5369, https://doi.org/10.5194/essd-15-5301-2023 

Download the file "Emission" from "Exercise - Data". When you click on the folder icon in your Environment and navigate to this file, you can load the `emission` dataset into your workspace. 
{% include figure image_path="/assets/images/unit_images/u10/loaddata.png" caption="You need to click here" %}




a) The dataset comprises information on the entity (e.g. country or continent), it's respective code, the year, the annual CO2 emission per capita and the source of the emission. First, use the vector given below to remove some non-country entities.

```
exclude <- c("Upper-middle-income countries", "European Union (27)","European Union (28)", 
             "Europe (excl. EU-27)",  "Europe (excl. EU-28)",
 "Europe", "Africa", "Asia", "Asia (excl. China and India)", "High-income countries", 
 "Lower-middle-income countries", "North America", "North America (excl. USA)", 
 "South Africa","South America",  "Upper-middle-income countries")
```

(if you can't make it work, continue without removing them)

 <details>
   <summary>Hint </summary>
     read [this]() carefully
  </details>



b) Sort the dataset by emissions. In which year, in which country and from which source did the largest annual CO2 emissions per capita originate?

c) What country produced the 10 greatest oil emissions in 2020? 
    
d) How many countries produced fewer gas emissions in 2020 than the average (mean)? 

Upload this assignment by 06.11.24 under the "Assignment" folder in Ilias in the following format:
A02_Lastname_Firstname.R