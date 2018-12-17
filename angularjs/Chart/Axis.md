---
layout: post
title: Syncfusion EJ1 AngularJS - Chart Axis
description: How to customize the grid lines, tick lines, labels and title of chart axis
platform: AngularJS
control: Chart
documentation: ug
---

# Axis

**Charts** typically have two axes that are used to measure and categorize data: a vertical (y) axis, and a horizontal (x) axis.

Vertical axis always uses numerical or logarithmic scale. Horizontal(x) axis supports the following types of scale:

* Category
* Numeric
* DateTime
* DateTime Category
* Logarithmic

## Category Axis

Category axis displays the text labels instead of numbers. To use the categorical axis, you can set the `e-valuetype` property of the axis to the **category**. Default value of `e-valuetype` is **double**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-valuetype="category">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}



![Category Axis](Axis_images/axis_img1.png)


### Place labels on ticks

Labels in the category axis can be placed on the ticks by setting the `e-primaryxaxis-labelPlacement` property of axis to the **onticks**. The default value of the `e-primaryxaxis-labelPlacement` property is **betweenticks** i.e. labels are placed between the ticks, by default.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-labelPlacement="onTicks">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Label Placement](Axis_images/axis_img2.png)


### Display labels after a fixed interval

To display the labels after a fixed interval n, you can set the `e-primaryxaxis-range-interval` property of the axis range as **n**. The default value of the interval is 1 i.e. all the labels are displayed.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-range-interval="2">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Labels in Fixed Interval](Axis_images/axis_img3.png)


### Indexed Category Axis

Category axis can also plot points based on index value of data points. Index based plotting can be enabled by setting `e-primaryxaxis-isIndexed` property to true in the axis.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-isindexed="true">
        <e-series>
        <e-series e-datasource=dataSource e-xname="x" e-yname="y">
        </e-series>
        </e-series>
        </div>
        <script>
       var chartData = [{ x: "Monday", y: 50 }, { x: "Tuesday", y: 40 }, 
                        { x: "Wednesday", y: 70 },
                        { x: "Thursday", y: 60 }, { x: "Friday", y: 50 },
                        { x: "Monday", y: 40 }, { x: "Monday", y: 30 }];
        angular.module('syncApp', ['ejangular'])
               .controller('Chart', function ($scope) {
                   $scope.dataSource = chartData;
                   
               });
           
        </script>
    </body>
</html>


{% endhighlight %}


![With Indexed Axis](Axis_images/axis_img50.png)

**While Category axis isIndexed value false**

![Without Indexed Axis](Axis_images/axis_img51.png)


## Numeric Axis 

Numeric axis uses numerical scale and displays numbers as labels. To use numeric axis, you can set the `e-valueType` property of the axis to **double**. 



{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-valuetype="double">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}



![Numeric Axis](Axis_images/axis_img4.png)


### Customize numeric range

To customize the range of an axis, you can use the `e-primaryxaxis-range` property of the axis to set the `e-primaryxaxis-range-minimum`,`e-primaryxaxis-range-maximum` and `e-primaryxaxis-range-interval` values. Nice range is calculated automatically based on the provided data, by default.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-range-min="0" e-primaryyaxis-range-max="50">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}


![Numeric Axis Customization](Axis_images/axis_img5.png)


#### Customizing numeric interval

Axis interval can be customized by using the `e-primaryyaxis-range-interval`property of the axis range. Nice interval is calculated based on the minimum and maximum value of the provided data, by default.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-range-interval="5">
        </div>
        <script>
           angular.module('ChartApp', ['ejangular'])
           .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Numeric Interval Customization](Axis_images/axis_img6.png)

### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the axis range by using the `e-primaryxaxis-rangePadding` property. Numeric axis supports the following types of padding

* None
* Round
* Additional
* Normal

**None**

