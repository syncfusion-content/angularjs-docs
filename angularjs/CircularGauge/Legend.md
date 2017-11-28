---
layout: post
title: Legend
description: legend for the ranges in circular gauge
platform: AngularJS
control: Circular Gauge
documentation: ug
---
# Legend

The legend contains the list of the ranges that appear in the circular gauge  

## Legend Visibility

By default, the legend  the legend will not be displayed in the circular gauge. You can enable or disable it by using the **visible** property of the e-legend.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS:CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CirculargaugeCtrl">
        <div id="container" ej-circulargauge e-legend-visible="true">
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                     });
        </script>
    </body>
</html>

{% endhighlight %}

![](Legend_images/Legend_img1.png)


[Click](http://ngjq.syncfusion.com/#/circulargauge/legend) here to view the online demo sample for legend .

### Legend Text

The text displayed in the legend can be customized by using the `e-legendText` property present in the `e-ranges` of the circular gauge. When the legendText is not specified in the ranges, then the legend item for that particular range will not displayed. By default the legendText value is null . 


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge>
        <e-scales>
        <e-scale>
        <e-ranges>
        <e-range e-legendText="Light Air"></e-range>
        </e-scales>
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                     });
        </script>
    </body>
</html>

{% endhighlight %}


## Position and Align the Legend

By using the `e-legend-position` property, you can position the legend at *left*, *right*, *top* or *bottom* of the CircularGauge. The legend is positioned at the **bottom** of the circular gauge, by default.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legend-position="top">
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                     });
        </script>
    </body>
</html>
{% endhighlight  %}


![](Legend_images/Legend_img2.png)

### Legend Alignment

You can align the legend to the *center*, *far* or *near* based on its position by using the `e-legend-alignment` property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legend-position="top" e-legend-alignment="far">
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                     });
        </script>
    </body>
</html>

{% endhighlight %}

![](Legend_images/Legend_img3.png)

## Customization

### Legend Fill and Opacity

You can change the opacity and fill color of legend text using `Opacity` and `Fill` property of legend. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legend-fill="red" e-legend-opacity="0.5">
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                     });
        </script>
    </body>
</html>

{% endhighlight %}


### Legend shape

To change the legend item, shape, you have to specify the desired shape in the `e-legend-shape` property of the legend. By default the legend shape is **circle**.It also supports rectangle,diamond,triangle,slider,line,pentagon,trapezoid and wedge shapes.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legend-shape="slider">
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                     });
        </script>
    </body>
</html>

{% endhighlight %}

![](Legend_images/Legend_img4.png)


### Legend Item Size and Border

You can change the size of the legend items by using the `width` and `height` properties in the `e-legend-itemStyle`. To change the legend item border, use `border` property of the legend itemStyle.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legend-itemStyle-width="13"
        e-legend-itemStyle-height="13" e-legend-itemStyle-border-color="#FF0000"
        e-legend-itemStyle-border-width="2">
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {    
                     });
        </script>
    </body>
</html>


{% endhighlight %}

![](Legend_images/Legend_img5.png)

### Legend size

You can change the default legend size by using the `e-legend-size` property of the legend.  

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legend-size-width="350px" e-legend-size-height="100px">
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {                  
                     });
        </script>
    </body>
</html>

{% endhighlight %}

![](Legend_images/Legend_img6.png)


### Legend Item Padding

You can control the spacing between the legend items by using the `e-legend-itemPadding` option of the legend.  The default value is 20. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legend-itempadding="30">
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                     });
        </script>
    </body>
</html>



{% endhighlight %}

![](Legend_images/Legend_img7.png)

### Legend border

You can customize the legend border by using the `e-legend-border` option in the legend. 

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legend-border-color="#FFC342" e-legend-border-width="2">
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                    });
        </script>
    </body>
</html>


{% endhighlight %}

![](Legend_images/Legend_img8.png)

### Font of the legend text

The font of the legend item text can be customized by using the `e-legend-font` property in legend.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legend-font-fontFamily="Segoe UI"
        e-legend-font-fontStyle="normal" e-legend-font-fontWeight="bold" e-legend-font-size="15px" >
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                    });
        </script>
    </body>
</html>


{% endhighlight %}

![](Legend_images/Legend_img9.png)

## Events

### Legend Item Render

`e-legendItemRender` event triggers before rendering the legend items. This event is triggered for each legend item in Circular gauge. You can use this event to customize legend item shape or add custom text to legend item.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legenditemrender=onLegendRender>
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                    $scope.onLegendRender="onLegendRender";
                    });
        function onLegendRender(sender) {
        //Get legend item details on legend item click.
        var legendItem = sender.data;
        }
        </script>
    </body>
</html>   

{% endhighlight %}

### Legend Item Click

You can get the legend item details such as *RangeIndex*, *bounds*, *shape* and *series* by subscribing the `e-legendItemClick` event on the circular gauge. When the legend item is clicked, it triggers the event and returns the legend information. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="container" ej-circulargauge e-legendItemClick=onLegendClicked>
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
                    $scope.onLegendClicked="onLegendClicked";
                    });
        function onLegendClicked(sender) {
        //Get legend item details on legend item click.
        var legendItem = sender.data;
        }
        </script>
    </body>
</html>   

{% endhighlight %}


