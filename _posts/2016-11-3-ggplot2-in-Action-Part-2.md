---
layout: post
title: "ggplot2 in Action - Part 2 (Update soon)"
author: hoanguc3m
date: "November 3, 2016"
categories: [ggplot2, cleanR]
output:
  pdf_document:
    number_sections: true
fontsize: 12pt 
linestretch: 1.5
---



I really like the default R plot system. It always brings elegant minimal clean plots which suits with most of my purpose.
However, there would be some circumstance that the default plot is way too simple and could not help me explain the data concretely. This website [**here**](http://shinyapps.org/apps/RGraphCompendium/index.php) is an awesome source of reference which convinces that you could do everything with R default plot (and even more).

How about elegant figures with elegant commands. Cool eh,...

These plots are rendered using **ggplot2** - "the Grammar of Graphics". I borrow the section names in [**shinyapps.org**](http://shinyapps.org/apps/RGraphCompendium/index.php)

# Correlations





{% highlight r %}
ggplot(cor_mat, aes(x=height.ratio,y = pop.vote)) + 
    geom_point(size = 5,shape = 21, colour = "black", fill = "grey") + 
    geom_smooth(method = "lm", se = F) + 
    xlab("Presidential Height Ratio") + 
    ylab("Relative Support for President") + 
    annotate("text", x =  1.15, y = .61, label = "r = .39") + 
    scale_y_continuous(breaks=seq(0.40, 0.7, 0.05)) + 
    scale_x_continuous(breaks=seq(0.9, 1.2, 0.05)) +
    theme_classic()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
          axis.line.y = element_line(color="black", size = 0.5))
{% endhighlight %}

<img src="/figure/source/2016-11-3-ggplot2-in-Action-Part-2/ggplot_reg-1.png" title="center" alt="center" style="display: block; margin: auto;" />

# Histograms

## Including "rug" Tick Marks




{% highlight r %}
ggplot(good.choices.df, aes(x=good.choices)) + 
    geom_histogram(breaks=seq(0.3, 0.8, 0.05), colour = "black", alpha = 0.3) + 
    geom_rug(sides = "b", aes(y = 0), position = "jitter", colour = 2) + 
    xlab("Prop. Choices from Good Decks") + 
    ylab("Number of Studies") + 
    theme_classic()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
        axis.line.y = element_line(color="black", size = 0.5))
{% endhighlight %}

<img src="/figure/source/2016-11-3-ggplot2-in-Action-Part-2/ggplot_hist-1.png" title="center" alt="center" style="display: block; margin: auto;" />

## Including a Density Estimator


{% highlight r %}
ggplot(good.choices.df, aes(x=good.choices,..density..)) + 
    geom_histogram(breaks=seq(0.3, 0.8, 0.05), colour = "black", alpha = 0.3) + 
    geom_rug(sides = "b", aes(y = 0), position = "jitter", colour = 2) + 
    geom_density(colour = "black")  +
    xlab("Prop. Choices from Good Decks") + 
    ylab("Density of Studies") + 
    xlim(0.3, 0.8) +
    theme_classic()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
        axis.line.y = element_line(color="black", size = 0.5))
{% endhighlight %}

<img src="/figure/source/2016-11-3-ggplot2-in-Action-Part-2/ggplot_dent-1.png" title="center" alt="center" style="display: block; margin: auto;" />

## Including Numbers on Top

{% highlight r %}
ggplot(good.choices.df, aes(x=good.choices)) + 
    geom_histogram(breaks=seq(0.3, 0.8, 0.05), colour = "black", alpha = 0.3) + 
    stat_bin(breaks=seq(0.4, 0.7, 0.05), geom="text", aes(label=..count..), vjust=-0.5) +
    geom_rug(sides = "b", aes(y = 0), position = "jitter", colour = 2) + 
    xlab("Prop. Choices from Good Decks") + 
    ylab("Number of Studies") + 
    xlim(0.3, 0.8) +
    theme_classic()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
        axis.line.y = element_line(color="black", size = 0.5))
{% endhighlight %}

