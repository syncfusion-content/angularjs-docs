---
layout: post
title: ToolTip
description: ToolTip
platform: AngularJS
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# ToolTip

Allows you to display the details of the cell on hovering value cells. By default, tooltip is enabled.  You can disable tooltip in PivotGrid by setting the `e-enableToolTip`  property to false.

{% highlight javascript %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient  e-enableToolTip=false />
</div

{% endhighlight %}

## ToolTip Animation

The PivotGrid provides option to animate tooltip displayed in the grid. The animation enhances the appearance of tooltip by displaying it slowly.  You can enable animation in tooltip by setting `e-enableToolTipAnimation` property to true.

{% highlight js %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient  e-enableToolTipAnimation=true />
</div

{% endhighlight %}

![](ToolTip_images/ToolTip.png)

