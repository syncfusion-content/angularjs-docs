---
layout: post
title: Enable-or-Disable-the-Uploadbox
description: enable or disable the uploadbox 
platform: Angular-1
control: Uploadbox
documentation: ug
---

# Enables or Disables the Uploadbox 

This feature helps set the **enable** or **disable** option for **Uploadbox** by setting **Boolean** type value to [enabled](https://help.syncfusion.com/api/js/ejuploadbox#members:enabled) property. For **enable** or **disable** option, set [enabled](https://help.syncfusion.com/api/js/ejuploadbox#members:enabled) property to ‘**false**’. The data type is **Boolean**.

The following steps explain the configuration of **enabled** property in **Uploadbox**. 

In the **HTML** page, add the **&lt;div&gt;** element to configure the **Uploadbox** element.

{% highlight html %}

    <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-enabled="false"></div>

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


![](Enable-or-Disable_images/Enable-or-Disable_img1.png)