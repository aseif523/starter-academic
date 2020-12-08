---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Intro to R"
subtitle: ""
summary: "
R does magic in terms of the reproducibility of your work. So, bare with me as we learn R 101 through this blog series. 
"
authors: [Ala'a Seif]
tags: [R-Project]
categories: []
date: 2020-12-07T14:41:12+03:00
lastmod: 2020-12-07T14:41:12+03:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
R does magic in terms of the reproducibility of your work. So, bare with me as we learn R 101 through this blog series. If it’s the first time you hear of R, its an opensource software project, available for free download. It’s a platform that is widely used by statistical researchers and working scientists for making new methods available to users. 
The first step you need to do is to download and install R and RStudio:

 1.	 [R](http://cran.utstat.utoronto.ca/) (Download/Install)

 2.	[RStudio](https://rstudio.com/products/rstudio/download/#download) (Download/Install)


The first trick of working with R is to keep all your data, scripts and project in one folder, your directory. In the first blog post we’ll learn the basics of importing your data and view it. 
When starting Rstudio:

1.	Choose New Directory

2.	Save your data in the same folder as your directory

3.	In RStudio, start a new script 

{{< figure src="blog 1.png">}}

R is a highly collaborative software in which many have previously made packages that make your life easier. Readxl package lets us import .xlsx files. 

You could install different packages by:

    Install.packages( “ readxl “)


You could also check if a package is installed by

    Intalled.packages(“readxl”)



Every time you need to use functions in a package you need to call its library first.

    Library (readxl)


Now to upload .xlsx file


    Bfi <- read_excel (“bfi.xlsx”)


Or if your data is in .csv

    Bfi <- read.excel (“bfi.csv”)


Names shows us the column names


    Names(bfi)


Head previews the first rows and tails previews the last six rows.


    Head(bfi)
    Tail(bfi)*


To view the entire data


    View(bfi)


When you need help theres a function for that too, it returns a tab with description, usage and arguments of the function asked about.

    Help(head)

{{< figure src="blog 2.png">}}