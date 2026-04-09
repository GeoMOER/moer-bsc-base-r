---
title: Base R - no statistics, no fancy packages, just plain R
layout: splash
date: '2024-02-19 13:00:00 +0100'
header:
  overlay_color: "#000"
  overlay_filter: 0.6
  overlay_image: "/assets/images/title/DALLE_R.png"
  caption: 'Image generated with DALL E: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
  cta_label: Go to course units
  cta_url: "/units.html"
excerpt: Learn the essentials for working with R.
feature_row_intro:
- excerpt: This course is brought to you by the Lab of Environmental Informatics (University of Marburg, Germany) and was funded by the "digLL" initiative of the Hessian Ministry of Higher Education, Research, Science and the Arts.
feature_row_ilos:
- image_path: "/assets/images/envobs_ilos.jpg"
  alt: PC monitor laying in the garden of the institute.
  title: Intended learning outcomes
  excerpt: "Template..."
---

{% include feature_row id="feature_row_intro" type="center" %}

A life without the free programming language R is no longer imaginable for many people and those who do not know R often do not know what they are missing.
Unfortunately, the widespread believe that R is difficult to learn still exists,
which makes it unnecessarily difficult for many newcomers to enter the world of R.
We would like to change this with this course.


# Intended learning outcomes
At the end of this course you should be able to
  
* know and understand the basic properties of an object-oriented programming language,
* flexibly use your knowledge and understanding in various programming contexts, and
* have the basic programming skills for working in more complex subject-specific projects.



# Setting

This course will take place in a synchronous setting in presence in room **F 14|00A19** every **Monday, 9:15-11:45.** 

{: .notice--info}

<!--
This course will take place in a hybrid setting with a digital classroom and additional students being present in person in the physical classroom (**F 14 | 00A19**).
Details on this synchronous hybrid classroom format will be provided in the first session, which will take place **in presence only on Tuesday 25.10.2022 at 9:15 am**.
The link to the digital classroom of the first session is provided in the [Ilias course environment](https://ilias.uni-marburg.de/goto.php?target=crs_2593121&client_id=UNIMR){:target="_blank"} (only accessible for members of the course who are logged-in into Ilias). 
Please also seriously check and follow the [Information on the Coronavirus](https://www.uni-marburg.de/de/universitaet/administration/sicherheit/coronavirus){:target="_blank"} of the University of Marburg.
-->



# Syllabus


| Session | Date | Topic | Units covered | Tasks |
|---|---|---|---|---|
| | | | **The basics** |
| 01 | 13.04.2026 | introduction of R, R Studio, data types  | 01-02 | A01 |
| 02 | 20.04.2026 | objects & indexing           | 03-04 | A02 |
| <!-- ab hier Datenbeispiel Klima Marburg --> | | | **Data handling** |
| 03 | 27.04.2026 | how to subset and sort your data by values, reading and writing tabulated data              | 04 -05 |  A03 |
| 04 | 04.05.2026 | how to deal with characters and regular expressions,  transfrom from long to wide format and back | 06| A04 |
| 05 | 11.05.2026 | use handy data checks to see whether your data and script are ok, work directly with your first project     | good practices | P01 |
| | | | **Plotting** |
| 06 | 18.05.2026    | graphs principles                          |  07 | P01 |
|    | ~~25.05.2026~~    | public holiday, no course today ||
| 07 | 01.06.2026    | Independent study: graphs  II  | 07 | A05 |
| | | | **Automation** |
| 08 | 08.06.2026 | feedback P01, automate your script and use conditions      | 08 | A06 |
| 09 | 15.06.2026 | for/if/else II, project II          |  good practices | P02 |
| 10 | 22.06.2026 | functions & apply             |  09 | P02|
| 11 | 29.06.2026 | maps              |   |
| 12 | 06.07.2026| project 03 + prediction  | good practices | P03 |
| 13 | 13.07.2026	| time for questions and feedback, individual data analysis problems, goodbye            | -- | P03 |



# Deliverables

The coursework consists of regular, individual assignments to be submitted.
The graded course certificate will be based on a portfolio of three marked project assignments. 

# Preparation and prerequisites

No preparation or prerequisites are needed for this course.



## Team

{% for author in site.data.authors %}
  {% include author-profile.html %}
 <br />
{% endfor %}
