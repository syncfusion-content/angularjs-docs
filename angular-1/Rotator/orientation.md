---
layout: post
title: orientation
description: orientation
platform: angular-1
control: Control Name undefined
documentation: ug
---

## Orientation

The Rotator component supports both vertical and horizontal orientations allowing it to fit into any scenario. The Rotator property e-orientation defines the orientation where the control is rendered. The value set to this property is enum or string type. It accepts the following values.

ej.Orientation.Horizontal or “Horizontal”

ej.Orientation.Vertical or “Vertical”

The following steps explain you how to set orientation for the Rotator.

### Horizontal

This property sets the Rotator in horizontal orientation. You can refer the following steps to set horizontal orientation for Rotator control.

In View, create ul-li list of Rotator items and invoke the Rotator helper.

Add the following script in your HTML page.

{% highlight html %}



                    	<ul id="sliderContent" ej-rotator e-slidewidth="600px" e-slideheight="350px" e-orientation="orien">
<li>
        <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" title="Nature" />
    </li>
    <li>
        <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" title="Beautiful Bird" />
    </li>
    <li>
        <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" title="Credit Card" />
    </li>
    <li>
        <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sculpture.jpg" title="Amazing Sculptures" />
    </li>
    <li>
        <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg" title="Sea-View" />
    </li>
    <li>
        <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" title="Snow Fall" />
    </li>
    <li>
        <img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" title="Colorful Night" />
    </li>						</ul>



{% endhighlight %}



{% highlight js %}


<script>

        angular.module('rotatApp', ['ejangular']).controller('RotatCtrl', function ($scope) {
            $scope.orien = ej.Orientation.Horizontal;
        });
    </script>


{% endhighlight %}



### Vertical

This property sets the Rotator in vertical orientation. You can refer the following steps to set vertical orientation for Rotator control.

Create ul-li list of Rotator items and invoke the Rotator helper.

Add the following script in your HTML page.

{% highlight js %}


<script>

        angular.module('rotatApp', ['ejangular']).controller('RotatCtrl', function ($scope) {
$scope.ori = ej.Orientation.Vertical;
        });
    </script>



{% endhighlight %}





