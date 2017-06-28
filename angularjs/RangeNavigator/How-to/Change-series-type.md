---
layout: post
title: Change-series-type
description: change series type
platform: Angular 1
control: RangeNavigator
documentation: ug
---

### Change the default type of the series

The **e-type** property in **e-series** is used to change the type of the series rendered within **RangeNavigator**. By default line series will be rendered to represent the data in **RangeNavigator**.



{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RangeApp">
    <head>
        <title>Essential Studio for AngularJS: RangeNavigator</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="RangeCtrl">
       <div id="rangecontainer">
       <ej-rangenavigator>
       <e-series>
       <e-series e-type="column"></e-series>
       </e-series>
       </ej-rangenavigator>
       </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                });
    </script>
   </body>
</html>

  

{% endhighlight %}



![](How-to/Change-series-type_images/Change-series-type_img1.png) 


When using multiple series in **RangeNavigator**, **e-type** property in **e-seriesSettings** is used to set a type common for all the series.



{% highlight html %}


<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RangeApp">
    <head>
        <title>Essential Studio for AngularJS: RangeNavigator</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="RangeCtrl">
       <div id="rangecontainer">
       <ej-rangenavigator e-seriessettings-type="stackingcolumn">
       </ej-rangenavigator>
       </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                });
    </script>
   </body>
</html>


{% endhighlight %}

![](How-to/Change-series-type_images/Change-series-type_img2.png) 


