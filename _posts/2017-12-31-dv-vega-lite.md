---
layout: post
title: Airquality Dataset Viz with Vega-lite
---

This project is a final project for Data Viz course by UIUC in Coursera. The purpose of the project is to practise narrative visualization structure using Java script plus Vega/Vega-lite libraries.  

This Data Viz project can be seen at [link](https://fengliplatform.github.io/dataviz-uiuc/index.html)

This project follows the Interactive Slideshow narrative visualization structure. It is a hybrid structure mixing author-lead and reader-lead scenes. This project consists a Home page, three Scene pages and a Final summary page. So user will follow an author directed path through the slideshow. During home page and the three scenes user can drill down a little bit for some details which they are interested. Or user can just continue if they are not interested to certain pages.  

In addition, the project provides this About page to describe the design of this project.  

The charts were built using Vega-lite to complete this project in limited time. Note, Vega plus D3 will support advanced interaction to those charts which leave the improvement at a later time.  

**User Interface Events**
The buttons in the navigation bar (page top) and the Prev, Next buttons (page bottom) enable the User Interface events. The buttons allow user to walk through the author-lead structure.  

**Annotations**
The annotation is represented by the legend on top right of the scatter plots and tooltips when mouse is hovered over the bar chart.  

**Triggers**
The mouse click acts as a trigger event for navigation on button. The mouse hover event is a trigger for the tooltip in bar chart. Also the mouse can be used to zoom in/out the scatter plots in the three scene pages for details.   

**Parameters**
All the pages are hyper linked to each other. The page names are passed as input to the buttons on page top and page bottom.    

Source code location is [link](https://github.com/fengliplatform/dataviz-uiuc)

