---
layout: post
title: Quantitative-Scale
description: quantitative scale
platform: AngularJS
control: BulletGraph	
documentation: ug
---

# Quantitative Scale

The **Quantitative Scale** appearance is customized using **quantitativeScaleSettings** property. It has properties to customize labels, major ticks, minor ticks, comparative measure and performance measure of the bullet graph

## Range for Quantitative Scale

**Quantitative Scale** range is set using the properties **minimum**, **maximum** and **interval** of **quantitativeScaleSettings** property. **Minimum** specifies the start range of the scale, **maximum** specifies the end range of scale and **interval** specifies the number of intervals between start and end range. Default values of **minimum**, **maximum** and **interval** are 0, 10 and 1 respectively. The number of minor ticks (ticks between intervals) are specified using **minorTicksPerInterval** property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-quantitativescalesettings-minimum="0" 
                 e-quantitativescalesettings-maximum="100" 
                 e-quantitativescalesettings-interval="10" 
                 e-quantitativescalesettings-minorticksperinterval="4">
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
           .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>




{% endhighlight %}



The following screenshot displays a **Bullet Graph** with start range 0, end range 10 and interval 1 with 4 minor ticks per interval

![](Quantitative-Scale_images/Quantitative-Scale_img1.png) 

## Quantitative scale location

Bullet Graph does not position Quantitative scale automatically based on its size or space required for caption text, etc. By default Quantitative scale is positioned at 10 pixels from left and 10 pixels from top. Quantitative scale location is customized as per the requirement using the location property available in quantitativeScaleSettings.

{% highlight html %}


<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-quantitativescalesettings-location-x="20" 
                 e-quantitativescalesettings-location-y="20">
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
           .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>



{% endhighlight %}

The following screenshot displays **Bullet Graph** with Quantitative scale at 20 pixels from left and 20 pixels from top

![](Quantitative-Scale_images/Quantitative-Scale_img2.png) 

## Major ticks

Color, size and width of **Major tick** lines are customized using **majorTickSettings** property in **quantitativeScaleSettings**. Default value of **size** and **width** properties are 13 and 2 respectively. **Ticks** are drawn in black color by default. The property **size** represents the height of **tick** lines and **width** represents the width of **tick** lines and **ticks** color are customized using **stroke** property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-quantitativescalesettings-majorticksettings-size="15"
                 e-quantitativescalesettings-majorticksettings-width="3" 
                 e-quantitativescalesettings-majorticksettings-stroke="gray">
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
           .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>




{% endhighlight %}



The following screenshot displays **Major ticks** in **gray** color with a width of 3 pixels and height 15 pixels.

![](Quantitative-Scale_images/Quantitative-Scale_img3.png) 

## Minor ticks

Minor ticks can also be customized similar to major ticks. The properties stroke, width and size of minorTickSettings are used to customize Minor ticks in quantitative scale. Stroke specifies the color of ticks, width specifies the width of ticks and size specifies the height of the ticks.

{% highlight html %}


<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-quantitativescalesettings-minorticksettings-size="7" 
                 e-quantitativescalesettings-minorticksettings-width="3" 
                 e-quantitativescalesettings-minorticksettings-stroke="gray">
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
           .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>


{% endhighlight %}



The following screenshot displays **Bullet Graph** with customized **Minor ticks** in quantitative scale

![](Quantitative-Scale_images/Quantitative-Scale_img4.png) 

## Tick position

**Ticks** are positioned below, above or inside the quantitative scale. By default **ticks** are positioned below the quantitative scale. The **tickPosition** property is used to customize the position of ticks in quantitative scale. **Ticks** can be placed inside the quantitative scale by setting **tickPosition** to **cross**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-quantitativescalesettings-tickposition = "above">               
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
           .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>


{% endhighlight %}



The following screenshot displays **Bullet Graph** with ticks positioned above quantitative scale

![](Quantitative-Scale_images/Quantitative-Scale_img5.png) 

## Tick Placement

**Quantitative****scale****ticks** can be placed either inside or outside the scale using “**tickPlacement**” property. By default ticks are placed outside the scale.



{% highlight html %}


<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-value="8" e-comparitiveMeasureValue="5" e-qualitativerangesize="50" 
                 e-quantitativescalesettings-location-x = "108" 
                 e-quantitativescalesettings-location-y="10" 
                 e-quantitativescalesettings-tickplacement="inside"
                 e-quantitativescalesettings-labelsettings-offset="5" 
                 e-quantitativescalesettings-labelsettings-size="10" 
                 e-quantitativescalesettings-labelsettings-labelPrefix="$" 
                 e-quantitativescalesettings-labelsettings-labelSuffix="K" e-captionSettings-textAngle="0"
                 e-captionSettings-location-x="17" e-captionSettings-location-y="28" 
                 e-captionSettings-text="Revenue YTD" e-captionSettings-subTitle-textAngle="0" 
                 e-captionSettings-subTitle-text="$ in Thousands" e-captionSettings-subTitle-location-x="10"
                 e-captionSettings-subTitle-location-y="42">               
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
           .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>




