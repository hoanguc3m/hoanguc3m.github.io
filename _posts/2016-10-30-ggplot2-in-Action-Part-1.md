---
layout: post
title: "ggplot2 in Action - Part 1"
author: hoanguc3m
date: "October 30, 2016"
categories: [ggplot2, Rgraphic]
output:
  pdf_document:
    number_sections: true
fontsize: 12pt 
linestretch: 1.5
---



This series of posts show how to use ggplot2 in my daily exercises. 
The posts contain detail tricks and tips to plot nice graphs with ggplots.
The structure of the post should be as followed,

- Firstly, the main object and final plot are shown.
- How to do data preparation and manipulation.
- How to match the data to the axes together with their summary statistics
- Some tweaks on the scales, colors, legends, ...

# How to plot histogram and density in the same plot
I will use the simple Iris data for this example. Here is the histogram and density of Petal.Length for Species (setosa, versicolor, virginica)

<img src="/figure/source/2016-10-30-ggplot2-in-Action-Part-1/ggplot_lib-1.png" title="center" alt="center" style="display: block; margin: auto;" />

# Detail explanation

Well, let take the data and obtain the histogram first. Remember that we want to group the data according to Species

{% highlight r %}
ggplot(iris, aes(x=Petal.Length, fill = Species)) + 
        geom_histogram(bins = 30) + 
        theme_bw() 
{% endhighlight %}

<img src="/figure/source/2016-10-30-ggplot2-in-Action-Part-1/ggplot_fig1-1.png" title="center" alt="center" style="display: block; margin: auto;" />

For the area overlap between versicolor and virginica, we need to change their position so that they are not stack over the other. 

{% highlight r %}
geom_histogram(position = "identity", alpha = 0.8, bins = 30)
{% endhighlight %}

Now we try to add the density plot 



{% highlight r %}
ggplot(iris, aes(x=Petal.Length, fill = Species)) + 
        geom_histogram(position = "identity", alpha = 0.8, bins = 30) + 
        geom_density(position = "identity", alpha = 0.5) + 
        theme_bw() 
{% endhighlight %}

<img src="/figure/source/2016-10-30-ggplot2-in-Action-Part-1/ggplot_fig2-1.png" title="center" alt="center" style="display: block; margin: auto;" />

Upsss, it seems that ggplot could not match the y scale of histogram and density together. In order to scale density up to histogram count or scale histogram count down to density, we use "..density.." or "..count.." for aes(y)


{% highlight r %}
ggplot(iris, aes(x=Petal.Length,..density.., fill = Species, colour = Species)) + 
        geom_histogram(position = "identity", alpha = 0.8, bins = 30) + 
        geom_density(position = "identity", alpha = 0.5)  +
        theme_bw() 
{% endhighlight %}

<img src="/figure/source/2016-10-30-ggplot2-in-Action-Part-1/ggplot_fig3-1.png" title="center" alt="center" style="display: block; margin: auto;" />

Well, that solves the problem! It took me a while to figure out.
