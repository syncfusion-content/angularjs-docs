---
layout: post
title: Enabling-the-ProgressBar
description: enabling the progressbar
platform: AngularJS
control: ProgressBar
documentation: ug
keywords: ejprogressbar, progressbar, angualarjs progressbar
---

# Enabling the ProgressBar

The ProgressBar is enabled by using the [enabled](https://help.syncfusion.com/api/js/ejprogressbar#members:enabled) Property. When this property is set to ‘**false**’, it disables the ProgressBar widget. By default, ‘**enabled**’ property is set to ‘**true**’ in the ProgressBar widget.

The following steps explains how to disable the ProgressBar widget when [enabled](https://help.syncfusion.com/api/js/ejprogressbar#members:enabled) property is set to ‘**false**’.

In the **HTML** page, add a **&lt;div&gt;** element to render the ProgressBar widget.

{% highlight html %}

<div class="control">
  <div id="progressbar" ej-progressbar e-enabled="false" e-value="50" e-height="40" e-width="500" e-create="create"></div>
</div>

{% endhighlight %}

{% highlight javascript %}

angular.module('ProgressBarApp', ['ejangular'])
.controller('ProgressBarCtrl', function ($scope) {
    $scope.create = function () {
        var progress = $("#progressbar").data("ejProgressBar");
        progress.setModel({ text: progress.getValue() + " %" });
    }
});

{% endhighlight %}

The following screenshot displays the output for the above code.

![](Enabling-the-ProgressBar_images/Enabling-the-ProgressBar_img1.png) 

