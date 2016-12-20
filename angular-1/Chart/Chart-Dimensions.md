---
layout: post
title: Chart size
description: Learn how to set Chart size and make it responsive. 
platform: Angular 1.0
control: Chart
documentation: ug
---

# Chart Dimensions

You can set the size of the chart directly on the chart or to the container of the chart. When you do not specify the size, it takes 450px as the height and window size as its width, by default. 

## Set size for the container

You can customize the chart dimension by setting the width and height for the container element. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        </div>
         <style type="text/css">
        #container {
        width:820px; 
        height:500px;
        }
        </style>
        <script>
         
            angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                 
                });
        </script>
    </body>
</html>

{% endhighlight %}

## Set size in pixels

You can also set the chart dimension by using the `e-size` property of the chart. 

{% highlight html %}

   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-size=size>
        </div>
        <script>
            var sizeObj = { height: "450px", width: "600px" };
            angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                    $scope.size = sizeObj;
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Dimensions_images/Chart-Dimensions_img1.png)


## Setting size relative to the container size

You can specify the chart size in percentage by using the `e-size` property. The chart gets its dimension with respect to its container.

{% highlight html %}

   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-size=size>
        </div>
        <script>
            var sizeObj = { height: "80%", width: "90%" };
            angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                    $scope.size = sizeObj;
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Dimensions_images/Chart-Dimensions_img2.png)


## Responsive chart

To resize the Chart when the browser or the chart container is resized, set the `e-isResponsive` property to **true**, where the chart adapts to the changes in size of the container.

{% highlight html %}

   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-isResponsive= true>
        </div>
        <script>
         
            angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  
                });
        </script>
    </body>
</html>


{% endhighlight %}


