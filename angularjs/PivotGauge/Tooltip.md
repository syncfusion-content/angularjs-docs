---
layout: post
title: Tooltip
description: tooltip
platform: Angular-1
control: PivotGauge
documentation: ug
keywords: ejPivotGauge, PivotGauge, PivotGauge widget, js PivotGauge 
---

# Tooltip

Tooltip can be enabled by using the `e-enableTooltip` property. 

N> By default, this property is set to "false".

{% highlight javascript %}

<div ng-controller="PivotGaugeCtrl">
    <div id="PivotGauge1" ej-pivotgauge e-enableTooltip="true" />
</div>

{% endhighlight %}

Tooltip appearance can be customized by overriding its CSS class.

{% highlight css %}

    .e-pivotgauge-tooltip {
        background-color: aqua!important;
        border: 2 px solid red!important;
        color: black!important;
        border-radius: 18 px!important;
        margin-top: 20 px;
        text-align: left;
        font: 12 px Segoe UI;
        line-height: 20 px;
    }

{% endhighlight %}
    
![](Tooltip_images/Tooltip.png) 

