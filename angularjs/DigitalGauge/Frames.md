---
layout: post
title: Frames
description: frames
platform: Angular 1.0
control: Digital Gauge
documentation: ug
---

# Frames

## Inner and Outer Width Customization

**Frames** are space that enclose the **Digital Gauge**. The inner width of the **Frame** is the distance between the canvas element and the frame. The outer width is the distance from the frame. The code example to set frame’s **innerWidth** and **outerWidth** is as follow.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="DigitalGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: DigitalGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="DigitalGaugeCtrl">
        <div id="digitalframe">
                 <ej-digitalgauge e-frame-innerwidth="6" e-frame-outerwidth="10" e-value="WELCOME">
                 </ej-digitalgauge>
        </div>
         <script>
        angular.module('DigitalGaugeApp', ['ejangular'])
        .controller('DigitalGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>



{% endhighlight %}



Execute the above code examples to render the **Digital****Gauge** as follows.

![](Frames_images/Frames_img1.png)



## Setting Background Image

For a better appearance, you can set the **background****image** for the **Digital Gauge** using the property **backgroundImageUrl.** 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="DigitalGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: DigitalGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="DigitalGaugeCtrl">
        <div id="digitalframe">
                 <ej-digitalgauge e-frame-backgroundimageurl="board3.jpg"  e-value="RADAR"
                 e-height="300">
                 <e-items>
                 <e-item e-position-x="95" e-position-y="10">
                 </e-item>
                 </e-items>
                 </ej-digitalgauge>
        </div>
        <script>
        angular.module('DigitalGaugeApp', ['ejangular'])
        .controller('DigitalGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>


{% endhighlight %}



Execute the above code examples to render the **Digital****Gauge** as follows.

![](Frames_images/Frames_img2.png)