<img src="/figure/source/2016-11-3-ggplot2-in-Action-Part-2/ggplot_dent_anno-1.png" title="center" alt="center" style="display: block; margin: auto;" />

# Line Plots

## Regular Line Plot




{% highlight r %}
ggplot(RT, aes(x=word_frequency, class =  AS)) + 
    geom_point(aes(y = mean, shape = AS), size = 4) + 
    geom_errorbar(aes(ymin = lower, ymax =  upper), width = 0.1) +
    geom_line(aes(y = mean, group = AS),linemitre = 100, linejoin = "bevel") +
    xlab("Word Frequency") + 
    ylab(expression(paste("Mean ", mu))) + 
    scale_y_continuous(breaks=seq(0.30, 0.6, 0.05),limits =c(0.3, 0.6) ) + 
    scale_shape_manual(values=c(1, 19))+
    theme_classic()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
        axis.line.y = element_line(color="black", size = 0.5),
        legend.position = c(0,1), legend.justification = c(-0.5, 1), 
        legend.title=element_blank()) 
{% endhighlight %}

<img src="/figure/source/2016-11-3-ggplot2-in-Action-Part-2/ggplot_line-1.png" title="center" alt="center" style="display: block; margin: auto;" />

## Box Plot




{% highlight r %}
ggplot(data = RT, aes(x=word_frequency,y = mean, class = AS)) + 
    geom_boxplot(aes(colour = AS), outlier.size = 0,width = 0.3, position = "identity", fill = "white") +
    stat_summary(geom = "point",aes(colour = AS), fun.y = "mean", size = 3) + 
    stat_boxplot(aes(colour = AS), geom ='errorbar', width = 0.3, position = "identity") +
    xlab("Word Frequency") + 
    ylab("Group Mean M") +
    scale_y_continuous(breaks=seq(0.30, 0.6, 0.05),limits =c(0.3, 0.6) ) + 
    scale_colour_manual(values=c("gray","black"))+
    scale_alpha_manual(values=c(0.5,1))+
    theme_classic()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
        axis.line.y = element_line(color="black", size = 0.5),
        legend.position = "none") +
    annotate("text", x = 2, y = 0.56, label = "Accuracy", color="gray", alpha = 1) + 
    annotate("text", x = 2, y = 0.35, label = "Speed", color="black", alpha = 1)
{% endhighlight %}

<img src="/figure/source/2016-11-3-ggplot2-in-Action-Part-2/ggplot_box-1.png" title="center" alt="center" style="display: block; margin: auto;" />

## Violin Plot


{% highlight r %}
ggplot(data = RT, aes(x=word_frequency,y = mean, class = AS)) + 
    geom_violin(aes(colour = AS, fill = AS), width = 0.3, position = "identity") +
    stat_summary(geom = "point", fun.y = "mean", size = 3, shape = 13) + 
    stat_boxplot(aes(colour = AS), geom ='errorbar', width = 0.3, position = "identity") +
    xlab("Word Frequency") + 
    ylab("Group Mean M") +
    scale_y_continuous(breaks=seq(0.30, 0.6, 0.05),limits =c(0.3, 0.6) ) + 
    scale_colour_manual(values=c("gray","black"))+
    scale_fill_manual(values=c("gray","white"))+
    scale_alpha_manual(values=c(0.5,1))+
    theme_classic()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
        axis.line.y = element_line(color="black", size = 0.5),
        legend.position = "none") +
    annotate("text", x = 2, y = 0.56, label = "Accuracy", color="gray", alpha = 1) + 
    annotate("text", x = 2, y = 0.35, label = "Speed", color="black", alpha = 1)
{% endhighlight %}

<img src="/figure/source/2016-11-3-ggplot2-in-Action-Part-2/ggplot_Violin-1.png" title="center" alt="center" style="display: block; margin: auto;" />

## Combined Line and Bar Plot



Well, I had some problems with this graph. The object is to plot 2 different scales on the left and the right hand sides. 
This type of graph usually makes people confused at first and requires more effort. 

