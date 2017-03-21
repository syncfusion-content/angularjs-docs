---
layout: post
title: Sunburst Zooming
description: Learn how to Zoom the SunburstChart for better data visualization
platform: ts
control: Sparkline
documentation: ug
---

# Zooming

Sunburst chart provides zooming (drill down) experience with animation for both mouse and touch enabled devices. It allows you to virtualize large sets of data into minimum data view.The zooming is achieved by using the property of `e-zoomsettings`

The following code shows how to initialize the zooming.

{% highlight js %}

<div id="container" ej-sunburstchart e-zoomsettings-enable="true">					
</div>

{% endhighlight %}

![](Zooming_images/Zooming_img1.gif)

## Zooming toolbar
By default, zooming toolbar will be enabled while zooming the segment.It contains both back and reset option.
You can align the zooming toolbar position by using `e-zoomsettings-toolbarHorizontalAlignment` and `e-zoomsettings-toolbarVerticalAlignment` property.


{% highlight js %}

<div id="container" ej-sunburstchart e-zoomsettings-enable="true" e-zoomsettings-toolbarhorizontalalignment="left"> 					
</div>

{% endhighlight %}

![](Zooming_images/Zooming_img2.png)

[Click](http://ngjq.syncfusion.com/#/sunburstchart/zooming) here to view the online demo sample of Zooming in the Sunburst Chart.
