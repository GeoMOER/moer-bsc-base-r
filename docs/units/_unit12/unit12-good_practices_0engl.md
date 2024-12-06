---
title: "Good practices - english version"
header:
  image: /assets/images/unit_images/u08/header.png
  image_description: "loop"
  caption: "Photo by [Christopher Kuszajewski](https://pixabay.com/de/users/kuszapro-369349/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537) [from Pixabay](https://pixabay.com/de/?utm_source=link-attribution&amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=583537)"
---

In the very first chapter, it was said:

*“The functional appearance of the interpreter, which in my experience has struck fear into the heart of so many an undergraduate, stays true to the very nature of the software – a blank statistical canvas that can be used for any number of tasks”*
— Tilman M. Davies, The Book of R

This blank canvas, waiting to be painted, can be intimidating. People tend to want to dive right in: load some data, try a few commands, and then suddenly hit a wall. In this guide, we aim to walk you through the steps that will help you develop a structured and methodical approach—from the blank canvas to the finished masterpiece of your analysis.

Of course, every artist is different, so the following workflow is merely a suggestion.

# Step 1: Understanding the Problem and Planning the Steps
*“Before painting a portrait, you must know what you want to draw.”*

The first and most important step is to understand the problem and outline the necessary steps. For this, you don't even need to open R—pen and paper or a whiteboard will suffice.

<details> <summary>Working with an example</summary> 
Imagine you are investigating how land use affects the microclimate. A first research question might be: **How does air temperature (10 cm above the ground) differ between two different land use types?
 </details>

Create a flowchart or similar visual aid for clarity.

Ask yourself the following questions:

1.1) What is the object of your investigation?  
1.2) What effect are you testing?  
1.3) What variables do you have, and what data types should they have? 
1.4) What aspects can you analyze?  
1.5) Are there additional factors to consider?  

By asking these questions, you can evaluate the various options, whether you're using the classical frequentist approach, Bayesian statistics, machine learning, or you "just" want to visualize something.

In this course, we will stay on the level of descriptive statistics and simple classical statistical tests. Good decision-making tools for classical statistics can be found, for example, [here](https://www.biostathandbook.com/). Information about data types and potential confounding variables can help you choose suitable analyses or review the methodology of similar studies.

# Step 2: Setting Up the Project, Checking Raw Data, and Making Adjustments
*“Prepare your palette and brushes.”*

2.1) Use a [template](/moer-bsc-base-r/unit10/unit10-assignment03.html) for your folder structure, README file, and script whenever possible.  
2.2) Download the raw data. Record important metadata in the README file:  
    Where did the data come from?  
    When did you receive it?  
    What does it contain?  
    How many data points are included?  
2.3) Load the data and check using **str()** to see if they match the expected data types (see 1.4).  
2.4) Perform a raw data check. Useful functions include **summary()**, **length()**, **unique()**, and **tapply()**, especially if you have grouping factors.  
2.5) Visualizing the data can also be helpful, particularly with spatially or temporally structured data.   
2.6) If your checks in 2.4 revealed problems, fix them in your script. Never modify the raw data directly!   
2.7) Document the changes and how they impact your data.  

# Step 3: Preparing the Data
*“Sketch your outlines.”*

You now know what your data looks like. The two questions to ask (again) are:

3.1) What is your unit of analysis?  
3.2) What structure must the data have for the chosen analysis to be performed?  

You can determine this by consulting the help function of the method (e.g., ?t.test or help(t.test)), reading its arguments, and reviewing examples. Alternatively, you can often find vignettes or handbooks explaining the functions and underlying concepts in more detail.

Visualize the current structure of your raw data and compare it to the structure required for analysis. This will help you identify the necessary transformation steps.

# Step 4: Writing and Checking the Script
*“Fill in your sketch and refine the details until the picture meets both the overall vision and the finer demands.”*

4.1) The necessary steps for data transformation and analysis have already been outlined in the previous steps. Now gather the appropriate functions—whether from this handbook, hardcover textbooks, or the vast resources of the internet.  
4.2) Always verify whether the result of a function—whether it’s for data transformation, analysis, or visualization—is correct. After transformations, does the number of individual values still match the logical expectation? Have any data been lost? Are the calculation results correct? If necessary, check them manually. Does the visualization make sense?

If you can confidently answer "yes" to these questions, congratulations—you’ve reached the course goal.

