---
title: "Unmarked Assignment 05 - Transforming Data again"
published: false
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---

Let's practice data handling a little bit more!

For this, you will work with with real-world financial time-series data in the ETF.zip "data_ewj_manipulated" and  "data_spy_manipulated", that has been manipulated by wicked people. 

1) You know that the data is not "clean". Get an overview of the data using handy functions shown in Tipp 2.4 of [good practices](/moer-bsc-base-r/unit13/unit13-good_practices_0engl.html) and make sure the data to do necessary adjustments. Get also an overview of NAs.  

<!-- we might ignore the 9999 here-->

Colunn explanation:
X.TICKER. – Identifier of the ETF, similar to a product name or code   
X.PER. – Period of the data, e.g. D for daily observations.  
X.DATE. – The calendar date for this row (trading day).  
X.TIME. – Time of the record; for daily data this is usually 0 and not used.  
X.OPEN. – Price at the start of the trading day (opening price).
X.HIGH. – Highest price reached during that trading day.  
X.LOW. – Lowest price reached during that trading day.  
X.CLOSE. – Price at the end of the trading day (closing price).  
X.VOL. – Trading volume: how many shares were traded that day (a measure of market activity).  
X.OPENINT. – “Open interest”: number of open contracts  


2) Merge the data with "div_data" to the common denominators. 

Upload this assignment by 27.11.25 under the "Assignment" folder in Ilias in the following format:
A05_Lastname_Firstname.zip

<!--
In this task, we'll work with an old familiar dataset, namely the emission-dataset first used in Assignment 2

1) Use the emission data created in Task 1a of Assignment 2, that is, after excluding non-country-entities

2) Calculate both the sum and the mean of CO2 emissions **per type (gas / oil) and entity (country)**. Name the data sets "total_CO2" and "average_CO2", respectively.

3) Merge total_CO2 and average_CO2 to one dataframe called "aggregated_data"

4) install and load the "reshape2" package and reform "aggregated_data" in a way, that for each entity the **average CO2** is shown in two columns, one for CO2-emissions created by gas, the other for CO2-emissions created by oil. 
-->