{% endhighlight %}



The following screenshot displays **Bullet Graph** ticks inside **Quantitative Scale**

![](Quantitative-Scale_images/Quantitative-Scale_img6.png) 

## Quantitative scale labels

**Quantitative****scale****labels** are customized with prefix, suffix, font, color and size using **labelSettings** property. By default, label text is displayed in black color with 12 pixel ‘Segoe UI’ font and there is a padding of 20 pixels space between quantitative scale and labels.

{% highlight html %}


<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-quantitativescalesettings-labelsettings-stroke="blue" 
                 e-quantitativescalesettings-labelsettings-labelPrefix="$" 
                 e-quantitativescalesettings-labelsettings-labelSuffix="K"
                 e-quantitativescalesettings-labelsettings-font-fontfamily="segoe ui" 
                 e-quantitativescalesettings-labelsettings-font-fontstyle="bold"   
                 e-quantitativescalesettings-labelsettings-font-fontweight="regular" 
                 e-quantitativescalesettings-labelsettings-font-opacity="0.8" 
                 e-quantitativescalesettings-size="12" e-quantitativescalesettings-offset="15">              
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
           .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>



{% endhighlight %}



The following screenshot displays **Bullet Graph** labels in blue color

![](Quantitative-Scale_images/Quantitative-Scale_img7.png) 

## Label Placement

**Quantitative****scale****labels** can be placed either inside or outside the scale using “**labelPlacement**” property. By default labels are placed 15 pixels outside the scale.

{% highlight html %}



<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-value="8" e-comparitiveMeasureValue="5" e-qualitativerangesize="50" 
                 e-quantitativescalesettings-location-x = "108" 
                 e-quantitativescalesettings-location-y="10" 
                 e-quantitativescalesettings-labelsettings-offset="5" 
                 e-quantitativescalesettings-labelsettings-size="10" 
                 e-quantitativescalesettings-labelsettings-labelPrefix="$" 
                 e-quantitativescalesettings-labelsettings-labelSuffix="K"
                 e-quantitativescalesettings-font-fontweight="bold" 
                 e-quantitativescalesettings-labelPlacement="inside" e-captionSettings-textAngle="0" 
                 e-captionSettings-location-x="17" e-captionSettings-location-y="28" 
                 e-captionSettings-text="Revenue YTD" e-captionSettings-subTitle-textAngle="0"
                 e-captionSettings-subTitle-text="$ in Thousands" e-captionSettings-subTitle-location-x="10"
                 e-captionSettings-subTitle-location-y="42">               
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
           .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>


{% endhighlight %}



The following screenshot displays **Bullet Graph** labels inside **Quantitative Scale.**

![](Quantitative-Scale_images/Quantitative-Scale_img8.png) 

## Performance measure bar

Performance measure bar is customized using featuredMeasureSettings in quantitativeScaleSettings property. Color of the bar is customized using stroke property and width using width property. By default bar is drawn in black color with 6 pixels of width.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-value="5" 
                 e-quantitativescalesettings-featuredMeasureSettings-stroke="blue"
                 e-quantitativescalesettings-featuredMeasureSettings-width="4">               
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
           .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>





{% endhighlight %}



The following screenshot displays **Bullet Graph** with customized **Performance measure bar**.

![](Quantitative-Scale_images/Quantitative-Scale_img9.png) 

## Comparative measure symbol

Comparative symbol color and width are customized using comparativeMeasureSettings through quantitativeScaleSettings property. Color of the symbol is customized using stroke property and width using width property. By default Comparative measure symbol is displayed in black color with a width of 5 pixels.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-comparativeMeasureValue="5" e-quantitativescalesettings-comparitiveMeasureSettings-stroke="blue" e-quantitativescalesettings-comparitiveMeasureSettings-width="5">               
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                         });
     </script>
    </body>
</html>



{% endhighlight %}



The following screenshot displays **Bullet Graph** with customized **Comparative measure value**.

![](Quantitative-Scale_images/Quantitative-Scale_img10.png) 

## Multiple performance measures comparison

**Bullet Graph** supports comparing more than one performance at a time, given that all the comparisons are related using **featureMeasure** in **quantitativeScaleSettings** property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-qualitativerangesize="60" e-height="120" e-quantitativescalesettings-featureMeasures="featureMeasure">               
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                 $scope.featureMeasure=[
                            { value: 6, comparativeMeasureValue: 3, category: 2010 },
                            { value: 9, comparativeMeasureValue: 6, category: 2011 },
                            { value: 5, comparativeMeasureValue: 5, category: 2012 },
                        ];
                         });
     </script>
    </body>
</html>




{% endhighlight %}



The following screenshot displays **Bullet Graph** that compares 3 related performance measures.

![](Quantitative-Scale_images/Quantitative-Scale_img11.png) 

