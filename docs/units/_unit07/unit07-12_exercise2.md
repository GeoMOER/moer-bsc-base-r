---
title: "Exercise: Fancy Data Visualization in R"
published: true
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

Consider the following plot, which depicts the predictions which depicts the overall predictions on how different parties will fare in the EU elcetion 2024 and the final results in Hessia:


{% include figure image_path="/assets/images/unit_images/u07/EU_Election.png" %}


 To create the right plot, download the data "HessiaErgebnisse" (results for Hessia) and "eu_election_forecast" from Ilias. IMPORTANT: The last two lines contain the information for whole Hessia in "HessenErgebnisse", and the city of Marburg respectively - handle them accordingly. 

Try to recreate the shown plot.


Useful tips for arranging plots can be found here: [YaRrr](https://bookdown.org/ndphillips/YaRrr/arranging-plots-with-parmfrow-and-layout.html)

Also look here for the cheat sheet about margins with base R. [https://r-graph-gallery.com/74-margin-and-oma-cheatsheet.html](https://r-graph-gallery.com/74-margin-and-oma-cheatsheet.html)

You can save the plot later by running **pdf("EU_Election.pdf", width = 8, height = 4)** before your plot command and executing dev.off() after you have executed your plot command. Do this only when you are satisfied with your plot.