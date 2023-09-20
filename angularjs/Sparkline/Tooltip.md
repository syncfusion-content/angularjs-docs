---
layout: post
title: Tooltip
description: Learn how to add Tooltip to Sparkline .
platform: AngularJS
control: Sparkline
documentation: ug
---

## Tooltip  

A [`tooltip`](../api/js/ejsparkline#members:tooltip) follows the pointer movement and is used to indicate the value of a point. This feature is applicable for line, column, pie, and area Sparkline. You can enable the tooltip by setting it's [`visible`](../api/js/ejsparkline#members:tooltip-visible) property as **true**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="SparklineApp">
    <head>
        <title>Essential Studio for AngularJS: Sparkline</title>
        <!--CSS and Script file References -->
    </head>
  <body ng-controller="SparkCtrl">
    <div id="container" >
    <ej-sparkline e-tooltip-visible="true" ></ej-sparkline>
    </div>
    <script>
    angular.module('SparkApp', ['ejangular'])
    .controller('SparkCtrl', function ($scope) {
                });
    </script>
    </body>
</html>

{% endhighlight %}

![](Tooltip_images/Tooltip_img1.png)

## Tooltip Customization

You can customize the tooltip [`fill color`](../api/js/ejsparkline#members:tooltip-fill), [`border`](../api/js/ejsparkline#members:tooltip-border) properties [`border color`](../api/js/ejsparkline#members:tooltip-border-color), [`border width`](../api/js/ejsparkline#members:tooltip-border-width) and [`font`](../api/js/ejsparkline#members:tooltip-font) properties [`color`](../api/js/ejsparkline#members:tooltip-font-color), [`font family`](../api/js/ejsparkline#members:tooltip-font-fontfamily), [`font style`](../api/js/ejsparkline#members:tooltip-font-fontstyle), [`font weight`](../api/js/ejsparkline#members:tooltip-font-fontweight), [`opacity`](../api/js/ejsparkline#members:tooltip-font-opacity), [`size`](../api/js/ejsparkline#members:tooltip-font-size)

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="SparklineApp">
    <head>
        <title>Essential Studio for AngularJS: Sparkline</title>
        <!--CSS and Script file References -->
    </head>
  <body ng-controller="SparkCtrl">
    <div id="container" >
    <ej-sparkline e-tooltip="tooltip" ></ej-sparkline>
    </div>
    <script>
    angular.module('SparkApp', ['ejangular'])
    .controller('SparkCtrl', function ($scope) {
          $scope.tooltip = {
                fill: 'red',
                border: {
                    color: "green",
                    width: 3
                },
                font: {
                    size: "12px",
                    fontFamily : "Algerian",
                    fontStyle : "italic",
                    fontWeight : "lighter",
                    opacity : 0.5,
                }
          };
    });
    </script>
    </body>
</html>

{% endhighlight %}

![](Tooltip_images/Tooltip_img3.png)

## Tooltip Template   

HTML elements can be displayed in the tooltip by using the [`template`](../api/js/ejsparkline#members:tooltip-template) option of the tooltip. The template option takes the value of the id attribute of the HTML element. You can use the **#point.x#** and **#point.y#** as place holders in the HTML element to display the x and y values of the corresponding point.

{% highlight html %}


<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="SparklineApp">
    <head>
        <title>Essential Studio for AngularJS: Sparkline</title>
        <!--CSS and Script file References -->
    </head>
  <body ng-controller="SparkCtrl">
  <div id="item" style="display: none;">
    <div>
        <div>#point.x#</div>
        <div>#point.y#</div>
    </div>
</div>
    <div id="container" >
    <ej-sparkline e-tooltip-visible="true" e-tooltip-template="item"></ej-sparkline>
    </div>
    <script>
    angular.module('SparkApp', ['ejangular'])
    .controller('SparkCtrl', function ($scope) {
                });
    </script>
    </body>
</html>

{% endhighlight %}

![](Tooltip_images/Tooltip_img2.png)