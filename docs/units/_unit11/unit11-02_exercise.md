---
title: "Maps - Exercise"
header:
  image:  /assets/images/unit_images/u06/header.png
  image_description: ""
  caption: ""
---

Provide a map with the voter turnout per constituency.
Tip: it might be necessary to define the data types while reading in the data via *colClasses* (see help of read.csv). The the number of district should be a character.



## Info:
The data set ‘kerg2.csv’ contains the results for different types of areas (federal, state, constituency) for **first and second** votes as well as first explanatory lines. You will find this data set in the ‘original’ folder.  There you will also find shape files that are relevant for creating the maps.   

To simplify things, the data sets have already been partially prepared for you in the ‘Datapreperation_by_LH’ script:
1) The first explanatory lines have been deleted from kerg2.csv
2) Data entries have been translated into English, Umlaute were removed from the names of the parties
3) Columns have been reduced to the essentials
4) Information on the number of votes cast was created (prepared/NoResults.csv)

All data was taken from the [open-data of the Bundeswahlleiterin](https://www.bundeswahlleiterin.de/bundestagswahlen/2025/ergebnisse/opendata.html)(© Die Bundeswahlleiterin, Wiesbaden 2025)

### Table: `prepared/VoteCounts.csv`

| Column              | Explanation                                                                |
|---------------------|--------------------------------------------------------------------------|
| Type_of_Territory  | Type of territory (state, electoral district)                            |
| Number_of_district | ID number of electoral district                                         |
| Name               | Name of the territory                                                   |
| Level              | Type of superordinate area (BUND, LAND)                                 |
| Type               | Whether the sum refers to the number of eligible voters, votes cast, invalid votes, valid votes, etc. |
| First_or_Second    | Whether the sum refers to the first or the second vote                 |
| Sum_2025           | Total number of votes in 2025                                          |
| Sum_2011           | Total number of votes in 2011                                          |

---