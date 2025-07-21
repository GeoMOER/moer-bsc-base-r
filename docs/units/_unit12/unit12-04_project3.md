---
title: Marked Assignment - Project 3
published: true
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  image_description: "assignment"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---

The  salamander *Salamandra salamandra* is an amphibian native to central and southern Europe. In Germany, it predominantly inhabits humid, deciduous and mixed forests in mid-elevation mountain regions, where cool streams provide suitable breeding habitats for its aquatic larvae.

The species is classified as “specially protected” under the German Federal Nature Conservation Act (BNatSchG).

Thanks to extensive contributions from state environmental agencies, the Federal Agency for Nature Conservation (BfN), and numerous working groups and regional committees of NABU, the German Society for Herpetology and Herpetoculture (DGHT e.V.) compiled detailed distribution records. These data have been published in the "DGHT e.V. (Ed. 2018): Verbreitungsatlas der Amphibien und Reptilien Deutschlands"

The data were provided as presence-absence maps for two time periods, 1980–1999 and 2000–2018.

These records were spatially aggregated per TK25 map sheet (1:25,000 topographic map grid, by the [BKG](https://www.bkg.bund.de/), [dl-de/by-2-0](https://www.govdata.de/dl-de/by-2-0)).

Additionally, per map grid there Forest cover data was also added, specifically the percentage of broadleaf/mixed forest per grid cell, derived from   Copernicus High-Resolution Layers (provided for two time periods; see: https://land.copernicus.eu/).

Lastly, Worldclim data on elevation and total annual precipitation (WorldClim version 2.1 climate data for 1970-2000) was averaged for each grid cell. Missing values indicated by 999.

# Task 1 - required for all

1) What were the average environmental conditions (elevation, forest cover, precipitation) in grid cells where fire salamanders were present during 1980–1999? 

2) Analyze the change in the distribution of the fire salamander between the two time periods.

3) Did the forest cover change significantly in grid cells where fire salamanders were present in 1980–1999, but absent in 2000–2018?

# Task 2 - MSc required, BSc bonus

Given a logistic regression model:

```{r}
model <- glm(presence ~ elevation + I(elevation^2) + precip + forest_pct,
             data = model_data, family = "binomial")

```
Use this model to predict occurrence probability using new forest cover data and evaluate predictions vs. observed presence in 2000–2018.

How many quadrants have a > 70% occurrence probability?

How many of the high-probability quadrants also have confirmed presence in 2000-2018?



# Task 3 - not required / Bonus points 
Create a map showing the probability of distribution based on the model in task 2. Add a detailed description.






Data Sources:
DGHT e.V. (Hrsg. 2018): Verbreitungsatlas der Amphibien und Reptilien Deutschlands, auf Grundlage der Daten der Länderfachbehörden, Facharbeitskreise und NABU Landesfachausschüsse der Bundesländer sowie des Bundesamtes für Naturschutz. (Stand: 1. Aktualisierung August 2018)

Fick, S.E. and R.J. Hijmans, 2017. WorldClim 2: new 1km spatial resolution climate surfaces for global land areas. International Journal of Climatology 37 (12): 4302-4315.




<!--

## Project Task: Analyzing Disturbance Patterns in Forests Using R

This project is inspired by the study ["Landscape patterns in stand-replacing disturbances across the world’s forests"](https://www.nature.com/articles/s41893-024-01450-3) by Acil, Sadler, Senf, Suvanto & Pugh in *Nature Sustainability*, **8**, 86-98 (2025)

Stand-replacing disturbances are natural or human-caused events that lead to the sudden death of a group of trees, significantly impacting carbon cycling and habitat diversity. They vary greatly in size, shape, and spatial arrangement. Which patterns are formed depends on a complex interplay of factors, including the forest's condition, the broader environmental context, and the disturbance agent.

In the referenced study, Landsat-based tree cover loss data from the Global Forest Change (GFC) dataset, along with additional sources, were used to identify disturbances, describe patch structures and to classify them into four categories, and assign the responsible agents. Additionally, it was determined whether each patch was located inside or outside of intact forests.

For this task, I have created a synthetic dataset based on this example.  
```Please note: the data does not necessarily reflect real-world distributions or findings. Interpret the results solely as an exercise, and do not use them as a basis for further work or discussions.```

For the biome assigned to you, create visualizations and analyses to address the following points:

- Show how the number of patches is distributed across the different patch types.

- Identify the proportion of different disturbance agents for each patch type and for overall forest damage.

- Analyze whether the proportions of disturbance agents differ between patches located inside and outside of intact forests.


Present your results using clear, well-structured graphs which are suited to represent proportional data. Provide a detailed description of the distributions you observe. 
You can improve your grade by up to 1.5 points if you apply an appropriate statistical test (e.g., from the [Biostatistics Handbook](https://www.biostathandbook.com/testchoice.html)) to test your observations for the last task.

## Data Files:

You will find all the necessary data on ILIAS. There are two datasets provided:

"Classification.txt":
Contains the patch ID (Gap_ID) and the assigned patch type (si = small-isolated patches with small areas, cl = clustered, co = complex patches with stretched shapes, lm = large-multiyear patches).

"Geoinfo.csv":

Includes the patch ID (Gap_ID), the biome type ("Boreal forests and taiga", "Mangroves", "Mediterranean forests, woodlands and scrubs","Temperate broadleaf and mixed forests","Temperate conifer forests", "Tropical and subtropical coniferous forests", "Tropical and subtropical dry broadleaf forests","Tropical and subtropical moist broadleaf forests"), the disturbance agent ("Other", "Urban", "Tree Farms", "Shifting Agriculture", "Harvest", "Fire"), and information on whether the majority of the patch lies within an intact forest ("inside") or outside of it ("outside").

The folder also contains a reference table (Assigned_Biome.csv) to help you identify your assigned biome.

#### Please submit your project folder as zip until 13.03.2025 in Ilias

-->