---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Let the Games Begin"
subtitle: ""
summary: "If you are like any other millennial, then you thrive on procrastination and do your best work when you’re in a time crunch. R got you covered there too! Fun is a package of R games and other funny stuff, such as the classical Mine sweeper and sliding puzzles. It also has a random password generator and a memory test."
authors: []
tags: [R-Project]
categories: []
date: 2020-12-08T23:10:14+03:00
lastmod: 2020-12-08T23:10:14+03:00
featured: true
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
If you are like any other millennial, then you thrive on procrastination and do your best work when you’re in a time crunch. R got you covered there too! Fun is a package of R games and other funny stuff, such as the classical Mine sweeper and sliding puzzles. It also has a random password generator and a memory test.

Start the script by to check whether windows or Linux/Mac. Then by choosing the game and its arguments. 

**Mine Sweeper**

    if (interactive()) {
    
    if (.Platform$OS.type == "windows") 
        
        x11() else x11(type = "Xlib")
    
    mine_sweeper()
    }

{{< figure src="1.png">}}

**Sliding Puzzle**

 if (interactive()) {
    
    if (.Platform$OS.type == "windows") 
        
        x11() else x11(type = "Xlib")
    
    sliding_puzzle()
    }

    
{{< figure src="2.png">}}


To know more about the other games and test, check the [R-documentation](https://www.rdocumentation.org/packages/fun/versions/0.2).