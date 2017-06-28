---
layout: post
title: Chart types
description: What are the different types of Charts available in Essential Javascript Chart.
platform: Angular 1.0
control: Chart
documentation: ug
---

# ChartTypes

## Line Chart

To render a Line Chart, set the series `e-type` as **"line"** in the chart series. To change the line segment color, you can use the `e-fill` property of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="line" e-fill="#E94649"></e-series>
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img1.png)


### Change the line width

To change the width of the line segment, you can use the `e-width` property in the series.

{% highlight html %}
 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="line" e-width="3"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img2.png)



### Dashed lines

To render the line series with dotted lines, you can use the `e-dashArray` option of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="line" e-dasharray="5,5"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img3.png)



### Changing the line cap

For customizing the start and end caps of the line segment, you can use the `e-lineCap`property.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-linecap="square"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img4.png)


### Changing the line join

You can use the `e-linejoin` property to specify how two intersecting line segments should be joined.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-linejoin="round"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}


![](Chart-Types_images/Chart-Types_img5.png)

### MultiColor Line

You can change the color of the line segments by using the `e-fill` property of the each `e-points` in the series.

{% highlight html %}

html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series>
        <e-points>
        <e-points e-fill="red">
        </e-points>
        </e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
               
                });
        </script>
    </body>
</html>
     


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img81.png)

## Step Line Chart

To render a Step Line Chart, set the series `e-type` as **"stepline"** in the chart series. To change the StepLine segment color, you can use the `e-fill` property of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="stepline" e-fill="#E94649"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img6.png)


### Changing the line width

To change the line width, you can use the **width** property.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-width="3"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>
{% endhighlight %}

![](Chart-Types_images/Chart-Types_img7.png)


### Dashed lines

To render the step line series with dotted lines, you can use the `e-dasharray` option of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-dashArray="5,5"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>
    
           
   

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img8.png)


### Changing the line cap

For customizing the start and end caps of the line segment, you can use the `e-linecap` property.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-lineCap="square"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img9.png)


### Changing the line join

You can use the `e-linejoin` property to specify how two intersecting line segments should be joined.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-linejoin="round"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img10.png)


## Area Chart

To render an Area chart, you can specify the series `e-type` as **"area"** in the chart series. To change the Area color, you can use the `e-fill` property of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="area"  e-fill = "#69D2E7"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img11.png)





## Range Area Chart

To render a Range Area Chart, set the `e-type` as **"rangeArea"** in the chart series. To change the RangeArea color, you can use the `e-fill` property of the series.

Since the RangeArea series requires two y values for a point, you have to add the `e-high` and `e-low`value. High and Low value specifies the maximum and minimum range of the points.

* When you are using the `e-points` option, specify the high and low values by using the `e-high` and `e-low` option of the point.

* When you are using the `e-datasource` option to assign the data, map the fields from the dataSource that contain high and low values by using the `e-series-high` and `e-series-low` options. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="rangeArea"  e-datasource="dataSource" e-xName="x"  e-high="high" 
        e-low="low" e-fill="Indigo"></e-series>
        </e-series>
        </div>
        <script>
         var chartData=[{ x: 1935, high:80, low:70},
                        { x: 1945, high:60, low:50}];
            angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                     $scope.dataSource=chartData;
                });
        </script>
    </body>
</html>
 
{% endhighlight %}

![](Chart-Types_images/Chart-Types_img12.png)




## Step Area Chart

To render a Step Area Chart, set the `e-type` as **"stepArea"** in the chart series. To change the StepArea color, you can use the `e-fill` property of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="stepArea"  e-fill="#69D2E7"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                 
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img13.png)





## Spline Area Chart

To render a Spline Area Chart, set the `e-type` as **"splineArea"** in the chart series. To change the SplineArea color, you can use the `e-fill` property of the series.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="splineArea"  e-fill="#C4C24A"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {                  
                 
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img14.png)


## Stacked Area Chart

To render a Stacked Area Chart, set the `e-type` as **"stackingArea"** in the chart series. To change the StackingArea color, you can use the `e-fill` property of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="stackingArea"  e-fill="#69D2E7"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {      
                 
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img15.png)


## 100% Stacked Area Chart  

