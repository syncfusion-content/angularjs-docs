---
layout: post
title: Resizing
description: resize support
platform: Angular-1
control: File Explorer
documentation: ug
---

# Resizing 

The FileExplorer has the resize support through the resize handle which appears at right-bottom corner of footer. By clicking the resize handle the user can resize the FileExplorer through the UI. While resizing the dimension of the FileExplorer is automatically adjusted.

The resize behavior can be enabled through the [enableResize](https://help.syncfusion.com/api/js/ejfileexplorer#members:enableresize) property. 

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-enableresize="true" ></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
        $scope.path = "http://mvc.syncfusion.com/ODataServices/FileBrowser/",
        $scope.ajaxaction = "http://mvc.syncfusion.com/OdataServices/fileExplorer/fileoperation/doJSONAction"
    });

{% endhighlight %}

## Responsiveness

By enabling the [isResponsive](https://help.syncfusion.com/api/js/ejfileexplorer#members:isresponsive) property, you can make the FileExplorer as responsive. While resizing the FileExplorer component, the inner content and toolbar items are automatically adjusted to equalize the size. The toolbar items are displayed within Dropdown on enabling the responsive. Otherwise it floated to the next line to equalize the space. 

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-isresponsive="true" e-enableresize="true" ></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
        $scope.path = "http://mvc.syncfusion.com/ODataServices/FileBrowser/",
        $scope.ajaxaction = "http://mvc.syncfusion.com/OdataServices/fileExplorer/fileoperation/doJSONAction"
    });

{% endhighlight %}

## Restriction on Resize

You can restrict the dimension of the FileExplorer by setting the [minHeight](https://help.syncfusion.com/api/js/ejfileexplorer#members:minheight), [maxHeight](https://help.syncfusion.com/api/js/ejfileexplorer#members:maxheight) and [minWidth](https://help.syncfusion.com/api/js/ejfileexplorer#members:minwidth),[maxWidth](https://help.syncfusion.com/api/js/ejfileexplorer#members:maxwidth) properties while resizing the FileExplorer. 

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-isresponsive="true" e-enableresize="true" minHeight="200px" maxHeight= "400px" minWidth="300px" maxWidth= "1200px"></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
        $scope.path = "http://mvc.syncfusion.com/ODataServices/FileBrowser/",
        $scope.ajaxaction = "http://mvc.syncfusion.com/OdataServices/fileExplorer/fileoperation/doJSONAction"
    });

{% endhighlight %}
