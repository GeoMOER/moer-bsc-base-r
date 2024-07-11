---
title: "Project 2: Biodiversity Exploratories"
---

## Project 2: Biodiversity Exploratories

This summer, you’re embarking on an exciting research journey as part of the ‘Biodiversity Exploratories’ project. You’re conducting your thesis on the topic of ‘land use effects on the microclimatic environment.’ Your research aims to understand how different land use practices impact the local climate in various natural plots. Before you commence your own data sampling and microclimatic modeling, your supervisor has assigned you a critical preliminary task. You are tasked with analyzing existing data collected from climate stations to gain insights into the changing measurements over time and how they relate on average to different land use components.

You have the following information on the rawdata/information:
#### plots.csv
Climate data for each location plot by month (here you need to subset the data to your specific location and time)
- plotID: first two letters indicating the location, third latter indicating the landuse (Grassland or Forest), numbers are the plot numbers
- datetime: time steps in month
- Ta_10: Air temperature 10 cm above ground (°C)
- Ta_200: Air temperature 200 cm above ground (°C)
- SM_10: Soil Moisture in 10 cm depth (%)
- Ts_10: Soil temperature in 10 cm depth (°C)


All data was taken from [https://www.bexis.uni-jena.de/ddm/publicsearch/index](https://www.bexis.uni-jena.de/ddm/publicsearch/index)

### Objectives
For your upcoming meeting with your supervisor, you have two main deliverables to prepare:

- Commented R-Project:
Develop a well-structured R-Project that includes all the necessary code, comments, and annotations. Ensure that your R-Project is organized into clear sections and that the code is well-documented. Write R code to import the existing data from climate stations, perform data cleaning and preprocessing as needed. Make sure to treat missing values thoughtfully. Visualize the annual variation of the variables (trends within years) and conduct a comparative analysis across years using diverse plot types. Include comments explaining the purpose and logic behind each step of your code (e.g. data was aggregated because….) Make sure your R-Project is reproducible, so anyone can understand and replicate your analysis.

- Short Report:
    - Write a concise report that describes the data you are working with, how you handled the data, and provides essential summary statistics. Detail the data, the time frame it covers, and any data quality considerations.
    - Summarize the data handling steps you took, such as addressing missing values and handling outliers. Present summary statistics for the variables of interest. 
    - Create the desired graphs that show how the measurements change over time and how they vary across the two components of land use. Ensure these graphs are properly labeled and easy to interpret.
    - You can integrate the short report in your R-Project by using Markdown. Otherwise, write it in doc/x format.

Please refer to the project guidelines for detailed instructions and criteria for evaluation.
