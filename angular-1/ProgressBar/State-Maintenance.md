---
layout: post
title: State-Maintenance
description: state maintenance
platform: Angular-1
control: ProgressBar
documentation: ug
keywords: ejprogressbar, progressbar, angualarjs progressbar
---

# State Maintenance

Saves current model value to cookies for **State Maintenance**. While refreshing the ProgressBar widget, page retains the model value applied from browser cookies. By default, the [enablePersistence](https://help.syncfusion.com/api/js/ejprogressbar#members:enablepersistence) property is set to ‘**false**’ in the ProgressBar.

The following steps explain the **State Maintenance** in the ProgressBar control.

In the **HTML** page, add a **&lt;div&gt;** element to render the ProgressBar widget.

{% highlight html %}

<div class="control">
  <div id="progressbar" ej-progressbar e-enablepersistence="true" e-value="40" e-height="40" e-width="500" e-create="create">
  </div>
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

The following screenshot displays the output.

![](State-Maintenance_images/State-Maintenance_img1.png) 

