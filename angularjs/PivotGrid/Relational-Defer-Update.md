---
layout: post
title: Defer-Update
description: defer update
platform: AngularJS
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Defer Update

I> This feature is applicable for Relational datasource only at Server Mode.

Defer Update support allows you to refresh the control only on-demand and not during every UI interaction.

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-url="url" e-pivotTableFieldListID="pivotTableFieldListID" />
    <div id="PivotSchemaDesigner1" ej-pivotschemadesigner="" ></div>
</div>
<script>
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        $scope.url = "/Relational";
        $scope.pivotTableFieldListID = "PivotSchemaDesigner1";
    });
</script>
  
{% endhighlight %}

![](Defer-Update_images/relationaldeferupdate.png) 



