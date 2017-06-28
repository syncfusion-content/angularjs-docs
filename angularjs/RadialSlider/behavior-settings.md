---
layout: post
title: behavior settings
description: behavior settings
platform: AngularJS
control: Radial Slider
documentation: ug
---

## Behavior settings

The following are some properties that enables you to an option to enhance the behavior of **RadialSlider** component.

### Show hide RadialSlider on initial rendering

The **RadialSlider** property **e-autoopen** allow you to make the component visible on initial rendering. By default, the value of the property is set as **true**. Setting it as **false** will hide the component on initial rendering.

{% highlight html %}


<div id="angularRadialSlider" ej-radialslider e-autoopen="autoopen" e-innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"></div>


{% endhighlight %}



{% highlight js %}

syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.autoopen = false;
    });


{% endhighlight %}


### Value accuracy

The **RadialSlider** property **e-enableroundOff** allow to show the rounded off value when user changes it. By default, the value of the property is set as **true**. For accurate values, you can set this as false.

{% highlight html %}


<div id="angularRadialSlider" ej-radialslider e-enableroundoff="roundoff" innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"></div>


{% endhighlight %}



{% highlight js %}


    syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.roundoff = false;
    });


{% endhighlight %}


### Display inline

The **RadialSlider** property **e-inline** is used to show the component values inline of the slider. By default, the value of the property is set as **false**.

{% highlight html %}


<div id="angularRadialSlider" ej-radialslider e-inline="inline" innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"></div>



{% endhighlight %}



{% highlight js %}


   syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.inline = true;
    });


{% endhighlight %}



### Modifying Label Space

The **RadialSlider** property **e-labelspace** allow to define the space of label in it. By default, the **RadialSlider** labelSpace is set as 30. Refer to the following code example.



{% highlight html %}


<div id="angularRadialSlider" ej-radialslider e-labelspace="space" innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"></div>



{% endhighlight %}



{% highlight js %}


   syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.space = 40;
    });


{% endhighlight %}



The following screenshot shows the output for the above code example.

![https://help.syncfusion.com/js/radialslider/Behavior-settings_images/Behavior-settings_images_img1.png](Behavior-settings_images\modifyinglabelspace_img1.png)

### Show Hide inner circle

The **RadialSlider** property **e-showinnercircle** allow to show or hide the inner circle of the **RadialSlider**. By default, the value of the property is set as **true** and type of the property is **Boolean**.

{% highlight html %}


<div id="angularRadialSlider" ej-radialslider e-showinnercircle="innercircle" innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"></div>



{% endhighlight %}



{% highlight js %}


   syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.innercircle = false;
    });


{% endhighlight %}



The following screenshot shows the output for the above code example.

![https://help.syncfusion.com/js/radialslider/Behavior-settings_images/Behavior-settings_images_img2.png](Behavior-settings_images\showhideinnercircle_img1.png)

### Values customization

The **RadialSlider** property **e-ticks** allow to set an array of a numeric value which will be displayed in it. By Default **RadialSlider** ticks value is a set to an array of length 11 as following,

ticks = { 0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100 }. You can refer the below code for reference.



{% highlight html %}



<div id="angularRadialSlider" ej-radialslider e-ticks="ticks" innercircleimageurl="http://js.syncfusion.com/demos/web/content/images/radialslider/chevron-right.png"></div>



{% endhighlight %}



{% highlight js %}


   syncApp.controller('radialSliderCtrl', function ($scope) {
        $scope.ticks = [100,200,300,400,500,600,700,800,900,1000];
    });


{% endhighlight %}



The following screenshot shows the output for the above code example.

![https://help.syncfusion.com/js/radialslider/Behavior-settings_images/Behavior-settings_images_img3.png](Behavior-settings_images\valuescustomization_img1.png)

