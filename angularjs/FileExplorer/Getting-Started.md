---
layout: post
title: Getting-Started
description: getting started
platform: Angular-1
control: FileExplorer
documentation: ug
---

# Getting Started

The following section is briefly explain the things to get started with FileExplorer control.

## Preparing the HTML Document

Create a new Html file and include the below code.

{% highlight html %}
<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">

<head>

    <meta charset="utf-8">

    <title> </title>

</head>

<body>

</body>

</html>
{% endhighlight %}

## Adding the References

## CSS References

Add the below CSS reference in the head section, for the default theme

{% highlight html %}
<link rel="stylesheet" href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" />
{% endhighlight %}

<b>Script References</b>

The external script dependencies of the FileExplorer widget are,

* [jQuery 1.7.1](http://jquery.com/#) or later versions.
* [jsrender](https://www.jsviews.com/#jsrender) – for grid view template.

And the internal script dependencies of the FileExplorer widget are:

<table>
<tr>
<td>
<b>File</b><br/><br/></td><td>
<b>Description/Usage</b><br/><br/></td></tr>
<tr>
<td>
Angular.min.js<br/><br/></td><td>
Angular common source file<br/><br/></td></tr>
<tr>
<td>
ej.core.min.js<br/><br/><br/></td><td>
Must be referred always before using all the JS controls.<br/><br/><br/></td></tr>
<tr>
<td>
ej.data.min.js<br/><br/><br/></td><td>
Used to handle data operation and should be used while binding data to JS controls.<br/><br/><br/></td></tr>
<tr>
<td>
ej. draggable.min.js<br/><br/><br/></td><td>
Used to handle the drag and drop functionality<br/><br/><br/></td></tr>
<tr>
<td>
ej.scroller.min.js<br/><br/><br/></td><td>
Used to show the scroller in the layout area<br/><br/><br/></td></tr>
<tr>
<td>
ej.button.min.js<br/><br/><br/></td><td>
Used to display the buttons in the toolbar<br/><br/><br/></td></tr>
<tr>
<td>
ej.treeview.min.js<br/><br/><br/></td><td>
Used to display the treeview in the navigation pane<br/><br/><br/></td></tr>
<tr>
<td>
ej.uploadbox.min.js<br/><br/><br/></td><td>
Used to perform the upload functionality <br/><br/><br/></td></tr>
<tr>
<td>
ej.waitingpopup.min.js<br/><br/><br/></td><td>
Used to showcase the waiting popup<br/><br/><br/></td></tr>
<tr>
<td>
ej.dialog.min.js<br/><br/><br/></td><td>
Used to create the alert windows <br/><br/><br/></td></tr>
<tr>
<td>
ej.splitter.min.js<br/><br/><br/></td><td>
Used as the body section to separate the navigation and layout area<br/><br/><br/></td></tr>
<tr>
<td>
ej.toolbar.min.js<br/><br/><br/></td><td>
Used to showcase the hearer section<br/><br/><br/></td></tr>
<tr>
<td>
ej.menu.min.js<br/><br/><br/></td><td>
Used to showcase the context menu<br/><br/><br/></td></tr>
<tr>
<td>
ej.grid.min.js<br/><br/><br/></td><td>
Used to showcase the grid layout view<br/><br/></td></tr>
<tr>
<td>
ej.widget.angular.min.js<br/><br/></td><td>
Essential Studio angular source file<br/><br/></td></tr>
</table>
For getting started you can use the “**ej****.****web****.****all****.****min****.****js**” file, which encapsulates all the ej controls and frameworks in one single file.

Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called **ejangular****.** To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.

So you can add the below Script references in the head section:

{% highlight html %}
<!doctype html>
<html lang="en" ng-app="'FileApp'">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for FileExplorer </title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->

</head>
<body>
    <!--Add the elements here-->
</body>
</html>
{% endhighlight %}

## Initialize and configure the control

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Once added the element you can initialize the control from the script section like below:


{% highlight html %}
<div id="fileExplorer" ej-fileexplorer e-path="path" e-ajaxaction="ajaxaction" e-isresponsive="true" e-layout="grid" e-width="100%" ></div>
{% endhighlight %}

{% highlight html %}
angular.module('FileCtrl', ['ejangular']).controller('FileCtrl', function ($scope) {
    $scope.path = "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/",
    $scope.ajaxaction = "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations"

});
{% endhighlight %}

To perform the server side actions using local web API service, please refer the [link](https://help.syncfusion.com/js/fileexplorer/how-to#service-for-fileexplorer)

Once you completed the above steps, you get an output like below,

![](Getting-Started_images/Getting-Started_img1.png)