When the value of the `e-primaryxaxis-rangePadding` property is **none**, padding can not be applied to the axis. This is also the default value of the rangePadding. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-rangePadding="none">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Numeric RangePadding None](Axis_images/axis_img7.png)


#### Round

When the value of `e-primaryyaxis-rangePadding`property is **round**, the axis range is rounded to the nearest possible value divided by the interval.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-rangePadding="round">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

**Chart before rounding axis range**

![Without Numeric RangePadding Round](Axis_images/axis_img8.png)



**Chart after rounding axis range**

![With Numeric RangePadding Roung](Axis_images/axis_img9.png)

**Additional**

When the value of the `e-primaryyaxis-rangePadding` property is **additional**, the axis range is rounded and an interval of the axis is added as padding to the minimum and maximum values of the range.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-rangePadding="additional">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Numeric RangePadding Additional](Axis_images/axis_img10.png)


**Normal**

When the value of the `e-primaryyaxis-rangePadding` property is **normal**, the padding is applied to the axis based on the range calculation.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-rangePadding="normal">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                  
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Numeric RangePadding Normal](Axis_images/axis_img11.png)

#### Customizing the starting range of the axis

By default the Y axis will be always calculated from the value 0 for column, bar, stacking column and stacking bar series types. You can modify this behavior by setting false to the property `e-startFromZero` in the axis. On setting this the axis minimum value will be calculated based on the value for the data points.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-rangePadding="none" e-primaryyaxis-startfromzero="false">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                  
                });
        </script>
    </body>
</html>

{% endhighlight %}

![Start From Zero](Axis_images/axis_img66.png)

## DateTime Axis

Date time axis uses date time scale and displays the date time values as axis labels in the specified format. To use date time axis, set the `e-valueType`property of the axis to **datetime**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-valuetype="datetime">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![DateTime Axis](Axis_images/axis_img12.png)




 
### Customizing date time range
 
 Axis range can be customized by using the `e-primaryxaxis-range` property to set the `e-primaryxaxis-range-minimum`, `e-primaryxaxis-range-maximum` and `e-primaryxaxis-range-interval`values. Nice range is calculated automatically based on the provided data, by default.
 
 {% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-range-min="2000/6/1"
         e-primaryxaxis-range-max="2010/6/1">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![DateTime Axis Customization](Axis_images/axis_img13.png)


### Date time intervals

Date time intervals can be customized by using the `e-primaryxaxis-range-interval`and `e-primaryxaxis-intervalType` properties of the axis. For example, when you set `e-primaryxaxis-range-interval` as **2** and `e-primaryxaxis-intervalType` as **years**, it considers the 2 years as interval.

Essential Chart supports the following types of interval for date time axis.

* Days
* Hours
* Milliseconds
* Minutes
* Months
* Seconds
* Years

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-primaryxaxis-range-interval="2" 
        e-primaryxaxis-intervaltype="years">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}


![DateTime Intervals](Axis_images/axis_img14.png)


### Apply padding to the range

Padding can be applied to the minimum and maximum extremes of the range by using the `e-primaryxaxis-rangePadding` property. Date time axis supports the following types of padding

* None
* Round
* Additional

**None**

When the value of the `e-primaryxaxis-rangePadding` property is **none**, padding is applied to the axis. This is also the default value of the rangePadding. 

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-rangePadding="none">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![DateTime RangePadding None](Axis_images/axis_img15.png)

**Round**

When the value of the `e-primaryxaxis-rangePadding`property is **round**, the axis range is rounded to the nearest possible date time value.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-rangePadding="round">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

**Chart before rounding axis range**

![Without DateTime RangePadding Round](Axis_images/axis_img16.png)


**Chart after rounding axis range**

![With DateTime RangePadding Round](Axis_images/axis_img17.png)

**Additional** 

When the value of the `e-primaryxaxis-rangePadding` property is **additional**, the range is rounded and date time interval of the axis are added as padding to the minimum and maximum extremes of the range.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-rangePadding="additional">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![DateTime RangePadding Additional](Axis_images/axis_img18.png)


