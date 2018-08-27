---
layout: post
title: Behavior Settings
description: Customize the behavior of FileExplorer.
platform: AngularJS
control: FileExplorer
documentation: ug
---

# Behavior Settings

Here are the some properties to customize the behavior of FileExplorer.

## File type restriction

FileExplorer control showcase all the files from the filesystem, here you can customize the file types that what you want to show by using [fileTypes](https://help.syncfusion.com/api/js/ejfileexplorer#members:filetypes) property. It filter the files based on the files extensions.

By default it having the value “*.*”, so it allows all the file types. In case of image browser you can allow the image files only by setting "*.png, *.gif, *.jpg, *.jpeg", so it doesn’t allow the other type of files.

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-isresponsive="true" e-filetypes=".png, *.gif, *.jpg, *.jpeg" ></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
        $scope.path = "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/",
        $scope.ajaxaction = "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations"
    });

{% endhighlight %}

## Customize the AJAX request settings

As you already know FileExplorer is a client – server based control and each action performed in the client sends an AJAX request to the server to perform the server side operations. While the AJAX request, the AJAX configurations can be customized through [ajaxSettings](https://help.syncfusion.com/api/js/ejfileexplorer#members:ajaxsettings) property.

The [beforeAjaxRequest](https://help.syncfusion.com/api/js/ejfileexplorer#events:beforeajaxrequest) event will be triggered before the AJAX request is performed. You can modify the ajax request in this event.

You can see the following requests passed during the **client – server actions**:

* Read, 
* Create folder
* Remove
* Rename
* Paste
* Get details
* Upload
* Download 
* Get Image

The following is the syntax for ajaxSettings property.

{% highlight javascript %}

   ajaxSettings= { read: {}, createFolder: {}, remove: {}, rename: {}, paste: {}, getDetails: {}, upload: {}, download: {}, getImage: {} }
   
{% endhighlight %}

The actions “read, createFolder, remove, rename, paste, getDetails” are supported all the jQuery AJAX configurations. The remaining actions “upload, download, getImage” are accepted the URL only.

If you want to customize read action alone, the AJAX **url** and **dataType** are changed for the read action, refer the below code example.

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-ajaxsettings="ajaxSettings" ></div>

{% endhighlight %}

{% highlight javascript %}

        angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
            $scope.path = "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/",
            $scope.ajaxaction = "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations",
            $scope.ajaxSettings= { read: { url: ajaxJSONPActionHandler, dataType: "jsonp" } }
        });
        
{% endhighlight %}

