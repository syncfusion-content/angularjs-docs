---
layout: post
title: Defer-Update
description: defer update
platform: Angular-1
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Defer Update

I> This feature is applicable only for OLAP data source bound from server-side.

Defer Update support allows the user to refresh the control on-demand and not during every user interaction. To enable this functionality, set the `e-enableDeferUpdate` property to true. By default, the value is set to false.

{% highlight javascript %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient e-enableDeferUpdate="true" />
</div>

{% endhighlight %}

After enabling this property, an icon for Defer Update will appear inside the toolbar.

![](Defer-Update_images/Before-defer-update.png)

On clicking the icon, after making the necessary UI interactions, the PivotGrid and PivotChart controls will be updated according to the OlapReport available at that instant.

![](Defer-Update_images/after-defer-update.png)

