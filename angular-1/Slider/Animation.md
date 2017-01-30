---
layout: post
title: Animation
description: animation
platform: angular-1
control: Slider
documentation: ug
---

# Animation

This feature includes the animation effect for the **Slider** when moving the **Slider** handle.

## Enabling Animation

By default, animation is enabled in the **Slider**. Using the **enableAnimation** property you can enable/disable the animation effects. Data type of this property is “Boolean”.

The following steps explains you on how to disable the animation effect in **Slider**.

In the **HTML** page, specify the **<div>** elements to render the “Default Slider”.



{% highlight html %}

<div class="txt">Default Slider</div>
<div id="defaultSlider" ej-slider e-value="60" e-enableAnimation="false"></div>

{% endhighlight %}

{% highlight javascript %}

 angular.module('sliderApp', ['ejangular'])
        .controller('SliderCtrl', function ($scope) {
   });

{% endhighlight %}

## Customizing Animation speed

Animation speed of the **Slider** indicates the speed at which the slider handle can be moved. Higher the value specified for this property decreases the rate of speed at which the **Slider** handle can be moved. You can customize the animation speed of the **Slider** using the **animationSpeed** property. Default value of this property is “500”.

The following steps explains you on how to customize the animation speed.

In an **HTML** page, specify the **<div>** elements to render the “Default Slider”.


{% highlight html %}

<div class="txt">Default Slider</div>
 <div id="defaultSlider" ej-slider e-value="60" e-animationSpeed ="600"></div>


{% endhighlight %}

{% highlight javascript %}

angular.module('sliderApp', ['ejangular'])
.controller('SliderCtrl', function ($scope) {
   });

{% endhighlight %}
