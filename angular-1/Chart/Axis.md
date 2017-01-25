---
layout: post
title: Chart Axis
description: How to customize the grid lines, tick lines, labels and title of chart axis
platform: Angular 1.0
control: Chart
documentation: ug
---

# Axis

**Charts** typically have two axes that are used to measure and categorize data: a vertical (y) axis, and a horizontal (x) axis.

Vertical axis always uses numerical or logarithmic scale. Horizontal(x) axis supports the following types of scale:

* Category
* Numeric
* DateTime
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



![](Axis_images/axis_img1.png)


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

![](Axis_images/axis_img2.png)


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

![](Axis_images/axis_img3.png)


### Indexed Category Axis

Category axis can also plot points based on index value of data points. Index based plotting can be enabled by setting `e-primaryxaxis-isindexed` property to true in the axis.


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


![](Axis_images/axis_img50.png)

**While Category axis isIndexed value false**

![](Axis_images/axis_img51.png)


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



![](Axis_images/axis_img4.png)


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


![](Axis_images/axis_img5.png)


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

![](Axis_images/axis_img6.png)

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

![](Axis_images/axis_img7.png)


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

![](Axis_images/axis_img8.png)



**Chart after rounding axis range**

![](Axis_images/axis_img9.png)

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

![](Axis_images/axis_img10.png)


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

![](Axis_images/axis_img11.png)


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

![](Axis_images/axis_img12.png)




 
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

![](Axis_images/axis_img13.png)


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


![](Axis_images/axis_img14.png)


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

![](Axis_images/axis_img15.png)

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

![](Axis_images/axis_img16.png)


**Chart after rounding axis range**

![](Axis_images/axis_img17.png)

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

![](Axis_images/axis_img18.png)


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


![](Axis_images/axis_img19.png)




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

![](Axis_images/axis_img20.png)

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

![](Axis_images/axis_img21.png)


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

![](Axis_images/axis_img22.png)


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

![](Axis_images/axis_img23.png)

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

![](Axis_images/axis_img24.png)


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

![](Axis_images/axis_img25.png)


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

![](Axis_images/axis_img52.png)


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

![](Axis_images/axis_img53.png)

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

![](Axis_images/axis_img54.png)


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
![](Axis_images/axis_img55.png)


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

![](Axis_images/axis_img56.png)


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

![](Axis_images/axis_img26.png)


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


![](Axis_images/axis_img27.png)

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

![](Axis_images/axis_img62.png)

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

![](Axis_images/axis_img28.png)


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
 


![](Axis_images/axis_img29.png)


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

![](Axis_images/axis_img30.png)


**Chart after setting edge label placement to X-axis**

![](Axis_images/axis_img31.png)


### Grid lines customization

The `e-primaryxaxis-majorGridLines` and `e-primaryxaxis-minorGridLines` properties in the axis are used to customize the major grid lines and minor grid lines of an axis. They provide options to change the width, color, visibility and opacity of the grid lines. The minor grid lines are not visible, by default.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-primaryxaxis-majorgridlines-color="blue" 
        e-primaryxaxis-majorgridlines-visible="true" 
        e-primaryxaxis-majorgridlines-width="1"
        e-primaryxaxis-minorgridlines-color="red" 
        e-primaryxaxis-minorgridlines-visible="false" 
        e-primaryxaxis-minorgridlines-width="1"
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

![](Axis_images/axis_img32.png)


### Tick lines customization

The `e-primaryxaxis-majorTickLines` and `e-primaryxaxis-minorTickLines` properties in the axis are used to customize the major tick lines of an axis and minor tick lines of an axis. They provide options to change the width, size, color and visibility of the grid lines. The minor tick lines are not visible, by default.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
      <div id="container" ej-chart e-primaryxaxis-majorticklines-color="blue" 
        e-primaryxaxis-majorticklines-visible="true" 
        e-primaryxaxis-majorticklines-width="1"
        e-primaryxaxis-majorticklines-size="5"
        e-primaryxaxis-minorticklines-color="red" 
        e-primaryxaxis-minorticklines-visible="false" 
        e-primaryxaxis-minorticklines-width="1"
        e-primaryxaxis-minorTicksPerInterval= "0"
        e-primaryxaxis-minorticklines-size="5" >
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

![](Axis_images/axis_img33.png)

  
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

![](Axis_images/axis_img34.png)


**Chart after inversing the axes**

![](Axis_images/axis_img35.png)

   

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

![](Axis_images/axis_img36.png)


**Chart with Y-axis at opposed position**

![](Axis_images/axis_img37.png)


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

![](Axis_images/axis_img38.png)


**Chart after setting maximum labels one per 100 pixels**

![](Axis_images/axis_img39.png)


## Multiple Axis

Multiple axes can be used in the Chart and chart area can be split into multiple panes to draw multiple series with multiple axes.

![](Axis_images/axis_img40.png)

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



![](Axis_images/axis_img41.png)



## Smart Axis Labels

When the Axis labels overlap with each other based on the chart dimensions and label size, you can use the `e-primaryxaxis-labelintersectaction` property of the axis to avoid overlapping. The default value of the `e-primaryxaxis-labelintersectaction` is **none**. The other available values of the Label Intersect Actions are **rotate45**, **rotate90**, **trim**, **multipleRows**, **wrap**, **wrapByWord** and **hide**.

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



![](Axis_images/axis_img42.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelintersectaction` property is set as **rotate45**.

![](Axis_images/axis_img43.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelintersectaction` property is set as **rotate90**.

![](Axis_images/axis_img44.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelintersectaction` property is set as **wrap**.

![](Axis_images/axis_img45.png)


The following screenshot displays the result, when of setting the **trim** as value to the `e-primaryxaxis-labelintersectaction` property.

![](Axis_images/axis_img46.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelintersectaction` property is set as **hide**.

![](Axis_images/axis_img47.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelintersectaction` property is set as **multipleRows **.

![](Axis_images/axis_img48.png)


The following screenshot displays the result, when the `e-primaryxaxis-labelintersectaction`property is set as **wrapByWord**.

![](Axis_images/axis_img49.png)

## Multi-level Labels
Axis can be customized with multiple levels of labels using the `e-primaryxaxis-multilevellabels` property. These labels are placed based on the start and end range values and we can add any number of labels to an axis.

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

![](Axis_images/axis_img57.png)

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

![](Axis_images/axis_img58.png)

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

![](Axis_images/axis_img59.png)

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

![](Axis_images/axis_img60.png)

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

![](Axis_images/axis_img61.png)

And these labels can be placed in various rows using the `level` property.

