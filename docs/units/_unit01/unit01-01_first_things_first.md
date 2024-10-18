---
title: R Introduction
header:
  image: "/assets/images/unit_images/u01/header.jpg"
  caption: 'image by <a href="https://pixabay.com/de/users/athree23-6195572/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Adrian</a> on <a href="https://pixabay.com/de//?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4855963">Pixabay</a>'
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


{% include figure image_path="/assets/images/unit_images/u01/workshop.png" caption="R offers many tools (image generated with DALL E)" %}


&#x1F914;  
One might ask, especially those with a computer science background, *Why not Python?* While both Python and R are widely used in data science, the choice often comes down to personal preference and the specific nature of the tasks at hand. R was specifically designed with statistical analysis, data manipulation, and visualization in mind, making it more intuitive for these types of tasks right out of the box, with *packages* specifically designed for the various tasks of data manipulation and analysis in science. Python, on the other hand, is a more general-purpose language, whose initial design did not focus solely on data science, which can make certain statistical procedures and visualizations less seamless compared to R, but can come in handy for tasks such as image recognition. Ultimately, both Python and R have their own merits, and it's up to your personal choice. That said, it's worth noting that both languages can be integrated, and you can now also use Python within RStudio. If you’re a programming enthusiast who wants to explore more, feel free to check out our ghtml-course on Python [here](https://geomoer.github.io/moer-base-python/).
{: .notice--info}

 

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

<script src="https://utteranc.es/client.js" repo="GeoMOER/moer-bsc-base-r" issue-term="moer-bsc_base_r_unit01" theme="github-light" crossorigin="anonymous" async> </script> 
