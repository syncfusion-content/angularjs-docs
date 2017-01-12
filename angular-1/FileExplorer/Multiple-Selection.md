---
layout: post
title: Multiple Selection
description: FileExplorer allows the user to select multiple files
platform: Angular-1
control: File Explorer
documentation: ug
---


# Multiple Selection

The FileExplorer allows the user to select multiple files by enabling the [allowMultiSelection](https://help.syncfusion.com/api/js/ejfileexplorer#members:allowmultiselection) property. The multiple selection can be done by pressing the **Ctrl** key or **Shift** key. You can select all the files in the directory by pressing “**Ctrl + A**”. The multiple selection is useful on copy pasting multiple files, deleting multiple files and downloading multiple files.

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-isresponsive="true" e-allowmultiselection="false" ></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
        $scope.path = "http://mvc.syncfusion.com/ODataServices/FileBrowser/",
        $scope.ajaxaction = "http://mvc.syncfusion.com/OdataServices/fileExplorer/fileoperation/doJSONAction"
    });

{% endhighlight %}
