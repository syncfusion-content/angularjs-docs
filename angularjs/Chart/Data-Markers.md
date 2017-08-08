---
layout: post
title: Markers and data labels in Essential Javascript Chart
description: Learn how to add markers and data point labels to a Chart series.
platform: AngularJS
control: Chart
documentation: ug
---

# Data Markers

Data markers are used to provide information about the data point to the user. You can add a shape and label to adorn each data point.

## Add Shapes

You can add shapes to any chart types but they are often used with line, area and spline series to indicate each data point. It is highlighted when you hover the mouse on the shape.

Shapes can be added to the chart by enabling the `visible` option of the `e-marker` property. There are different shapes you can add to the chart by using the shape option such as rectangle, circle, diamond etc.

The following code example explains on how to enable series marker and add shapes,

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-visible="true" e-marker-shape="diamond">
         </e-series>
         <e-series e-marker-visible="true" e-marker-shape="triangle" >
         </e-series>
         <e-series e-marker-visible="true" e-marker-shape="Hexagon">
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

![](Data-Markers_images/Data-Markers_img1.png)



## Add image as marker

Apart from the shapes, you can also add images to mark the data point by using the `imageUrl` option.

The following code example illustrates this,

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-visible="true" e-marker-shape="image"
         e-marker-imageurl="sun_annotation.png" e-marker-size-height="20"
         e-marker-size-width="20">
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

![](Data-Markers_images/Data-Markers_img2.png)


## Add labels

Data label can be added to a chart series by enabling the `visible` property in the `dataLabel` option. The labels appear at the top of the data point, by default.

The following code example shows how to enable data label and set its horizontal and vertical text alignment. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-datalabel-visible="true" 
         e-marker-datalabel-horizontaltextalignment="center"
         e-marker-datalabel-verticaltextalignment="far">
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

![](Data-Markers_images/Data-Markers_img3.png)


Label content can be formatted by using the template option. Inside the template, you can add the placeholder text *"point.x"* and *"point.y"* to display corresponding data points x & y value.

You can adorn the labels with background shapes by setting *shape* option.

The following code example shows how to add background shapes and set template to data label.

{% highlight html %}


<div id="template">
<div id="left">
<img src="../images/chart/icon_investments.png"/>
</div>
<div id="right">
<div id="point">#point.y#%</div>
</div>
</div>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-datalabel-visible="true"
         e-marker-datalabel-template="template"></e-series>
         <e-series e-marker-datalabel-visible="true"
         e-marker-datalabel-shape="rectangle" 
         e-marker-datalabel-border-width="1"
         e-marker-datalabel-border-color="red"></e-series>
         <e-series e-marker-datalabel-visible="true"></e-series>
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

![](Data-Markers_images/Data-Markers_img4.png)


The appearance of the labels can be customized by using the `font` and `offset` options. The `offset` option is used to move the labels vertically. Also, labels can be rotated by using the `rotate` option.

The following code example shows how to rotate datalabel text and customize the font.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-datalabel-visible="true"
         e-marker-datalabel-angle="30" e-marker-datalabel-offset="15"
         e-marker-datalabel-font-color="black" e-marker-datalabel-font-size="13px">
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

![](Data-Markers_images/Data-Markers_img5.png)


You can position the label to the top, center or bottom position of the segment by using the `textPosition` option for the chart types such as column, bar, stacked bar, stacked column, 100% stacked bar, 100% stacked column, candle and OHLC.

The following code example shows how to set textPosition to display data label in the middle of the column rectangle.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-datalabel-visible="true"
         e-marker-datalabel-textposition="middle">
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

![](Data-Markers_images/Data-Markers_img6.png)


The label can be positioned inside or outside the perimeter of the series by using the `e-labelPosition` option for the chart types such as Pie and Doughnut, .

The following code example shows how to set the *labelPosition*,

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-datalabel-visible="true" e-marker-datalabel-shape="rectangle"
         e-marker-datalabel-font-color="white" e-type="doughnut" e-labelPosition="outside" 
         e-datasource="dataSource" e-xname="x" e-yname="y" e-textmappingname="text">
         </e-series>
         </div>
         <script>
         var chartData= [{ x: 'India', y: 24, text: 'India 24%' },
                        { x: 'Japan', y: 25, text: 'Japan 25%' },
                        { x: 'Australia', y: 20, text: 'Australia 20%' },
                        { x: 'USA', y: 35, text: 'USA 35%' },
                        { x: 'China', y: 23, text: 'China 23%' },
                        { x: 'Germany', y: 27, text: 'Germany 27%' },
                        { x: 'France', y: 22, text: 'France 22%' }];
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                    $scope.dataSource=chartData;
              
                });
        </script>
    </body>
</html>

{% endhighlight %} 

![](Data-Markers_images/Data-Markers_img7.png)


The following screenshot displays the labels when the `e-labelPosition` is set as *inside* position.

![](Data-Markers_images/Data-Markers_img8.png)


The following screenshot displays the labels when the `e-labelPosition` is set as *outsideExtended* position.

![](Data-Markers_images/Data-Markers_img9.png)


The label can be wrapped for pie, doughnut, funnel, and pyramid series by setting the enableWrap property. 

{% highlight html %} 

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-datalabel-visible="true"
         e-marker-datalabel-enablewrap="true" 
         e-marker-datalabel-maximumlabelwidth="32">
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

![](Data-Markers_images/Data-Markers_img13.png)

## Contrast Color for the data label

 
To change the contrast color for the data label, you can set the `e-enableContrastColor` as **true** in the dataLabel property of the chart series.

