---
layout: post
title: Restricting-uploading-files-based-on-its-extension
description: restricting uploading files based on its extension
platform: Angular-1
control: Uploadbox
documentation: ug
---

# Restricting uploading files based on its extension

## Allow Extension

Files are filtered before they are uploaded. You can select the files to be filtered by using **browse** button. The [extensionsAllow](https://help.syncfusion.com/api/js/ejuploadbox#members:extensionsallow) property allows upload of the selected extensions only. You can give multiple extensions by using comma (,).  The data type is **string**.

N> Prepend dot (.) symbol with extension like “.pdf”.



The following steps explain the configuration of [extensionsAllow](https://help.syncfusion.com/api/js/ejuploadbox#members:extensionsallow) property in **Uploadbox**. 

In the **HTML** page, add the **&lt;div&gt;** element to configure the **Uploadbox** element.

{% highlight html %}

   <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-extensionsallow="allow"></div>

{% endhighlight %}

{% highlight js %}

             angular.module('UploadboxApp', ['ejangular'])
        .controller('UploadboxCtrl', function ($scope) {
            $scope.save = "saveFiles.ashx";
            $scope.remove = "removeFiles.ashx";
            $scope.allow = ".docx, .pdf";
        });


{% endhighlight %}

For **JS**, configure **saveFiles.ashx** and **removeFiles.ashx** files as mentioned in the Save file action and Remove file action respectively. 

## Deny Extension

Files are filtered before they are uploaded. You can select the files to be filtered by using **browse** button. The [extensionsDeny](https://help.syncfusion.com/api/js/ejuploadbox#members:extensionsdeny) property denies upload of the selected extensions. You can give multiple extensions by using comma (,).  The data type is **string**.

N> Prepend dot (.) symbol with extension like “.pdf”.

The following steps explain the configuration of [extensionsDeny](https://help.syncfusion.com/api/js/ejuploadbox#members:extensionsdeny) property in **Uploadbox**

In the **HTML** page, add the **&lt;div&gt;** element to configure the **Uploadbox** element.

{% highlight html %}

   <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-extensionsdeny="deny"></div>

{% endhighlight %}

{% highlight js %}

    angular.module('UploadboxApp', ['ejangular'])
        .controller('UploadboxCtrl', function ($scope) {
            $scope.save = "saveFiles.ashx";
            $scope.remove = "removeFiles.ashx";
            $scope.deny = ".docx,.pdf";
    });

{% endhighlight %}

For **JS**, configure **saveFiles.ashx** and **removeFiles.ashx** files as mentioned in the Save file action and Remove file action respectively. 

