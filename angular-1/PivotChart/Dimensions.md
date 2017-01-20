---
layout: post
title: Dimensions
description: dimensions
platform: Angular-1
control: pivotchart
documentation: ug
keywords: ejpivotchart, pivotchart, pivotchart widget, js pivotchart 
---

# Dimensions

## Set size in percentage

You can customize the PivotChart dimension by setting the width and height of the widget in percentage.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-dataSource="dataSource" e-size="size" style="height: 480px; width: 100%;"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            $scope.dataSource = {
                ///...
        };
        $scope.dataSource = $scope.dataSource;
        //Setting size to Chart container
        $scope.size = { height: "80%", width: "80%" };
    });
</script>
</body>

{% endhighlight %}

## Set size in pixels

You can customize the PivotChart dimension by setting the width and height of the widget in pixels.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-dataSource="dataSource" e-size="size" style="height: 460px; width: 950px;"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            $scope.dataSource = {
                ///...
        };
        $scope.dataSource = $scope.dataSource;
        //Setting size to Chart container
        $scope.size = { height: "460px", width: "950px" };
    });
</script>
</body>

{% endhighlight %}

![](Dimensions_images/Dimensions.png) 

## Responsive

PivotChart widget supports responsive rendering based on the target device (desktop & tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in PivotChart by setting `e-isResponsive` property to true.

{% highlight html %}

<div ng-controller="PivotChartCtrl">
    <div id="PivotChart1" ej-pivotchart e-dataSource="dataSource" e-isResponsive ="true" style="height: 460px; width: 950px;"/>
</div>

{% endhighlight %}

![](Dimensions_images/NormalView.png)

_Normal View_

![](Dimensions_images/ResponsiveView.png)

_ResponsiveView_