## DateTime Category Axis

DateTime category axis takes date time value as input but behaves like category axis. This is used to display the date time values with nonlinear intervals (used to depict the business days by skipping holidays). To use date time axis, set the `e-valueType` property of the axis to **datetimeCategory**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-valuetype="datetimecategory">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>

{% endhighlight %}

![DateTimeCategory Axis](Axis_images/axis_img63.png)

 [Click](http://ngjq.syncfusion.com/DateTimeCategoryAxis) here to view our online demo sample for date time axis.

### Customizing DateTime Category range

Axis range can be customized by using the `e-range` property to set the `e-minimum`, `e-maximum` and `e-interval` values. Datetime category axis takes numeric input for minimum and maximum property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
    //Customizing X-axis date time category range
        <div id="container" ej-chart  e-primaryxaxis-range-min="0"
         e-primaryxaxis-range-max="4">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>

{% endhighlight %}

![DateTimeCategory Range Customization](Axis_images/axis_img64.png)

### DateTime Category intervals

Date time category intervals can be customized by using the `e-interval`and `e-intervalType` properties of the axis. For example, when you set the intervalType as months, it displays only the first label of all the months from the data.

Essential Chart supports the following types of interval for date time category axis.
* Days
* Hours
* Milliseconds
* Minutes
* Months
* Seconds
* Years
* Auto

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
       <div id="container" ej-chart e-primaryxaxis-intervaltype="months">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>

{% endhighlight %}

![DateTimeCategory Intervals](Axis_images/axis_img65.png)



## Logarithmic Axis

Logarithmic axis uses logarithmic scale and it is very useful in visualizing when the data has values with both lower order of magnitude **(eg: 10<sup>-6</sup>)** and higher order of magnitude **(eg: 10<sup>6</sup>)**. To use logarithmic axis, set the `e-valueType` property of the axis to **logarithmic**.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-valuetype="logarithmic">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}


![Logarithmic Axis](Axis_images/axis_img19.png)




### Customize Logarithmic range

Logarithmic range can be customized by using the `e-primaryxaxis-range` property of the axis to change the `e-primaryyaxis-range-minimum`, `e-primaryyaxis-range-maximum` and `e-primaryyaxis-range-interval` values. Nice range is calculated automatically based on the provided data, by default.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-range-min="1" e-primaryyaxis-range-max="4">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Logarithmic Range Customization](Axis_images/axis_img20.png)

### Logarithmic base

Logarithmic base can be customized by using the `e-primaryyaxis-logBase` property of the axis. The default value of the `e-primaryyaxis-logBase` is **10**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-logBase="2">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Logarithmic Base](Axis_images/axis_img21.png)


### Logarithmic interval

Logarithmic axis interval can be customized by using the `e-primaryyaxis-range-interval`property of the axis. When the logarithmic base is 10 and logarithmic interval is 2, then the axis labels are placed at an interval of 10<sup>2</sup>. The default value of the interval is 1. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-range-interval="2">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Logarithmic Interval](Axis_images/axis_img22.png)


## Label Format

### Format numeric labels

Numeric labels can be formatted by using the `e-primaryyaxis-labelFormat` property. Numeric values can be formatted with n (number with decimal points), c (currency) and p (percentage) commands.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-labelFormat="c">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Numeric LabelFormat](Axis_images/axis_img23.png)

The following table describes the result of applying some commonly used label formats on numeric values. 
 
