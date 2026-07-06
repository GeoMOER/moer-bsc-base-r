---
title: Marked Assignment - Project SoSe 2026
published: true
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  image_description: "assignment"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
---

# Project Assignment: Hydrometeorology — River Discharge Response to Heavy Rainfall Events
 
## Background
Rivers don't react to rain instantly — water has to travel through the landscape and collect in tributaries before affecting the water level. Understanding how and how fast a river responds to rainfall is at the heart of flood forecasting and water resource management.
In this project, you will work with **real hydrological and meteorological data** to explore the relationship between precipitation and river water levels. By the end, each of you will have analyzed a stretch of a real German river.

---
 
## Your River & Gauging Stations
 
Germany's federal waterway authority operates a network of over 600 river gauging stations, many of which publish continuous water level records going back decades. For this project, you will select **5 gauging stations along the same river**.
 

**Where to find the data:**
👉 [pegelonline.wsv.de](https://www.pegelonline.wsv.de/gast/pegeltabelle)
 
When selecting your stations, make sure they:
- All belong to the **same river** (*Gewässer*)
- Include **long-term water level records** — look for the option *"Download langfristiger Wasserstände (Rohdaten)"*
- Are **not already claimed** by another student (see coordination note below)
> **Coordination:** To avoid duplicate stations and ensure good spatial coverage, please register your 5 chosen stations in the shared list in the ILIAS course folder before downloading anything. Rivers with many stations (e.g. the Elbe has ~25) can be split across multiple students.

---

## Interactive Map — DWD Weather Stations

### Your Weather Station

For each of your gauging stations, you'll also need **hourly precipitation data** from a nearby DWD (German Weather Service) station.
 
**Where to find the data:**
- Station list with coordinates: [RR_Stundenwerte_Beschreibung_Stationen.txt](https://opendata.dwd.de/climate_environment/CDC/observations_germany/climate/hourly/precipitation/historical/RR_Stundenwerte_Beschreibung_Stationen.txt)
- Hourly precipitation records: [opendata.dwd.de/…/precipitation/historical/](https://opendata.dwd.de/climate_environment/CDC/observations_germany/climate/hourly/precipitation/historical/)

---

### DWD Weather Station Map

To make life a bit more easy, this map showes all DWD weather stations.
Use this map to identify DWD weather stations near your study area.

> **Task:** Zoom into the map and click on a marker to see the station name and ID.
Find the closest station to your gauging station.
Use the retrieved ID to download the relevant meteorological datasets directly from the DWD Open Data portal.

<iframe src="dwd_map.html" width="100%" height="400px" style="border:none;"></iframe>

---
<details markdown="1">
  <summary><h1><strong>Part 1 — Getting to Know Your Data</strong></h1></summary>

  >**Submission deadline:** Please submit your first project till 02.06.2026 via ILIAS.

  <h2><strong>The question:</strong></h2>
  > **Is there a direct relationship between precipitation and water level at your station? When do water levels peak — and was it actually raining at the time?**
 
  Tasks 1–3 get your data into a shape where you can answer that question. Task 4 is where you answer it.
 



  <h2><strong>Task 1 — Data Import</strong></h2>
 
  Download and import the datasets for **one** of your gauging stations and its nearest weather station.

  **Key columns to work with:**
 
  | Dataset | Column | Description |
  |---|---|---|
  | Gauging station | `timestamp` | Date & time of measurement |
  | Gauging station | `value` | Water level [cm] |
  | Weather station | `MESS_DATUM` | Date & time of measurement |
  | Weather station | `R1` | Precipitation [mm] |
  | Weather station | `RS_IND` | Precipitation indicator (0 = none, 1 = yes, -999 = missing) |

  ---

  <h2><strong>Task 2 — Inspect & Clean</strong></h2>
 
  Take a close look at your data before doing anything with it and summarize it in your [report](/moer-bsc-base-r/unit12/unit12-01_project_guidelines.html).

  *Things to think about: What data types did R assign on import — are they correct? Do you have missing values? Is your time series without gaps?*

  ---

  <h2><strong>Task 3 — One dataframe to rule them all</strong></h2>

  Create a single merged dataframe with an hourly resolution that covers the overlapping time period of both datasets.

  *Things to think about: What does merging on a timestamp require?*

  ---

  <h2><strong>Task 4 — Is Rain Making the River Rise?</strong></h2>
 
  Now put your merged dataset to work. You're looking for evidence of a relationship between precipitation and water level — but that relationship may not be instantaneous.
 
  **a) Hourly scale**
 
  Find the single highest and lowest water levels in your record.
 
  - What were precipitation conditions like **at that exact hour**?
  - And in the **1-3 hours before**?

  **b) Daily scale**
  
  - On the day of the highest and lowest water levels — how much did it rain?
  - What about the **1–3 days before** each extreme?

  **c) Seasonal patterns**
 
  Calculate monthly averages for both precipitation and water level across your full record.
 
  - In which month is flood risk theoretically highest at your station?
  - Is the rainiest month also the month with the highest water levels? 

  ---

  <h2><strong>Bonus — Visualisation</strong></h2>
 
  Create one or two plots that bring your findings to life and summarize your results.
 
