---
layout: post
title: Responsive-Layout
description: responsive layout
platform: AngularJS
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Responsive Layout

PivotClient widget supports responsive rendering based on the target device (desktop & tablet) resolution. It supports resolution up to 1024x600. You can enable responsiveness in PivotClient by setting `e-isResponsive` property to true.

{% highlight javascript %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient  e-isResponsive="true" />
</div>

{% endhighlight %}

![](Responsive-Layout_images/responsive.png)




