---
title: Style your plot!
published: false
toc: TRUE
toc_float: TRUE
header:
  image: /assets/images/unit_images/u07/header.png
  image_description: "statistics"
  caption: "Photo by [Gerd Altmann](https://pixabay.com/de/users/geralt-9301/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=4705451) [from Pixabay](https://pixabay.com/)"
---

There are a lot of options on how to change the appearance of your plot. See the help of **par()** to get an overview of some of the options. With **par**, you an change parameters of plot appearence.

For example, you can adjust the *area around your plot* (=margin, **mar**) and the area beyond that (=outer margin area, **oma**)

This is displayed expertly here [https://r-graph-gallery.com/74-margin-and-oma-cheatsheet.html](https://r-graph-gallery.com/74-margin-and-oma-cheatsheet.html)

Generally, to change the size you have to give a vector of lines (correspond to a certain number of pixels??) you want to have as spacer around first, the bottom, left, top and right to the plot. A mar=c(4,5,1,0) would mean you have 4 lines space from the axis to the end of the margin, 5 to the left, 1 to the top, 0 to the right,




```{r}

plot(1:10)
?par

par(mar=c(2,8,0,0))


plot(1:100)

plot(1:100)
par(las=1)

plot(log(1:100), axes=F, ylab="")
axis(1)
val.orig <- c(1,10,100)
val.log <- log(val.orig)
axis(2, at= val.log, labels=val.orig)
axis(4, at= val.log, labels=round(val.log,2))


values <- c(7,3,6,8)

par(mar=c(4,4,1,1))
par(las=1)
par(cex.axis=0.8, cex.main=1.2)

bp <- barplot(values, col=c("steelblue", "tomato", "gold", "seagreen"),
        border="pink",
        main = "Customized",
        xlab="Category",
        ylab="Value",
        ylim=c(0,10))
bp

names <- c("A","B","C","D")
axis(1, at=bp, labels = names)

dev.off() 

barplot(values, density=c(10,20), angle=c(45,90), lwd=5)
?par


par(mfrow=c(2,2))
barplot(values, col=c("steelblue", "tomato", "gold", "seagreen"),
        border="pink",
        main = "Customized",
        xlab="Category",
        ylab="Value",
        ylim=c(0,10))
plot(1:10)
plot(30:500)

dev.off()

```