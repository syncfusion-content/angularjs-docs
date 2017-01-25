---
layout: post
title: Create and configure color codes for heatmap value. 
description: How to configure colors codes for heatmap?
platform: Angular-1
control: ejHeatMap
documentation: ug
---

# Color Mapping

Color mapping is used to indicate values as colors instead of numerical values. For example, if a HeatMap represents a data from 0 to 100. `ColorMapping` is used to specify a color for lower value and higher value. For any value between two values, a medium color will be automatically be chosen.

In color mapping, when white color is set to value 0 and red color is set for value 30, as shown below.

{% highlight html %}

<div ng-controller="heatmapCtrl">
    <ej-heatmap id="HeatMap"
                e-width="100%"
                e-height="300px">
        <div>
        <e-colormappingcollection>
            <div e-colormapping e-value="0" e-color="#8ec8f8"></div>
            <div e-colormapping e-value="100" e-color="#0d47a1"></div>
        </e-colormappingcollection>
            </div>
    </ej-heatmap>
  </div>

syncApp.controller('heatmapCtrl', function ($scope) {
});

{% endhighlight %}

Resultant HeatMap will be as shown below.

![](Color-Mapping_images/Color-Mapping_img1.png)
 