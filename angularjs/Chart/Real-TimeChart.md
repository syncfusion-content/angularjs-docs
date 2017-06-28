---
layout: post
title: Using Essential JavaScript Chart in real-time scenario 
description: Learn how to update the chart dynamically with real-time data. 
platform: Angular 1.0
control: Chart
documentation: ug
---

# Real-Time Chart 

Chart can be updated dynamically with the real time data. Whenever you add a point or remove a point from the dataSource, you can call the `redraw` method to request the chart to redraw its content.    

N> You can get the chart **instance** using instance method.

{% highlight html %}

   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-series ></e-series>
        </e-series>
        </div>
        <script>
        var duration;
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
        duration=window.setInterval(update, 100);  
          });
        function updateChart(){
        //Creating chart instance
        var chart =  $("#chartcontainer").ejChart("instance");      
        if (chart.model.series[0].points.length > 10)
               chart.model.series[0].points.splice(0, 1);
        var point = chart.model.series[0].points;
        var xValue = point.length > 0 ? point[point.length - 1].x + 1 : 1;
        point[point.length] = { x:  xValue, y: getRandomNum( 1000 ) }  
        //Update Chart dynamically using redraw option
        //chart.redraw() can also be used here instead of redraw option
        $("#container").ejChart("redraw");      
       }
        </script>
    </body>
</html> 

{% endhighlight %}

[Click](http://ngjq.syncfusion.com/#/chart/live) here to view the online demo sample for real-time Chart.


