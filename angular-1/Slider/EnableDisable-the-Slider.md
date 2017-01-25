---
layout: post
title: EnableDisable-the-Slider
description: enable/disable the slider
platform: js
control: Slider
documentation: ug
---

# Enable/Disable the Slider

**Slider** widget includes an option to enable/disable it. When you disable the Slider, it is displayed in a blur state and you cannot perform any operations in it.

## Enabled	

Using this **enabled** property you can enable/disable the **Slider**. Data type of this property is “Boolean”.

The following steps explains you on how to disable the **Slider**.

In an **HTML** page, specify the **<div>** elements to render the **Default Slider**.



{% highlight html %}

   <div class="txt">Default Slider</div>
  <div id="defaultSlider" ej-slider e-value="60" e-enabled="false"></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
    .controller('SliderCtrl', function ($scope) {
        });

{% endhighlight %}

Execute the above code example to render the following output.


![](EnableDisable-the-Slider_images/enabledisable_img1.png) 

