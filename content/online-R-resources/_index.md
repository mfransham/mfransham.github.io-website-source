---
header:
  caption: ""
  image: ""
# layout: docs
title: Free online resources for social data science with R
---

There are many free resources and online books available to learn social data science methods in R. Here is a selection that I have found useful.

## General resources

### Introductions to applied statistics with R

RLadies Sydney [RYouWithMe course](https://rladiessydney.org/courses/ryouwithme/): An introductory course split into three: BasicBasics, CleanItUp (data manipulation), VizWhiz (data visualisation), MarkyMark (output in RMarkdown). Some very nice video walk-throughs

[Modern dive](https://moderndive.com/index.html) by Chester Ismay and Albert Y. Kim: This book includes a very nice introduction to R and RStudio in chapter 1 using `flights` data. Chapters 2-4 cover basic data science; Chapters 5-6 cover data modelling; Chapters 7-10 cover statistical inference, including using bootstrap as an alternative to parametric methods

[Learning statistics with R](https://learningstatisticswithr.com/book) by Dani Navarro: basic statistics for psychologists online book written by one of the RLadies Sydney group, with an emphasis on ANOVA, regression and factorial ANOVA, plus an intro to Bayesian statistics

### Quick tips and tricks

[Quick-R](https://www.statmethods.net/) by Rob Kabacoff: quick introductions to how to implement a range of statistical methods

[R Cookbook](https://rc2e.com/) second edition by James Long and Paul Teetor: a book with a large number of 'how to' recipes

[Cookbook for R](http://www.cookbook-r.com/) by Winston Chang: similar idea to the Long & Teetor book, but with less detail. Particularly useful for [how to modify charts in ggplot2](http://www.cookbook-r.com/Graphs/)

The peer (and often very expert) [help forum on Stack Overflow](https://stackoverflow.com/questions/tagged/r)

### Data science and programming in R

[R for Data Science](https://r4ds.had.co.nz/) by Hadley Wickham and Garrett Grolemund: co-authored by Hadley Wickham, the person responsible for developing the `tidyverse`. Exploration, wrangling, programming, modelling, communicating

[Hand-on programming with R](https://rstudio-education.github.io/hopr/): Chapters 1-3 cover a basic dice-rolling project that introduces basic arithmetic, functions, objects, script files and help

[Getting used to R, RStudio and RMarkdown](https://rbasics.netlify.app/index.html): a short book, with a lot of emphasis on basic programming concepts and RMarkdown

[RStudio 'basics' primers](https://rstudio.cloud/learn/primers/1): visualisation basics - the basics of using ggplot to visualise data; programming basics - functions, arguments, objects, vectors, types, lists, packages. Short videos alongside quiz questions and R exercises to check comprehension

[Advanced R](https://adv-r.hadley.nz/) by Hadley Wickham - for those who really want to get under the hood of R programming

The `tidyverse` coding [style guide](https://style.tidyverse.org/)

### Useful resources from RStudio

RStudio [suggested resources for beginners](https://education.rstudio.com/learn/beginner/)

[Cheatsheets](https://www.rstudio.com/resources/cheatsheets/) for important R packages

RStudio [webinars](https://rstudio.com/resources/webinars/): lots of useful stuff. Videos are approx. 50 mins each, so many are more appropriate for intermediate / advanced R users

### Working with R Markdown

[R Markdown reference guide](https://www.rstudio.com/wp-content/uploads/2015/03/rmarkdown-reference.pdf)

[R Markdown Cookbook](https://bookdown.org/yihui/rmarkdown-cookbook/) by Yihui Xie, Christophe Dervieux and Emily Riederer

[R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/) by Yihui Xie, J. J. Allaire and Garrett Grolemund

[bookdown: Authoring Books and Technical Documents with R Markdown](https://bookdown.org/yihui/bookdown/) by Yihui Xie: write your PhD thesis or your next book in R Markdown

[blogdown: Creating Websites with R Markdown](https://bookdown.org/yihui/blogdown/), by Yihui Xie, Amber Thomas, Alison Presmanes Hill


## Specific methods 

### Bayesian analysis

An [introduction to Bayesian statistics](https://learningstatisticswithr.com/book/bayes.html) in Learning Statistics with R by Dani Navarro

Statistical Rethinking: a series of [YouTube lectures](https://www.youtube.com/playlist?list=PLDcUM9US4XdMROZ57-OIRtIK0aOynbgZN) by Richard McElreath, with [code in R](https://github.com/rmcelreath/stat_rethinking_2022), to accompany his book of the same name (available via the Bodleian for Oxford University members)

### Causal inference / econometrics general

[Causal inference: the mixtape](https://mixtape.scunning.com/), Scott Cunningham - introduction to modern methods of causal inference with examples in R

[Introduction to Econometrics with R](https://www.econometrics-with-r.org/) by Christoph Hanck, Martin Arnold, Alexander Gerber, and Martin Schmelzer

[Applied Causal Analysis (with R)](https://bookdown.org/paul/applied-causal-analysis/) by Paul C. Bauer

### Data visualisation 

[ggplot2 book](https://ggplot2-book.org/) by Hadley Wickham: an online version of the original book on ggplot2

[ggplot2 grammar guide](https://evamaerey.github.io/ggplot2_grammar_guide/about): a visual guide to ggplot2

[R Graphics Cookbook, 2nd edition](https://r-graphics.org/) by Winston Chang

[Data Visualization: A practical introduction](https://socviz.co/) by Kieran Healy

[Fundamentals of Data Visualisation](https://clauswilke.com/dataviz/) by Claus O. Wilke

### Machine learning

[An Introduction to Statistical Learning: with Applications in R](https://www.statlearning.com/), 2nd edition, by James, Witten, Hastie and Tibshirani; there are also [video lectures](https://www.dataschool.io/15-hours-of-expert-machine-learning-videos/) that follow the first edition

[Introduction to Data Science](https://rafalab.github.io/dsbook/): Data Analysis and Prediction Algorithms with R, by Rafael A. Irizarry

### Meta-analysis

[Doing Meta-Analysis in R](https://bookdown.org/MathiasHarrer/Doing_Meta_Analysis_in_R/) by Harrer *et al.*: a comprehensive applied guide, with very useful links to free resources on the theory

[How to perform a meta-analysis with R](https://ebmh.bmj.com/content/22/4/153) by Balduzzi *et al.*: a short tutorial in the *Evidence-Based Mental Health* on doing meta-analysis with the package `meta`

The website for the `metafor` package has [data and replication code for around 25 meta-analysis papers](http://www.metafor-project.org/doku.php/analyses) using a variety of meta-analysis techniques  

[R packages for meta-analysis](https://cran.r-project.org/view=MetaAnalysis): an overview of the R packages available for meta-analysis

### Missing data methods

[Flexible Imputation of Missing Data](https://stefvanbuuren.name/fimd/) by Stef van Buuren

### Multilevel models

Centre for Multilevel Modelling [LEMMA course](https://www.bristol.ac.uk/cmm/learning/): a free online course with instructions in R and Stata 

NCRM [introductory videos on multilevel modelling](https://www.ncrm.ac.uk/resources/online/all/?main&id=20720)

[Beyond Multiple Linear Regression](https://bookdown.org/roback/bookdown-BeyondMLR/): Applied Generalized Linear Models and Multilevel Models in R by Paul Roback and Julie Legler

### Propensity score matching

Code and walkthrough videos to accompany Leite (2017) [Practical Propensity Score Methods Using R](https://www.practicalpropensityscore.com/)


### Spatial analysis

[Introduction to GIS in R](https://onsgeo.github.io/geospatial-training/docs/intro_to_gis_in_r): an introductory tutorial from the Office for National Statistics

`sf`, [Simple Features for R](https://r-spatial.github.io/sf/) - spatial data, simplified

[Geocomputation with R](https://geocompr.robinlovelace.net/) by Lovelace, Nowosad and Muenchow

[Spatial Modelling for Data Scientists](https://gdsl-ul.github.io/san/): an introduction to working with spatial analysis from the University of Liverpool's Geographic Data Science Lab

### Synthetic control

Synthetic control methods for the evaluation of single-unit interventions in epidemiology: a tutorial, Bonander et al (2021): [article](https://doi.org/10.1093/aje/kwab211) | [replication code](https://osf.io/6udsq/)

Comparative Politics and the Synthetic Control Method, Abadie et al (2014): [article](https://web.stanford.edu/~jhain/Paper/AJPS2015a.pdf) | [replication code](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/24714)

### Survey analysis

[Survey analysis in R](http://r-survey.r-forge.r-project.org/survey/): the homepage of the `survey` package, written and maintained by Thomas Lumley

### Text analysis: qualitative

`RQDA` package: [Qualitative Analysis Using R](https://nsuworks.nova.edu/cgi/viewcontent.cgi?article=2659&context=tqr)

### Text analysis: quantitative

[Text Mining with R](https://www.tidytextmining.com/) by Julia Silge and David Robinson

`quanteda` package: [Quantitative Analysis of Textual Data](http://quanteda.io/)

[Text Analysis in R](https://kenbenoit.net/pdfs/text_analysis_in_R.pdf) (2017): introductory article by Kasper Welbers , Wouter Van Atteveldt and Kenneth Benoit

### Time series and forecasting

[Forecasting: Principles and Practice](https://otexts.com/fpp3/) (3rd ed), Hyndman and Athanasopoulos