To render a 100% Stacked Area Chart, set the `e-type` as **"stackingArea100"** in the chart series. To change the StackingArea100 color, you can use the `e-fill` property of the series.   

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="stackingArea100"  e-fill="#C4C24A"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
            
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img16.png)


## Column Chart

To render a Column Chart, set the `e-type` as **"column"** in the chart series. To change the color of the column series, you can use the `e-fill` property.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
            <e-series  e-type="column"  e-fill="#E94649"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
       .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>



{% endhighlight %}

![](Chart-Types_images/Chart-Types_img17.png)

### Change a point color

You can change the color of a column by using the `fill` property of the point.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-points>
        <e-points e-fill="skyblue" ></e-points>
        //...
        </e-points>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                 
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img18.png)



### Column width customization

Width of the column type series can be customized by using the `e-columnWidth` property. Default value of `e-columnWidth` is 0.7. Value ranges from 0 to 1. Here 1 corresponds to 100% of available width and 0 corresponds to 0% of available width.

N> Width of a column also depends upon the `e-columnSpacing` property, because `e-columnSpacing` will reduce the space available for drawing a column. This is also applicable for StackingColumn, StackingColumn100, Bar, StackingBar, StackingBar100, RangeColumn, HiLo, HiLoOpenClose, Candle and Waterfall charts.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-commonseriesoptions-columnwidth="0.7">
        <e-series>
        <e-series  e-columnwidth="0.8"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img86.png)

### Column with rounded corners
Corners of the column chart can be customized by setting value to the `e-cornerradius` property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-commonseriesoptions-cornerradius="20" >
         </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img88.png)

### Spacing between column series

Spacing between column type series can be customized using the `e-columnspacing` property. Default value of `e-columnSpacing` is 0. Value ranges from 0 to 1. Here 1 corresponds to 100% available space and 0 corresponds to 0% available space.

N> Column spacing will also affect the width of the column. For example, setting 20% spacing and 100% width will render columns with 80% of total width. This is also applicable for StackingColumn, StackingColumn100, Bar, StackingBar, StackingBar100, RangeColumn, HiLo, HiLoOpenClose, Candle and Waterfall charts.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-commonseriesoptions-columnspacing="0">
        <e-series>
        <e-series  e-columnspacing="0.2"></e-series>
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>
{% endhighlight %}

![](Chart-Types_images/Chart-Types_img87.png)


### Cylindrical Chart

To render a cylindrical chart, set the `e-columnfacet` property as "cylinder" in the chart series along with the series type. 

The following chart types can be rendered as cylinder in both 2D and in 3D view.

* Column Chart, Bar Chart, Stacked Column Chart, Stacked Bar Chart, 100% Stacked Column Chart, 100% Stacked Bar Chart.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-series  e-type="column" e-columnfacet="cylinder"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>  

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img89.png)

## RangeColumn Chart

To render a Range Column Chart, set the `e-type` as **"rangeColumn"** in the chart series. To change the RangeColumn color, use the `e-fill` property of the series.

Since, the RangeColumn series requires two y values for a point, add the `e-high` and `e-low` value. High and Low value specifies the maximum and minimum range of the points.

* When you are using the `e-points` option, specify the high and low values by using the `high` and `low` option of the point.

* When you are using the `e-datasource` option to assign the data, you have to map the fields from the dataSource that contains high and low values by using the `e-series-high` and `e-series-low` options.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="rangeColumn"  e-datasource="dataSource" e-xName="x"  e-high="high"  
        e-low="low" e-fill="#E94649"></e-series>
        </e-series>
        </div>
        <script>
         var chartData=[{ x: 1935, high:80, low:70},
                        { x: 1945, high:60, low:50}];
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {               
                   $scope.dataSource=chartData;
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img19.png)


### Change a point color 

To change the color of a range column, you can use the `fill` property of point. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-points>
        <e-points e-fill="skyblue" ></e-points>
        //...
        </e-points>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.points=[
                      { fill: 'skyblue' }, //...
                     }];
                   });
        </script>
    </body>
</html>



{% endhighlight %}

![](Chart-Types_images/Chart-Types_img20.png)

## Stacked Column Chart

