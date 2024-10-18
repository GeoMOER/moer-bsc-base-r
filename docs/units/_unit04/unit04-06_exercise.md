---
title: "Exercise: Objects and indexing in R"
published: false
toc: true
toc_label: "In this example"
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

1. Download the .rds file "Day4_Task1" from "Exercise - Data". When you click on the folder icon in your Environment and navigate to this file, you can load the `Emission_per_Country` dataset into your workspace. <br/>
    a) How many countries are there in total in the dataset?
    <details>
    <summary>Solution Task a)</summary>
      <code>
      total_countries <- length(unique(Emission_per_Country$Country))<br/>
      print(total_countries)
      </code>
    </details>
    <br>
    b) How many countries appear more than once?
    <details>
    <summary>Solution Task b)</summary>
      <code>
      duplicate_countries <- sum(duplicated(Emission_per_Country$Country))<br/>
      print(duplicate_countries)
      </code>
    </details>
    <br>
    c) Which countries produced more emissions in 2021 than the average? Note: at this point, we ignore that some countries appear twice and thus are counted twice in the calculation - that's a topic for another day.
    <details>
    <summary>Solution Task c)</summary>
      <code>
      avg_emissions_2021 <- mean(Emission_per_Country$CO2_2021_MT)<br/>
      high_emitters_2021 <- Emission_per_Country$Country[Emission_per_Country$CO2_2021_MT > avg_emissions_2021]<br/>
      print(high_emitters_2021)
      </code>
    </details>
    <br>
    d) Which country's emissions have reduced more from 1990 to 2021 than the median change?
    <details>
    <summary>Solution Task d)</summary>
      <code>
      median_change <- median(Emission_per_Country$Change_1990_2021_Percent)<br/>
      more_than_median <- Emission_per_Country$Country[Emission_per_Country$Change_1990_2021_Percent < median_change]<br/>
      print(more_than_median)
      </code>
    </details>
    <br>
    e) Sort the dataset by emissions in 2020. Which country has the third-largest emissions?
    <details>
    <summary>Solution Task e)</summary>
      <code>
      Emission_per_Country <- Emission_per_Country[order(-Emission_per_Country$CO2_2020_MT),]<br/>
      third_largest_emitter <- Emission_per_Country$Country[3]<br/>
      print(third_largest_emitter)
      </code>
    </details>
    <br>
    f) Name two variants that could be used to filter the data into a new data set called "relSmall", which only contains the countries that emitted less than the average (arothmetic mean).
    <details>
    <summary>Solution Task f)</summary>
      <code>
      avg_emissions <- mean(Emission_per_Country$CO2_2021_MT)<br/>
      relSmall1 <- subset(Emission_per_Country, CO2_2021_MT < avg_emissions)<br/>
      print(relSmall1)<br/>
      <br/>
      relSmall2 <- Emission_per_Country[Emission_per_Country$CO2_2021_MT < avg_emissions,]<br/>
      print(relSmall2)
      </code>
    </details>
    <br>

Please save your file as “FirstName_LastName_Task_Assignment05_Unit04.R”.
