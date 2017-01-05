---
layout: post
title: Ranges-and-Frames
description: ranges and frames
platform: Angualr 1.0
control: Circular Gauge
documentation: ug
---

# Ranges and Frames

Ranges are used to specify or group the scale values. By using ranges, you can describe the values in the pointers. 

## Adding Range Collection

Range collection is directly added to the scale object. Refer the following code example to add range collection in a **Gauge** control. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="circularframe">
                 <ej-circulargauge >
                 <e-scales>
                 <e-scale >
                 <e-ranges>
                 <e-range e-startValue="20" e-endValue="80"></e-range>
                 </e-ranges>
                 </e-scale>
                 <e-scales> 
                </ej-circulargauge>
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>

{% endhighlight %}



## Range Customization

**Appearance**

The API **size** is used to specify the width of the ranges.  The major attributes for ranges are **startValue** and **endValue**. **startValue** defines the start position of the ranges and **endValue** defines the end position of the ranges.

**StartWidth** and **endWidth** are used to specify the range width at the starting and ending position of the ranges. You can add the gradient effects to the ranges by using **gradient** object.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="circularframe">
                 <ej-circulargauge >
                 <e-scales>
                 <e-scale e-showRanges="true" e-showScaleBar="true" e-radius="150" e-size="2">
                 <e-ranges>
                 <e-range e-startValue="20" e-endValue="80" e-backgroundColor="green"></e-range>
                 </e-ranges>
                 </e-scale>
                 <e-scales> 
                </ej-circulargauge>
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>


{% endhighlight %}



Execute the above code to render the following output.

![](Ranges-and-Frames_images/Ranges-and-Frames_img1.png)

## Colors and Border

By customizing the ranges, the appearance of the **Gauge** can be improved. The range border is modified with the object called **border**. It has two border property such as **color** and **width.** These are used to customize the border color of the ranges and border width of the ranges. 

You can set the background color to improve the look and feel of the **Circular Gauge**. For customizing the background color of the ranges, **backgroundColor** is used.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="circularframe">
                 <ej-circulargauge >
                 <e-scales>
                 <e-scale e-showRanges="true" e-showScaleBar="true" e-radius="150" e-size="2">
                 <e-ranges>
                 <e-range e-startValue="20" e-endValue="80" e-backgroundColor="yellow" 
                 e-border-color="green" e-border-width="2"></e-range>
                 </e-ranges>
                 </e-scale>
                 <e-scales> 
                 </ej-circulargauge>
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>


{% endhighlight %}



Execute the above code to render the following output.

![](Ranges-and-Frames_images/Ranges-and-Frames_img2.png)

## Positioning the ranges

You can position ranges using two properties such as **distanceFromScale** and **placement**. **distanceFromScale** property defines the distance between the scale and range. **Placement** property is used to locate the pointer with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="circularframe">
                 <ej-circulargauge >
                 <e-scales>
                 <e-scale e-showRanges="true" e-showScaleBar="true" e-radius="150" e-size="2">
                 <e-ranges>
                 <e-range e-startValue="0" e-endValue="100" e-backgroundColor="green"
                 e-border-color="black" e-border-width="2" e-placement="far"
                 e-distanceFromScale="-30"></e-range>
                 </e-ranges>
                 </e-scale>
                 <e-scales> 
                 </ej-circulargauge>
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>

{% endhighlight %}



Execute the above code to render the following output.

![](Ranges-and-Frames_images/Ranges-and-Frames_img3.png)

## Multiple Ranges

You can set multiple ranges by adding an array of ranges objects. Refer the following code example for multiple ranges functionality.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="circularframe">
                 <ej-circulargauge >
                 <e-scales>
                 <e-scale e-showRanges="true" e-showScaleBar="true" e-radius="150" e-size="2">
                 <e-pointers>
                 <e-pointer e-value="40" e-showbackneedle="true" e-length="100">
                 </e-pointers>
                 <e-ranges>
                 <e-range e-startValue="0" e-endValue="50" e-backgroundColor="green"  e-placement="far"
                 e-distanceFromScale="-30"></e-range>
                 <e-range e-startValue="50" e-endValue="80" e-backgroundColor="yellow"  e-placement="far"
                 e-distanceFromScale="-30"></e-range>
                 <e-range e-startValue="80" e-endValue="100" e-backgroundColor="red"  e-placement="far"
                 e-distanceFromScale="-30"></e-range>
                 </e-ranges>
                 </e-scale>
                 <e-scales> 
                 </ej-circulargauge>
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>


{% endhighlight %}



Execute the above code to render the following output.

![](Ranges-and-Frames_images/Ranges-and-Frames_img4.png)

## Frames

Frame is the element that decides the appearance of the **Circular Gauge**. You can customize it using the object called **frame**.  It has the properties such as frameType, backGroundUrl, halfCircleFrameStartAngle and halfCircleFrameEndAngle.

**frameType** is used to specify whether frame is a half circle frame or full circle frame. **halfCircleFrameStartAngle** and **halfCircleFrameEndAngle** are used to specify the angle for **Gauge** with frame type as half circle. **backgroundUrl** is used to set the background image for the frame.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="CircularGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: CircularGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="CircularGaugeCtrl">
        <div id="circularframe">
                <ej-circulargauge  e-frame-frameType="halfcircle" e-halfCircleFrameStartAngle="205" 
                e-halfCircleFrameEndAngle="335" e-pointercap-radius="50"
                e-backgroundColor="#FFCCCC">
                <e-scales>
                <e-scale  e-startangle="180" e-sweepangle="180">
                <e-pointers>
                <e-pointer e-type="needle" e-needletype="rectangle" e-width="1" e-value="40"
                e-length="120">
                </e-pointer>
                </e-pointers>
                </e-scale>
                <e-scales> 
                </ej-circulargauge>
        </div>
        <script>
        angular.module('CircularGaugeApp', ['ejangular'])
        .controller('CircularGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>

{% endhighlight %}



Execute the above code to render the following output.

![](Ranges-and-Frames_images/Ranges-and-Frames_img5.png)

