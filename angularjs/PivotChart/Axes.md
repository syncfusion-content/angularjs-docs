---
layout: post
title: Axes
description: axes 
platform: AngularJS
control: pivotchart
documentation: ug
keywords: ejpivotchart, pivotchart, pivotchart widget, js pivotchart 
---

# Axes 

## Label Format

### Format Numeric labels
By using the [`labelFormat`](/api/js/ejchart#members:primaryyaxis-labelformat) property, you can format the numeric labels. Numeric values can be formatted with n (number with decimal points), c (currency) and p (percentage) commands.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.primaryYAxis = {
                //... 
                //Applying currency format to Y-Axis labels
                labelFormat: 'c'
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/FormatNumericLabels.png)

Following table describes the result on applying some commonly used label formats on numeric values.

<table>
<tr>
<th>Label Value</th>
<th>Label Format Property Value</th>
<th>Result</th>
<th>Description</th>
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

### Label Format Customization 
By using the [`labelFormat`](/api/js/ejchart#members:primaryyaxis-labelformat) property of `e-primaryYaxis`, you can add the category labels with prefix and/or suffix. 

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.primaryYAxis = {
                //... 
                //Adding prefix and suffix to Y-axis labels
                labelFormat: '${value} K'
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/LabelFormatCustomization.png)

## Common Axis Features

### Axis Visibility
Axis visibility can be set by using the [`visible`](/api/js/ejchart#members:primaryyaxis-visible) property of the respective axis. 

N> By default, the value of [`visible`](/api/js/ejchart#members:primaryyaxis-visible) property is true in PivotChart.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.primaryYAxis = {
                //... 
                //Disabling visibility of Y-axis
                visible: false
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/AxisVisibility.png)

### Label Customization
By using the [`font`](/api/js/ejchart#members:primaryxaxis-font) property of the axis, we can customize the labels ??? font family, color, opacity, size and font-weight.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.primaryYAxis = {
                //Customizing label appearance
                font:
                {
                    fontFamily: 'Segoe UI',
                    size: '14px',
                    fontWeight: 'bold',
                    color: 'blue'
                }
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/LabelCustomization.png)

### Label and Tick Positioning
Axis labels and ticks can be positioned inside or outside the Chart area by using the [`labelPosition`](/api/js/ejchart#members:primaryxaxis-labelposition) and [`tickLinesPosition`](/api/js/ejchart#members:primaryxaxis-ticklinesposition) properties. The labels and ticks are positioned outside the Chart area, by default.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.primaryYAxis = {
                //Customizing label and tick positions
                labelPosition: 'inside',
                tickLinesPosition: 'inside'
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/LabelAndTickPositioning.png)

### Grid Lines Customization
By using the [`majorGridLines`](/api/js/ejchart#members:primaryxaxis-majorgridlines) and [`minorGridLines`](/api/js/ejchart#members:primaryxaxis-minorgridlines) properties of the axis, you can customize the width, color, visibility and opacity of the grid lines.

N> By default, the minor grid lines are not visible in PivotChart.


{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.primaryYAxis = {
                //Customizing Grid Lines
                majorGridLines:
                {
                    color: 'blue',
                    visible: true,
                    width: 5
                },
                minorTicksPerInterval: 1,
                minorGridLines:
                {
                    color: 'red',
                    visible: true,
                    width: 5
                }
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/GridLinesCustomization.png)

### Tick Lines Customization
By using the [`majorTickLines`](/api/js/ejchart#members:primaryxaxis-majorticklines) and [`minorTickLines`](/api/js/ejchart#members:primaryxaxis-minorgridlines) properties of the axis, you can customize the width, color, visibility, size and opacity of the tick lines.

N> By default, the minor tick lines are not visible in PivotChart.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.primaryYAxis = {
                //Customizing Tick Lines
                majorTickLines:
                {
                    color: 'blue',
                    visible: true,
                    width: 10,
                    size: 15,
                },
                minorTicksPerInterval: 1,
                minorTickLines:
                {
                    color: 'red',
                    visible: true,
                    width: 20,
                    size: 15
                }
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/TickLinesCustomization.png)

### Inversing Axes
Axes can be inversed by using the [`isInversed`](/api/js/ejchart#members:primaryxaxis-isinversed) property of the respective axis.

N> By default, the [`isInversed`](/api/js/ejchart#members:primaryyaxis-isinversed) property is false in PivotChart.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.primaryYAxis = {
                //... 
                primaryXAxis:
                {
                    //Inversing the X-axis
                    isInversed: true
                },
                primaryYAxis:
                {
                    //Inversing the Y-axis
                    isInversed: true
                }
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/InversingAxes.png)

### Placing Axes at Opposite Side
The [`opposedPosition`](/api/js/ejchart#members:primaryxaxis-opposedposition) property of Chart axis can be used to place the axis at the opposite direction from its default position.

N> By default, the [`opposedPosition`](/api/js/ejchart#members:primaryyaxis-opposedposition) property is false in PivotChart.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryXAxis="primaryXAxis" e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.primaryYAxis = {
                //Placing Y-axis at the opposite side of its normal position
                opposedPosition: true
            };
            $scope.primaryXAxis = {
                //Placing X-axis at the opposite side of its normal position
                opposedPosition: true
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/PlacingAxesAtOppositeSide.png)

## Smart Axis Labels

When the axis labels overlap with each other based on the Chart dimensions and label size, you can use [`labelIntersection`](/api/js/ejchart#members:primaryxaxis-labelintersectaction) property of the axis to avoid overlapping. 

N> By default, the [`labelIntersection`](/api/js/ejchart#members:primaryxaxis-labelintersectaction) property is none in PivotChart.

The following options that are supported for `labelIntersection` property are: 

* rotate45
* rotate90
* trim
* multipleRows
* wrap
* hide. 

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryXAxis="primaryXAxis" e-primaryYaxis="primaryYAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            // Avoid overlapping of X-axis labels
            $scope.primaryXAxis = {
                labelIntersectAction: 'multipleRows'
            };
        });
    </script>
</body>

{% endhighlight %}

![](Chart-Axes_images/SmartAxisLabels.png)