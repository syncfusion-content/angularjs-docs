---
layout: post
title: Grid-Layout
description: Layouts
platform: AngularJS
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Grid Layout

## Normal Layout

A layout in which summary cells are positioned at the bottom of each parent member and their child members appear next to them. Normal layout is the default layout in PivotGrid control. The enumeration property `e-layout` needs to be set to **"ej.PivotGrid.Layout.Normal"** in-order to view PivotGrid in normal layout. 

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-url="url" e-layout="layout" />
</div>
<script>   
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        $scope.url = "/Olap";
        $scope.layout = ej.PivotGrid.Layout.Normal;
    });
</script>

{% endhighlight %}

![](Grid-Layout_images/layout-normal.png)

## No Summaries Layout

I> This feature is applicable only for OLAP datasource.

A layout in which summary cells are completely hidden and the child members appear next to their parent member.  The enumeration property `e-layout` needs to be set to **"ej.PivotGrid.Layout.NoSummaries"** in-order to view PivotGrid without summaries.

{% highlight js %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-layout="layout" />
</div>
<script>   
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        //..
        $scope.layout = ej.PivotGrid.Layout.NoSummaries;
    });
</script>

{% endhighlight %}
 
![](Grid-Layout_images/layout-nosummary.png)

## Excel-like Layout
A layout in which summary cells are positioned besides each parent member and their child members appear next to them. The enumeration property `e-layout` needs to be set to **"ej.PivotGrid.Layout.ExcelLikeLayout"** in-order to view PivotGrid in excel-like layout.

{% highlight js %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-layout="layout" />
</div>
<script>   
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        //..
        $scope.layout = ej.PivotGrid.Layout.ExcelLikeLayout;
    });
</script>

{% endhighlight %}

![](Grid-Layout_images/layout-excel.png)

## Top Summary Layout

I> This feature is applicable only for OLAP datasource only at Server Mode.

A layout in which summary cells are positioned at the top of each parent member and their child members appear next to them. The enumeration property `e-layout` needs to be set to **"ej.PivotGrid.Layout.NormalTopSummary"** in-order to view PivotGrid in top summaries layout.

{% highlight js %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-url="url" e-layout="layout" />
</div>
<script>   
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        $scope.url = "/Olap";
        $scope.layout = ej.PivotGrid.Layout.NormalTopSummary;
    });
</script>

{% endhighlight %}

![](Grid-Layout_images/layout-top.png)

