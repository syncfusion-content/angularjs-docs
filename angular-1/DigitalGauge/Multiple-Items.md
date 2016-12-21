---
layout: post
title: Multiple-Items
description: multiple items 
platform: Angular 1.0
control: Digital Gauge
documentation: ug
---

# Multiple Items 

The text in the **Digital Gauge** is positioned with position object. This object contains two attributes such as **x** and **y.** The **x** variable positions the text in the horizontal axis and **y** variable positions the text in the vertical axis.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="DigitalGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: DigitalGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="DigitalGaugeCtrl">
        <div id="digitalframe">
                 <ej-digitalgauge e-width="1350" e-height="400" e-frame-backgroundimageurl="Board1.png" >
                 <e-items>
                 <e-item e-value="BLUE" e-segmentsettings-color="blue" e-position-x="90" e-position-y="0">
                 </e-item>
                  <e-item e-value="RED" e-segmentsettings-color="red" e-position-x="90" e-position-y="15">
                 </e-item>
                  <e-item e-value="PINK" e-segmentsettings-color="pink" e-position-x="90" e-position-y="30">
                 </e-item>
                 </e-items>
                 </ej-digitalgauge>
        </div>
         <script >
        angular.module('DigitalGaugeApp', ['ejangular'])
       .controller('DigitalGaugeCtrl', function ($scope) {
         });
    </script>
    </body>
</html>



{% endhighlight %}

Execute the above code example to render the **Digital****Gauge** as follows.

![](Multiple-Items_images/Multiple-Items_img1.png)

