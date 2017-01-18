---
layout: post
title: ExcelLikeLayout
description: excellikelayout
platform: Angular-1
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# ExcelLikeLayout

A layout in which summary cells are positioned besides each parent member and their child members appear next to them. The `e-layout` enumeration needs to be set to **ej.PivotGrid.Layout.ExcelLikeLayout** in-order to view PivotGrid in excel-like layout.

I> We provide excel-like layout support for both OLAP and Relational data sources in client and server mode. 

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-layout="layout"  />
</div>
<script>   
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) {
        ///...
        $scope.layout = ej.PivotGrid.Layout.ExcelLikeLayout;
    });
</script>

{% endhighlight %}

![](ExcelLikeLayout_images/layout-excel-relational.png)

![](ExcelLikeLayout_images/layout-excel-olap.png)