<table>
<tr>
<td><b>Label Value</b></td>
<td><b>Label Format property value</b></td>
<td><b>Result </b></td>
<td><b>Description </b></td>
</tr>        
<tr>
<td>1000</td>
<td>n1</td>
<td>1000.0</td>
<td>The Number is rounded to 1 decimal place</td>
</tr> 
<tr>
<td>1000</td>
<td>n2</td>
<td>1000.00</td>
<td>The Number is rounded to 2 decimal place</td>
</tr> 
<tr>
<td>1000</td>
<td>n3</td>
<td>1000.000</td>
<td>The Number is rounded to 3 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p1</td>
<td>1.0%</td>
<td>The Number is converted to percentage with 1 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p2</td>
<td>1.00%</td>
<td>The Number is converted to percentage with 2 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p3</td>
<td>1.000%</td>
<td>The Number is converted to percentage with 3 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c1</td>
<td>$1,000.0</td>
<td>The Currency symbol is appended to number and number is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c2</td>
<td>$1,000.00</td>
<td>The Currency symbol is appended to number and number is rounded to 2 decimal place</td>
</tr>
</table>


### Format date time values

Date time labels can be formatted by using the `e-primaryxaxis-labelFormat` property of the axis.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-labelFormat="dd/MM/yyyy">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![DateTime LabelFormat](Axis_images/axis_img24.png)


The following table describes the result of applying some common date time formats to the labelFormat property

<table>
<tr>
<td><b>Label Value</b></td>
<td><b>Label Format Property Value</b></td>
<td><b>Result </b></td>
<td><b>Description </b></td>
</tr>        
<tr>
<td>new Date(2000, 03, 10)</td>
<td>dddd</td>
<td>Monday</td>
<td>The Date is displayed in day format</td>
</tr> 
<tr>
<td>new Date(2000, 03, 10)</td>
<td>MM/dd/yyyy</td>
<td>04/10/2000</td>
<td>The Date is displayed in month/date/year format</td>
</tr> 
<tr>
<td>new Date(2000, 03, 10)</td>
<td>n3</td>
<td>1000.000</td>
<td>The Number is rounded to 3 decimal place</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>MMM</td>
<td>Apr</td>
<td>The Shorthand month for the date is displayed</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>t</td>
<td>12:00 AM</td>
<td>Time of the date value is displayed as label</td>
</tr>
<tr>
<td>new Date(2000, 03, 10)</td>
<td>hh:mm:ss</td>
<td>12:00:00</td>
<td>The Label is displayed in hours:minutes:seconds format</td>
</tr>
</table>

### Custom label format

Prefix and suffix can be added to the category labels by using the `e-primaryxaxis-labelFormat` property. You can use the *{value}* as placeholder text in your custom text, it is replaced with the corresponding axis label at the runtime.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-labelFormat="${value}K">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![LabelFormat Customization](Axis_images/axis_img25.png)


## Common axis features

Customization of features such as axis crossing, title, labels, grid lines and tick lines are common to all the axis. Each of these features are explained in this section.


### Axis Crossing

Axis can be positioned anywhere in chart area using the `e-primaryxaxis-crossesAt` property of axis. This property specifies where the horizontal axis should intersect or cross the vertical axis and vice versa. Default value of `e-primaryxaxis-crossesAt` property is null.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
    <!--crosses PrimaryYAxis at 0 -->
        <div id="container" ej-chart  e-primaryxaxis-crossesAt="0">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Axis Crossing](Axis_images/axis_img52.png)


#### Crossing a specific Axis

The `e-primaryxaxis-crossesInAxis` property takes axis name as input and determines the axis used for crossing. By default all the horizontal axes crosses in primary Y axis and all the vertical axes crosses in primary X axis.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
    <!--crosses PrimaryYAxis at 0 -->
        <div id="container" ej-chart  e-primaryxaxis-crossesAt="-0.2" 
        e-primaryxaxis-crossesInAxis="secondaryYAxis">
        <e-axes>
        <e-axis e-orientation="vertical" e-name="secondaryYAxis"></e-axis>
        </e-axes>
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Numeric Axis Crossing](Axis_images/axis_img53.png)

