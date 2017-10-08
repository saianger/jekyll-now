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