When we enable this property, the data label text will be rendered in contrast color based on the segment on which it is placed.
If the data label is placed inside the data points segment, then that particular point's color is taken. Else the chart area or chart background color is considered for deriving the contrast color.

{% highlight html %} 

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-datalabel-visible="true"
         e-marker-datalabel-enablecontrastcolor="true">
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



## Customize specific points

By using the ejChart, you can also customize the individual/specific markers with different colors, shapes and also with different images.

There are two ways to achieve this based on how the data is fed to the series.

When the data is provided by using the `e-points` option, you can add marker for each data point or specific point by using the `e-marker` option as illustrated in the following code example.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-series>
        <e-series>
        <e-points>
        <e-points e-x="Jan" e-y="35"></e-points>
        <e-points e-x="Feb" e-y="28"></e-points>
        <e-points e-x="Mar" e-y="34"></e-points>
        <e-points e-x="Apr" e-y="32"></e-points>
        <e-points e-x="May" e-y="40"></e-points>
        <e-points e-x="Jun" e-y="33"></e-points>
        <e-points e-x="Jul" e-y="35"></e-points>
        <e-points e-x="Aug" e-y="55" e-marker-datalabel-visible="true"
        e-marker-datalabel-offset="-10"
        e-marker-datalabel-shape="upArrow" e-marker-datalabel-font-color="white"
        e-marker-datalabel-font-size="11px" e-marker-datalabel-margin-left="15"
        e-marker-datalabel-margin-right="15" e-marker-datalabel-margin-top="10"
        e-marker-datalabel-margin-bottom="10" e-marker-datalabel-fill="green" ></e-points>
        <e-points e-x="Sep" e-y="38"></e-points>
        <e-points e-x="Oct" e-y="30"></e-points>
        <e-points e-x="Nov" e-y="25" e-marker-datalabel-visible="true"
        e-marker-datalabel-offset="-22" e-marker-datalabel-verticaltextalignment="near"
        e-marker-datalabel-shape="downArrow" e-marker-datalabel-font-color="white"
        e-marker-datalabel-font-size="11px" e-marker-datalabel-margin-left="15"
        e-marker-datalabel-margin-right="15" e-marker-datalabel-margin-top="10"
        e-marker-datalabel-margin-bottom="10" e-marker-datalabel-fill="red"></e-points>
        <e-points e-x="Dec" e-y="32"></e-points>        
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

![](Data-Markers_images/Data-Markers_img10.png)

When the data is bound to the series by using the `e-dataSource` option, you can customize the points in the `e-seriesrendering` event as illustrated in the following code example,

{% highlight html %}
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart e-seriesrendering=seriesrender>
         <e-series>
         <e-series e-marker-datalabel-visible="true"  e-datasource="dataSource" e-xname="month" 
         e-yname="sales">
         </e-series>
         </div>
         <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                    $scope.dataSource=chartData;
                    $scope.seriesrender="seriesrender";
                   });
         function seriesRender(sender)
            {
	                   //Enable and customize the dataLabel for a point using event
               sender.data.series.points[7].marker = {
               dataLabel: {
                    visible: true,
                    offset: -10,
                    shape: "upArrow", font: { color: "white", size: '11px' },
                    margin: { left: 15, right: 15, top: 10, bottom: 10 },                    
                    fill: "green"
               }};
               sender.data.series.points[10].marker = {
                 //Enable and customize the dataLabel for a point using event
               dataLabel: {
                        visible: true,
                        offset: -22,
                        verticalTextAlignment: 'near',
                        shape: "downArrow", font: { color: "white", size: '11px' },
                        margin: { left: 15, right: 15, top: 10, bottom: 10 },                    
                        fill: "red"
               }};
        }
        </script>
    </body>
</html>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img10.png)


## Connect Line

This feature is used to connect label and data point by using a line. It can be enabled only for Pie, Doughnut, Pyramid and Funnel chart types. Connector line types can be set as *bezier* or *line* by using the `type` option.

 The following code example illustrates this,

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-datalabel-visible="true"
         e-marker-datalabel-connectorline-type="bezier"
         e-marker-datalabel-color="black"
         e-labelPosition="outsideextended" >
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

![](Data-Markers_images/Data-Markers_img11.png)


## Smart labels

Overlapping of the labels can be avoided by enabling the `e-enableSmartLabels` property. The default value is *true* for *accumulation type series* and *false* for *other series types*.

The following code example shows how to enable smart labels,

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart>
         <e-series>
         <e-series e-marker-datalabel-visible="true" e-marker-datalabel-shape="none"
         e-marker-datalabel-font-size="14px" e-marker-datalabel-connectorline-type="bezier"
         e-marker-datalabel-connectorline-color="black" e-type="pie" 
         e-labelPosition="outsideextended" e-enablesmartlabels="true" 
         e-datasource="dataSource" e-xname="x" e-yname="y" 
         e-textmappingname="text">
         </e-series>
         </div>
         <script>
         var chartData= [{ x: 'Other Personnal', y: 94658, text: 'Other Personal, 88.47%' },
                             { x: 'Medical care', y: 9090, text: 'Medical care, 8.49%' },
		                     { x: 'Housing', y: 2577, text: 'Housing, 2.40%' },
                             { x: 'Transportation', y: 473, text: 'Transportation, 0.44%' },
                             { x: 'Education', y: 120, text: 'Education, 0.11%' },
                             { x: 'Electronics', y: 70, text: 'Electronics, 0.06%' }];
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                    $scope.dataSource=chartData;
                     });
        </script>
    </body>
</html>



{% endhighlight %}

![](Data-Markers_images/Data-Markers_img12.png)


