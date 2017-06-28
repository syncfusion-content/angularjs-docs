---
layout: post
title:  Nested Splitter Support
description: Nested Splitter Support
platform: AngularJS
control: Splitter
documentation: ug
---

# Nested Splitter Support

**Splitter** provides nested pane support that allows you to add a pane between two pane elements.

## Configure Nested Splitter

The following steps explain the implementation of the **“nested splitter”** option.

In the HTML page set the corresponding **&lt;div&gt;** elements for outer and inner Splitter component.

{% highlight html %}

    <div id="outersplitter" ej-splitter e-properties="proper1" e-height="280" e-width="600" e-orientation="orientation">
        <div>
            <div style="padding: 0px 15px;">
                <h3 class="h3"> JavaScript </h3>
            </div>
        </div>
        <div id="innersplitter" ej-splitter e-properties="proper2" e-width="600">
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

Define properties of outersplitter and innersplitter in angular module in script.

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
            .controller('SplitterCtrl', function ($scope) {
                $scope.proper1 = [{ paneSize: 60 }];
                $scope.orientation = ej.Orientation.Vertical;
                $scope.proper2 = [{ paneSize: 200 }, { paneSize: 170 }];
    })

{% endhighlight %}

The output for the above code as follows.

![](Nested-Splitter-Support_images\Nested-Splitter-Support_img1.png) 