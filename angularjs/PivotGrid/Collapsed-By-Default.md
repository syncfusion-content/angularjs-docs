---
layout: post
title: Collapse by default
description: Collapse by default
platform: Angular-1
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Collapse by default

I> This feature is applicable only for Relational datasource.

Allows you to collapse all members displayed in the grid. You can enable collapsing all members by default in PivotGrid by setting `e-enableCollapseByDefault` property to true.

{% highlight js %}
   
<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient  e-enableCollapseByDefault=true />
</div

{% endhighlight %}

![](Collapsed-By-Default_images/Collapse-members.png)

