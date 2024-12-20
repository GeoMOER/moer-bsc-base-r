---
title: "Exercise: Data Visualization in R"
published: true
header:
  image: "/assets/images/title/title_1600_500.jpg"
  caption: 'Image: [**Environmental Informatics Marburg**](https://www.uni-marburg.de/en/fb19/disciplines/physisch/environmentalinformatics)'
---

Based on the datasets which were developed together in Assignment 06 (see Script in Ilias), create:

1)  a histogram of all temperature measurements

{::options parse_block_html="true" /}
<details><summary markdown="span">solution</summary>
    # Data cleaning
    temp.raw <- read.csv("data/raw/plots.csv")
    temp.raw$datetime <- as.Date(temp.raw$datetime) #correct data type
    temp <- temp.raw[which(temp.raw$Ta_10>=-36.1),] # exclude extremes
    temp <- temp[which(temp$Ta_10<=40.2),]          # exclude extremes

    hist(temp$Ta_10, las=1, main="Temperature (°C) at ground level", xlab="Degrees Celsius")
</details>
{::options parse_block_html="false" /}


2)  a dotplot depicting the average temperature of year 2009 per plot

{::options parse_block_html="true" /}
<details><summary markdown="span">solution</summary>
    meanT_2009 <- aggregate(Ta_10~plotID, data=temp[temp$year==2009,], mean)
    dotchart(meanT_2009$Ta_10,labels=meanT_2009$plotID,cex=.6,xlab="average temperature") #.cex reduces size of elements such as labels
</details>
{::options parse_block_html="false" /}

3)  a barplot of the number of sampled plots in june in per year

{::options parse_block_html="true" /}
<details><summary markdown="span">solution</summary>
    plots.sampled <- tapply(temp$plotID,list(temp$month,temp$year), function(x)length(unique(x)))
    barplot(plots.sampled[6,], main="Number of sampled plots in June",xlab="Year")

    temp$LandUse <- factor(substr(temp$plotID, 3, 3))
    plots.sampled <- tapply(temp$plotID,list(temp$LandUse,temp$year,temp$month), function(x)length(unique(x)))
    barplot(plots.sampled[,,6], main="Number of sampled plots in June",xlab="Year")
</details>
{::options parse_block_html="false" /}

4)  a boxplot of temperatures, measured as monthly means, showing the contrast between grasland and forest for 2009

{::options parse_block_html="true" /}
<details><summary markdown="span">solution</summary>
     
     # Version 1: aggregating by Month/Plot/Year, depicting differences between land use
     mean.temp <- aggregate(Ta_10~plotID+LandUse+year+month, data=temp, mean)
     boxplot(Ta_10~LandUse, data=mean.temp[mean.temp$year==2009,])

     # Version 2: Depicting differences between landuse and months
     library(ggplot2)
     boxplot(Ta_10 ~ month + LandUse,
        data = mean.temp[mean.temp$year==2009,],
        col = colors <- rep(c("orange", "darkgreen"), each = 12), # This repeats each color 12 times (for each month)
        main = "Monthly Temperature Distribution by Land Cover Type in 2009",
        xlab = "Month",
        ylab = "Mean Temperature (°C)")
</details>
{::options parse_block_html="false" /}


5)  a linechart depicting the temperature along datetime for plot AEW10

{::options parse_block_html="true" /}
<details><summary markdown="span">solution</summary>

     plot(Ta_10~datetime, data=temp[temp$plotID=="AEW10",], col = "orange", type="l")
</details>
{::options parse_block_html="false" /}

6)  a scatterplot depicting the temperatures per plot along datetime in 2024
{::options parse_block_html="true" /}
<details><summary markdown="span">solution</summary>

    # for some extras, we'll also color the points according to landuse
    temp$LandUse <- factor(substr(temp$plotID, 3, 3))
    dat24 <- temp[temp$year==2024,]

    # creation of a color-vector including transparency
     colR <- col2rgb(c("darkgreen","orange")) #generation of RGB values from color-title
     colR <- colR/255 #Scaling for them to be within 0-1 instead of 255
     alpha.green <- rgb(colR[1,1],colR[2,1],colR[3,1],alpha=0.2) # generating new color incl. transparency
     alpha.orange <- rgb(colR[1,2],colR[2,2],colR[3,2],alpha=0.2)# generating new color incl. transparency

     colors <- c(alpha.orange, alpha.green)[dat24$LandUse] #generating a vector of colors sorted by the factor

    # the line which was asked for in the task 
      plot(Ta_10~datetime, data=dat24, col=colors, pch=19) #pch=changing point shape

    # add some line depicting the average as extra
    mean.temp.tab <- tapply(dat24$Ta_10, INDEX=list(dat24$datetime,dat24$LandUse), function(x)mean(x, na.rm=T))
    mean.temp24 <- as.data.frame(mean.temp.tab)
    mean.temp24$datetime <- as.Date(rownames(mean.temp.tab))
    lines(G~datetime, mean.temp24,
      col = "darkorange4", 
      lwd = 2)
    lines(W~datetime, mean.temp24,
      col = "black", 
      lwd = 2)
</details>
{::options parse_block_html="false" /}
