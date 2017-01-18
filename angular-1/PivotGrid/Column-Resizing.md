---
layout: post
title:  Column Resizing
description: column resizing
platform: Angular-1
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Column Resizing

Allows you to resize the column by changing its width while holding and dragging the column border using the mouse.

You can enable column resizing option in PivotGrid by setting the `e-enableColumnResizing` property to true.

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-enableColumnResizing="true" />
</div>

{% endhighlight %} 

![](Column-Resizing_images/columnresizing.png)