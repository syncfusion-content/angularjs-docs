---
layout: post
title: Strict Mode | TimePicker | AngularJS | Syncfusion
description: strict mode
platform: AngularJS
control: TimePicker
documentation: ug
---

# Strict mode

Input the **valid** and **invalid** value behavior can be personalized with **e-enablestrictmode**. Setting false to this API, we can enter the valid date only and restrict other invalid dates. Providing wrong date will be set to previous value. By setting false invalid date can be entered but with e-error class. 

When the **e-enableStrictMode** is set as true it allows the value outside of the range and also indicate with red color border, otherwise it internally changed to the min or max range value based an input value.

**HTML View Section**

{% highlight html %}

     <input id="timepicker" ej-timepicker e-value="value" e-enableStrictMode="true" e-minTime="minTime" e-maxTime="maxTime"/>

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

        <script type="text/javascript">
            angular.module("TimeCtrl", ['ejangular']).controller("TimeCtrller", function ($scope) {
                $scope.value = "09:00 AM",
                $scope.minTime = "10:00 AM",
                $scope.maxTime = "10:00 PM"
                    });
        </script>

{% endhighlight %}

Run the above code to render the following output.

![](Strict-Mode_images/Strict mode_images1.png)