To render a Stacked Column Chart, set the `e-type` as **"stackingColumn"** in the chart series. To change the StackingColumn color, you can use the `e-fill` property of the series.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
         <e-series  e-type="stackingColumn"  e-fill="#E94649"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>
    

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img21.png)


### Cluster / Group stacked columns

You can use the `e-stackinggroup` property to group the stacked columns. Columns with same group name are stacked on top of each other.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series e-stackinggroup="GroupOne"></e-series>
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>



{% endhighlight %}

![](Chart-Types_images/Chart-Types_img22.png)


### Change a point color

To change the color of a stacking column, you can use the `fill` property of the point. 

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-points>
        <e-points e-fill="skyblue" ></e-points>
        //...
        </e-points>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img23.png)


## 100% Stacked Column Chart    

To render a 100% Stacked Column Chart, set the `e-type` as **"stackingColumn100"** in the chart series. To change the StackingColumn100 color, you can use the `e-fill` property of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="stackingcolumn100"  e-fill="#E94649"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>
 

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img24.png)


### Cluster / Group 100% stacked columns

By using the `e-stackinggroup` property, you can group the 100% stacking columns. Columns with same group name are stacked on top of each other. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-stackinggroup="GroupOne"></e-series>
        <e-series  e-stackinggroup="GroupOne"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>



{% endhighlight %}

![](Chart-Types_images/Chart-Types_img25.png)


### Change a point color

To change the color of a 100% stacking column, you can use the `fill` property of the point. 

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-points>
        <e-points e-fill="skyblue" ></e-points>
        //...
        </e-points>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {

        });         
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img26.png)


## Bar Chart

To render a bar Chart, set the `e-type` as **"bar"** in the chart series. To change the bar color, you can use the `e-fill` property of the series.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="bar" e-fill="#E94649"></e-series>            
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img27.png)


### Change the color of a bar

By using the `fill` property of the point, you can change the specific point of the series. 

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-points>
        <e-points e-fill="skyblue" ></e-points>
        //...
        </e-points>
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
              
            });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img28.png)


## Stacked Bar Chart

To render a Stacked Bar Chart, set the `e-type` as **"stackingBar"** in the chart series. To change the StackingBar color, you can use the `e-fill` property of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="stackingBar" e-fill="#E94649"></e-series>            
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>
        


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img29.png)




### Cluster / Group stacked bars

You can use the `e-stackinggroup` property to group the stacking bars with the same group name. 

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-stackinggroup="GroupOne"></e-series>
        <e-series  e-stackinggroup="GroupOne"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img30.png)


### Change a point color

You can change the color of a stacking bar by using the `fill` property of the point.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-points>
        <e-points e-fill="skyblue" ></e-points>
        //...
        </e-points>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img31.png)


## 100% Stacked Bar Chart

To render a 100% Stacked Bar Chart, set the `e-type` as **"stackingBar100"** in the chart series. To change the StackingBar100 color, you can use the `e-fill` property of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="stackingBar100" e-fill="#E94649"></e-series>            
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>
        

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img32.png)


By using the `e-stackingGroup` property, you can group the 100% stacking bars with the same group name. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-stackinggroup="GroupOne"></e-series>
        <e-series  e-stackinggroup="GroupOne"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img33.png)


### Change a point color

To change the color of a 100% stacking bar, you can use the `fill` property of the point. 

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-points>
        <e-points e-fill="skyblue" ></e-points>
        //...
        </e-points>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img34.png)



## Spline Chart

To render a Spline Chart, set the `e-type` as **"spline"** in the chart series. To change the Spline segment color, you can use the `e-fill` property of the series.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="spline" e-fill="#6ADCB0"></e-series>            
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>
        

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img35.png)


### Change the spline width

To change the spline segment width, you can use the `e-width` property of the series.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="spline" e-fill="#6ADCB0" e-width="3"></e-series>            
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>



{% endhighlight %}

![](Chart-Types_images/Chart-Types_img36.png)


### Dashed lines

To render the spline series with dotted lines, you can use the `e-dasharray` option of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="spline" e-dasharray="5,5"></e-series>            
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img37.png)


## Pie Chart

You can create a pie chart by setting the series `e-type` as **"pie"** in the chart series.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="pie"></e-series>            
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img38.png)



