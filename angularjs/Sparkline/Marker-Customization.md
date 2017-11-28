---
layout: post
title: Markers Customization
description: Learn how to add markers to Sparkline.
platform: AngularJS
control: Sparkline
documentation: ug
---

## Marker Customization

You can customize markers by initializing the `e-markerSettings` property. The customization option allow you to change the visibility, fill, width, opacity and border optionscolor, width, opacity for marker. This customization only applicable for line, column and area type Sparkline.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="SparklineApp">
    <head>
        <title>Essential Studio for AngularJS: Sparkline</title>
        <!--CSS and Script file References -->
    </head>
  <body ng-controller="SparkCtrl">
    <div id="container" >
    <ej-sparkline e-markersettings-visible="true" e-markersettings-fill="#ff14ae" e-markersettings-width="4" 
    e-markersettings-border-width="1"></ej-sparkline>
    </div>
    <script>
    angular.module('SparkApp', ['ejangular'])
    .controller('SparkCtrl', function ($scope) {
                });
    </script>
    </body>
</html>


{% endhighlight %}

![](Marker-Customization_images/Marker-Customization_img1.png)