</details>

<details markdown="1">
  <summary><h1><strong>Part 2 — Automation Across the River</strong></h1></summary>
 
  <h2><strong>Background</strong></h2>
 
  In Part 1, you developed a workflow for **one** gauging station and its nearest weather station. In Part 2, you'll scale that workflow up to **all five** of your chosen stations — and use the combined dataset to look for patterns along your river.

  >**Submission deadline:** Please submit your second project till 26.07.2026 via ILIAS.

  ---

  <h2><strong>Task 1 — Automate Import & Merging</strong></h2>
 
  Apply the import, cleaning, and merging steps from Part 1 to all five gauging stations and their corresponding weather stations.
 
  *Things to think about: How can you avoid copy-pasting your Part 1 code five times? What are shared steps and what are unique identifier of your 5 data sets?*

  NOTE: IMPORT & MERGE MANUALLY IF YOU FAIL TO AUTOMATE THESE STEPS

  ---

  <h2><strong>Task 2 — Visualizing Along the River</strong></h2>
 
  > **Does the water level follow the geographical course of the river?**

  Depict the average, annual water level ordered along the river's course. 

  To order your stations correctly, you'll need the **river kilometre (Flusskilometer)** and **gauge zero point (Pegelnullpunkt, PNP)** for each station. These are listed on the station's *Stammdatenblatt* (master data sheet), available via:
 
  - [pegelonline.wsv.de](https://www.pegelonline.wsv.de/gast/pegeltabelle) — click on a station for its details

  If a station's PNP isn't listed there, try other sources such as regional state portals (e.g. [pegelonline.nlwkn.niedersachsen.de](https://www.pegelonline.nlwkn.niedersachsen.de/Messwerte) for Lower Saxony) — a quick web search for the station name plus *"Stammdatenblatt"* usually helps. If you can't find the PNP for a station within reasonable time, note this in your report and proceed with raw water levels.

  ---

  <h2><strong>Task 3 — Heavy Rainfall Events (Starkregen)</strong></h2>

  > **Did heavy rainfall events occur along your river — and if so, how severe were they?**
 
  The German Weather Service (DWD) classifies heavy rainfall ("Starkregen") into three warning levels based on hourly precipitation. You can read more [here](https://www.dwd.de/DE/service/lexikon/begriffe/S/Starkregen.html):
 
  | Warning Level | Precipitation (1 hour) |
  |---|---|
  | Level 1 | > 15 to < 25 l/m² |
  | Level 2 | > 25 to < 40 l/m² |
  | Level 3 | > 40 l/m² |
 
  **a)** Using your combined dataset from Task 1, check whether any of these thresholds were exceeded at any of your five stations.
 
  **b)** If so — which warning level occurred most often, and at which station(s)?
 
  ---
 
  <h2><strong>Bonus — Visualizing Heavy Rainfall Events</strong></h2>
 
  Create a plot that visualizes when and where these heavy rainfall events occurred across your five stations — for example, a timeline or tile plot showing station vs. time, colored by warning level.
 
  ---

  <h2><strong>Task 4 (Master's) — Quantifying the Relationship: Correlation</strong></h2>
 
  > Background: The `cor()` function
 
  So far you've looked at the relationship between precipitation and water level visually and by inspecting extremes. Now you'll quantify it.
 
  R's built-in `cor()` function calculates the correlation coefficient between two numeric vectors:
 
  ```r
  cor(x, y, use = "complete.obs")
  ```
 
  - `x` and `y` are your two variables (e.g. precipitation and water level)
  - The result ranges from **-1** (perfect negative relationship) to **+1** (perfect positive relationship); **0** means no linear relationship
  - `use = "complete.obs"` tells R to ignore rows where either value is `NA` — important, since real-world data often has gaps
  By default, `cor()` computes the **Pearson** correlation, which measures *linear* relationships. Given that hydrological relationships are often non-linear, you may also want to try `method = "spearman"`, which measures whether two variables tend to increase/decrease together, regardless of whether that relationship is linear.
 
 
  For each of your five stations, calculate the correlation between daily precipitation of 1-3 days prior to the water level measurement and water level. Depict these.

</details>

<details markdown="1">
  <summary><h1><strong>Part 3 — Prediction</strong></h1></summary>

  <h2><strong>Background</strong></h2>

  In Parts 1 and 2 you established whether precipitation, river km, and water level 
  are related, and Master's students quantified the strength of that relationship 
  with cor(). In Part 3 you'll go one step further: build simple statistical models 
  that predict water level from these variables, and test how well one of them 
  actually forecasts unseen data.

  > **Submission deadline:** Please submit your third project till 09.08.2026 via ILIAS.

  ---

  <h2><strong>Task 1: Modelling</strong></h2>

  Using your merged five-station dataset from Part 2, aggregate to daily resolution: 
  calculate the **sum** of precipitation and the **mean** water level per day and 
  station. River kilometer should also be added.

  Choose a **10-day test window** that (a) is covered by all five stations, and 
  (b) contains a rather strong precipitation event — e.g. one identified in Project #2. Set this window aside as your "test" set and remove it from the rest ("train").

  Using the **train** data, model water level as a response to:  
  1) the sum of precipitation of the day prior (model 1)  
  2) river km (model 2)  
  3) both (model 3)  

  > ⚠️ **Simplification:** fixing the lag at 1 day keeps this comparable across 
  > stations, even though your earlier work showed the *best* lag varies by 
  > station. Keep this in mind when interpreting model 1's fit — a station whose 
  > true best lag is, say, 4 days will look artificially weak here.

  > **Compare R² across all three models. Does precipitation add explanatory power 
  > beyond river position alone — and does river position add anything beyond 
  > precipitation alone?**

  Add a simple visualization (e.g. observed vs. fitted water level).

  ---

  <h2><strong>Task 2 (Obligatory for Master's, bonus for Bachelor's): Predict</strong></h2>

  Use your full test set to predict water level using the three models. Add a seasonal term using a cyclic day-of-year predictor so the model can represent a smooth 
  seasonal curve rather than treating day 365 and day 1 as far apart:

```r
  df$doy <- as.numeric(format(df$date, "%j"))
  df$doy_sin <- sin(2 * pi * df$doy / 365)
  df$doy_cos <- cos(2 * pi * df$doy / 365)

  model_season <- lm(value ~ doy_sin + doy_cos + ..., data = df)
```

  Compare predicted vs. observed and compute RMSE by hand:

  RMSE = sqrt( mean( (observed − predicted)² ) )

  > **Are these models suitable to act as a warning tool?**

  ---

  <h2><strong>Task 3 (Bonus) — Mapping Record Water Levels and Rainfall</strong></h2>

  For each station, identify the day with its highest precipitation sum, and create 
  a map showing the water level one day later, along the river.

  Tip: `leaflet` could be a nice package — you already have station coordinates 
  and river_km from Part 2.

</details>