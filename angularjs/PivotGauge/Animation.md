---
layout: post
title: Animation
description: animation
platform: Angular-1
control: PivotGauge
documentation: ug
keywords: ejPivotGauge, PivotGauge, PivotGauge widget, js PivotGauge 
---

# Animation

The animation option makes the pointer to rotate from minimum value to actual value with animation effects.  Animation could be enabled/disabled by using the `e-enableAnimation` property.  Speed of the pointer could be controlled by using the `e-animationSpeed` property. Time is represented in milliseconds.

{% highlight javascript %}

<div ng-controller="PivotGaugeCtrl">
    <div id="PivotGauge1" ej-pivotgauge e-enableAnimation="true" e-animationSpeed=1000 />
</div>

{% endhighlight %}