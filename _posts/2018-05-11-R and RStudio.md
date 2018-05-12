---
layout: post
title: R and RStudio
tags: [R, RStudio]
---

R is a programming language for statistical computing and graphics. R is free to download [here](https://www.r-project.org) and RStudio can be downloaded [here](https://www.rstudio.com), also for free. It is important to note that R is not only limited to statistical computing and graphics, you can even develop dashboards with R using Shiny (an R package), so it is highly extensible.

![R and RStudio]({{ site.baseurl }}/assets/img/blog_images/R_series/R_RStudio.png)

<br>
So what is the difference?

R
=

When you open R, this is what you will see, an R Console.

![R Console]({{ site.baseurl }}/assets/img/blog_images/R_series/Rconsole.png)

With R Console, you can straight away write your code and see the output, as easy as that. I personally does not use R Console as I prefer to use RStudio.

RStudio
=======

RStudio is an Integrated Development Environment (IDE) for R. You can look up what an IDE is and you can get a more comprehensive definition which can be quite technical, but don't worry, all my posts will be written in a simple, easy-to-understand language, with less jargon. Let's take a look at the following screenshot of RStudio for further explanation.

To experience the power of RStudio, you will need to download R into your machine first.

![RStudio]({{ site.baseurl }}/assets/img/blog_images/R_series/RStudio.png)

In RStudio, you will have four sections.

**Top-left**
This is where you write your R script or Rmarkdown. It is best practice to comment on your codes, i.e. what the code chunk does, so this is where you write them all.

**Bottom-left**
If you look carefully, there are two tabs shown in the picture, Console and Terminal. Whenever you run your code in the top-left section, the codes will run in the Console as well. Remember that we saw the R Console in R previously, so basically that R Console is now embedded as this bottom-left section in RStudio.

<iframe width="800" height="400" src="https://www.youtube.com/embed/e1DjV9t-g5o" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen>
</iframe>  

<br>

**Top-right**
You can see that there are three tabs in this section, Environment, History and Connections. The tab that we are concerned about is Environment. This is where you can see all the variables that you have assigned in R. If you look at the previous video, when I run `x <- c(1, 2, 3, 4)` , this also appeared in the Environment tab.

**Bottom-right**
In this section, you will see a few more tabs, Files, Plots, Packages, Help and Viewer.

-   <span style="color:#2980B9">**Files**</span> - You can quickly access your file in this tab.
-   <span style="color:#2980B9">**Plots**</span> - This is where you can see your plots or graphs.
-   <span style="color:#2980B9">**Packages**</span> - All the packages installed in R and their versions.
-   <span style="color:#2980B9">**Help**</span> - The Viewer pane can be used to view local web content.

RStudio is easy to use, I can navigate my way in RStudio quickly after a few weeks of using it. With the ability to write your Rmarkdown file and setting the output to html, pdf or word document, you can produce high quality and pretty content in just one software.
