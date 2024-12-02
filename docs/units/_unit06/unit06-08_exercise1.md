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

{::options parse_block_html="true" /}
<details><summary markdown="span">solution</summary>
     rawtext <- read.delim("Butterflies of Pakistan - all species.txt", sep="\t", header=FALSE, encoding = "UTF-8")
     # note, that this reads in the data as a dataframe with one column - we need to refer in the following functions to that column by saying rawtext[1,]
</details>
{::options parse_block_html="false" /}

2) Extract the positions (row numbers) of Family, Subfamily, Species, Subspecies and coordinates and Records for Pakistan based on different markers within the Text. 

A species name generally consists of Genus and Epitheton, Author name and year of description.  
Genus: The first word, indicating the genus to which the species belongs.  
Specific epithet: The second word, which identifies the species within the genus.  
Author: The name of the person who first formally described the species.  
Year: The year in which the species was first formally described.  
For example, in Homo sapiens Linnaeus, 1758, "Homo" is the genus, "sapiens" is the specific epithet, "Linnaeus" is the author, and "1758" is the year of publication.

If the author’s name is in parentheses (e.g., *Canis lupus* (Linnaeus, 1758)), it indicates that the species was originally described in a different genus.  
Species might be further divided into subspecies - populations of a species that are distinct in certain ways but still capable of interbreeding and producing fertile offspring with other members of the species.- in this case, there are three names.  
Example: *Panthera leo persica* (Asiatic lion) and *Panthera leo leo* (African lion).

{::options parse_block_html="true" /}

<details><summary markdown="span">solution</summary>
    pos.Family <- grep("^FAMILY", rawtext[,1]) # positions of the Family are marked with family. Use grep to return those positions
    pos.Subfamily <- grep("^Subfamily", rawtext[,1]) #same as above for subfamily
    pos.Family%in%pos.Subfamily # just to be sure, we can check whether our grep-function was too unspecific
    pos.Subfamily%in%pos.Family # in both cases, there is no TRUE shown (TRUE: this position is found in (=%in%) the other positions)
    # #for species, we could for example check all the lines with 4 digits, as indicated by d{4}
    pos.Species <- grep(""\\d{4}", rawtext[,1]) 
    # however, if we check what text is actually chosen, we see, that there are also other levels (subspecies, subfamily):
    rawtext[pos.species.all,1]
    # it seems as if we'd need to refine it.
    # there must be two words (\\w+ \\w+) at the beginning (^)
    # then, there are two options (... | ...)
    # Option one: there are 4 digits somewhere inside a parentheses  \\(.*\\d{4}\\)
    # Option two: sometimes, the author is not inside parantheses. Then, there must be a word (the authors name) followed by a "," and 4 digits \\w+, \\d{4}.
    # This is at the end ($)
    pos.Species <- grep("^\\w+ \\w+( \\(.*\\d{4}\\)| \\w+, \\d{4})$", rawtext[,1])
    # This removes subspecies, but subfamily may still be included. Let's remove those:
    pos.Species <- pos.Species[!pos.Species%in%c(pos.Family,pos.Subfamily)]
    # For subspecies, it's the same, only one word more:
    pos.subspecies <- grep("^\\w+ \\w+ \\w+( \\(.*\\d{4}\\)| \\w+, \\d{4})$", rawtext[,1])

    #coordinates are simpler, just search for the degree sign:
    pos.coordinates <- grep("°", rawtext[,1])       #degree sign
</details>


{::options parse_block_html="false" /}




3) Take the coordinate lines and extract the latitude and longitude from the coordinates themselves.
Correct spelling if needed beforehand.

{::options parse_block_html="true" /}
<details><summary markdown="span">solution</summary>
    latitude <- sub(".*?(\\d+° \\d+ [NS]).*", "\\1", rawtext[pos.coordinates,1])
    longitude <- sub(".*?(\\d+° \\d+ [NS]), (\\d+° \\d+ [EW]).*", "\\2", text)
</details>
{::options parse_block_html="false" /}