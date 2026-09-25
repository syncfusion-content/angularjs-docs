---
layout: post
title: 3D Chart types available in Essential Javascript Chart
description: Learn here all about 3D chart support in Syncfusion AngularJS Chart control, its elements and more details.
platform: AngularJS
control: Chart
documentation: ug
---

# 3D Chart in AngularJS Chart

Essential 3D Chart for html allows you to view 8 chart types in 3D view such as `Bar`, `StackingBar`, `StackingBar100`, `Column`, `Stacked Column`, `100% Stacked Column`, `Pie`, `Doughnut`.


## 3D Column Chart

For rendering a 3D Column Chart, specify the series `e-type` as **"column"** in the chart series and set `e-enable3D` option as **true** in the chart.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true">
        <e-series>
        <e-series e-type="column"></e-series>
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


![3D column Chart fruits nutrients in AngularJS Chart](3D-Chart_images/3D-Chart_img1.png)


## 3D Bar Chart

You can create a 3D Bar Chart by setting the series `e-type` as **"bar"** in the chart series and enable `e-enable3D` option in the chart.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true">
        <e-series>
        <e-series e-type="bar"></e-series>
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


![3D Bar Chart employees in self insured plans in AngularJS Chart](3D-Chart_images/3D-Chart_img2.png)


## 3D Stacked Column Chart

Stacking Column 3DChart is rendered by specifying the series `e-type` as **"stackingColumn"** in the chart series and enable `e-enable3D` option in the chart.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true">
        <e-series>
        <e-series e-type="stackingcolumn"></e-series>
        <e-series e-type="stackingcolumn"></e-series>
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


![3D stacked column chart passenger car sales per year in AngularJS Chart](3D-Chart_images/3D-Chart_img3.png)


## 3D 100% Stacked Column Chart

100% Stacking Column 3DChart is rendered by specifying the series `e-type` as **"stackingColumn100"** in the chart series and enable `e-enable3D` option in the chart.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true">
        <e-series>
        <e-series e-type="stackingcolumn100"></e-series>
        <e-series e-type="stackingcolumn100"></e-series>
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


![Smartphone penetration in Asia per year in AngularJS Chart](3D-Chart_images/3D-Chart_img4.png)





## 3D Stacked Bar Chart

To create Stacking Bar 3DChart, set the series `e-type` as **"stackingBar"** in the chart series and enable `enable3D` option in the chart.

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true">
        <e-series>
        <e-series e-type="stackingbar"></e-series>
        <e-series e-type="stackingbar"></e-series>
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


![Real time bidding digital ad sales in AngularJS Chart](3D-Chart_images/3D-Chart_img5.png)


## 3D 100% Stacked Bar Chart

You can create 100% Stacking Bar 3DChart by setting the series `e-type` as **"stackingbar100"** in the chart series and enable `e-enable3D` option in chart.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true">
        <e-series>
        <e-series e-type="stackingbar100"></e-series>
        <e-series e-type="stackingbar100"></e-series>
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


![Money savings by year in AngularJS Chart](3D-Chart_images/3D-Chart_img6.png)


## 3D Pie Chart

To render the Pie Chart in 3D view, enable the **enbel3D** option in the chart and set the series `e-type` as **"pie"** in the chart series.  

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true">
        <e-series>
        <e-series e-type="pie"></e-series>
        <e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                      });
        </script>
    </body>
</html>

{% endhighlight %}


![Expenditure shares on a child from birth through 17 in AngularJS Chart](3D-Chart_images/3D-Chart_img7.png)




## 3D Doughnut Chart

To render the Doughnut Chart in 3D view, enable the **enbel3D** option in the chart and set the series `e-type` as **"doughnut"** in the chart series. 

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true">
        <e-series>
        <e-series e-type="doughnut"></e-series>
        <e-series>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                      });
        </script>
    </body>
</html>   


{% endhighlight %}


![People's hobbies in AngularJS Chart](3D-Chart_images/3D-Chart_img8.png)





## Configure 3D Chart

### 3D View

To render the EjChart in 3D view, set the `e-enable3D`option as *true* in the chart.
 
{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                      });
        </script>
    </body>
</html>   
     


{% endhighlight %}


![3D view fruits nutrients in AngularJS Chart](3D-Chart_images/3D-Chart_img9.png)


 
### Placing Bar / Column kind of series side-by-side
 
 The `e-sideBySideSeriesPlacement` defines the appearance of the different sets of data on the 3D Chart. When this property is enabled, the data is displayed side by side, otherwise it is displayed along the depth of the axis.  
 
{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true" e-sidebysideseriesplacement="true">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                      });
        </script>
    </body>
</html>   

{% endhighlight %}


![Placing bar fruits nutrients in AngularJS Chart](3D-Chart_images/3D-Chart_img10.png)


### Setting Axis Wall Size

In 3DChart, Cartesian axes lines are represented as walls and it defines the width of the 3D wall. 3D Pie and Doughnut Chart does not support `e-wallSize` because they don’t have axes.  

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true" e-wallsize="10">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                      });
        </script>
    </body>
</html>   
  

{% endhighlight %}


![3D chart fruits nutrients in AngularJS Chart](3D-Chart_images/3D-Chart_img11.png)


### 3D Depth

By using the `e-depth` property, you can view the 3D Chart from the front view of the series to the background wall.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true" e-depth="120">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                      });
        </script>
    </body>
</html>   
{% endhighlight %}


![3D depth fruits nutrients in AngularJS Chart](3D-Chart_images/3D-Chart_img12.png)


### Rotating and Tilting 3D Chart

To spin the 3D Chart on mouse dragging, enable `e-enableRotation` option in the chart. The `e-tilt` property specifies the angle of the slope of the 3D Chart. The positive and negative values are declared to the side where the slope is present. The `e-rotation` option is used to rotate the 3D chart towards left or right side of the chart. The direction of the chart depends upon the positive and negative values of the angle.  

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true" e-tilt="10" e-enablerotation="true" 
        e-rotation="40">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                      });
        </script>
    </body>
</html>   


{% endhighlight %}


![Rotating and tilting 3D chart fruits nutrients in AngularJS Chart](3D-Chart_images/3D-Chart_img13.png)


### PerspectiveAngle	

The `e-perspectiveAngle` specifies the appearance of the height, width, depth and wall of the 3D Chart. When the perspectiveAngle is decreased, the 3D object appears very close to the viewer. But when it is increased, the 3D object appears far away from the viewer.   

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-enable3d="true" e-perspectiveangle="150">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                      });
        </script>
    </body>
</html>   

{% endhighlight %}


![Perspective angle fruits nutrients in AngularJS Chart](3D-Chart_images/3D-Chart_img14.png)
