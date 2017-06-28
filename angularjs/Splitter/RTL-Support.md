---
layout: post
title: RTL Support
description: RTL Support
platform: AngularJS
control: Splitter
documentation: ug
---

# RTL Support

**Splitter** provides you with **RTL (Right-To-Left)** support. The alignment of Splitter can be changed from Left-To-Right to Right-To-Left.

## Enable RTL

The following steps explain enabling the right-to-left property for Splitter component.

In the **HTML** page set the corresponding **&lt;div&gt;** elements for outer and inner Splitter component.


{% highlight html %}

        
    <div id="outersplitter" ej-splitter e-height="250" e-width="600" e-orientation="orientation" e-enablertl="rtl" e-properties="proper1">
        <div>
            <div style="padding: 0px 15px;">
                <h3 class="h3"> JavaScript </h3>
            </div>
        </div>
        <div id="innersplitter" ej-splitter e-width="600" e-properties="proper2">
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Tools </h3>
                    Essential Tools is an collection of user interface components used to create interactive
                    JavaScript applications.
                </div>
            </div>
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Chart </h3>
                    Essential Chart is a business-oriented charting component.
                </div>
            </div>
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Grid </h3>
                    Essential JavaScript Grid offers full featured a Grid control with extensive support for
                    Grouping and the display of hierarchical data.
                </div>
            </div>
        </div>
    </div>

{% endhighlight %}

Define **“e-enableRTL”** property as true in angular module in script section.

{% highlight javascript %}

       
    angular.module('syncApp', ['ejangular'])
               .controller('SplitterCtrl', function ($scope) {
                   $scope.orientation = ej.Orientation.Vertical;
                   $scope.rtl = true;
                   $scope.proper1 = [{ paneSize: 60 }];
                   $scope.proper2 = [{ paneSize: 200 }, { paneSize: 170 }];
    })

{% endhighlight %}

The output for Splitter when **e-enableRTL** is “true”.

![](RTL-Support_images\RTL-Support_img1.png) 

