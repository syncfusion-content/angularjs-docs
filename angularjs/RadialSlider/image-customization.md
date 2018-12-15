---
layout: post
title: image customization
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

<div id="angularRadialSlider" ej-radialslider e-innercircleimageclass="imageclass" ></div>

{% endhighlight %}

{% highlight js %}


    syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.imageclass = "myclass";
    });


{% endhighlight %}


{% highlight css %}

    .myclass {

        background-image : url("http://js.syncfusion.com/UG/Mobile/Content/sent.png");
    }
{% endhighlight %}

The following screenshot illustrates the output of above code.

![](Image_customization_images\usingclass_img1.png)

### Using image URL

The **RadialSlider** property [`e-innercircleimageurl`] allow to set URL image to the inner circle of the **RadialSlider**. By default, the **Radial Slider** innercircleimageurl is set as “null”. Refer to the following code example.

{% highlight html %}

<div id="angularRadialSlider" ej-radialslider innercircleimageurl="imageurl "></div>

{% endhighlight %}

{% highlight js %}

  syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.imageurl = "http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png";
    });

{% endhighlight %}

The following screenshot illustrates the output of above code.

![https://help.syncfusion.com/js/radialslider/image-customization_images/image-customization_img2.png](Image_customization_images\usingimageurl_img1.png)

