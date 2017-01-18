---
layout: post
title: Responsive-Layout
description: responsive layout
platform: Angular-1
control: PivotGauge
documentation: ug
keywords: ejPivotGauge, PivotGauge, PivotGauge widget, js PivotGauge 
---

# Responsive Layout

PivotGauge widget supports responsive rendering based on the target device (desktop & tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in PivotGauge by setting `e-isResponsive` property to true.

{% highlight javascript %}

<div ng-controller="PivotGaugeCtrl">
    <div id="PivotGauge1" ej-pivotgauge e-isResponsive="true" />
</div>

{% endhighlight %}

![](Responsive-Layout_images/Responsive1.png)

_Normal View_


![](Responsive-Layout_images/Responsive2.png)

_Responsive View_





