---
layout: post
title: Enable RTL
description: Enable RTL 
platform: Angular-1
control: Button
documentation: ug
---

# Enable RTL

Buttons are provided with built-in right to left alignment of the button contents. Here, RTL support is provided using e-enableRTL property. In RTL mode when you have more than one content (image/text, image/image) in button, then these contents are aligned in right to left format. The button RTL enabled using e-enableRTL property is shown below.

{% highlight html %}

        <div ng-controller="ButtonCtrl">
        <div>
                <button id="button1" ej-button  e-contentType="textandimage" e-prefixIcon="e-icon e-handup" e-enableRTL="enable">Button</button>

        </div>
        </div>
   
{% endhighlight %}

{% highlight javascript %}

        <script>
                angular.module('buttonApp', ['ejangular'])
                .controller('ButtonCtrl', function ($scope) {
                $scope.enable = true;
                });
        </script>
    
{% endhighlight %}

Run the above code to get the below output.

![](rtl/RTL.png)

