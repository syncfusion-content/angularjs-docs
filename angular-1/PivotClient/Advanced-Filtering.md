---
layout: post
title: Advanced Filtering and Sorting
description: advanced filtering and sorting
platform: Angular-1
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Advanced Filtering & Sorting

It allows to filter and sort the field members in PivotClient.

### Client Mode

In client mode, you can enable Advanced Filtering and Sorting option in PivotClient by setting the `enableAdvancedFilter` property under `e-dataSource` to true.

{% highlight html %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient e-dataSource="dataSource" />
</div>
<script>   
    angular.module("PivotClientApp",["ejangular"]).controller('PivotClientCtrl', function ($scope) 
    {
        $scope.dataSource = {
            //..
            enableAdvancedFilter: true
        }
    });
</script>

{% endhighlight %}

### Server Mode

In server mode, you can enable the Advanced Filtering and Sorting option in PivotClient by setting the `e-enableAdvancedFilter` property to true

{% highlight html %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient e-enableAdvancedFilter=true />
</div>

{% endhighlight %}

## Sorting

Sorting provides an option to sort the members of a field either in ascending or descending order. 

I> This feature is not applicable for OLAP datasource bound from server-side. 

![](AdvanceFiltering_images/sorting.png)

## Label Filtering

Label filtering provides an option to filter the members of a field purely based on their caption. 

![](AdvanceFiltering_images/filtering.png)

![](AdvanceFiltering_images/filtering_dialog.png)


## Value Filtering

Value filtering provides an option to filter members based on the total values of the appropriate measure between the members of the level. 

![](AdvanceFiltering_images/valuefilter.png)

![](AdvanceFiltering_images/valuefilter_dialog.png)
