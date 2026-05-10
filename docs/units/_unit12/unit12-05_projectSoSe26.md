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

## Part 1 — Getting to Know Your Data

### The question:
> **Is there a direct relationship between precipitation and water level at your station? When do water levels peak — and was it actually raining at the time?**
 
Tasks 1–3 get your data into a shape where you can answer that question. Task 4 is where you answer it.
 



### Task 1 — Data Import
 
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

### Task 2 — Inspect & Clean
 
Take a close look at your data before doing anything with it and summarize it in your [report](/moer-bsc-base-r/unit12/unit12-01_project_guidelines.html).

*Things to think about: What data types did R assign on import — are they correct? Do you have missing values? Is your time series without gaps?*

---

### Task 3 — One dataframe to rule them all

Create a single merged dataframe with an hourly resolution that covers the overlapping time period of both datasets.

*Things to think about: What does merging on a timestamp require?*

---

### Task 4 — Is Rain Making the River Rise?
 
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

### Bonus — Visualisation
 
Create one or two plots that bring your findings to life and summarize your results.
 


<!--
## Teil 2 ###



## Teil 3 ###
-->