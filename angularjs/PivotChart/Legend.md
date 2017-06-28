---
layout: post
title: Legend
description: legend
platform: AngularJS
control: pivotchart
documentation: ug
keywords: ejpivotchart, pivotchart, pivotchart widget, js pivotchart 
---

# Legend

## Legend Visibility

You can enable or disable legend using the [`visible`](/api/js/ejchart#members:legend-visible) property inside the `e-legend` object. By default, legend is enabled in PivotChart.

N> By default, the legend is visible in PivotChart.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-legend="legend"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.legend = {
                //Legend Visibility 
                visible: true
            };
        });
    </script>
</body>

{% endhighlight %}

![](Legend_images/Legend_img1.png) 

## Legend Shape
You can customize the legend [`shape`](/api/js/ejchart#members:legend-shape) in PivotChart widget. Default value of legend shape is “Rectangle”. Following legend shapes that are supported:

* Rectangle
* Circle
* Cross
* Diamond
* Pentagon
* Hexagon
* Star
* Ellipse
* Triangle etc.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-legend="legend"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.legend = {
                //Legend Visibility 
                visible: true,
                //Applying Legend Shape
                shape: "Star"
            };
        });
    </script>
</body>

{% endhighlight %}

![](Legend_images/Legend_img2.png) 

## Legend Position
By using the [`position`](/api/js/ejchart#members:legend-position) property, you can place the legend at top, bottom, left or right of the PivotChart. 

N> Default value of legend position is “bottom” in PivotChart.

{% highlight javascript %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-legend="legend"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.legend = {
                //Legend Visibility 
                visible: true,
                //To place the legend at top of the Chart
                position: "top"
            };
        });
    </script>
</body>

{% endhighlight %}

![](Legend_images/Legend_img3.png) 

## Legend Title
To add the legend title, you have to specify the title text in [`title.text`](/api/js/ejchart#members:legend-title-text) property.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-legend="legend"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.legend = {
                //Legend Visibility 
                visible: true,
                //Add title to the Chart legend
                title: {
                    text: "Countries"
                }   
            };
        });
    </script>
</body>

{% endhighlight %}

![](Legend_images/Legend_img4.png) 

## Legend Alignment
You can align the legend to center, far and near based on its position in the Chart area using the [`alignment`](/api/js/ejchart#members:legend-alignment) option.
 
{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-legend="legend"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.legend = {
                //Legend Visibility 
                visible: true,
                //Aligning the legend near to the Chart
                alignment: "Near"
            };
        });
    </script>
</body>

{% endhighlight %}

![](Legend_images/Legend_img5.png)

## Legend Items - Size and Border
By using the legend [`itemStyle.width`](/api/js/ejchart#members:legend-itemstyle-width), [`itemStyle.height`](/api/js/ejchart#members:legend-itemstyle-height) and [`itemStyle.border`](/api/js/ejchart#members:legend-itemstyle-border) properties, you can change the legend items - size and border.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-legend="legend"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.legend = {
                //Legend Visibility 
                visible: true,
                //Changing legend items border, height and width
                itemStyle: {
                    height: 12,
                    width: 12,
                    border:
                    {
                        color: 'magenta',
                        width: 1.5
                    }
                }
            };
        });
    </script>
</body>

{% endhighlight %}

![](Legend_images/Legend_img6.png)
 
## Legend Border
By using the [`border`](/api/js/ejchart#members:legend-border) option in legend, you can customize border color and width.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-legend="legend"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.legend = {
                //Legend Visibility 
                visible: true,
                //Setting border color and width to legend
                border: {
                    color: "#FFC342",
                    width: 2
                }
            };
        });
    </script>
</body>

{% endhighlight %}

![](Legend_images/Legend_img7.png)

## Legend Text
By using the [`font`](/api/js/ejchart#members:legend-font) option, you can customize the font family, font style, font weight and size of the legend text. 

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-legend="legend"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.legend = {
                //Legend Visibility 
                visible: true,
                //Customizing the legend text
                font:
                {
                    fontFamily: 'Segoe UI',
                    fontStyle: 'italic',
                    fontWeight: 'bold',
                    size: '13px'
                }
            };
        });
    </script>
</body>

{% endhighlight %}

![](Legend_images/Legend_img8.png)