### Change the pie size

You can use the `e-pieCoefficient` property to change the diameter of the Pie chart with respect to the plot area. It ranges from 0 to 1 and the default value is **0.8**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="pie" e-piecoefficient="0.4"></e-series>            
        </e-series>
        </div>
        <script>
          angular.module('ChartApp', ['ejangular'])
          .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img39.png)


### Explode a pie segment

You can explode a pie segment on the chart load by using the `e-explodeindex` of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-explodeindex="1"></e-series>            
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img40.png)


### Explode all the segments

To explode all the segments of the Pie chart, you can enable the `e-explodeall` property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-explodeall="true"></e-series>            
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img41.png)


### Explode a pie segment on mouse over

To explode a pie segment on a mouse over, you can enable the `e-explode` property of the series.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-explode="true"></e-series>   
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img42.png)


### Sector of Pie

EjChart allows you to render all the data points/segments in the semi-pie, quarter-pie or in any sector by using the `e-startangle` and `e-endangle` options.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="pie" e-startangle="-90" e-endangle="90"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             
                });
        </script>
    </body>
</html>
{% endhighlight %}

![](Chart-Types_images/Chart-Types_img43.png)


## Doughnut Chart

To create a Doughnut chart, you can specify the series `e-type` as **"doughnut"** in the chart series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="doughnut"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img44.png)


### Change Doughnut inner radius

You can change the doughnut chart inner radius by using the `e-doughnutcoefficient` with respect to the plot area. It ranges from 0 to 1 and the default value is **0.4**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="doughnut" e-doughnutcoefficient="0.6"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img45.png)


### Change the doughnut size

You can use the `e-doughnutsize` property to change the diameter of the Doughnut chart with respect to the plot area. It ranges from 0 to 1 and the default value is **0.8**.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="doughnut" e-doughnutsize="0.4"></e-series>
         </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img46.png)


### Explode a doughnut segment

To explode a specific doughnut segment, set the index to be exploded by using the `e-explodeindex` option of the series.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="doughnut" e-explodeindex="1"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img47.png)


### Explode all the segments

To explode all the segments, you can enable the `e-explodeall` property of the series.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="doughnut" e-explodeall="true"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img48.png)


### Explode a doughnut segment on mouse over

To explode a doughnut segment on a mouse over, you can enable the `e-explode` property of the series.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="doughnut" e-explode="true"></e-series>
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img49.png)


### Sector of Doughnut

EjChart allows you to render all the data points/segments in the semi-doughnut, quarter- doughnut or in any sector by using the `e-startAngle` and `e-endAngle` options.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="doughnut" e-startangle="-90" e-endangle="90"></e-series>
         </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img50.png)


## Multiple Pie Chart

EjChart provides support to render more than one series in pie and in doughnut chart. Radius of each series is calculated based on the radius of the previous series. And in addition legend is displayed according to the list of chart series.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="pie"></e-series>
        <e-series  e-type="pie"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

**Multiple Pie** 

![](Chart-Types_images/Chart-Types_img82.png)

**Multiple Doughnut** 

![](Chart-Types_images/Chart-Types_img83.png)

### Start and End Angle Support

In the Multiple Pie chart, the start and end angle property is also supported.

**Sector of Multiple Pie**

![](Chart-Types_images/Chart-Types_img84.png)

**Sector of Multiple Doughnut**

![](Chart-Types_images/Chart-Types_img85.png)


## Pyramid Chart

To create a Pyramid chart, you can specify the series `e-type` as **"pyramid"** in the chart series.  

{% highlight html %}
 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="pyramid"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img51.png)


### Pyramid Mode

Pyramid mode has two types, *linear* and *surface* respectively. The default **"pyramidMode"** type is "linear".

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="pyramid" e-pyramidmode="surface"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img52.png)


### Gap between the segments

You can control the gap between the segments by using the `e-gapratio` option of the series. Its ranges from 0 to 1.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="pie" e-gapratio="0.1"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>
{% endhighlight %}

![](Chart-Types_images/Chart-Types_img53.png)


### Explode a pyramid segment

You can explode a pyramid segment on the chart load by using the `e-explodeindex` of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="pyramid"  e-explodeindex="4"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img54.png)


