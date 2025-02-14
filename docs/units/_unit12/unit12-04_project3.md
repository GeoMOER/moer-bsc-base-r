---
title: Marked Assignment - Project 3
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  image_description: "assignment"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---

## Project Task: Analyzing Disturbance Patterns in Forests Using R

This project is inspired by the study ["Landscape patterns in stand-replacing disturbances across the world’s forests"](https://www.nature.com/articles/s41893-024-01450-3) by Acil, Sadler, Senf, Suvanto & Pugh in *Nature Sustainability*, **8**, 86-98 (2005)

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