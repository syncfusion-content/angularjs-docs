---
layout: post
title: Orientation
description: orientation
platform: angular-1
control: Slider
documentation: ug
---

# Orientation

This property is used to set the **Slider** in either horizontal or vertical direction. By default, **Slider** renders in horizontal direction. Data type of this property is “enum”.

Possible **Slider** orientations are as follows,

Property Table for JavaScript

<table>
<tr>
<th>
Property</th><th>
Allowed values</th><th>
Description</th></tr>
<tr>
<td rowspan = "2">
orientation</td><td>
ej.Orientation.Vertical</td><td>
Displays the Slider in vertical direction</td></tr>
<tr>
<td>
ej.Orientation.Horizontal (default value)</td><td>
Displays the Slider in horizontal direction</td></tr>
</table>


The following steps explains you on how to configure the **orientation** property.

In an **HTML** page, add a **<div>** element to render it as a **Slider** widget.



{% highlight html %}

 <div id="rangeSlider" ej-slider e-width="width" e-height="height" e-values="slidevalue" e-orientation='Vertical'></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
        .controller('SliderCtrl', function ($scope) {
            $scope.sliderValue = 60;
            $scope.width = 16;
            $scope.height = 150;
            $scope.Vertical = ej.Orientation.Vertical;
        });

{% endhighlight %}

Execute the above code example to render the following output.

![](Orientation_images/orientation_img1.png) 



