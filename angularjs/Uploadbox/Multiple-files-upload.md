---
layout: post
title: Multiple-files-upload
description: multiple files upload
platform: AngularJS
control: Uploadbox
documentation: ug
---

# Multiple files upload

The **Uploadbox** widget provides support to upload multiple files spontaneously. The [multipleFilesSelection](https://help.syncfusion.com/api/js/ejuploadbox#members:multiplefilesselection) property enables you to select multiple files while browsing.  To achieve this, set the [multipleFilesSelection](https://help.syncfusion.com/api/js/ejuploadbox#members:multiplefilesselection) property to ‘**true**’. The data type is **Boolean**.

N> The Multiple file selection supports all the latest versions of browser except Internet Explorer 9 and its previous versions.

The following steps explain the configuration of **multipleFilesSelection** property in **Uploadbox**. 

In the **HTML** page, add the **&lt;div&gt;** element to configure the **Uploadbox** element.


{% highlight html %}

<div class="control">
    <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-multiplefilesselection="true"></div>
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


![](Multiple-files-upload_images/Multiple-files-upload_img1.png)


![](Multiple-files-upload_images/Multiple-files-upload_img2.png)