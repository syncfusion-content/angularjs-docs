---
title: Drag and Drop Support | FileExplorer | JavaScript | Syncfusion
description: Drag and Drop option in FileExplorer
platform: AngularJS
control: FileExplorer
documentation: UG
keywords: Drag and drop option
---

# Drag and Drop Support

The FileExplorer allows files to be moved from one folder to another by using drag and drop. It also supports uploading a file by dragging it from Windows Explorer to a folder in the FileExplorer control.

You can enable or disable this support by using “**allowDragAndDrop**” API of FileExplorer.

The [dragStart](https://help.syncfusion.com/api/js/ejfileexplorer#events:dragstart), [drag](https://help.syncfusion.com/api/js/ejfileexplorer#events:drag), [dragStop](https://help.syncfusion.com/api/js/ejfileexplorer#events:dragstop) and [drop](https://help.syncfusion.com/api/js/ejfileexplorer#events:drop) events occur in the mentioned order when a drag and drop operation is performed.

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-isresponsive="true" e-allowdraganddrop="false" ></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
        $scope.path = "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/",
        $scope.ajaxaction = "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations"
    });

{% endhighlight %}

