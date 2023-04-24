---
layout: post
title: RTL Support in AngularJS Uploadbox Control | Syncfusion
description: Learn here about rtl support in Syncfusion Essential AngularJS Uploadbox Control, its elements, and more.
platform: AngularJS
control: Uploadbox
documentation: ug
---

# RTL Support in AngularJS Uploadbox

This feature supports the change of left-to-right alignment of the **Uploadbox** widget to right-to-left (**RTL**). That is, it sets the **Uploadbox** to right-to-left actions.

The following steps explain the configuration of [enableRTL](https://help.syncfusion.com/api/js/ejuploadbox#members:enablertl) property in **Uploadbox**. 

In the **HTML** page, add the **&lt;div&gt;** element to configure the **Uploadbox** element.

{% highlight html %}

<div class="control">
  <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-enablertl="true"></div>
</div>

{% endhighlight %}

{% highlight js %}
  
angular.module('UploadboxApp', ['ejangular'])
.controller('UploadboxCtrl', function ($scope) {
    $scope.save = "saveFiles.ashx";
    $scope.remove= "removeFiles.ashx";
});

{% endhighlight %}

For **JS**, configure **saveFiles.ashx** and **removeFiles.ashx** files as mentioned in the Save file action and Remove file action respectively.

The following screenshot displays the output.

![AngularJS Uploadbox rtl support](RTL-Support_images/RTL-Support_img1.png) 