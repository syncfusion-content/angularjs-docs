---
layout: post
title:  Splitter Orientation
description: Splitter Orientation
platform: AngularJS
control: Splitter
documentation: ug
---

# Splitter Orientation

 **Splitter** supports both vertical and horizontal orientation of the pane. You can define **e-orientation** with enum values **“ej.Orientation.Vertical“** or **“ej.Orientation.Horizontal”**. Or else set value of orientation as string.

## Configure Splitter Orientation

The following steps explain the implementation of Splitter orientation option.

In the **HTML** page set the **&lt;div&gt;** element for rendering Splitter component.

{% highlight html %}

    <div id="splitter" ej-splitter e-properties="proper" e-orientation="orientation" e-height="280" e-width="600">
    <div>
        <div style="padding: 0px 15px;">
            <h3 class="h3">Tools </h3>
            Essential Tools is an collection of user interface components used to create interactive JavaScript applications.
        </div>
    </div>
    <div>
        <div style="padding: 0px 15px;">
            <h3 class="h3">Grid </h3>
            Essential JavaScript Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.
        </div>
    </div>
    </div>      

{% endhighlight %}

Define the splitter orientation as **“ej.Orientation.Vertical”** in angular module in script.

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
           .controller('SplitterCtrl', function ($scope) {  
             $scope.orientation=ej.Orientation.Vertical;
    })

{% endhighlight %}


The output of Splitter with **ej.Orientation.Vertical** orientation as follows,

![](Splitter-Orientation_images\Splitter-Orientation_img1.png) 

The output of Splitter with **ej.Orientation.Horizontal** orientation as follows,

![](Splitter-Orientation_images\Splitter-Orientation_img2.png) 

