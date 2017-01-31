---
layout: post
title: Customization | TimePicker | AngularJS | Syncfusion
description: customization
platform: AngularJS
control: TimePicker
documentation: ug
---

# Customization

## Rounded Corner

**e-showRoundedCorner** property is used to display the **TimePicker** control with rounded corners. By default, **showRoundedCorner** is in **disabled state**.

**HTML View Section**

{% highlight html %}

     <input id="timepicker" ej-timepicker e-showRoundedCorner="true" />

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

        <script type="text/javascript">
            angular.module("TimeCtrl", ['ejangular']).controller("TimeCtrller", function ($scope) {
            });
        </script>

{% endhighlight %}

Run the above code to render the following output.

![](Customization_images/Customization_images1.png)

## Height/Width
You can use **e-height** and **e-width** property to customize TimePicker **width** and **height**.

**HTML View Section**

{% highlight html %}

     <input id="timepicker" ej-timepicker e-height="height" e-width="width"/>

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

        <script type="text/javascript">
            angular.module("TimeCtrl", ['ejangular']).controller("TimeCtrller", function ($scope) {
            //set height and width
                $scope.height=40,
                $scope.width= 150
                    });
        </script>

{% endHighlight %}

Run the above code to render the following output.

![](Customization_images/Customization_images2.png)


## PopupHeight and PopupWidth

You can use **e-popupHeight** and **e-popupWidth** property to customize **TimePicker popup width and height**.

**HTML View Section**

{% highlight html %}

     <input id="timepicker" ej-timepicker e-popupHeight="popupHeight" e-popupWidth="popupWidth"/>

{% endhighlight %}

**Controller Section**

{% highlight javascipt %}

        <script type="text/javascript">
            angular.module("TimeCtrl", ['ejangular']).controller("TimeCtrller", function ($scope) {
        //set popup height and popup width
                $scope.popupHeight=200,
                $scope.popupWidth=150
                    });
        </script>

{% endhighlight %}

Run the above code to render the following output.

![](Customization_images/Customization_images3.png)




