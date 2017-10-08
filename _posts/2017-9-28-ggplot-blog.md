---
layout: post
title: ggplot guide and cheat sheet
---
This blog reviews the usage cases of ggplot.

```R
# Box plot
bp<-ggplot(ToothGrowth, aes(x=dose, y=len, fill=dose)) +
  geom_boxplot()
bp
# Scatter plot
sp<-ggplot(mtcars, aes(x=wt, y=mpg, color=cyl)) + geom_point()
sp
```
![_config.yml]({{ site.baseurl }}/images/ggplot1.png)

```R
# Box plot
bp + scale_fill_manual(values=c("#999999", "#E69F00", "#56B4E9"))
# Scatter plot
sp + scale_color_manual(values=c("#999999", "#E69F00", "#56B4E9"))
```
![_config.yml]({{ site.baseurl }}/images/ggplot2.png)

```R
# Box plot
bp + scale_fill_manual(breaks = c("2", "1", "0.5"), 
                       values=c("red", "blue", "green"))
# Scatter plot
sp + scale_color_manual(breaks = c("8", "6", "4"),
                        values=c("red", "blue", "green"))
```
![_config.yml]({{ site.baseurl }}/images/ggplot3.png)

```R
# Box plot
bp + scale_fill_brewer(palette="Dark2")
# Scatter plot
sp + scale_color_brewer(palette="Dark2")
```
![_config.yml]({{ site.baseurl }}/images/ggplot4.png)

```R
# Color by qsec values
sp2<-ggplot(mtcars, aes(x=wt, y=mpg, color=qsec)) + geom_point()
sp2
# Change the low and high colors
# Sequential color scheme
sp2+scale_color_gradient(low="blue", high="red")
# Diverging color scheme
mid<-mean(mtcars$qsec)
sp2+scale_color_gradient2(midpoint=mid, low="blue", mid="white",
                     high="red", space ="Lab" )
```
![_config.yml]({{ site.baseurl }}/images/ggplot5.png)

```R
set.seed(1234)
x <- rnorm(200)
# Histogram
hp<-qplot(x =x, fill=..count.., geom="histogram") 
hp
# Sequential color scheme
hp+scale_fill_gradient(low="blue", high="red")
```
![_config.yml]({{ site.baseurl }}/images/ggplot6.png)

```R
# Scatter plot
# Color points by the mpg variable
sp3<-ggplot(mtcars, aes(x=wt, y=mpg, color=mpg)) + geom_point()
sp3
# Gradient between n colors
sp3+scale_color_gradientn(colours = rainbow(5))
```
![_config.yml]({{ site.baseurl }}/images/ggplot7.png)
