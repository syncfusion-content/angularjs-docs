---
layout: post
title: Syncfusion Radial Slider image customization
description: image customization
platform: AngularJS
control: Radial Slider
documentation: ug
---

## Image customization

## Customizing inner circle

### Using Class

The **RadialSlider** property **e-innerCircleimageclass** allow to set image for the inner circle of the **RadialSlider**. By default, the **Radial Slider** innerCircleImageClass is set as “null”. Refer to the following code example.

{% highlight html %}

<div id="angularRadialSlider" ej-radialslider e-innercircleimageclass="imageClass" ></div>

{% endhighlight %}

{% highlight js %}


    syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.imageClass = "myClass";
    });


{% endhighlight %}


{% highlight css %}

    .myClass {

        background-image : url("http://js.syncfusion.com/UG/Mobile/Content/sent.png");
    }
{% endhighlight %}

The following screenshot illustrates the output of above code.

![Image customization](Image_customization_images\usingclass_img1.png)

### Using image URL

The **RadialSlider** property [`e-innercircleimageurl`] allow to set URL image to the inner circle of the **RadialSlider**. By default, the **Radial Slider** [`innercircleimageurl`] is set as “null”. Refer to the following code example.

{% highlight html %}

<div id="angularRadialSlider" ej-radialslider innercircleimageurl="imageUrl"></div>

{% endhighlight %}

{% highlight js %}

  syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.imageUrl = "http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png";
    });

{% endhighlight %}

The following screenshot illustrates the output of above code.

![Image customization](Image_customization_images\usingimageurl_img1.png)

