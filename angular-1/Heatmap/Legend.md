---
layout: post
title: Legend gives visual guideline for mapping between value and color.
description: How to create and configure legend for HeatMap
platform: Angular-1
control: HeatMapLegend
documentation: ug
---

# Legend

Legend is a control used to summarize the range of colors in HeatMap. This gives visual guideline for mapping between value and color.

##Create Legend

Legend can be created with color mapping as shown below.

{% highlight html %}

  <div ej-heatmaplegend id="heatmap_legend"
       e-colormappingcollection="colorMappingCollection"
       e-height="50px"
       e-width="75%"
       e-showlabel="true">
   <div e-colormappingcollection>
       <div e-colormapping e-value="0" e-color="#8ec8f8"></div>
       <div e-colormapping e-value="100" e-color="#0d47a1"></div>
   </div>
 </div>

syncApp.controller('heatmapCtrl', function ($scope) {
});

{% endhighlight %}

Resultant legend will be like following image.

![](Legend_images/Legend_img1.png)
 
##Legend Mode

There are two modes for Legend
* Gradient
* List

###Gradient:

{% highlight html %} 

<div ej-heatmaplegend id="heatmap_legend"
     e-colormappingcollection="colorMappingCollection"
     e-height="50px"
     e-width="75%"
     e-showlabel="true"
     e-legendmode="ej.heatmap.legendmode.gradient">
    <div e-colormappingcollection>
        <div e-colormapping e-value="0" e-color="#8ec8f8"></div>
        <div e-colormapping e-value="100" e-color="#0d47a1"></div>
    </div>
</div>

syncApp.controller('heatmapCtrl', function ($scope) {
});
        
{% endhighlight %}

![](Legend_images/Legend_img2.png)

###List:

{% highlight html %} 

<div ej-heatmaplegend id="heatmap_legend"
     e-colormappingcollection="colorMappingCollection"
     e-height="50px"
     e-width="75%"
     e-showlabel="true"
     e-legendmode="ej.HeatMap.LegendMode.List">
    <div e-colormappingcollection>
        <div e-colormapping e-value="0" e-color="#8ec8f8"></div>
        <div e-colormapping e-value="100" e-color="#0d47a1"></div>
    </div>
</div>

syncApp.controller('heatmapCtrl', function ($scope) {
});
  
{% endhighlight %}

![](Legend_images/Legend_img3.png)

##Orientation

There are 2 types of Orientation, applicable for Gradient and List Mode 
* Horizontal
* Vertical

###Horizontal:

{% highlight html %} 

<div ej-heatmaplegend id="heatmap_legend"
     e-colormappingcollection="colorMappingCollection"
     e-height="50px"
     e-width="75%"
     e-showlabel="true"
     e-legendmode="ej.HeatMap.LegendMode.List">
    <div e-colormappingcollection>
        <div e-colormapping e-value="0" e-color="#8ec8f8"></div>
        <div e-colormapping e-value="100" e-color="#0d47a1"></div>
    </div>
</div>

syncApp.controller('heatmapCtrl', function ($scope) {
});
        
{% endhighlight %}

![](Legend_images/Legend_img3.png)

###Vertical:

{% highlight html %} 

<div ej-heatmaplegend id="heatmap_legend"
     e-colormappingcollection="colorMappingCollection"
     e-height="50px"
     e-width="75%"
     e-showlabel="true"
     e-legendmode="ej.HeatMap.LegendMode.List"
     e-orientation=" ej.HeatMap.LegendOrientation.Vertical">
    <div e-colormappingcollection>
        <div e-colormapping e-value="0" e-color="#8ec8f8"></div>
        <div e-colormapping e-value="100" e-color="#0d47a1"></div>
    </div>
</div>

syncApp.controller('heatmapCtrl', function ($scope) {
});
        
{% endhighlight %}

![](Legend_images/Legend_img4.png)