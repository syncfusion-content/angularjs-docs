---
layout: post
title: Setting-Range
description: setting range
platform: Angular-1
control: ProgressBar
documentation: ug
keywords: ejprogressbar, progressbar, angualarjs progressbar
---

# Setting Range

The **range** of the ProgressBar is set by using minimum and maximum values. The Minimum value specifies the value where the ProgressBar shows the process to have started. The Maximum value specifies the value where the process is completed. You can set the range by using the [minValue](https://help.syncfusion.com/api/js/ejprogressbar#members:minvalue) and [maxValue](https://help.syncfusion.com/api/js/ejprogressbar#members:maxvalue) property.

In the **HTML** page, add a **&lt;div&gt;** element to render the ProgressBar widget.

{% highlight html %}

   <div class="control">
    <div id="progressbar" ej-progressbar e-minvalue="40" e-maxvalue="80" e-value="80" e-height="20" e-width="500" e-create="create"></div>
   </div>

{% endhighlight %}

{% highlight js%}

angular.module('ProgressBarApp', ['ejangular'])
.controller('ProgressBarCtrl', function ($scope) {
    $scope.create = function () {
        var progress = $("#progressbar").data("ejProgressBar");
        progress.setModel({ text: progress.getPercentage() + " % Completed" });
    }
}); 

{% endhighlight %}

The following screenshot displays the output.

![](Setting-Range_images/Setting-Range_img1.png) 

