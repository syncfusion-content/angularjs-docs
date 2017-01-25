---
layout: post
title: Marker-Pointers
description: marker pointers
platform: Angular 1.0
control: Linear Gauge
documentation: ug
---

# Marker Pointers

**Marker Pointer** value points out the actual value set in the **Linear Gauge**. You can set values for various pointer attributes such as value, type, length, width, border and color in pointer collection. You can also customize the pointers to improve the appearance of gauge.

## Adding marker pointer collection

You can add **Marker Pointer** collection directly to the scale object. To add pointer collection in a gauge control refer the following code example.  


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge e-value="78" >
                 <e-scales>
                 <e-scale  e-width="8" e-position-x="20" e-position-y="50" e-backgroundColor="grey"
                 e-border-color="transparent" e-border-width="0" e-showBarPointers="true" 
                 e-showmarkerpointers="true" >
                 <e-labels>
                 <e-label  e-distancefromscale-x="50" e-distancefromscale-y="0"></e-label>
                 </e-labels>
                  <e-barpointers>
                 <e-barpointer   e-width="5" e-backgroundColor="grey">
                 </e-barpointer>
                 </e-barpointers>
                 <e-markerpointers>
                 <e-markerpointer  e-width="10" e-length="10" e-backgroundColor="grey" 
                 e-distancefromscale="-12">
                 </e-markerpointer>
                 </e-markerpointers>
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


![](/Marker-Pointers_images/Marker-Pointers_img1.png)

## Add marker pointer value

The **value** property is the important element in the marker pointer collection which indicates the gauge value. Real purpose of the **Linear Gauge** is based on the pointer value. You can set the pointer value either directly during rendering the control or it can be achieved by public method.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge e-enableanimation="false" e-width="600" e-height="150" 
                 e-orientation="horizontal" e-labelcolor="black" e-enableresize="true" 
                 e-frame-backgroundImageUrl="../images/gauge/Gauge_linear_light1.png">
                 <e-scales>
                 <e-scale  e-backgroundColor="#AEC75F" e-direction="Clockwise" e-type="roundedrectangle"
                 e-border-color="#AEC75F" e-border-width="30" >
                 <e-labels>
                 <e-label  e-distancefromscale-x="0" e-distancefromscale-y="100" e-angle="90"></e-label>
                 </e-labels>
                 <e-markerpointers>
                 <e-markerpointer  e-width="30" e-length="30" e-backgroundColor="#FE5C09" 
                 e-distancefromscale="20" e-placement="near" e-value="67.5">
                 </e-markerpointer>
                 </e-markerpointers>
                 <e-ticks>
                 <e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c" e-distancefromscale-x="45" 
                 e-distancefromscale-y="-1"></e-tick>
                 <e-tick e-type="minorinterval" e-width="1" e-height="6" e-color="#8c8c8c" 
                 e-distancefromscale-x="45" e-distancefromscale-y="-1"></e-tick>
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


![](/Marker-Pointers_images/Marker-Pointers_img2.png)

## Pointer Styles

**Appearance**

* Based on the value, the **pointer** points out the label value. You can set the pointer length and width using **length** and **width** property respectively. You can also adjust the opacity of the pointer using the **opacity** property which holds the value between 0 and 1. You can add the gradient effects to the pointer using **gradient** object. 

* The marker pointer border is modified with the **border** object. It contains two border property namely **color** and **width** which are used to customize the border color of the scale and border width of the marker pointer. The background color can be customized with attribute **backgroundColor**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge e-enableanimation="false" e-width="600" e-height="150" 
                 e-orientation="horizontal" e-labelcolor="black" e-enableresize="true" 
                 e-frame-backgroundImageUrl="../images/gauge/Gauge_linear_light1.png" >
                 <e-scales>
                 <e-scale   e-backgroundColor="#AEC75F" e-direction="Clockwise" e-type="roundedrectangle"
                 e-border-color="#AEC75F" e-border-width="30" >
                 <e-labels>
                 <e-label  e-distancefromscale-x="0" e-distancefromscale-y="100" e-angle="90"></e-label>
                 </e-labels>
                 <e-markerpointers>
                 <e-markerpointer  e-width="30" e-length="30" e-backgroundColor="#FCDD34" e-opacity="0.4"
                  e-distancefromscale="20" e-placement="near" e-value="67.5">
                 </e-markerpointer>
                 </e-markerpointers>
                 <e-ticks>
                 <e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c" e-distancefromscale-x="45"
                 e-distancefromscale-y="-1"></e-tick>
                 <e-tick e-type="minorinterval" e-width="1" e-height="6" e-color="#8c8c8c" 
                 e-distancefromscale-x="45" e-distancefromscale-y="-1"></e-tick>
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



