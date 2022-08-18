---
layout: post
title: Getting-Started | RichTextEditor | JavaScript | Syncfusion
description: Learn here all about getting started support in Syncfusion AngularJS RichTextEditor control, its elements, and more.
platform: AngularJS
control: RichTextEditor Control
documentation: ug
keywords: ejrte, rte, js rte
---

# Getting Started with AngularJS RichTextEditor

This section helps to understand the getting started of RTE control with the step-by-step instruction.

## Create RTE Control in AngularJS

Essential JS includes angular directives for all controls in the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called angular.min.js. To render our ej controls in angular, you need to refer the **“angular.min.js”** and **“ej.widget.angular.min.js”** in your application.

The following steps describe the creation of **RTE** control.  

Create an **HTML** file and add the following template in the HTML file for creating **RTE** control.

{% highlight html %}

<!doctype html>
<html lang="en" ng-app="rteApp">
<head>
    <title>Essential Studio for JavaScript : AngularJS Support for RTE </title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script> 
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="RTECtrl">

<!--Add necessary HTML elements-->

</body>
</html>

{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter.  This object is used to bind the controller with view.   

Properties can be bind to ejRTE control using the prefix e- and particular property name.

{% highlight html %}

   <textarea id ="texteditor" ej-rte></textarea>

{% endhighlight %}

Initialize **RTE** in &lt;script&gt; tag.

To render the ejRTE using angular directive, we need to inject the ej angular directive with modules shown as below,

{% highlight js %}

    <script>
        angular.module('rteApp', ['ejangular'])
         .controller('RTECtrl', function ($scope) {
         });
    </script>

{% endhighlight %}

The following screenshot displays a RTE widget.

![AngularJS RichTextEditor initialize](/js/RichTextEditor/Getting-Started_images/Getting-Started_img1.png)

## Toolbar–Configuration

You can configure a toolbar with the tools as your application requires.

{% highlight html %}

 <textarea id ="texteditor" ej-rte e-toolslist="list" e-tools="tools"></textarea>

{% endhighlight %}

{% highlight js %}

    <script>
        angular.module('rteApp', ['ejangular'])
         .controller('RTECtrl', function ($scope) {
            $scope.list = ["style", "lists", "doAction", "links", "images"];
            $scope.tools= {style: ["bold", "italic"], lists: ["unorderedList", "orderedList"],doAction: ["undo", "redo"],links: ["createLink"],images: ["image"] }  
         });
    </script>

{% endhighlight %}

The following screenshot displays a RTE widget.

![AngularJS RichTextEditor toolbar configuration](/js/RichTextEditor/Getting-Started_images/Getting-Started_img2.png)

## Setting and Getting Content

You can set the content of the editor as follows.

{% highlight html %}

 <textarea id ="texteditor" ej-rte e-value="rteValue"></textarea>

{% endhighlight %}

{% highlight js %}

    <script>
       angular.module('rteApp', ['ejangular'])
         .controller('RTECtrl', function ($scope) {
            $scope.rteValue = "Description: The Rich Text Editor (RTE) control is an easy to render in client side. Customer easy to edit the contents and get the HTML content for the displayed content. A rich text editor control provides users with a toolbar that helps them to apply rich text formats to the text entered in the text area.";
         });
    </script>

{% endhighlight %}

The following screenshot displays a RTE widget.

![AngularJS RichTextEditor setting and getting ccontent](/js/RichTextEditor/Getting-Started_images/Getting-Started_img3.png)