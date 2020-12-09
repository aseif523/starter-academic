---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "The Magic of Patching"
subtitle: ""
summary: " PatchWork is a great for aesthetically combining all your graphs into a single figure. 
"
authors: [Ala'a Seif]
tags: [R-Project]
categories: []
date: 2020-12-08T21:28:06+03:00
lastmod: 2020-12-08T21:28:06+03:00
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
PatchWork is a great for aesthetically combining all your graphs into a single figure. 

As plots will always be added to the patchwork on the left-hand side, it is not possible to nest the left-hand side beside the right-hand side with the standard operators shown above. When creating a patchwork, the resulting object remain a ggplot object referencing the last added plot. This means that you can continue to add objects such as geoms, scales, etc. to it as you would a normal ggplot.

It has 4 main components:
* Assembling Plots
*	Defining Layouts
* Adding Annotations
* Aligning Across Pages

I’ll use data of refugees across the levant area to showcase the magic of patchwork. Patchwork works effortlessly with ggplot which makes the entire process a bliss.


The following plot is the timeline of refugees in levant area based on each country.
{{< figure src="1.png" title="Timeline" >}}

The Below graph is refugee per capital of each country.
{{< figure src="2.png">}}
By using the simple + or | after calling patchwork I can have both graphs in a single figure. You could use / to have figures above each other.

      patch_1<- pl.timeline + pl.meanRefPerCap
{{< figure src="3.png">}}


You could also patch with text for form a figure including explanation.

      patch_2<- pl.timeline+ grid::textGrob('Some really important text')
{{< figure src="4.png">}}

Text wrap function is used it you want to place the text first then the graph.

     patch_3<- wrap_elements(grid::textGrob('Text on left side')) + pl.meanRefPerCap
{{< figure src="5.png">}}

It’s possible to mix different operators. 

     patch_4<- patch_3 / (pl.timeline | pl.meanRefPerCap )
{{< figure src="6.png">}}

Some useful functions in patchwork: 

**plot_spacer()**

Explanation: To add an empty area in between plots	

    patch_5<- pl.timeline + plot_spacer()+ plot_spacer()+pl.meanRefPerCap   

{{< figure src="7.png">}}

**wrap_plots()**

Explanation: makes it easy to take a list of plots and add them into one composition	

     patch_6<- wrap_plots(pl.Syria, pl.Lebanon, pl.refugee_Lebanon_Syria)

{{< figure src="8.png">}}

**plot_layout()**

Explanation: controls how different plots are layed out	

    patch_7<- wrap_plots(pl.Syria, pl.Lebanon, pl.refugee_Lebanon_Syria) + plot_layout(widths = c(2, 1))

{{< figure src="9.png">}}

**plot_annotation()**

Explanation: controls different aspects of the annotation and tagging	

    patch_8<- pl.Syria + pl.Lebanon + plot_annotation('Refugees per Capita', 
    caption = 'Shows the influx of refugees from Syria to Lebanon after the start of Syrian civil war ')

{{< figure src="10.png">}}

**align_patches()**

Explanation: Aligns different plots together, both figures will have same dimensions based on max dimensions	

    max_dim<- get_max_dim(pl.Lebanon, pl.refugee_Lebanon_Syria) #get maximum dimensions
    aligned_plots <- align_patches(pl.Lebanon, pl.refugee_Lebanon_Syria)
    p1<-aligned_plots[[1]]
    p2<-aligned_plots[[2]]

{{< figure src="11.png">}}
{{< figure src="12.png">}}

This is a general idea of the possible functions, if you want to know more about optional arguments in them and see more examples check their [guide]( https://patchwork.data-imaginist.com/index.html).