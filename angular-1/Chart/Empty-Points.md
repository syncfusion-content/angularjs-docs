---
layout: post
title: Empty Points 
description: How to show or hide an empty point in Essential Javascript Chart.
platform: Angular 1.0
control: Chart
documentation: ug
---

# Empty Points 

The Data points that uses the **null** or **undefined** as value are considered as empty points. Empty data points are ignored and not plotted in the Chart. When the data is provided by using the `e-points` property, you can set the **isEmpty** to true to specify that the particular point is an empty point.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-series e-points="points"></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.points=[{ x: 0, y: 210 }, 
                              { x: 1, y: null }, { x: 2, y: 150 },
                              { x: 3, y: 180,isEmpty: true }, 
                              { x: 4, y: 170},
                              { x: 5, y: 200 }, 
                              { x: 6, y: 140, isEmpty: true },
                              { x: 7, y: 120 }, { x: 8, y: 140 } ];
                   });
        </script>
    </body>
</html>
   
{% endhighlight %}

![](Empty-Points_images/Empty-Points_img1.png)


## emptypointsettings

You can customize the empty points visibility and change its `displayMode` *(gap, zero and average)* using `e-emptypointsettings` option.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series e-emptypointsettings="emptypoint"></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                    $scope.emptypoint= { 
                        visible: true,
                        displayMode : "average"
                    };
                     });
        </script>
    </body>
</html>

{% endhighlight %}

![](Empty-Points_images/Empty-Points_img2.png)


If the `visible` property of `e-emptypointsettings` is *false*, then the empty points has been dropped and chart will be rendered without empty points.

![](Empty-Points_images/Empty-Points_img3.png)

## Customizing Styles

Empty points color and border can be customized using `style` property of `e-emptypointsettings`.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series e-emptypointsettings="emptypoint"></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                    $scope.emptypoint= { 
                        visible: true,
                       //Customizing empty points styles
                       style: {
                           color: "#ffa000",
                           border:{
                               color: "gray",
                               width:2
                            }
                        }
                     };
                     });
        </script>
    </body>
</html>
 

{% endhighlight %}

![](Empty-Points_images/Empty-Points_img4.png)