Well, my first solution here is to rescale data to fit with one range. 
The other solution is dual axis (see [**rpubs**](https://rpubs.com/kohske/dual_axis_in_ggplot2)) where we plot them separately and combine into a final plot.

In comparison to the original R plot, ggplot2 makes a great improvement and easy maintenance. Es fantastico!



{% highlight r %}
ggplot(data = RTER.MRT, aes(x=cue,y = mrt)) + 
    geom_point(size = 4) + 
    geom_errorbar(aes(ymin = lower, ymax =  upper), width = 0.1) +
    geom_line(aes(y = mrt, group = 1)) +
    geom_text(aes(x=cue, y = mrt+50 ,label = mrt) ) + 
    geom_errorbar(data = RTER.Er, aes(ymin = lower*500 + 150, ymax =  upper*500+150), width = 0.2) +
    geom_bar(data = RTER.Er.Mod,aes(y = mrt),  stat = "identity", colour ="black", fill = "white", width = 0.5) + 
    scale_x_discrete(limits=c("Speed","Neutral","Accuracy")) + 
    xlab("Cue") + 
    ylab("Mean Response Time (ms.)") + 
    ggtitle("Behaviour Data") + 
    geom_text(data = RTER.Er.Mod, aes(x=cue, y = mrt - 50,label = RTER.Er$mrt) ) + 
    scale_y_continuous(breaks=seq(300, 700, 100),limits =c(000, 700) ) + 
    theme_classic()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
        axis.line.y = element_line(color="black", size = 0.5),
        legend.position = "none") 
{% endhighlight %}

<img src="/figure/source/2016-11-3-ggplot2-in-Action-Part-2/ggplot_libar-1.png" title="center" alt="center" style="display: block; margin: auto;" />



{% highlight r %}
p1 <- ggplot(data = RTER.MRT, aes(x=cue,y = mrt)) + 
    geom_point(size = 4) + 
    geom_errorbar(aes(ymin = lower, ymax =  upper), width = 0.1) +
    geom_line(aes(y = mrt, group = 1)) +
    xlab("Cue") + 
    ylab("Mean Response Time (ms.)") + 
    ggtitle("Behaviour Data") + 
    geom_text(aes(x=cue, y = mrt+50 ,label = mrt) ) + 
    scale_x_discrete(limits=c("Speed","Neutral","Accuracy")) + 
    scale_y_continuous(breaks=seq(300, 700, 100),limits =c(200, 700) ) + 
    theme_bw()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
        axis.line.y = element_line(color="black", size = 0.5),
        panel.grid.major = element_blank(), panel.grid.minor = element_blank(),
        legend.position = "none",
        plot.margin = unit(c(1,1.8,1,1), "cm") ) 

p2 <- ggplot(data = RTER.Er, aes(x=cue,y = mrt)) + 
    geom_errorbar(aes(ymin = lower, ymax =  upper), width = 0.2) +
    geom_bar(stat = "identity",width = 0.5, colour ="black", fill = "white") + 
    xlab("Cue") + 
    ylab("Mean Proportion of Errors") + 
    geom_text(data = RTER.Er, aes(x=cue, y = mrt-0.05 ,label = mrt) ) + 
    scale_x_discrete(limits=c("Speed","Neutral","Accuracy")) + 
    scale_y_continuous(breaks=seq(0, 0.4, 0.1),limits =c(0,1.2) ) + 
    theme_bw()+
    theme(axis.line.x = element_line(color="black", size = 0.5),
        axis.line.y = element_line(color="black", size = 0.5),
        panel.grid.major = element_blank(), panel.grid.minor = element_blank(),
        legend.position = "none",
        plot.margin = unit(c(1,2,1,1), "cm")) 

p <- ggplot_dual_axis(lhs = p1, rhs = p2)
grid.draw(p)
{% endhighlight %}

<img src="/figure/source/2016-11-3-ggplot2-in-Action-Part-2/ggplot_libar2-1.png" title="center" alt="center" style="display: block; margin: auto;" />
