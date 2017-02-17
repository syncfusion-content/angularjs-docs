---
layout: post
title: Value-Sorting
description: value Sorting
platform: Angular-1
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Value Sorting

I> This feature is applicable for Relational datasource only at Client Mode.

Value Sorting allows to sort columns and rows based on value fields.

The headers of the column to be sorted is given in the 'headerText' property under 'valueSortSettings' in field wise order separated by a string.  The string which is used to separate the headers is given in the property 'headerDelimiters'.

{% highlight js %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-dataSource="dataSource" e-valueSortSettings="valueSortSettings"/>
</div>
<script>
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) {
        //..
        $scope.valueSortSettings = {
            headerText: "Bike##Quantity",
            headerDelimiters: "##",
            sortOrder: ej.PivotAnalysis.SortOrder.Descending
        };
    });
</script>

{% endhighlight %}

![](Value-Sorting_images/Before.png) 

![](Value-Sorting_images/After.png) 



