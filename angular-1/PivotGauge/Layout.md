---
layout: post
title: Layout
description: layout 
platform: Angular-1
control: PivotGauge
documentation: ug
keywords: ejPivotGauge, PivotGauge, PivotGauge widget, js PivotGauge 
---

# Layout

## Row-wise Layout 

Gauges can be arranged in specified number of rows by using the `e-rowsCount` property.

{% highlight javascript %}

<div ng-controller="PivotGaugeCtrl">
    <div id="PivotGauge1" ej-pivotgauge e-rowsCount=2 />
</div>

{% endhighlight %}

![](Layout_images/Row-wiseLayout.png) 

## Column-wise Layout

Gauges can be arranged in specified number of columns by using the `e-columnsCount` property.

{% highlight javascript %}

<div ng-controller="PivotGaugeCtrl">
    <div id="PivotGauge1" ej-pivotgauge e-columnsCount=2 />
</div>

{% endhighlight %}

![](Layout_images/Column-wiseLayout.png)