Axis will be placed in the opposite side if value of `e-primaryxaxis-crossesAt` property is greater than the maximum value of crossing axis (axis name provided through `e-primaryxaxis-crossesInAxis` property or primary Y axis for horizontal axis).

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-crossesAt="200">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Numeric Axis CrossesAt](Axis_images/axis_img54.png)


#### Crossing in DateTime Axis

For crossing in a date time horizontal axis, date object should be provided as value for `e-primaryxaxis-crossesAt` property of vertical axes.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-crossesAt="2010/4/29">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}
![DateTime Axis Crossing](Axis_images/axis_img55.png)


#### Crossing in Category Axis

For crossing in a category type horizontal axis, either a string object or a number corresponding to the index of category value can be used for `e-primaryxaxis-crossesAt` property of vertical axes.

W> String value provided for `e-primaryxaxis-crossesAt` property is case-sensitive. 


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-crossesAt="Tuesday">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Category Axis Crossing](Axis_images/axis_img56.png)


#### Positioning the axis elements while crossing

The `e-primaryxaxis-showNextToAxisLine`property is used for controlling the axis elements movement along with the axis line while axis crossing is performed. When the showNextToAxisLine is set as false only the axis line and the tick lines are placed at the crossing Value and the axis elements will be placed outside the chart area. The default value of `e-primaryxaxis-showNextToAxisLine` is **true**.  

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-crossesAt="0" e-primaryxaxis-shownexttoaxisline="false">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>


{% endhighlight %}

The axis is placed at the crossing value without the axis elements 

![ShowNextToAxisLine](Axis_images/axis_img67.png)



### Axis Visibility

Axis visibility can be controlled by using the `e-primaryxaxis-visible` property of the axis. The default value of the `e-primaryxaxis-visible` property is **true**. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryyaxis-visibile=false>
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                   
                });
        </script>
    </body>
</html>

{% endhighlight %}

![Axis Visibility](Axis_images/axis_img26.png)


### Axis title

The `e-primaryxaxis-title` property in the axis provides options to customize the text and font of the axis title. Axis does not display the title, by default. Title text can also be trimmed based on the title text length or specified length.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-title ="title" e-primaryxaxis-title-text="Month" 
        e-primaryxaxis-enableTrim="true" e-primaryxaxis-maximumTitleWidth="80"
        e-primaryxaxis-title-font-fontfamily="Segoe UI" e-primaryxaxis-title-font-size="16px"
        e-primaryxaxis-title-font-fontweight="bold" e-primaryxaxis-title-font-color="grey">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                 });
        </script>
    </body>
</html>


{% endhighlight %}


![Axis Title](Axis_images/axis_img27.png)

You can modify the position of the axis title either inside or outside the chart area using the property `e-primaryxaxis-title-position`. By default, it will be placed outside the chart area. In addition, you can also change the alignment of the title to near, far and center by `e-primaryxaxis-title-alignment` property, using `e-primaryxaxis-title-offset` property you can change the position with respect to pixels.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-title-text="Month" 
        e-primaryxaxis-title-position="inside" e-primaryxaxis-title-alignment="near" 
        e-primaryxaxis-title-offset="10">
        </div>
        <script>
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                  
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Axis Title Customization](Axis_images/axis_img62.png)

### Label customization

The `font` property of the axis provides options to customize the `font-family`, `color`, `opacity`, `size` and `font-weight` of the axis labels.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-primaryxaxis-font-fontfamily="Segoe UI" 
        e-primaryxaxis-font-size="14px" e-primaryxaxis-font-fontweight="bold"
        e-primaryxaxis-font-color="blue">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
               
                });
        </script>
    </body>
</html>


{% endhighlight %}

![Axis Label Customization](Axis_images/axis_img28.png)

#### Axis Labels Line Break

Axis Labels can be placed in multiple lines by specifying **<br>** for data points x value and in label format.

For category value type, **<br>** can be specified in x value of data points.

{% highlight html %}

