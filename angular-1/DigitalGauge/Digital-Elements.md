---
layout: post
title: Digital-Elements
description: digital elements
platform: Angular 1.0
control: Digital Gauge
documentation: ug
---

# Digital Elements

**Text Customization**

* The attribute **value** refers the text displayed in the **Digital Gauge**. This text is applicable only for that item instead of all items. Text color is changed by using the property **textColor.**

* It is possible to align the text inside the **Digital Gauge** control by using the property **textAlign**. Two possible values for text align are as follows

  * left

  * right


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="DigitalGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: DigitalGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="DigitalGaugeCtrl">
        <div id="digitalframe">
                 <ej-digitalgauge >
                 <e-items>
                 <e-item e-value="STOP" e-textalign="right">
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

![](Digital-Elements_images/Digital-Elements_img1.png)

