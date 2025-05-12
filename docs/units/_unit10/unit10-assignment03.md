---
title: Unmarked Assignment 03 - reading in and writing data
published: true
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---

Read chaper 05 - In- and output of Data!

The data for this exercise was downloaded from [Ourworldindata](https://ourworldindata.org/co2-and-greenhouse-gas-emissions),   
Friedlingstein et al.: Global Carbon Budget 2023, Earth Syst. Sci. Data, 15, 5301-5369, https://doi.org/10.5194/essd-15-5301-2023 

#### 1. Create a template for how you want to organize your future projects (folderstructure) and rules on how to name your files (both data and R-Scripts). Submit this in form of an .txt file
  This example shows how you *could* structure it - it's by no means good and shall just illustrate what is meant by this task. Adapt it to your specific style, requirements and what you think is good. At the end of the course, we'll discuss whether your structure and naming rules worked out or not.
  Add a README.txt which contains what you think is important for data descriptions.

  ```
  Folderstructure

  └── my_awesome_project          | Name of the project, see rules
      ├── data                    | all data files go here
      ├── run_analyses.R          | Script to run your super analysis, add versioning numbers etc

  ```

#### 2. Create a folder structure accordingly for this assignment, download the files "emission1", "emission2", "emission3" and "emission4" and save them in the folder of your choice.  

#### 3. Read in all emission-dataframes (1-4) using a suitable function-argument combination. Check with **str()** whether the data is in the right format.  

#### 4. Extract from one of the dataframes the C02 emissions of the year 2020 and safe it as a .csv in your folder structure. Zip your whole folder and upload it


Upload this assignment by 16.05.25 under the "Assignment" folder in Ilias in the following format:
A03_Lastname_Firstname.zip