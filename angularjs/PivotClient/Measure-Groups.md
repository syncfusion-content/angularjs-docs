---
layout: post
title: Measure-Groups
description: measure groups 
platform: AngularJS
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Measure Groups 

I> This feature is applicable only for OLAP data source bound from server-side.

In Cube Dimension Browser, treeview can be viewed in a filtered manner through the Measure Groups option. This feature allows you to view the list of measures and dimensions associated with the selected measure group from the cube. For enabling this, the `e-enableMeasureGroups` property is set to true. By default, its value is set to false.

{% highlight javascript %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" e-url="url" ej-pivotclient e-enableMeasureGroups="true" />
</div>
<script>
    angular.module('PivotClientApp', ['ejangular']).controller('PivotClientCtrl', function ($scope) {
        //..
        $scope.url = "/Olap"
    });
</script>

{% endhighlight %}

On selecting a measure group from the drop-down list, the Cube Dimension Browser treeview displays the related measures and dimensions alone as follows.

![](Measure-Groups_images/beforemeasure.png)

![](Measure-Groups_images/aftermeasure.png)