![](/Marker-Pointers_images/Marker-Pointers_img3.png)

## Positioning the pointer

* You can position the Pointer with two properties, **distanceFromScale** and **placement**. The **distanceFromScale** property defines the distance between the scale and pointer. 

* The **Placement** property is used to locate the pointer with respect to scale either inside or outside the scale or along the scale. It is an enumerable data type.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge e-enableanimation="false" e-width="600" e-height="150" 
                 e-orientation="horizontal" e-labelcolor="black" e-enableresize="true" 
                 e-frame-backgroundImageUrl="../images/gauge/Gauge_linear_light1.png" >
                 <e-scales>
                 <e-scale   e-backgroundColor="#AEC75F" e-direction="Clockwise" e-type="roundedrectangle"
                 e-border-color="#AEC75F" e-border-width="30" >
                 <e-labels>
                 <e-label  e-distancefromscale-x="0" e-distancefromscale-y="100" e-angle="90"></e-label>
                 </e-labels>
                 <e-markerpointers>
                 <e-markerpointer  e-width="30" e-height="8" e-length="30" e-backgroundColor="#01A357" 
                 e-opacity="0.4" e-distancefromscale="60" e-placement="near" e-value="55.5">
                 </e-markerpointer>
                 </e-markerpointers>
                 <e-ticks>
                 <e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c" e-distancefromscale-x="45" 
                 e-distancefromscale-y="-1"></e-tick>
                 <e-tick e-type="minorinterval" e-width="1" e-height="6" e-color="#8c8c8c" 
                 e-distancefromscale-x="45" e-distancefromscale-y="-1"></e-tick>
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

![](/Marker-Pointers_images/Marker-Pointers_img4.png)

## Types

It is possible to change the dimension of the marker pointer. Dimensions available for marker pointer are,

* Rectangle

* Triangle

* Ellipse

* Diamond

* Pentagon

* Circle

* Slider

* Pointer

* Wedge

* Trapezoid

* Rounded Rectangle

**Multiple Marker Pointers**

**Linear Gauge** can contain multiple pointers on it. You can use any combination and any number of pointers in a gauge. That is, a gauge can contain any number of marker pointer and any number of bar pointers. Refer the following code example containing multiple marker pointers.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge e-enableanimation="false" e-width="600" e-height="250" 
                 e-orientation="horizontal" e-labelcolor="black" e-enableresize="true" 
                 e-theme="flatlight" 
                 e-frame-backgroundImageUrl="../images/gauge/Gauge_linear_light1.png" >
                 <e-scales>
                 <e-scale   e-backgroundColor="#AEC75F" e-showcustomlabels="true" e-direction="Clockwise" 
                 e-type="roundedrectangle" e-border-color="#AEC75F" e-border-width="30" >
                 <e-labels>
                 <e-label  e-distancefromscale-x="0" e-distancefromscale-y="100" e-angle="90"></e-label>
                 </e-labels>
                 <e-markerpointers>
                 //Adding pointer 1
                 <e-markerpointer  e-width="30"  e-length="30" e-backgroundColor="#01A357"
                  e-distancefromscale="60" e-placement="near" e-value="32.2">
                 </e-markerpointer>
                  //Adding pointer 2
                 <e-markerpointer  e-width="10"  e-length="30" e-backgroundColor="#90DAFB"
                  e-distancefromscale="60" e-placement="near" e-value="23.7" e-type="circle">
                 </e-markerpointer>
                  //Adding pointer 3
                 <e-markerpointer  e-width="3"  e-length="30" e-backgroundColor="#90DAFB"
                  e-distancefromscale="60" e-placement="near" e-value="23.7" e-type="star">
                 </e-markerpointer>
                 </e-markerpointers>
                 <e-ticks>
                 <e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c" e-distancefromscale-x="45" 
                 e-distancefromscale-y="-1"></e-tick>
                 <e-tick e-type="minorinterval" e-width="1" e-height="6" e-color="#8c8c8c" 
                 e-distancefromscale-x="45" e-distancefromscale-y="-1"></e-tick>
                 </e-ticks>
                 <e-customlabels>
                 <e-customlabel e-value="Weather Condition in California" e-position-x="50" 
                 e-position-y="20"></e-customlabel>
                 </e-customlabels>
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


![](/Marker-Pointers_images/Marker-Pointers_img5.png)

