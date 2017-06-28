---
title: Thumbnail Compression | FileExplorer | JavaScript | Syncfusion
description: Thumbnail image size reduction option in FileExplorer
platform: Angular-1
control: FileExplorer
documentation: UG
keywords: Thumbnail compression, image compression, reduce image size
---

# Thumbnail Compression

The “FileExplorer” allows thumbnail images to be compressed on the server side and loaded into the “FileExplorer” layout to improve performance when working with large size images.

You can enable this option using “**enableThumbnailCompress**” API of FileExplorer. Refer following code block that will be helpful to you.

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-layout="tile" e-width="100%" e-enablethumbnailcompress="true" ></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
        $scope.path = "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/",
        $scope.ajaxaction = "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations"
    });

{% endhighlight %}

N> In server side, don’t forget to add “[GetImage](http://help.syncfusion.com/cr/cref_files/aspnetmvc/dociohelper/Syncfusion.EJ~Syncfusion.JavaScript.FileExplorerOperations~GetImage.html#)” handling operation that helps to reduce the image size before loading.
