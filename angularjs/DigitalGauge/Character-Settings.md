---
layout: post
title: Character-Settings
description: character settings
platform: Angular 1.0
control: Digital Gauge
documentation: ug
---

# Character Settings

## Appearance

The opacity of the character is adjustable with the help of **opacity** property. The space between two characters are adjusted with **spacing** property as like in the segment settings.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="DigitalGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: DigitalGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="DigitalGaugeCtrl">
        <div id="digitalframe">
                 <ej-digitalgauge e-width="800" >
                 <e-items>
                 <e-item e-value="SYNCFUSION" e-charactersettings-opacity="0.3"
                 e-charactersettings-spacing="3">
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

![](Character-Settings_images/Character-Settings_img1.png)

## Count and Type

The number of text to be displayed can be limited by the attribute called **count**. In **Digital Gauge** five different types of characters are supported. They are as follows, 

  * EightCrossEightDotMatrix

  * SevenSegment

  * FourteenSegment

  * SixteenSegment 

  * EightCrossEightSquareMatrix.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="DigitalGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: DigitalGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="DigitalGaugeCtrl">
        <div id="digitalframe">
                 <ej-digitalgauge e-width="800" >
                 <e-items>
                 <e-item e-value="1234567890" e-segmentsettings-length="8" e-segmentsettings-width="1" 
                 e-charactersettings-count="10" e-charactersettings-spacing="10" 
                 e-charactersettings-type="sevensegment">
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

![](Character-Settings_images/Character-Settings_img2.png)

## Text Positioning

The text in the **Digital****Gauge** is positioned with position object. This object contains two attributes such as **x** and **y.** The **x** variable positions the text in the horizontal axis and the **y** variable positions the text in the vertical axis.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="DigitalGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: DigitalGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="DigitalGaugeCtrl">
        <div id="digitalframe">
                 <ej-digitalgauge e-width="800" e-height="300" e-frame-backgroundimageurl="board1.jpg" >
                 <e-items>
                 <e-item e-value="YELLOW" e-segmentsettings-color="yellow" e-position-x="80"
                 e-position-y="10">
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


![](Character-Settings_images/Character-Settings_img3.png)

## Shadow Effects

The text in the **Digital Gauge** is positioned with position object. This object contains two attributes such as **x** and **y.** The **x** variable positions the text in the horizontal axis and **y** variable positions the text in the vertical axis.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="DigitalGaugeApp">
    <head>
        <title>Essential Studio for AngularJS: DigitalGauge</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="DigitalGaugeCtrl">
        <div id="digitalframe">
                 <ej-digitalgauge e-width="800" >
                 <e-items>
                 <e-item e-value="WELCOME" e-segmentsettings-length="3" e-segmentsettings-width="3" 
                 e-shadowcolor="yellow" e-shadowblur="20" e-shadowoffsetx="15" e-shadowoffsety="15">
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

![](Character-Settings_images/Character-Settings_img4.png)

