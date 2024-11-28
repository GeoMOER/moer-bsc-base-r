---
title: "Unmarked Assignment 05 - reforming data"
published: true
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---
In this task, we'll work with an old familiar dataset, namely the emission-dataset first used in Assignment 2

1) Use the emission data created in Task 1a of Assignment 2, that is, after excluding non-country-entities

2) Calculate both the sum and the mean of CO2 emissions **per type (gas / oil) and entity (country)**. Name the data sets "total_CO2" and "average_CO2", respectively.

3) Merge total_CO2 and average_CO2 to one dataframe called "aggregated_data"

4) install and load the "reshape2" package and reform "aggregated_data" in a way, that for each entity the **average CO2** is shown in two columns, one for CO2-emissions created by gas, the other for CO2-emissions created by oil. 