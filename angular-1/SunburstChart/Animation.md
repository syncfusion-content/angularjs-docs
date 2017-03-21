---
layout: post
title: Animation
description: Learn how to animate the SunburstChart .
platform: Angular 1
control: SunburstChart
documentation: ug
---

# Animation

Sunburst chart allows you to animate the chart segments. You can enable animation using **e-enableanimation** property. 

{% highlight html %}

<div id="container" ej-sunburstchart e-enableanimation="true" >					
</div>


{% endhighlight %}


## Animation Types 
Sunburst chart provide options to animate the chart segments in different ways using **e-animationtype** property.
FadeIn – It gradually changes opacity of the chart segment.
Rotation – During an animation, control rotate from 0 to 360 angle.

### Fade In

The Fade In animation is enabled as follows 

{% highlight html %}

<div id="container" ej-sunburstchart e-enableanimation="true" e-animationtype="fadeIn" >					
</div>


{% endhighlight %}

![](Animation_images/Animation_img1.gif)


### Rotation

The following example shows how to enable rotation animation in ejSunburstChart

{% highlight html %}

<div id="container" ej-sunburstchart e-enableanimation="true" e-animationtype="rotation" >					
</div>

{% endhighlight %}

![](Animation_images/Animation_img2.gif)

[Click](http://ngjq.syncfusion.com/#/sunburstchart/animation) here to view the online demo sample of  Animation in  the Sunburst Chart.
