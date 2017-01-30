---
layout: post
title: RTL-support
description: rtl support
platform: angular-1
control: Slider
documentation: ug
---

# RTL support

**Slider** includes the Right to Left alignment support. Operations in the **Slider** is performed from Right to Left.

## Enabling RTL

Use the **enableRTL** property to enable the RTL support. By default this property is disabled. Data type of this property is “Boolean”.

The following steps explains you on how to enable RTL support in **Slider**.

In an **HTML** page, specify the **div** elements to render the **Range Slider.**



{% highlight html %}

<div class="txt">Range Slider</div>
<div id="rangeSlider" ej-slider e-width="500" e-sliderType="Range" e-values="value" e-enableRTL="true"></div>


{% endhighlight %}

{% highlight javascript %}

    angular.module('sliderApp', ['ejangular'])
    .controller('SliderCtrl', function ($scope) {
    $scope.value=[25,75]
    });

{% endhighlight %}

Execution of above code will render the following output.

![](RTL-support_images/RTL-support_img1.png)