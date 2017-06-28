---
layout: post
title: Populate-Data
description: Populate Data
platform: AngularJS
control: RangeNavigator
documentation: ug
---

### Populate Data

When you provide data to **RangeNavigator**, it produces limited set of data. You can populate the **RangeNavigator** with data using the **dataSource** and **series** properties.

#### Add series to the RangeNavigator

The **Series** property provides access to a collection of all series that are defined explicitly within a **RangeNavigator** control. Each series is assigned with type and name. It contains collection of data point, each point contains x value and y values. You can add data points to the series through **dataSource** property.



{% highlight html %}


<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RangeApp">
    <head>
        <title>Essential Studio for AngularJS: RangeNavigator</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="RangeCtrl">
       <div id="rangecontainer">
       <ej-rangenavigator >
       <e-series>
       <e-series e-type="line" e-datasource=datasource e-xname="XValue" e-yname="YValue" e-opacity="0.5" e-fill="#69D2E7" 
       e-border-color="transparent" e-border-color-width="2"></e-series>
       </e-series>
       </ej-rangenavigator>
       </div>
    <script>
      function GetData() {
            var series1 = [];       
            var value = 100;
            for (var i = 1; i < 360; i++) {
                if (Math.random() > .5) {
                    value += Math.random();                 
                } else {
                    value -= Math.random();           
                }
                var point1 = { XValue: new Date(2010, 0, i), YValue: value };               
                series1.push(point1);             
            }
            data = { Open: series1};
            return data;
        }
      var data=GetData();
            angular.module('RangeApp', ['ejangular'])
            .controller('RangeCtrl', function ($scope) {
                $scope.datasource=data.Open;
                });
    </script>
   </body>
</html>

{% endhighlight %}


The following screenshot illustrates the **RangeNavigator** that is populated with data using **dataSource** property in series.

![](Populate-Data_images/Populate-Data_img1.png) 