## Funnel Chart

You can create a funnel chart by setting the series `e-type` as **"funnel"** in the chart series.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="funnel"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img55.png)


### Change the funnel width and height

Funnel segments height and width is calculated from the chart size, by default. You can change this height and width directly without changing the chart size by using the `e-funnelheight` and `e-funnelWidth` property of the series.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="funnel" e-funnelheight="22%" e-funnelwidth="25%"></e-series>     
        </e-series> 
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img56.png)


### Explode a funnel segment

You can explode a funnel segment on the chart load by using the `e-explodeindex` of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="funnel" e-explodeindex="3"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img57.png)


## Bubble Chart

To create a Bubble chart, you can set the series `e-type` as **"bubble"** in the chart series. Bubble chart requires 3 fields (*x, y and size*) to plot a point. Here, **size** is used to specify the size of each bubble segment. 

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="bubble" e-datasource="datasource" e-xname="month" e-yname="sales"
        e-size="profit" ></e-series>
        </e-series>
        </div>
        <script>
         var chartData = [
                { month: 'Jan', sales: 35, profit:1.34 },
                { month: 'Feb', sales: 28, profit:1.05 },
                { month: 'Mar', sales: 34, profit:0.45 },
                { month: 'Apr', sales: 32, profit:1.10 },
               // ...     
        ];
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
               $scope.datasource=chartData;
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img58.png)


## Scatter

To create a Scatter chart, you can set the series `e-type` as **"scatter"**’ in the chart series. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="scatter" ></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img59.png)


### Customize the scatter chart

You can change the scatter size by using the `e-size` property of the series marker. And you can change the scatter color by using the series `e-fill` property. 

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="scatter" e-marker-size-height="13" e-marker-size-width="13" 
        e-fill="#41F282"></e-series>
        </e-series>
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img60.png)


## HiLoOpenClose Chart 

To create a HiLoOpenClose chart, you can set the series `e-type` as **"hiloopenclose"** in the chart series. HiLoOpenClose chart requires 5 fields (`e-x`,`e-high`, `e-low`], `e-open` and `e-close`) to plot a segment.  


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="hiloopenclose" e-datasource="datasource" e-xname="month" e-high="high" 
        e-low="low" e-open="open" e-close="close" ></e-series>
        </e-series>
        </div>
        <script>
         var chartData = [
            { month: 'Jan', high: 38, low: 10, open: 38, close: 29 },
            { month: 'Feb', high: 28, low: 15, open: 18, close: 27  },
            { month: 'Mar', high: 54, low: 35, open: 38, close: 49  },
            { month: 'Apr', high: 52, low: 21, open: 35, close: 29  },
            // ...    
         ];
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                    $scope.datasource=chartData;
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img61.png)


### DrawMode

You can change the HiLoOpenClose chart `e-drawMode` to `open`, `close` or *both*. The default value of `e-drawMode` is **"both"**. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="hiloopenclose" e-drawmode="open" ></e-series>
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                    });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img62.png)


### Bull and Bear Color	

HiLoOpenClose chart `e-bullFillColor` is used to specify a fill color for the segments that indicates an increase in stock price in the measured time interval and `e-bearFillColor` is used to specify a fill color for the segments that indicates a decrease in the stock price in the measured time interval. 

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="hiloopenclose" e-bullfillcolor="#FF6600" e-bearfillcolor="#336600">
        </e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img63.png)


## Candle

You can create a Candle chart by specifying the series `e-type` as **"candle"** in the chart series. Candle chart requires 5 fields (`e-x`, `e-high`, `e-low`, `e-open` and `e-close`) to plot a segment.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="candle" e-datasource="datasource" e-xname="month" e-high="high" 
         e-low="low" e-open="open" e-close="close" ></e-series>
         </e-series>
        </div>
        <script>
         var chartData = [
            { month: 'Jan', high: 38, low: 10, open: 38, close: 29 },
            { month: 'Feb', high: 28, low: 15, open: 18, close: 27  },
            { month: 'Mar', high: 54, low: 35, open: 38, close: 49  },
            { month: 'Apr', high: 52, low: 21, open: 35, close: 29  },
            // ...    
         ];
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                    $scope.datasource=chartData;
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img64.png)


