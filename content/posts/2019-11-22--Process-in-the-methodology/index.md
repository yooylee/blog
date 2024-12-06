---
title: "(Hidden) research data analysis processes"
date: "2019-11-22"
template: "post"
draft: false
slug: "/posts/hidden-research-data-analysis-processes"
category: "Open Science"
tags:
  - "Research"
  - "Data analysis"
  - "Publication"

description: "This blog post is about my trial and error on the data analysis for research collaboration with Ayoung Yoon, Assistant Professor at IUPUI. I would like to share how I arrived to choose a statistical method, open source tool, and its package which wasn't mentioned in the publication."

socialImage: "./image.jpg"

---

In the traditional scholarly communication, a reader can see only a final product of research, usually in an article format - Title, Abstract, Keywords, Introduction, Literature Review, Methodologies, Analysis and Results, Discussion, Conclusion, and References. Research is an iterative process, but often times, it is hard to capture the process and share with other people. In the open scholarship (open science) movement, researchers encourage themselves to make their own research open, not just their final product but also the entire process and data valuing **transparent** and **accessible**. Open source tools like <a href="https://osf.io/">OSF</a> (Open Science Framework) and <a href="https://jupyter.org/">Project Jupyter</a> enable them to do that.

I had a great opportunity to work with <a href="https://ayoungyoon.com/">Ayoung Yoon</a>, Assistant Professor at Indiana University School of Informatics and Computing (IUPUI), Department of Library and Information Science, on her research project - what trust factors could affect a data reuse practice (publication: <a href="https://doi.org/10.1108/OIR-01-2019-0014">Factors of trust in data reuse</a>). In the final publication, we simply described what a statistical method (Partial Least Squares Path Modeling (PLS-PM)) was used with which software and package (plspm R package, version 0.4.9), but there was a (hidden) process of how we arrived there which nobody mention in an article in general.

When I read scholarly articles, I am always in awe of research methodologies and analyses, especially how researchers arrive their conclusion from their research question. It's simple yet beautiful. However, based on my research experience, it's not that simple and beautiful. In this blog post, in order to make a small contribution to open science movement, I would like to share my trial and error regarding the data analysis of our work.

#### Preparation for data analysis

The study utilized a survey method using <a href="https://www.surveymonkey.com/">SurveyMonkey</a> institutional account and data collected were exported into csv and Excel formats. I imported original datasets in the csv file to <a href="https://rstudio.com/">RStudio</a> as a dataframe and then started tidying the original datasets with data validation (check if it is in compliance with the research criteria e.g., in our case, it was data reuse experience) and data coding (column's name e.g., in our case, from question of *the producers of the data are the experts in the domain of this research* to ABILITY01).

#### Why R and RStudio?

<a href="https://www.r-project.org/">R</a> is a powerful and open source language for statistical analysis with a strong community behind. <a href="https://www.statmodel.com/">Mplus</a> is a great tool for latent variable model analyses including exploratory factor analysis (EFA), structural equation modeling (SEM), item response theory (IRT) analysis, and many more, but it's very expensive. I knew that <a href="https://crdcn.org/carleton-ottawa-outaouais-rdc-cool-rdc">COOL RDC</a> at uOttawa Library has a copy of Mplus, but learned that its access to COOL RDC is very restricted. In R, there are packages such as <a href="http://lavaan.ugent.be/index.html">lavaan</a> developed by <a href="https://users.ugent.be/~yrosseel/index.html">Yves Rosseel</a> or <a href="https://cran.r-project.org/web/packages/psych/index.html">psych</a> (mostly for researchers in psychology but it also provides functions for factor analysis) developed by <a href="https://orcid.org/0000-0003-4880-9610">William Revelle</a>. In addition, RStudio is an easy and user-friendly integrated development environment for R in which I can save all codes, data, workflow, command history, and etc. as a project so that I can reload them whenever I want to. Like Python and Jupyter Notebook, R and RStudio enable researchers to make their research open, reproducible, and easily sharable.

#### From CFA (Confirmatory Factor Analysis) to PLS-PM (Partial Least Squares Path Modeling)

Since we would like to identify an underlying latent factor from a set of observed variables (e.g., ABILITY01, ABILITY02, ABILITY03, ETHICS01, ETHICS02, ETHICS03, COMMIT01, COMMIT02, RAPPORT01, RAPPORT02 for Data Producer), our first considered method was the <a href="https://en.wikipedia.org/wiki/Confirmatory_factor_analysis">confirmatory factor analysis</a> (CFA) using <a href="https://cran.r-project.org/web/packages/lavaan/index.html">lavaan</a> package. One of the CFA assumptions, though, is a normal distribution of variables as it is based on the covariances. We examined each variable, but our datasets were not normally distributed so we could either transform those variables, drop them from our model or simply choose other methods.

The second method we considered was the <a href="https://en.wikipedia.org/wiki/Rasch_model">Rasch model</a> (one of the most known item response theory (IRT)) using <a href="https://cran.r-project.org/web/packages/ltm/index.html">ltm</a> package. Since our datasets were skewed, we could transform them from continuous data to categorical data as "0" (Not agree) and "1" (agree). From this approach, we were able to identify how each item was related to the TRUST factor, but we couldn't identify relationships between observed variables and latent variables.

Finally, we chose the <a href="https://en.wikipedia.org/wiki/Partial_least_squares_path_modeling">partial least squares path modeling</a> (PLS-PM) with <a href="https://cran.r-project.org/web/packages/plspm/index.html">plspm</a> package for our method. This approach is a two-step process: factor model for constructing measurements and relationships between constructs for structural model. In addition, the PLS-PM approach doesn't assume normal distribution or sample size, so it was a good match for us to proceed in order to pursue our research question from datasets collected.

#### Same datasets but different approaches

I attended a session delivered by <a href="https://osf.io/jqycf/">Thomas Lindsay</a> and <a href="https://osf.io/rgvsz/">Alicia Hofelich Mohr</a> from the University of Minnesota at the <a href="https://www.library.mcgill.ca/iassistcarto2018/">IASSIST & CARTO 2018 conference</a> and I was fascinated by the study that they introduced. The study was <a href="https://psyarxiv.com/qkwst">*Many analysts, one dataset: Making transparent how variations in analytical choices affect result*</a> which talks about how different analysts address the same research question with the same dataset with different analytic approaches.

Although we chose the PLS-PM approach, there would be other approaches to answer our original research question and I would like to learn and improve myself. I am afraid of my mistakes and public humiliation, but I learn from mistakes. I want to contribute to open scholarship movement, but when I think back, I always benefit from the community who is willing to open their research and share their knowledge so that I can be a better librarian and researcher.
