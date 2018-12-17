---
layout: post
title: Syncfusion Radial Slider dimension
description: dimension
platform: AngularJS
control: Radial Slider
documentation: ug
---

## Dimension

### Stroke Width

**Radial Slider** [`e-strokewidth`] property specifies the width of the outline. By default, the **Radial slider** stroke width is set as 2. Refer to the following code example.

{% highlight html %}

<div id="angularRadialSlider" ej-radialslider e-strokewidth="widthValue" innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/ radialslider/chevron-right.png"></div>

{% endhighlight %}

Add the following script in your code.

{% highlight js %}

       syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.widthValue = 4;
    });

{% endhighlight %}

The following screenshot illustrates the output of the above code.

![Stroke Width](dimension_images\strokewidth_img1.png)

### Setting radius

The **RadialSlider** property **e-radius** indicates the radius of the RadialSlider’s circle and it allow to change radius value. By default, the **Radial Slider** radius is set to 200. Refer to the following code example.

{% highlight html %}

<div id="angularRadialSlider" ej-radialslider e-radius="radiusValue" e- innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/ radialslider/chevron-right.png"></div>

{% endhighlight %}

{% highlight js %}

    syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.radiusValue = 300;
    });

{% endhighlight %}
