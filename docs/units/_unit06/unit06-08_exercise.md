---
title: "Exercise: working with characters"
published: true
toc: true
toc_label: "In this example"
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

For this exercise, we'll work on a real-life example from my working group. Our aim is to create an tool to digitize species distribution maps from book scans. 
To test whether we were accurate, the author of the book provided us with raw data as a word document, where all data records were listed per species.

Here's the task:

1) Download the "Species-Text" textfile from the Data-folder in Ilias.

 <details>
   <summary>Tip </summary>
     be aware of the UTF-8 encoding!
  </details>

2) Extract the positions (row numbers) of Family, Subfamily, Species, Subspecies and coordinates and Records for Pakistan based on different markers within the Text. 

A species name generally consists of Genus and Epitheton, Author name and year of description.  
Genus: The first word, indicating the genus to which the species belongs.  
Specific epithet: The second word, which identifies the species within the genus.  
Author: The name of the person who first formally described the species.  
Year: The year in which the species was first formally described.  
For example, in Homo sapiens Linnaeus, 1758, "Homo" is the genus, "sapiens" is the specific epithet, "Linnaeus" is the author, and "1758" is the year of publication.

If the author’s name is in parentheses (e.g., Canis lupus (Linnaeus, 1758)), it indicates that the species was originally described in a different genus.  
Species might be further divided into subspecies - populations of a species that are distinct in certain ways but still capable of interbreeding and producing fertile offspring with other members of the species.- in this case, there are three names.  
Example: Panthera leo persica (Asiatic lion) and Panthera leo leo (African lion).

3) Take the coordinate lines and extract the latitude and longitude from the coordinates themselves.
Correct spelling if needed beforehand.