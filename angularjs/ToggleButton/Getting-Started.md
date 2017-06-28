---
layout: post
title: Getting-Started
description: getting started
platform: AngularJS
control: Toggle Button
documentation: ug
---

# Getting Started

This section explains briefly about how to create a **Toggle Button** in your application with **AngularJS** 

## Control structure

The HTML checkbox element can be easily configured as **Essential JavaScript Toggle Button** control. The basic rendering of **Essential JavaScript Toggle Button** is achieved by using default functionality.

![](/js/ToggleButton/Getting-Started_images/Getting-Started_img1.png) 

![](/js/ToggleButton/Getting-Started_images/Getting-Started_img2.png) 


## Toggle Button Creation

Create an HTML file and paste the following template to HTML file for **ejToggleButton** creation.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" ng-app="ToggleCtrl">
<head>
    <title>Getting Started Essential JS</title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="ToggleButtonCtrl">
    <!--add Toggle Button element here-->
</body>
</html>

{% endhighlight %}


The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Properties can be bind to ejToggleButton control using the prefix e- and particular property name as shown as below


Adding input Checkbox element for Toggle Button rendering.

{% highlight html %}

<input type="checkbox" id="tbutton" ej-togglebutton e-size="size"/>
<label for="tbutton">Play</label>

{% endhighlight %}

{% highlight javascript %}

<script type="text/javascript">
            
    angular.module('ToggleCtrl', ['ejangular'])
        .controller('ToggleButtonCtrl', function ($scope) {
            $scope.size="large";
    });
</script>

{% endhighlight %}

N> The advantages of using checkbox element and label element for the rendering of Toggle Button are as follows.


## Checkbox Element

The HTML checkbox element is made as the base for **Essential JavaScript Toggle Button**, because to provide convenient look and feel while building forms and support basic methods and its states.


## Label Element

A label element has to be explicitly associate a form control. A label is attached to a specific form control through the use of for attribute. The value of for attribute must be the same as the value of the id attribute of the form control. Clicking on the label or the control will activate the control in order to provide larger area of the control.


Output of above steps

![](/js/ToggleButton/Getting-Started_images/Getting-Started_img4.png) 

