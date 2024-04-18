---
title: R Introduction
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---
*Learn about R and R Studio*
<!--more-->


R is a programming language designed created by Ross Ihaka and Robert Gentleman in 1992. As a an open-source language, which means that it is freely available for anyone to use, modify, and distribute, it became a popular tool for statistical analysis and data visualization with an active user community. It includes a wide range of statistical and graphical techniques, provides extensive tools for data manipulation, transformation, and cleaning and is highly extensible, allowing users to write their own functions and packages. This extensibility has led to a vast ecosystem of contributed packages for a wide range of specialized tasks and domains, including geography.
Base R hat no graphical user interface for data preparation or analysis. These tasks are only performed by entering code into the script. Although this approach may seem intimidating to first-time users, it has the advantage of requiring thoughtful consideration of the analysis while simultaneously documenting all steps. Another advantage is that, in R, many analysis steps can be automated once they are defined.

> “Since then, the popularity of R has grown in leaps and bounds because of its unrivaled flexibility for data analysis and powerful graphical tools, all for the princely sum of *nothing*.”
 -- Tilman M. Davies, The book of R 

## Learning objectives
At the end of this unit you should be able to
* Understand the basic functionality of R
* Find your way around the R Studio interface
* Utilize basic R commands to perform arithmetic operations and assignments.

## Why  R ?

{% include figure image_path="/assets/images/unit_images/u01/gui_r.png" caption="**User Interface of R:** *“the functional appearance of the interpreter, which in my experience has struck fear into the heart of so many an undergraduate, stays true to the very nature of the software – a blank statistical canvas that can be used for any number of tasks”*- Tilman M. Davies, The book of R " %}

The *[r-project](https://www.r-project.org/)* describe their work as such:


> One of R’s strengths is the ease with which well-designed publication-quality plots can be produced, including mathematical symbols and formulae where needed. Great care has been taken over the defaults for the minor design choices in graphics, but the user retains full control.
>
> Many users think of R as a statistics system. We prefer to think of it as an environment within which statistical techniques are implemented. R can be extended (easily) via packages. There are about eight packages supplied with the R distribution and many more are available through the CRAN family of Internet sites covering a very wide range of modern statistics.
>
> R is available as Free Software under the terms of the Free Software Foundation’s GNU General Public License in source code form. It compiles and runs on a wide variety of UNIX platforms and similar systems (including FreeBSD and Linux), Windows and MacOS.

Examples from a very large and fast growing cosmos: [R-bloggers](https://www.r-bloggers.com/){:target="_blank"}.


{% include figure image_path="/assets/images/unit_images/u01/Workshop.png" caption="R offers many tools (image generated with DALL E)" %}

## Getting to know RStudio
{% include figure image_path="/assets/images/unit_images/u01/gui_rstudio.png" caption="User Interface of RStudio" %}

RStudio is an integrated development environment (IDE) for R. It includes a console, syntax-highlighting editor that supports direct code execution, as well as tools for plotting, history, debugging and workspace management.

---

## What is the difference between R and RStudio?

Cran R (or simply R) is a programming language or a software environment as they call it for scientific computing and graphics and RStudio is an IDE for using R.

R and RStudio are not two different versions of the same thing. One can't be substituted for the other. In fact, they work together. R is a programming language for statistical calculation. And RStudio is an Integrated Development Environment (IDE) that helps you develop programs in R. So if you want to learn more about them, you should start by learning R programming.

You can use R without using RStudio, but you can't use RStudio without using R, so R comes first.


## Comments?
You can leave comments below if you have questions or remarks about any of the text or code in this unit. 
Please copy the corresponding line into your comment to make it easier to answer your question.

<script src="https://utteranc.es/client.js" repo="GeoMOER/moer-mpg-data-analysis" issue-term="moer-mpg-data-analysis_unit01" theme="github-light" crossorigin="anonymous" async> </script> 
