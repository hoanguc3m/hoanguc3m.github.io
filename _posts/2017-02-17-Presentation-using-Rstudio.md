---
layout: post
title: "Presentation using Rstudio"
author: hoanguc3m
date: "February 17, 2017"
categories: [R_tricks]
output:
  pdf_document:
    number_sections: true
fontsize: 12pt 
linestretch: 1.5
---




As this term, I am responsible for two classes of time series analysis. 
I would like to propose a efficient way of communication with students 
so they do not get bored with the numbers and notations. After taking a brief look at
the [Rstudio webpage](http://rmarkdown.rstudio.com/formats.html) about the presentation styles,
I found myself enjoying [reveal.js](http://lab.hakim.se/reveal-js/#/). It is elegant, flexible 
with many support options. 

As usual, we need to install the package to start


{% highlight r %}
install.packages("revealjs")
{% endhighlight %}

# reveal.js

**reveal.js** is a HTML Presentation Framework based on HTML5 and CSS3. The project starts from 2011. Among [competitors](https://en.wikipedia.org/wiki/Web-based_slideshow), **reveal.js** has attractive default styles.
It could also help speaker with server side notes and stop watch timers which is better than beamer (:D). Check this youtube [video](https://www.youtube.com/watch?v=6VRMcHyXEKc) to see how it works.
You could have a GUI website to design your *reveal.js* pages at [slides.com](https://slides.com/). So, no markdown requirement. However, I need to take advantage of Rmarkdown in this case.

First of all, I start to write the contents in my rmarkdown file. 
After that, I just change the header of rmarkdown file as

{% highlight rcpp %}
---
title: "Lab note 3"
author: "Hoang Nguyen"
date: "Feb 17, 2017"
output: 
    revealjs::revealjs_presentation:
        theme: sky
        highlight: pygments
        center: true
        transition: concave
        self_contained: false
        reveal_plugins: ["notes", "search","zoom","chalkboard"]
---
{% endhighlight %}
then you could enjoy the slides.
Remember some shortcut keys:

- f: full screen
- o: overview
- s: server note sides. (For this, you need to refer to [notes](https://github.com/hakimel/reveal.js#speaker-notes))

# Plug-in
The [reveal plugins](http://rmarkdown.rstudio.com/revealjs_presentation_format.html#reveal_plugins) are just awesome. They are the main reasons that I use for my slides.

- [**notes**](https://github.com/hakimel/reveal.js/#speaker-notes): Speaker notes on server sides
- [**zoom**](http://lab.hakim.se/zoom-js/): Zoom at anywhere with clicks.
- [**search**](https://github.com/hakimel/reveal.js/blob/master/plugin/search/search.js): Search text anywhere.
- [**chalkboard**](https://github.com/rajgoel/reveal.js-plugins/tree/master/chalkboard): Hand writing notes!!

I highly recommend that you should try all of them in your presentation slides.

# Conclusion
**reveal.js** helps you quickly design the presentations from markdown documents. 
Not only that, you could describe different concepts efficiently using **zoom** and **chalkboard** plugin. 
If you need to customize your own styles, little css knowlegde would be useful.
Simple change could be made with *html tag*. And lastly, leave some comments and take a look at my [examples](/Rmd/lab3.html).