### Bull and Bear Color

Candle chart `e-bullFillColor` is used to specify a fill color for the segments that indicates an increase in the stock price in the measured time interval and `e-bearFillColor` is used to specify a fill color for the segments that indicates a decrease in the stock price in the measured time interval.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="candle" e-bullfillcolor="#FF6600" e-bearfillcolor="#336600"></e-series>
        </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img65.png)


## HiLo

HiLo chart is created by setting the series `e-type` as **"hilo"** in the chart series. HiLo chart requires 3 fields (`e-x`, `e-high` and `e-low`) to plot a segment.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="high" e-datasource="datasource" e-xname="month" e-high="high" 
        e-low="low"></e-series>
        </e-series>
        </div>
        <script>
         var chartData = [
              { month: 'Jan', high: 38, low: 34 },
              { month: 'Feb', high: 28, low: 15 },
              { month: 'Mar', high: 54, low: 45 },
              { month: 'Apr', high: 32, low: 21 },
              // ...      
         ];
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                    $scope.datasource=chartData;
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img66.png)


## Polar

Polar chart is created by setting the series `e-type` as **polar** in the chart series. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="polar"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html> 


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img67.png)


### DrawType

Polar `e-drawType`property is used to change the series plotting type to *line*, *column* or *area*. The default value of `e-drawType` is **"line"**.  

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="polar" e-drawtype="column"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img68.png)


### Stack columns in Polar chart

By using the `e-isStacking` property, you can specify whether the column has to be stacked when the `e-drawType` is column. Its default value is **false**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="polar" e-isstacking="true"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img69.png)


## Radar Chart  

To create a Radar chart, you can specify the series `e-type` as **"radar"** in the chart series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="radar" ></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img70.png)


### DrawType

Radar `e-drawType` property is used to change the series plotting type to *line*, *column* or *area*. The default value of `e-drawType` is **"line"**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="radar" e-drawtype="column"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img71.png)


### Stack columns in Radar chart

By using the `e-isStacking` property, you can specify whether the column has to be stacked when the `e-drawType` is set as *column*. Its default value is set to **false**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="radar" e-isstacking="true"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>

{% endhighlight %}


![](Chart-Types_images/Chart-Types_img72.png)


## Waterfall Chart 

For rendering a Waterfall chart, set series `e-type` as **"waterfall"** in the chart series. To change the waterfall series segment color use `e-fill` option of series and use [`positiveFill`](../api/ejchart.html#members:series-positiveFill) property to differentiate the positive segments.

N> The inline property of the **series.positiveFill** has the first priority and override the **series.fill**.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-type="waterfall" e-fill="#C64E4A" e-positivefill="#C64E4A"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>


{% endhighlight %}


![](Chart-Types_images/Chart-Types_img73.png)


**ShowIntermediateSum**

To display the summary of values since the last intermediate point of the waterfall series, set **showIntermediateSum** property as true in the specific point.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-points>
        <e-points e-x="Intermediate sum" e-showIntermediateSum= "true"></e-points>
        <e-points>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                    });
        </script>
    </body>
</html>


{% endhighlight %}


**ShowTotalSum**

The sum of all previous point in the waterfall series is displayed on enabling the **showTotalSum** property for a specific point.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-points>
        <e-points e-x="Total sum" e-showtotalSum= "true"></e-points>
        <e-points>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>
{% endhighlight %}


### ConnectorLine

To customize the connector line color, width, opacity and dashArray of the waterfall series, you can use `e-connectorLine` option of series.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-connectorline-color="#333000" e-connectorline-width="1" e-connectorline-opacity="1" 
        e-connectorline-dasharray="3,2"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                           });
        </script>
    </body>
</html>
{% endhighlight %}


![](Chart-Types_images/Chart-Types_img74.png)


## Error bar Chart 

EjChart can generate Error bar for Cartesian type series *(Line, Column, Bar, Scatter, Area, Candle, HiLo, etc.)*. To render the Error bar for the series, set `e-visibility` as *"visible"* to `e-errorBar` in the series.


{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-errorbar-visibility="visible"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                  });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img75.png)

### Changing Error Bar Type

