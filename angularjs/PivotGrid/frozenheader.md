---
layout: post
title:  Frozen Header
description:  frozen header
platform: AngularJS
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Frozen Header

Allows you to freeze the header of the Grid so that it will be always visible when scrolling the content with a large number of rows or columns providing a precise view.

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-frozenHeaderSettings="frozenHeaderSettings" />
</div>
<script>   
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) {
        ///...
        $scope.frozenHeaderSettings = {
            enableFrozenHeaders : true
        };
    });
</script>

{% endhighlight %}

![](FrozenHeader_images/row_col_freeze.png)

We can also freeze the row/column headers individually by setting the below properties.

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-frozenHeaderSettings="frozenHeaderSettings" />
</div>
<script>   
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) {
        ///...
        $scope.frozenHeaderSettings = {
            enableFrozenRowHeaders : true   //To Freeze the Row headers only
        };
    });
</script>
    
{% endhighlight %}

![](FrozenHeader_images/row_freeze.png)

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-frozenHeaderSettings="frozenHeaderSettings" />
</div>
<script>   
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) {
        ///...
        $scope.frozenHeaderSettings = {
            enableFrozenColumnHeaders : true  //To Freeze the Column headers only
        };
    });
</script>

{% endhighlight %}

![](FrozenHeader_images/col_freeze.png)