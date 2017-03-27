---
layout: post
title: Appearance
description: What are the different ways to customize the SunburstChart 
platform: Angular -1 
control: SunburstChart
documentation: ug
---

# Appearance
The appearance of the Sunburst Chart can be customized as shown below 

## Palette
The Sunburst Chart displays different segments in different colors by default. You can customize the color of each segment by providing a custom color palette of your choice by using the **e-palette** property.

{% highlight js %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="SunburstChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="SunburstChartCtrl">
        <div id="container" ej-sunburstchart e-palette="palette">
        </div>
        <script>
                angular.module('SunburstChartApp', ['ejangular'])
                .controller('SunburstChartCtrl', function ($scope) {
                      $scope.palette=["#002e4d", "#005c99", "#008ae6", "#33adff", "#80ccff"];
                 });
        </script>
    </body>
</html>

{% endhighlight %}

The Sunburst Chart rendered with palette colors

![](Appearance_images/Appearance_img1.png)

 
## Built- in Themes

The Sunburst Chart supports different themes. 

*	flatlight
*	flatdark
*	gradientlight
*	gradientdark
*	azure
*	azuredark
*	lime
*	limedark
*	saffron
*	saffrondark
*	gradient-azure
*	gradient-azuredark
*	gradient-lime
*	gradient-limedark
*	gradient-saffron
*	gradient-saffrondark

You can set your desired theme by using the **e-theme** property. **Flat light** is the default theme used in the Sunburst Chart.

{% highlight js %}

<div id="container" ej-sunburstchart e-theme="flatdark" >					
</div>

{% endhighlight %}

![](Appearance_images/Appearance_img2.png)