You can change the error bar rendering type using `e-type` *(like fixedValue, percentage, standardDeviation, standardError and custom)* option of errorBar. To change the error bar line length you can use `e-verticalErrorValue` property.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-errorbar-type="percentage" e-errorbar-verticalerrorvalue="3"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
               });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img76.png)


#### Customizing error bar type              

To customize the error bar type, set error bar `e-type` as **"custom"** and then change the horizontal/vertical positive and negative value of error bar.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-errorbar-type="custom" e-errorbar-verticalPositiveErrorValue="5"
                   e-errorbar-horizontalPositiveErrorValue="1"
                   e-errorbar-verticalNegativeErrorValue="3"
                   e-errorbar-horizontalNegativeErrorValue="1"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
               });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img77.png)


### Changing Error Bar Mode

Error bar mode is used to define whether the error bar line has to be drawn *horizontally, vertically* or in *both* side.  To change the error bar mode use `e-errorBar-mode` option.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-errorbar-type="fixedValue" e-errorbar-mode="vertical"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
               });
        </script>
    </body>
</html>



{% endhighlight %}

![](Chart-Types_images/Chart-Types_img78.png)


### Changing Error Bar Direction

You can change the error bar direction to plus, minus or both side using `e-errorBar-direction` option.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-errorbar-type="fixedvalue"  e-errorbar-mode="vertical"
                   e-errorbar-direction="minus"></e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
               });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img79.png)


### Customizing Error bar cap

To customize the error bar cap *visibility, length, width* and *fill* color, you can use `e-cap` option in the **series.errorBar**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-series>
        <e-series  e-errorbar-cap-visible="true" e-errorbar-cap-length="20"
                   e-errorbar-cap-width="1" e-errorbar-fill="#000000">
        </e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
               });
        </script>
    </body>
</html>
 
{% endhighlight %}

![](Chart-Types_images/Chart-Types_img80.png)

## Box and Whisker Chart 

To render a Box and Whisker Chart, set the series `e-type` as **"boxandwhisker"** in the chart series. Box and Whisker chart requires
2 fields (x and y) to plot a segment. The feild y requires n number of data or it should  contain minimum five values to plot a segment.

{% highlight html %}


<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
<head>
    <title>Essential Studio for AngularJS: Chart</title>
    <!--CSS and Script file References -->
</head>
<body ng-controller="ChartCtrl">
    <div id="container" ej-chart>
        <e-series>
            <e-series e-type="boxandwhisker" e-datasource="datasource" e-xname="x" e-yname="y"></e-series>
        </e-series>
    </div>
    <script>
        var chartData = [
             { x: 'Development',        
               y:[22,22,23,25,25,25,26,27,27,28,28,29,30,32,34,32,34,36,35,38] },
             { x: 'Testing', y: [22,33,23,25,26,28,29,30,34,33,32,31,50] },
             { x: 'HR', y: [22,24,25,30,32,34,36,38,39,41,35,36,40,56] },
             { x: 'Finance', y: [26,27,28,30,32,34,35,37,35,37,45] },
             { x: 'R&D', y: [26, 27, 29, 32, 34, 35, 36, 37, 38, 39, 41, 43, 58] },
             // ...
        ];
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
            $scope.datasource = chartData;
        });
    </script>
</body>
</html>


{% endhighlight %}

![](=Chart-Types_images/Chart-Types_img90.png)

### BoxPlotMode

You can change the rendering mode of the  Box and Whisker series using the `e-boxplotmode` property. The default value of `e-boxplotmode` is **"exclusive"**.The other boxPlotModes available are `inclusive` and `normal`. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
<head>
    <title>Essential Studio for AngularJS: Chart</title>
    <!--CSS and Script file References -->
</head>
<body ng-controller="ChartCtrl">
    <div id="container" ej-chart>
        <e-series>
            <e-series e-boxplotmode="inclusive"></e-series>
        </e-series>
    </div>
    <script>
       // Add the dataSource
      //… 
    </script>
</body>
</html>

{% endhighlight %}

### ShowMedian

Box and Whisker `e-showMedian` property is used to show the box and whisker average value. The default value of `e-showmedian` is **"false"**.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
<head>
    <title>Essential Studio for AngularJS: Chart</title>
    <!--CSS and Script file References -->
