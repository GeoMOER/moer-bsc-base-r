---
title: "Exercise: Data Visualization in R"
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

1. <br/>
    a) Download the dataset "CharacterValues" and read it into R. <br/>

    b) What hair and eye colors are present in the dataset? Perform adjustments such as converting uppercase to lowercase, etc., so that 1) grey and white hair are combined into one category (grey), yellow and blonde are combined, and hair color spelling is standardized ("Gelb" counts as blonde in this case) 2) for eye colors, combine "schwarz" (black), "hazel", and "brown" into brown, combine "grey" and "blue" into "bluegrey," and all other eye colors not categorized as brown, bluegrey, or green are combined into "other." <br/>
    c) Record the frequency of entries for gender, hair color, and eye color. Note: remove one entry for characters that appear twice. First check if other entries (age, eye color/hair color, and gender, etc.) differ. If so, keep the entry that makes more sense to you.<br/>
    d) Now capture the frequency of eye color per hair color.<br/>
    e) Create a bar chart displaying the frequency of each eye color and hair color.<br/>
    f) Create a "stacked" bar chart showing eye colors for hair colors "black", "brown", and "blonde".<br/>
    g) Create a pie chart that displays the gender ratio.<br/>
    h)  Create a histogram to show the distribution of age.<br/>
    i) Create a box plot to compare the distribution of height between worldly and otherworldly characters.<br/>
<br/>
2. First, create a simple scatter plot where you plot body height (Y-axis) against shoe size (X-axis). Then change the plot type to a plot where the points are sensibly connected with lines. What step is essential in this process?

3. Consider the following plot, which represents the beautified plot from today and the box plot from last week (or this week):

{% include figure image_path="/assets/images/unit_images/u07/Unit07_plot.png" %}

Try to recreate this plot.

Note: the "stars" in the example plot represent data from animal-like characters (such as Goofy, Donald Duck, Pluto, and Scrooge McDuck).

Refer to the "Graphic-Example" script for changing axes, etc.

Useful tips for arranging plots can be found here: https://bookdown.org/ndphillips/YaRrr/arranging-plots-with-par-mfrow-and-layout.html

You can save the plot later by running png("Output/Scatterplot_Boxplot.png") before your plot command and executing dev.off() after you have executed your plot command. Do this only when you are satisfied with your plot.