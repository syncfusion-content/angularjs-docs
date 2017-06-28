---
layout: post
title: Performance tips 
description: How to improve the performance of Essential Javascript Chart
platform: Angular 1.0
control: Chart
documentation: ug
---

# Performance 

* When there are large number of points to load, you can enable canvas rendering mode in chart. Canvas rendering is faster than SVG because it does not involve manipulating DOM elements as much as SVG rendering.   

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enablecanvasrendering="true">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}




* Instead of enabling data markers and labels when there are large number of data points, you can use **trackball** and **tooltip** to view point information.

## Lazy Loading

Lazy loading feature provides an effective way for loading data on demand by scrolling and viewing a smaller range of data from a larger collection.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enablecanvasrendering="true" 
        e-primaryxaxis-scrollbarsettings-visible="true" 
        e-primaryxaxis-scrollbarsettings-canresize="true"
        e-primaryxaxis-scrollbarsettings-range-min="2009/1/1"
        e-primaryxaxis-scrollbarsettings-range-max="2014/1/1">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                        });
        </script>
    </body>
</html>
 
 {% endhighlight %}

![](Performance_images/Perform_img1.png)