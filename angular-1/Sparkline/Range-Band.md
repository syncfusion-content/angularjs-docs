---
layout: post
title: RangeBand
description: Learn how to add Rangeband to Sparkline .
platform: Angular 1.0
control: Sparkline
documentation: ug
---

## Range Band  

The range band feature is used to highlight a particular range along the y-axis using start and end range property. You can also customize the color and opacity of the range band. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="SparklineApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
  <body ng-controller="SparkCtrl">
    <div id="container" >
    <ej-sparkline e-rangebandsettings-startrange="4" e-rangebandsettings-endrange="30" e-rangebandsettings-color="#ff14ae" e-rangebandsettings-opacity="0.4"></ej-sparkline>
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
            .controller('SparkCtrl', function ($scope) {
                });
    </script>
    </body>
</html>

{% endhighlight %}

![](Range-Band_images/Range-Band_img1.png)

