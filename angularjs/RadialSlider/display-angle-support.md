---
layout: post
title: display angle support
description: display angle support
platform: AngularJS
control: Radial Slider
documentation: ug
---

## Display Angle Support

### Start Angle

The **RadialSlider** property **e-startangle** allows you to change the start angle level of the **RadialSlider**. By default, the **Radial Slider** start angle is set as 0. Refer to the following code example.

{% highlight html %}


<div id="angularRadialSlider" ej-radialslider e-startangle="startangle" e-innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"></div>


{% endhighlight %}

{% highlight js %}

syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.startangle = 20;
    });

{% endhighlight %}

The following screenshot illustrates the output of the above code.

![https://help.syncfusion.com/js/radialslider/display-angle-settings_images/display-angle-settings_images_img1.png](display-angle-settings_images\startangle_img1.png)

### End Angle

The **RadialSlider** property **e-endangle** allows you to change the end angle level of the **RadialSlider**. By default, the **Radial Slider** end angle is set as 360. Refer to the following code example.

{% highlight html %}


<div id="angularRadialSlider" ej-radialslider e-endangle="endangle" e-innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"></div>


{% endhighlight %}


{% highlight js %}

syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.endangle = 300;
    });


{% endhighlight %}


The following screenshot illustrates the output of the above code.

![https://help.syncfusion.com/js/radialslider/display-angle-settings_images/display-angle-settings_images_img2.png](display-angle-settings_images\endangle_img1.png)

