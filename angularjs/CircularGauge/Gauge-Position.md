---
layout: post
title: Gauge-Position
description: gauge position
platform: AngularJS
control: Circular Gauge
documentation: ug
---

# Gauge Position

**Semi-circular Gauge** can be positioned within the canvas element which provides better appearance for the gauge in the canvas.

**Positioning**

Semi-circular Gauge can be positioned with the help of the attribute called gaugePosition. It is an enumerable value. You can position the gauge away from the corner with the help of the distanceFromCorner attribute. 

The possible enum values for the gaugePosition are as follows:

* TopLeft

* TopCenter

* TopRight

* MiddleLeft

* Center

* MiddleRight

* BottomLeft

* BottomCenter

* BottomRight

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="circularframe"> 
        <ej-circulargauge e-backgroundcolor="transparent" e-width="800" e-height="500" e-radius="120" e-value="60"
        e-gaugePosition="center" e-distanceFromCorner="30" e-frame-frameType="HalfCircle" 
        e-frame-halfCircleFrameStartAngle="270" e-frame-halfCircleFrameEndAngle="90">
        <e-scales>
           <e-scale e-startangle="270" e-sweepangle="180" e-radius="160" e-showscalebar="true" e-size="1"
           e-maximum="120" e-majorIntervalValue="20" e-minorintervalvalue="10" e-border-width="0.5">
           </e-scale>
           <e-scales> 
        </ej-circulargauge>
        </div>
        <script >
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>

{% endhighlight %}



Execute the above code to render the following output.

![](Gauge-Position_images/Gauge-Position_img1.png)

