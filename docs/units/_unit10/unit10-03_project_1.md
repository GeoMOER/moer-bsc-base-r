---
title: "Project 1: EU Votes"
---

## Project 1: EU Votes

Imagine you have been hired as a data analyst for a research institute focusing on European political studies. The institute plans to conduct an analysis of links between socioeconomic developments of the different EU countries and their effects on the respective seats in the European Parliament's composition and its evolution over time. 
Your task is to prepare the raw data on the parliamentary seats per political group, gender balance among members, and voter turnout for one particular country across different periods. Your goal is to clean, transform, and visualize this data. Further, you have to document the process of preparation and visualization.

You have the following information on the rawdata/information:
#### _results.csv
The results of the election for each period.
- period:   the period for which the election was conducted
- PARTY_ID: ID of the party (can change between periods, for example "DE01" can refer to the SPD between 1994-1999 and to the CDU between 1999-2004)
- TYPE: whether the party is a party or a coalition (e.g. CDU/CSU)
- SEATS_TOTAL: the number of seats
- GROUP_ID: ID of the political group
#### groups.csv
IDs, Acronyms and Labels for all political groups, one for each language
- period:   the period for which the election was conducted
- ID: ID of the political group
- Language_ID: For which language the label is given
- Acronym: short group name
- Label: long group name, in different languages

#### _gender_balance_turnout.csv
The estimates of gender balance and turnout for your specific nation provided by Verian for the European Parliament.
- Year
- Men (Gender Balance): % of male voters
- Women (Gender Balance): % of female voters
- Turnout (your nation): % of turnout of your nation
- Turnout (EU): % turnout on EU level

There are also overview graphs, which can be used to check information such as party-group associations.

All data was taken from https://results.elections.europa.eu/en/tools/download-datasheets/

### Objectives

- Clean and Prepare the data  and fill in missing information if necessary
- Plot trends in seats per political group, gender balance, and voter turnout over time/per election period.  
- Prepare a report documenting the data preparation and visualization process.  
**TIPP: Not every given data is necessary for reaching your goal! / the Dataprovider might make mistakes**

Please refer to the project guidelines for detailed instructions and criteria for evaluation.
