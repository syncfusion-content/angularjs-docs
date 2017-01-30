---
layout: post
title: Persistence-Support
description: persistence support
platform: js
control: Slider
documentation: ug
---

# Persistence Support

This feature supports you to save current model value to browser cookies for state maintenance. When you refresh the web page, the **Slider** control retains the model value apply from browser cookies. The data type of **enablePersistence** is Boolean type. 

The following steps explain you on how to enable the **enablePersistence** property.

In an **HTML** page, add a **<div>** element to render it as a **Slider** widget.

{% highlight html %}

<div id="rangeSlider" ej-slider e-width="width" e-slidertype="Range" e-enablePersistence="true"></div>

{% endhighlight %}


{% highlight javascript %}

  angular.module('syncApp', ['ejangular'])
           .controller('SliderCtrl', function ($scope) {
           });

{% endhighlight %}

Execution of above code will render the below output 

![](Enable_persistence_images/persist_img1.png)

Change the handle values and refresh the page will shows the output like below.

![](Enable_persistence_images/persist_img2.png)