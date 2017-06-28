---
layout: post
title: Updating-slider-value
description: updating slider value
platform: AngularJS
control: Slider
documentation: ug
---

# Updating slider value

**Slider** widget includes an option to specify/update its value. And also you can specify the starting and ending value for the **Slider** using the **minValue** and **maxValue** properties.

## Value

This property is used to set the value in the “Default” and “Min-Range” Sliders. By default its value is null when no value is specified. Data type of this property is “number”.

## Values

This property is used to set the value in “Range Slider”. By default range values is from 0 to 100. This property is of “Array” data type.

The following steps explains you the configuration of “value” and “values” property.

In an **HTML** page, specify the **<div>** elements to render the “Range Slider” and “Default Slider”.



{% highlight html %}


  <div class="txt">Default Slider</div>
<div id="defaultSlider" ej-slider e-slidertype="Default" e-width="500" e-value="50"></div>
<br />
<br />
<div class="txt">range Slider</div>
<div id="rangeSlider" ej-slider e-slidertype="Range" e-values="value" e-width="500"></div>



{% endhighlight %}

{% highlight javascript %}

    angular.module('sliderApp', ['ejangular'])
    .controller('SliderCtrl', function ($scope) {
    $scope.value = [20, 80]
    });


{% endhighlight %}

Execute the above code example to render the following output.


![](Updating-slider-value_images/Updating-slider-value_img1.png) 

## MinValue

To set the minimum/starting value of the Slider, you can use the minValue property. By default its value is 0. Data type of this property is “number”.

## MaxValue

To set the maximum/ending value of the Slider, you can use the maxValue property. By default its value is 100. Data type of this property is “number”.

The following steps explains you on how to configure minValue and maxValue property.

In an **HTML** page, specify the **<div>** elements to render the **Default Slider** and **Range Slider**.

{% highlight html %}

<div class="txt">Default Slider</div>
<div id="defaultSlider" ej-slider e-slidertype="Default" e-width="500" e-value="60" e-minvalue="40" e-maxvalue="80"></div>
<br />
<br />
<div class="txt">Range Slider</div>
<div id="rangeSlider" ej-slider e-slidertype="Range" e-values="value" e-width="500" e-minvalue="10" e-maxvalue="90"></div>


{% endhighlight %}

{% highlight javascript %}

    angular.module('sliderApp', ['ejangular'])
    .controller('SliderCtrl', function ($scope) {
    $scope.value = [10, 90]
        });


{% endhighlight %}

Execute the above code example to render the following output.

![](Updating-slider-value_images/Updating-slider-value_img2.png) 

In the above example, for **Default Slider** the slider value starts from “40” (min value) and ends in “80” (max value), so the slider handle is placed at the center of the Slider while specifying the value as “60”.

For **Range Slider**, the value starts from “10” (min value) and ends in “90” (max value). The range shadow occupies the entire **Slider**, since the range (values) is specified as “[10, 90]”.