<div id="container" ej-chart >
    <e-series >
        <e-points>
            <e-points e-x="India" e-y="61.3"></e-points>
            <e-points e-x="United<br>States<br>of<br>America" e-y="31"></e-points>
            <e-points e-x="South<br>Korea" e-y="39.4"></e-points>
            <e-points e-x="United<br>Arab<br>Emirates" e-y="65.1"></e-points>
            <e-points e-x="United<br>Kingdom" e-y="75.9"></e-points>
        </e-points>
    </e-series>
</div>

{% endhighlight %}

![Axis Label LineBreak](Axis_images/axis_img68.png)

For numeric, datetime and datetimeCategory value type, **<br>** can be specified in labelFormat.

{% highlight html %}

<div id="container" ej-chart  e-primaryxaxis-labelFormat="MMM<br>dd<br>yyyy" e-primaryxaxis-valuetype="datetime">
</div>  

{% endhighlight %}

![DateTime, Numeric LineBreak](Axis_images/axis_img69.png)

### Label and tick positioning
 
Axis labels and ticks can be positioned inside or outside the chart area by using the `e-primaryxaxis-labelPosition`and `e-primaryxaxis-tickPosition` properties. The labels and ticks are positioned outside the chart area, by default.
 
{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart   e-primaryxaxis-labelPosition="inside" 
        e-primaryxaxis-tickLinesPosition="inside">
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
            });
        </script>
    </body>
</html>


{% endhighlight %}
 


![Positioning Labels and Ticks](Axis_images/axis_img29.png)


### Edge labels placement

Labels with long text at the edges of an axis may appear partially outside the chart. The `e-primaryxaxis-edgeLabelPlacement` property can be used to avoid the partial appearance of the labels at the corners. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart   e-primaryxaxis-edgeLabelPlacement="shift">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
       .controller('ChartCtrl', function ($scope) {
            });
        </script>
    </body>
</html>


{% endhighlight %}

**Chart before setting edge label placement to X-axis**

![Before EdgeLabelPlacement](Axis_images/axis_img30.png)


**Chart after setting edge label placement to X-axis**

![After EdgeLabelPlacement](Axis_images/axis_img31.png)


### Grid lines customization

The `e-primaryxaxis-majorGridLines` and `e-primaryxaxis-minorGridLines` properties in the axis are used to customize the major grid lines and minor grid lines of an axis. They provide options to change the width, color, visibility and opacity of the grid lines. The minor grid lines are not visible, by default.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-primaryxaxis-majorGridLines-color="blue" 
        e-primaryxaxis-majorGridLines-visible="true" 
        e-primaryxaxis-majorGridLines-width="1"
        e-primaryxaxis-minorGridLines-color="red" 
        e-primaryxaxis-minorGridLines-visible="false" 
        e-primaryxaxis-minorGridLines-width="1"
        e-primaryxaxis-minorTicksPerInterval= "0" >
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {  
                  });
        </script>
    </body>
</html>

{% endhighlight %}

![GridLine Customization](Axis_images/axis_img32.png)


### Tick lines customization

The `e-primaryxaxis-majorTickLines` and `e-primaryxaxis-minorTickLines` properties in the axis are used to customize the major tick lines of an axis and minor tick lines of an axis. They provide options to change the width, size, color and visibility of the grid lines. The minor tick lines are not visible, by default.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
      <div id="container" ej-chart e-primaryxaxis-majorTickLines-color="blue" 
        e-primaryxaxis-majorTickLines-visible="true" 
        e-primaryxaxis-majorTickLines-width="1"
        e-primaryxaxis-majorTickLines-size="5"
        e-primaryxaxis-minorTickLines-color="red" 
        e-primaryxaxis-minorTickLines-visible="false" 
        e-primaryxaxis-minorTickLines-width="1"
        e-primaryxaxis-minorTicksPerInterval= "0"
        e-primaryxaxis-minorTickLines-size="5" >
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {  
                  });
            angular.module('ChartApp', ['ejangular'])
            .controller('ChartCtrl', function ($scope) {
                 
                  });
        </script>
    </body>
