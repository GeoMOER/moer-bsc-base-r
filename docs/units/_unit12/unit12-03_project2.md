---
title: Marked Assignment - Project 2
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  image_description: "assignment"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---


On 23 February there will be federal elections in Germany. We will take this as an opportunity to process the data on the last election (2021) provided by the Federal Electoral Administration in our Project 2.


## A short background information for students outside Germany:

The German Bundestag is elected according to the so-called personalised proportional representation. Germany is divided into 299 electoral districts.  
1) First vote: The candidate who receives the relative majority of first votes in a electoral district becomes a direct mandate and moves directly into the Bundestag provided that the proportion of second votes allows this.  
2) Second vote: This determines the party-political composition of the Bundestag. Each party draws up a list of candidates at state level (state list). The parties that either receive at least 5% of the second vote or win at least 3 direct mandates (‘basic mandate clause’) take part in the distribution of seats. If a party wins more direct mandates (first vote) in a federal state than the total number of seats it would be entitled to according to the proportion of second votes, there were so-called overhang mandates until the 2023 reform - i.e. seats that were not balanced out by the proportion of second votes. To compensate for this advantage, equalising seats were introduced, i.e. the other parties were given additional seats to restore the majority balance. Since the 2023 electoral law reform, direct mandates only count if they are covered by the second votes. This means that a party can no longer retain additional direct mandates if it receives fewer seats overall. Independent candidates without association with a party continue to retain their seat in the Bundestag.
{: .notice--info}

The results of the last Bundestag election (2021), structural data of the electoral districts and geometries of the electoral districts are provided by the **Bundeswahlleiterin here (© Die Bundeswahlleiterin, Wiesbaden 2024)**. The following parties are currently represented in the Bundestag: SPD, CDU, Greens, FDP, AfD, CSU, Die Linke, SSW. The latter is a party of national minorities that is not taken into account for the following task.

## Your task
Your task is to calculate, for the country assigned to you (see data set: Assigned_state)
1) the voter turnout (ratio of **number of votes** to the number of **eligible voters**) for the individual electoral districts and in total. The total and average voter turnout should be set against that of the previous election and presented in an appealing way.  
2) To discuss graphically whether the percentage of *second votes* of SPD, Greens, FDP, Die Linke and CDU/CSU 2021 are related to the following structural data:  
2a) the population  
2b) % of foreigners in the population  
2c) disposable income per household  
Please note that although the CDU and CSU are independent parties, they act as so-called sister parties in the Bundestag and votes that fall to these two parties must be added together. Additionally, the data was prepared to be readable across systems.
```{r}
parties <- c("CDU", "CSU", "AfD","FDP", "DIE LINKE","SPD","GRUeNE")
```
3) Voluntary extra task (improvement by max. 1.5 grade points): provides a map with the voter turnout per constituency.
Tip: it might be necessary to define the data types while reading in the data via *colClasses* (see help of read.csv). The the number of district should be a character.

## Provided data
You can find all the necessary data in the ‘Project II’ folder on Ilias. 

The data set ‘kerg2.csv’ contains the results for different types of areas (federal, state, constituency) for **first and second** votes as well as first explanatory lines. You will find this data set in the ‘original’ folder.  There you will also find shape files that are relevant for task 3.   

To simplify things, the data sets have already been partially prepared for you in the ‘Datapreperation_by_LH’ script:
1) The first explanatory lines have been deleted from kerg2.csv
2) Data entries have been translated into English, Umlaute were removed from the names of the parties
3) Columns have been reduced to the essentials
4) The original data set has been split into the actual votes (prepared/VoteCounts.csv) and information on the number of votes cast (prepared/NoResults.csv)
5) Reduced structural data can be found in prepared/structure.csv

All data was taken from the [open-data of the Bundeswahlleiterin](https://www.bundeswahlleiterin.de/bundestagswahlen/2021/ergebnisse/opendata.html)(© Die Bundeswahlleiterin, Wiesbaden 2024)

### Table 1: `prepared/VoteCounts.csv`

| Column              | Explanation                                                                |
|---------------------|--------------------------------------------------------------------------|
| Type_of_Territory  | Type of territory (state, electoral district)                            |
| Number_of_district | ID number of electoral district                                         |
| Name               | Name of the territory                                                   |
| Level              | Type of superordinate area (BUND, LAND)                                 |
| Type               | Whether the sum refers to the number of eligible voters, votes cast, invalid votes, valid votes, etc. |
| First_or_Second    | Whether the sum refers to the first or the second vote                 |
| Sum_2021           | Total number of votes in 2021                                          |
| Sum_2017           | Total number of votes in 2017                                          |

---

### Table 2: `prepared/Results.csv`

| Column              | Explanation                                        |
|---------------------|--------------------------------------------------|
| Number_of_district | ID number of electoral district                   |
| Name               | Name of the electoral district                     |
| Party_or_Person    | Name of the party or independent candidate         |
| First_or_Second    | Whether the sum refers to the first or second vote |
| Sum_2021           | Total number of votes in 2021                      |
| Sum_2017           | Total number of votes in 2017                      |

---

### Table 3: `prepared/structure.csv`

| Column                      | Explanation                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| State                       | Name of the state                                                          |
| Number_of_district          | ID number of electoral district                                           |
| Name                        | Name of the electoral district                                             |
| Total_population_in_tsd     | Population in thousands                                                   |
| Percentage_of_foreigners    | Percentage of people who are not German within the meaning of Article 116 (1) of the GG. |
| Disposable_income_pP        | Disposable income (Euro per head)                                         |
