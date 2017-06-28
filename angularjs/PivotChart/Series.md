---
layout: post
title: Series
description: series
platform: AngularJS
control: pivotchart
documentation: ug
keywords: ejpivotchart, pivotchart, pivotchart widget, js pivotchart 
---

# Series

## Series Point Customization
By using the [`fill`](/api/js/ejchart#members:series-fill) and [`border`](/api/js/ejchart#members:series-border) properties of Chart series, you can customize the PivotChart series color, border color and border width.
 
{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-commonSeriesOptions="commonSeriesOptions" e-seriesRendering="seriesRendering"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.commonSeriesOptions = {
                type: ej.PivotChart.ChartTypes.Column
            };
            $scope.seriesRendering = function(args){
                this.model.series[0].points[0].fill = "aqua";
                this.model.series[0].points[0].border = {
                    color: "black",
                    width: 2
                };
            };
        });
    </script>
</body>

{% endhighlight %}

![](Series_images/Series_img1.png)