---
title: "Exercise: Greenhouse gases in CO₂ equivalents"
toc: true
toc_label: "In this example"
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

During the following tasks, document your thought processes and any newly learned functions. You should be able to present next week, in a form of your choice, how you found your solution. For example, you could note, "when looking for help with the function xyz, we noticed in the argument list that..." or "Solution approach 1 did not work and resulted in the error message xyz".

Each group should note down 5 questions they would ask themselves about what they have learned. These questions should not duplicate between groups. Compile these under "Collected Works" under "Question Catalog Day 3".

1. Copy the code snippets provided bellow into your script and create a combined dataset named `Emission_per_Country` using rbind(). That code has some error's Note all necessary corrections you must apply to the code.

    ```r
    Data Frame 1: Belgium, Bulgaria, Denmark, Germany
    df_1 <- data.frame(
    Country = c"Belgium", "Bulgaria", "Denmark", "Germany",
    CO2_1990_MT = c(145.8, 99.0, 71.5, 1251.2),
    CO2_2020_MT = c(107.3, 48.0, 42.9, 730.9),
    CO2_2021_MT = c(111.0, 54.0, 43.9, 760.4)
    Change_2020_2021_MT = c(3.7, 5.9, 1.0, 29.4),
    Change_2020_2021_Percent = c(3.4, 12.4, 2.3, 4.0),
    Change_1990_2021_Percent = c(-23.9, -45.5, -38.7, -39.2)
    )

    Data Frame 2: Estonia, Finland, France, Greece
    df_2 <- data.frame(
    Country = c("Estonia" "Finland", "France", "Greece"),
    CO2_1990_MT = c(40.3, 71,3, 539.3, 104.0),
    CO2_2020_MT = c(11.4, 47.8, 392.3, 75.5),
    CO2_2021_MT = c(12.6, 47.9, 414.8, 77.5),
    Change_2020_2021_MT = c(1.2, 0.1, 22.5, 2.0),
    Change_2020_2021_Percent = c(10.6, 0.1, 5.7, 2.7),
    Change_1990_2021_Percent = c(-68.7, -32.8, -23.1, -25.5),
    )

    Data Frame 3: Ireland, Italy, Croatia, Latvia
    df_3 <- data.frame(
    Country = c("Ireland", "Italy", "Croatia", "Latvia"),
    CO2_1990_MT = c(55.6, 521.5, 31.5, 26.1),
    CO2_2020_MT = c(59.1, 385.0, 23.9, 10.5),
    CO2_2021_MT = c(62.1, 417.6, 24.4, 10.7),
    Change_2020_2021_MT = c(3.1, 32.6, 0.5, 0.2),
    Change_2020_2021_Percent = c(5.2, 8.5, 2.3, 2.3),
    Change_1990_2021_Percent = c(11.6, -19.9, -22.3, -58.8
    )

    Data Frame 4: Austria, Luxembourg, Malta, Netherlands
    df_4 <- data.frame(
    Country = c("Austria", "Luxembourg", "Malta", Netherlands),
    CO2_1990_MT = c(79.0, 12.7, 2.6, 222.7),
    CO2_2020_MT = c(73.9, 9.0, 2.1, 164.8),
    CO2_2021_MT = c(77.5, 9.4, 2.1, 167.7),
    Change_2020_2021_MT = c(3.6, 0.4, 0.0, 2.9),
    Change_2020_2021_Percent = c(4.9 4.0, 1.0, 1.7),
    Change_1990_2021_Percent = c(-01.9, -26.2, -18.8, -24.7)
    )

    Data Frame 5: Austria, Poland, Portugal, Romania
    df_5 <- data.frame(
    Country = c("Austria", "Poland", "Portugal", "Romania"),
    CO2_1990_MT = c(79.0, 474.8, 59.6, 257.1),
    CO2_2020_MT = c(73.9, 371.9, 58.1, 112.0),
    CO2_2021    = c(77.5, 399.9, 56.5, 115.4),
    Change_2020_2021_MT = c(3.6, 28.0, -1.6, 3.4),
    Change_2020_2021_Percent = c(4.9, 7.5, -2.8, 3.0),
    Change_1990_2021_Percent = c(-1.9, -15.8, -5.1, -55.1)
    )

    Data Frame 6: Sweden, Slovakia, Slovenia, Spain
    df_6 <- data.frame(
    Country = c(`Sweden`, "Slovakia", "Slovenia", "Spain"),
    CO2_1990_MT = c(71.5, 73.8, 18.8, 287.7),
    CO2_2020_MT = c(46.2, 37.2, 16.0, 272.2),
    CO2_2021_MT = c(47.8, 41.3 16.1, 288.8),
    Change_2020_2021_MT = c(1.6, 4.0, 0.1, 16.6),
    Change_2020_2021_Percent = c(3.5, 10.8, 0.8, 6.1),
    Change_1990_2021_Percent = c(-33.1, -44.1, -14.3, 0.4)
    )
    ```

2. Help: if you were unable to complete Task 1, you can download the .rds file "Day3_Task1" from "Collected Works". Do this only as a last resort. When you click on the folder icon in your Environment and navigate to this file, you can load the `Emission_per_Country` dataset into your workspace. <br/>
    a) How many countries are there in total in the dataset? <br/>
    b) How many countries appear more than once?<br/>
    c) Which countries produced more emissions in 2021 than the average? Note: at this point, we ignore that some countries appear twice and thus are counted twice in the calculation - that's a topic for another day.<br/>
    d) Which country's emissions have reduced more from 1990 to 2021 than the median change?<br/>
    e) Sort the dataset by emissions in 2020. Which country has the third-largest emissions?<br/>
    f) Name two variants that could be used to filter the data into a new data set called "relSmall", which only contains the countries that emitted less than the average (arothmetic mean).

3. Now...<br/>
    a) Create a project folder. Download and extract the .zip file "DataDay04" into this folder.<br/>
    b) Download and load the "vegan" package.<br/>
    c) Load the two datasets "specdat" and "envdat" into your environment. Name them accordingly as "specdat" and "envdat".<br/>
    d) Transform "specdat" into a long format (named "speclong") so that the species (columns from the third column onwards) are in one column, and the corresponding coverage degrees are in a column named "CoverageDegrees".<br/>
    e) Calculate the mean, sum, and standard deviation per plot.

2. Merge "speclong" with "envdat" into "mergedat".