</html>

{% endhighlight %}

![TickLine Customization](Axis_images/axis_img33.png)

  
### Inversing axis

Axis can be inversed by using the `e-primaryxaxis-isInversed` property of the axis. The default value of the `e-primaryxaxis-isInversed` property is **false**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart   e-primaryxaxis-isInversed="true">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
             });
        </script>
    </body>
</html>

{% endhighlight %}

**Chart before inversing the axes**

![Before Inversed Axis](Axis_images/axis_img34.png)


**Chart after inversing the axes**

![After Inversed Axis](Axis_images/axis_img35.png)

   

### Place axes at the opposite side

The `e-primaryxaxis-opposedPosition` property of axis can be used to place the axis at the opposite side of its default position. The default value of the `e-primaryxaxis-opposedPosition` property is **false**. 

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart   e-primaryyaxis-opposedPosition="true">
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
            });
        </script>
    </body>
</html>

{% endhighlight %}

**Chart with X and Y axes at normal position**

![Without OpposedPosition](Axis_images/axis_img36.png)


**Chart with Y-axis at opposed position**

![With OpposedPosition](Axis_images/axis_img37.png)


### Maximum number of labels per 100 pixels

A maximum of 3 labels are displayed for each 100 pixels in the axis, by default. The maximum number of labels that is present within the 100 pixels length can be customized by using the `e-primaryxaxis-maximumLabels` property of the axis. This property is applicable only for an automatic range calculation and it does not work when you set the value for `e-primaryxaxis-range-interval` property in the axis range.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart   e-primaryxaxis-maximumLabels="1">
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
             });
        </script>
    </body>
</html>

{% endhighlight %}

**Chart before setting maximum labels per 100 pixels**

![Before setting Maximum Labels](Axis_images/axis_img38.png)


**Chart after setting maximum labels one per 100 pixels**

![After setting Maximum Labels](Axis_images/axis_img39.png)


## Multiple Axis

Multiple axes can be used in the Chart and chart area can be split into multiple panes to draw multiple series with multiple axes.

![Multiple Axis](Axis_images/axis_img40.png)

An additional horizontal or vertical axis can be added to the chart by adding an axis instance to the **axes** collection and then you can associate it to a series by specifying the name of the axis to the `e-xaxisname` or `e-yaxisname` property of the series.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
         <e-axes>
            <e-axis e-name="SecondaryX" e-orientation="vertical" e-opposedposition="true"></e-axis>
            <e-axis e-name="SecondaryY" e-orientation="horizontal" e-opposedPosition="true"></e-axis>
        </e-axes>
         <e-series>
            <e-series e-xaxisname="SecondaryX" e-yaxisname="SecondaryY"></e-series>
            </e-series>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                                });
        </script>
    </body>
</html>

{% endhighlight %}



![Axes Collection](Axis_images/axis_img41.png)



## Smart Axis Labels

When the Axis labels overlap with each other based on the chart dimensions and label size, you can use the `e-primaryxaxis-labelIntersectAction` property of the axis to avoid overlapping. The default value of the `e-primaryxaxis-labelIntersectAction` is **none**. The other available values of the Label Intersect Actions are **rotate45**, **rotate90**, **trim**, **multipleRows**, **wrap**, **wrapByWord** and **hide**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-primaryxaxis-labelIntersectAction="multipleRows">
          </div>
        <script>
             angular.module('ChartApp', ['ejangular'])
             .controller('ChartCtrl', function ($scope) {
                                });
        </script>
    </body>
</html>


{% endhighlight %}



