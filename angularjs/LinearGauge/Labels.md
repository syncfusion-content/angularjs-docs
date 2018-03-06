---
layout: post
title: Labels
description: labels
platform: AngularJS
control: Linear Gauge
documentation: ug
---

# Labels

Labels are units that are used to display the values in the scales. You can customize Labels with the properties like angle, color, font, opacity, etc.

## Label Customization

**Appearance**

* The attribute **angle** is used to display the labels in the specified angles and **color** attribute is used to display the labels in specified color. You can adjust the opacity of the label with the property **opacity** and the values of it lies between 0 and 1.The **includeFirstValue** is a special property by enabling this property, the first value of the label is not rendered.

* Font option is also available on the labels. The basic three properties of fonts such as size, family and style can be achieved by **size**, **fontStyle** and **fontFamily**. Labels are two types such as major and minor.Major type labels are for major interval values and minor type labels are for minor interval values.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge   e-enableanimation="false" e-value="40" e-frame-innerwidth="8" 
                 e-frame-outerWidth="10" 
                 e-frame-backgroundImageUrl="../images/gauge/Gauge_linear_light.png" >
                 <e-scales>
                 <e-scale   e-backgroundcolor="transparent" e-border-color="transparent" 
                 e-border-width="0" e-showBarPointers="true" e-showMarkerPointers="false" 
                 e-showCustomLabels="true" >
                 <e-barpointers>
                 <e-barpointer  e-width="10" >
                 </e-barpointer>
                 </e-barpointers>
                 <e-labels>
                 <e-label e-textcolor="red" e-angle="10" e-opacity="0.5" e-includeFirstValue="false" 
                 e-font-fontFamily="arial" e-font-size="12px" e-font-fontStyle="bold"></e-label>
                 </e-labels>
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


![](Labels_images/Labels_img1.png)

## Unit text and Positioning

* The **unitText** property is used to add some text along with the labels. For example, in speedometer, you need to mention the units in kph. You can also add the unit text in front of the labels. To achieve this use the enumerable property **unitTextPosition**. 

* Labels can be positioned with the help of two properties such as **distanceFromScale** and **placement**. **distanceFromScale** property defines the distance between the scale and labels. **Placement** property is used to locate the labels with respect to scale either inside the scale or outside the scale or along the scale. It is an enumerable data type.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="LinearGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: LinearGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="LinearGaugeCtrl">
        <div id="linearframe">
                 <ej-lineargauge   e-enableanimation="false" e-value="31" e-width="600" e-height="250" 
                 e-theme="flatlight" e-orientation="horizontal" e-labelcolor="black" e-enableresize="true" 
                 e-frame-backgroundImageUrl="../images/gauge/Gauge_linear_light.png" >
                 <e-scales>
                 <e-scale   e-backgroundcolor="White" e-width="5" e-majorintervalvalue="25" 
                 e-minorintervalvalue="5" e-type="roundedrectangle" e-border-color="#AEC75F" 
                 e-border-width="2" e-showBarPointers="true" e-showMarkerPointers="false" 
                 e-showCustomLabels="true" >
                 <e-barpointers>
                 <e-barpointer  e-width="4" e-backgroundcolor="Red" >
                 </e-barpointer>
                 </e-barpointers>
                 <e-labels>
                 <e-label  e-angle="90" e-distancefromscale-x="0" e-distancefromscale-y="60" 
                 e-unittext="%"></e-label>
                 </e-labels>
                 <e-ticks>
                 <e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c" e-distancefromscale-x="0" 
                 e-distancefromscale-y="25"></e-tick>
                 <e-tick e-type="minorinterval" e-width="1" e-height="6" e-color="#8c8c8c" 
                 e-distancefromscale-x="0" e-distancefromscale-y="25"></e-tick>
                 </e-ticks>
                 <e-customlabels>
                 <e-customlabel e-value="Download In Progress" e-position-x="50" e-position-y="20">
                 </e-customlabel>
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


![](Labels_images/Labels_img2.png)



