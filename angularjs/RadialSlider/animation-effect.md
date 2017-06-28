---
layout: post
title: animation effect
description: animation effect
platform: Angular-1
control: Radial Slider
documentation: ug
---

## Animation Effect

The animation effect for the **RadialSlider** can be enabled or disabled using the **e-enableanimation** property. By default, it is set as **true**, so that the handle movement will be animated.

{% highlight html %}

<div id="angularRadialSlider" ej-radialslider e-enableanimation="animation" e-innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"></div>

{% endhighlight %}

Add the following script in your code and this will stop the handle movement’s animation.

{% highlight js %}

syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.animation = false;
    });

{% endhighlight %}