</head>
<body ng-controller="ChartCtrl">
    <div id="container" ej-chart>
        <e-series>
            <e-series e-showMedian="true"></e-series>
        </e-series>
    </div>
    <script>
       // Add the dataSource
      //… 
    </script>
</body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img91.png)

###  Customize the Outlier

Outlier symbol, width and height can be customized using outlierSettings through `e-outliersettings` property. By default Outlier symbol is displayed as circle with a height and width of 6 pixels.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
<head>
    <title>Essential Studio for AngularJS: Chart</title>
    <!--CSS and Script file References -->
</head>
<body ng-controller="ChartCtrl">
    <div id="container" ej-chart>
        <e-series e-outlierSettings-shape="triangle"
                  e-outlierSettings-size-height="10"
                  e-outlierSettings-size-width="10">
        </e-series>    </div>
    <script>
       // Add the dataSource
      //… 
    </script>
</body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img92.png)

[Click](http://ngjq.syncfusion.com/#/chart/boxandwhisker) here to view the Box and Whisker Chart online demo sample.

## Pie Of Pie Chart

To render the pie of pie chart, set the series `e-type` as **pieofpie**. Pie of pie chart is used for displaying the data of a pie slice as another pie chart. The values in the second pie is displayed based on the **e-splitMode**  property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-series e-type="pieofpie" e-splitvalue="10" >
        <e-points>
        <e-points e-x="Saudi Arabia" e-y="58" e-text="58%"></e-points>
         <e-points e-x="Persian Gulf" e-y="15" e-text="15%"></e-points>
         <e-points e-x="Canada" e-y="13" e-text="13%"></e-points>
         <e-points e-x="Venezula" e-y="8" e-text="8%"></e-points>
         <e-points e-x="Mexico" e-y="3" e-text="3%"></e-points>
         <e-points e-x="Russia" e-y="2" e-text="2%"></e-points>
           <e-points e-x="Miscellaneous" e-y="1" e-text="1%"></e-points>
        </e-points>
        </e-series>
        </e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img93.png)

[Click](http://ngjq.syncfusion.com/#/chart/pieofpie) here to view the Pie Of Pie Chart online demo sample.

### Split Mode and Split Value 

The points to be displayed in the second pie is decided based on the `e-splitMode`property.**SplitMode** property takes the following values. 
* Position – Have to split the data points based on its position
* Value – Have to split the data points based on its Y value
* Percentage – Have to split the points based on the percentage value
* Indexes – The data points with the specified indexes are split separately 
 By default, the splitMode is set to  **Value**. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
<head>
    <title>Essential Studio for AngularJS: Chart</title>
    <!--CSS and Script file References -->
</head>
<body ng-controller="ChartCtrl">
    <div id="container" ej-chart>
        <e-series e-splitmode="position" e-splitvalue="3">
        </e-series>   
         </div>
   
</body>
</html>

{% endhighlight %}

![](Chart-Types_images/Chart-Types_img94.png)

### Changing Pie Of Pie Size

The size of the second Pie can be customized by using the `e-pieOfPieCoefficient` property. The default value of pieOfPieCoefficient is **0.6**.Its value ranges from 0 to 1.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
<head>
    <title>Essential Studio for AngularJS: Chart</title>
    <!--CSS and Script file References -->
</head>
<body ng-controller="ChartCtrl">
    <div id="container" ej-chart>
        <e-series e-pieofpiecoefficient="1" >
        </e-series>   
         </div>
   
</body>
</html>

{% endhighlight %}

The following screenshot represents the pie of pie series with pieOfPieCoefficient as 1

![](Chart-Types_images/Chart-Types_img95.png)

#### Customizing the Gap

The distance between the two pies in the pie of pie chart can be controlled by using the `e-gapWidth` property. The default value is **50**.

 {% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
<head>
    <title>Essential Studio for AngularJS: Chart</title>
    <!--CSS and Script file References -->
</head>
<body ng-controller="ChartCtrl">
    <div id="container" ej-chart>
        <e-series e-gapWidth="150" >
        </e-series>   
         </div>
   
</body>
</html>


{% endhighlight %}

![](Chart-Types_images/Chart-Types_img96.png)


