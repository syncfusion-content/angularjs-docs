---
layout: post
title: RTL-Support
description: rtl support
platform: AngularJS
control: ProgressBar
documentation: ug
keywords: ejprogressbar, progressbar, angualarjs progressbar
---

# RTL Support

Right-To-Left starts from the right of the page and continues to the left. By default, this option is set to ‘**false**’ in the ProgressBar control. The [enableRTL](https://help.syncfusion.com/api/js/ejprogressbar#members:enablertl) property allows the ProgressBar control to display it in the right to left direction.

The following steps explains how to **enable** the **RTL** property of the ProgressBar control.

In the **HTML** page, add a **&lt;div&gt;** element to render the ProgressBar widget.

{% highlight html %}

<div class="control">
  <div id="progressbar" ej-progressbar e-enablertl="true" e-value="80" e-text="80" e-height="20" e-width="500">
  </div>
</div>

{% endhighlight %}

The following screenshot displays the output.

![](RTL-Support_images/RTL-Support_img1.png)



















