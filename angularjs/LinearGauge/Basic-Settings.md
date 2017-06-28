---
layout: post
title: Basic-Settings
description: basic settings
platform: AngularJS
control: Linear Gauge
documentation: ug
---

# Basic Settings

## Adding Dimension

* The basic customization for any control is setting the dimension. Here dimension refers the two major attributes, height and width. The height and width assigned in the control will render the canvas element in the given size. 

* The value attribute is used to set all pointer value in the Linear Gauge control. The attributes, minimum and maximum value are used to set the minimum value and maximum value for all the scales exist in the Linear Gauge control.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge e-width="300" e-height="500" e-minimum="10" e-maximum="110" e-value="78">
                 <e-scales>
                 <e-scale e-border-color="transparent" e-border-width="0" e-showMarkerPointers="false" 
                 e-showBarPointers="true" >
                 <e-barpointers>
                 <e-barpointer e-width="5" e-backgroundColor="grey">
                 </e-barpointer>
                 </e-barpointers>
                 <e-ticks>
                 <e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c" e-distancefromscale-x="7" 
                 e-distancefromscale-y="0"></e-tick>
                 <e-tick e-type="minorinterval" e-width="1" e-height="6" e-color="#8c8c8c" 
                 e-distancefromscale-x="7" e-distancefromscale-y="0"></e-tick>
                 </e-ticks>
                 </e-scale>
                 </e-scales>
                 </ej-lineargauge>
        </div>
        <script>
        angular.module('LinearGaugeApp', ['ejangular'])
        .controller('LinearGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>



{% endhighlight %}



Execute the above code to render the following output.



![](Basic-Settings_images/Basic-Settings_img1.png)



## Adding frame

* Frame is the element that decides the appearance of the **Linear Gauge**. You can customize it by using the object called **frame.** It contains frame inner width, frame outer width and frame background image URL properties. 

* The **innerWidth** of the frame defines the distance between the canvas element and the frame and the **outerWidth** refers to distance from the frame. **backgroundUrl** is used to set the background image for the frame.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge  e-value="80" e-frame-innerwidth="8" e-frame-outerwidth="10" 
                 e-frame-backgroundImageUrl="../images/gauge/Gauge_linear_light.png" >
                 <e-scales>
                 <e-scale e-border-color="transparent" e-border-width="0" e-backgroundColor="transparent" 
                 e-showMarkerPointers="false" e-showBarPointers="true" >
                 <e-barpointers>
                 <e-barpointer e-width="5" e-backgroundColor="grey">
                 </e-barpointer>
                 </e-barpointers>
                 <e-ticks>
                 <e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c" e-distancefromscale-x="7" 
                 e-distancefromscale-y="0"></e-tick>
                 <e-tick e-type="minorinterval" e-width="1" e-height="6" e-color="#8c8c8c" 
                 e-distancefromscale-x="7" e-distancefromscale-y="0"></e-tick>
                 </e-ticks>
                 </e-scale>
                 </e-scales>
                 </ej-lineargauge>
        </div>
        <script>
        angular.module('LinearGaugeApp', ['ejangular'])
        .controller('LinearGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>



{% endhighlight %}



Execute the above code to render the following output.



![](Basic-Settings_images/Basic-Settings_img2.png)



## Appearance

* The attribute orientation is used to render the Linear Gauges either in horizontal position or vertical position.You can set the background color for the Linear Gauge for better appearance using the backgroundColor property. borderColor specifies the border color of the Linear Gauge. You can also add gradient effects to Linear Gauge with the help of pointerGradient1 and pointerGradient2 attribute.

* Theme is the basic property of any control. It is used to set the theme for Linear Gauge. There are two types of themes used for Linear Gauge such as

 * flatlight

 * flatdark


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge  e-enableanimation="false" e-width="400" e-height="100" e-value="80" 
                 e-theme="flatlight" e-orientation="horizontal"
                 e-labelcolor="black" e-frame-backgroundImageUrl="../images/gauge/Gauge_linear_light.png">
                 <e-scales>
                 <e-scale e-border-color="transparent" e-direction="Clockwise" e-border-width="0" 
                 e-backgroundColor="transparent" e-showMarkerPointers="false" e-showBarPointers="true">
                 <e-barpointers>
                 <e-barpointer e-width="5" e-backgroundColor="grey">
                 </e-barpointer>
                 </e-barpointers>
                 <e-labels>
                 <e-label e-angle="90" e-distancefromscale-x="5" e-distancefromscale-y="-5">
                 </e-labels>
                 <e-ticks>
                 <e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c" e-distancefromscale-x="0" 
                 e-distancefromscale-y="0"></e-tick>
                 <e-tick e-type="minorinterval" e-width="1" e-height="6" e-color="#8c8c8c" 
                 e-distancefromscale-x="0" e-distancefromscale-y="0"></e-tick>
                 </e-ticks>
                 </e-scale>
                 </e-scales>
                 </ej-lineargauge>
        </div>
        <script>
        angular.module('LinearGaugeApp', ['ejangular'])
        .controller('LinearGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>


{% endhighlight %}



Execute the above code to render the following output.

![](Basic-Settings_images/Basic-Settings_img3.png)



## Responsive 

* For any display devices, the control is to be rendered based on the space in that device. The control must be responsive. For this purpose resizing property is present in **Linear Gauge** control. 

* The **Linear Gauge** renders with the specified value. When the browser changes its size, the canvas element checks the dimension with its parent element and if there are any changes in parent dimension, gauge control also changes the dimension based on its parent changes. You can enable this feature using **isResponsive** property**.**


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge  e-enableanimation="false" e-width="400" e-height="100" e-value="80" 
                 e-isresponsive="true" e-orientation="horizontal" e-labelcolor="black" 
                 e-frame-backgroundImageUrl="../images/gauge/Gauge_linear_light.png">
                 <e-scales>
                 <e-scale e-border-color="transparent" e-direction="Clockwise" e-border-width="0" 
                 e-backgroundColor="transparent" e-showMarkerPointers="false" e-showBarPointers="true">
                 <e-barpointers>
                 <e-barpointer e-width="5" e-backgroundColor="grey">
                 </e-barpointer>
                 </e-barpointers>
                 <e-labels>
                 <e-label e-angle="90" e-distancefromscale-x="5" e-distancefromscale-y="-5">
                 </e-labels>
                 <e-ticks>
                 <e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c" e-distancefromscale-x="0" 
                 e-distancefromscale-y="0"></e-tick>
                 <e-tick e-type="minorinterval" e-width="1" e-height="6" e-color="#8c8c8c" 
                 e-distancefromscale-x="0" e-distancefromscale-y="0"></e-tick>
                 </e-ticks>
                 </e-scale>
                 </e-scales>
                 </ej-lineargauge>
        </div>
        <script>
        angular.module('LinearGaugeApp', ['ejangular'])
        .controller('LinearGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>
{% endhighlight %}



Execute the above code to render the following output.


![](Basic-Settings_images/Basic-Settings_img4.png)