![Smart Axis Labels](Axis_images/axis_img42.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelIntersectAction` property is set as **rotate45**.

![LabelIntersectAction Rotate45](Axis_images/axis_img43.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelIntersectAction` property is set as **rotate90**.

![LabelIntersectAction Rotate90](Axis_images/axis_img44.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelIntersectAction` property is set as **wrap**.

![LabelIntersectAction Wrap](Axis_images/axis_img45.png)


The following screenshot displays the result, when of setting the **trim** as value to the `e-primaryxaxis-labelIntersectAction` property.

![LabelIntersectAction Trim](Axis_images/axis_img46.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelIntersectAction` property is set as **hide**.

![LabelIntersectAction Hide](Axis_images/axis_img47.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelIntersectAction` property is set as **multipleRows **.

![LabelIntersectAction MultipleRows](Axis_images/axis_img48.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelIntersectAction`property is set as **wrapByWord**.

![LabelIntersectAction WrapByWord](Axis_images/axis_img49.png)

## Multi-level Labels
Axis can be customized with multiple levels of labels using the `e-primaryxaxis-multiLevelLabels` property. These labels are placed based on the start and end range values and we can add any number of labels to an axis.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart>
        <e-primaryxaxis-multilevellabels>
        <e-primaryxaxis-multilevellabel e-visible="true" e-text="Quarter1"
         e-start="-0.5" e-end="2.5">
        </e-primaryxaxis-multilevellabel>
        </e-primaryxaxis-multilevellabels>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                });
        </script>
    </body>
</html>


{% endhighlight %}

![MultiLevel Labels](Axis_images/axis_img57.png)

### Customizing the multi-Level labels
The color, width and type of the border can be customized. The default border type is `Rectangle`. And the other supported border types are namely brace, curly brace, without top/bottom border and none. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >  
        <e-primaryxaxis-multilevellabels>
        <e-primaryxaxis-multilevellabel e-border-type="brace" e-border-width="2"
         e-border-color="black">
        </e-primaryxaxis-multilevellabel>
        </e-primaryxaxis-multilevellabels>
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
           
                 });
        </script>
    </body>
</html>

{% endhighlight %}

![MultiLevel Labels Customization](Axis_images/axis_img58.png)

The text of the labels can be customized using the `text` and `font` properties

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-primaryxaxis-multilevellabels>
        <e-primaryxaxis-multilevellabel e-text="Year - 2015" e-font-fontfamily="Algerian" 
        e-font-size="12px" e-font-color="black">
        </e-primaryxaxis-multilevellabel>
        </e-primaryxaxis-multilevellabels>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                 });
        </script>
    </body>
</html>   

{% endhighlight %}

![Text and Font Customization](Axis_images/axis_img59.png)

You can change the alignment of the text to far, near and center position using the `textAlignment` property. By default, the text will be center aligned. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
         <div id="container" ej-chart >
        <e-primaryxaxis-multilevellabels>
        <e-primaryxaxis-multilevellabel e-textalignment="far">
        </e-primaryxaxis-multilevellabel>
        </e-primaryxaxis-multilevellabels>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                 });
     </script>            
    </body>
</html>         

{% endhighlight %}

![MultiLevel Label Alignment](Axis_images/axis_img60.png)

You can trim, wrap or wrapAndTrim the text if it exceeds the maximum text width value using the property `textOverflow`

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart >
        <e-primaryxaxis-multilevellabels>
        <e-primaryxaxis-multilevellabel e-textoverflow="trim" e-maximumtextwidth="40">
        </e-primaryxaxis-multilevellabel>
        </e-primaryxaxis-multilevellabels>
        </div>
        <script>
         angular.module('ChartApp', ['ejangular'])
         .controller('ChartCtrl', function ($scope) {
                 });
       </script>          
    </body>
</html>         

{% endhighlight %}

The below screenshot shows the trimmed multi-level labels

![MultiLevel Label Overflow](Axis_images/axis_img61.png)

And these labels can be placed in various rows using the `level` property.

