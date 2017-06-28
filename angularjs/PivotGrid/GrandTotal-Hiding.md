---
layout: post
title:  GrandTotal Hiding
description: GrandTotal Hiding
platform: AngularJS
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Grand Total Hiding

Grand Total Hiding can be classified into three categories.

* Row Grand Total Hiding
* Column Grand Total Hiding
* Both

## Row Grand Total Hiding

You can hide the **Grand Total** in row alone by setting the property `e-enableRowGrandTotal` to `false`

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-enableRowGrandTotal="false" />
</div>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableRowGrandTotal.png)

## Column Grand Total Hiding

You can hide the **Grand Total** in column alone by setting the property `e-enableColumnGrandTotal` to `false`

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-enableColumnGrandTotal="false" />
</div>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableColumnGrandTotal.png)

## Both

You can hide the **Grand Total** in both row and column by setting the property `e-enableGrandTotal` to `false`

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-enableGrandTotal="false" />
</div>

{% endhighlight %}

![](GrandTotal-Hiding_images/enableGrandTotal.png)