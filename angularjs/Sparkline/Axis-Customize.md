---
layout: post
title: Axis Customize
description: Learn how to customize axis in Sparkline.
platform: AngularJS
control: Sparkline
documentation: ug
---

## Axis Customize 

The Sparkline axis can be collapsed using visible property in `e-axislinesettings` and this not applicable for win-loss. You can customize `e-axislinesettings-color`, `e-axislinesettings-width` and `e-axislinesettings-dasharray` of axis line.

 {% highlight html %}
 
 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="SparklineApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
  <body ng-controller="SparkCtrl">
    <div id="container" >
    <ej-sparkline e-axislinesettings-visible="true" e-axislinesettings-color="#ff14ae"></ej-sparkline>
    </div>
    <script>
    angular.module('SparkApp', ['ejangular'])
    .controller('SparkCtrl', function ($scope) {
                });
    </script>
    </body>
</html>

{% endhighlight %}

![](Axis-Customize_images/Axis-Customize_img1.png)