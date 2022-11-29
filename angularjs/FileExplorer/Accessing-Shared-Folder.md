---
title: Accessing shared folder in AngularJS FileExplorer | Syncfusion
description: Learn about Accessing shared folder option in Syncfusion AngularJ FileExplorer congtrol, its element,  and more.
platform: AngularJS
control: FileExplorer
documentation: UG
keywords: Accessing shared folder
---

# Accessing shared folder in AngularJS FileExplorer

Using “FileExplorer”, you can manage the files that are available in a shared folder of another system which is connected through LAN. Refer following steps, here you will see the details about accessing the shared folder with FileExplorer. 

First you have to specify the shared folder path in any of following formats.

1. “//Server/SharedFolder”
2. “//Server”

Refer following code block to load the shared folder in our FileExplorer component.

{% highlight html %}

<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-layout="tile" e-width="100%" ></div>

{% endhighlight %}

{% highlight javascript %}

    angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
        $scope.path = "//Server/SharedFolder",
        $scope.ajaxaction = "/Fileoperations",
        $scope.
    });

{% endhighlight %}

N> In above code block, please specify the action method and shared folder path that is integrated with your server.


**Authentication problem in shared folder**

If shared folder is restricted with authentication, that time you are not able to access this folder using our FileExplorer. Here you will get an exception like “**System.UnauthorizedAccessException, Please add your windows credential details to open '\\server\'**”. In order to solve this problem, you have to add the shared folder credential details in the windows credential manager that is available in your service hosted machine.

![AngularJS FileExplorer Accessing shared folder](Accessingsharedfolder_images/Accessingsharedfolder_img1.jpeg)

