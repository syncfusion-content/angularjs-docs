---
layout: post
title: Asynchronous-Upload
description: asynchronous upload
platform: Angular-1
control: Uploadbox
documentation: ug
---

# Asynchronous Upload

This feature allows you to upload and remove files **asynchronously**. To achieve this, set the [asyncUpload](https://help.syncfusion.com/api/js/ejuploadbox#members:asyncupload) property to ‘**true**’. The default value of [asyncUpload](https://help.syncfusion.com/api/js/ejuploadbox#members:asyncupload) property is ‘**true**’. The data type is **Boolean.**

The following steps guide you in uploading the file **asynchronously**.

In the **HTML** page, add the **&lt;div&gt;** element to configure the **Uploadbox** element.

{% highlight html %}

 <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-asyncupload="true"></div>

{% endhighlight %}

{% highlight js %}

    angular.module('UploadboxApp', ['ejangular'])
        .controller('UploadboxCtrl', function ($scope) {
            $scope.save = "saveFiles.ashx";
            $scope.remove= "removeFiles.ashx";
    });

{% endhighlight %}

For **JS**, configure **saveFiles.ashx** and **removeFiles.ashx** files as mentioned in the Save file action and Remove file action respectively.