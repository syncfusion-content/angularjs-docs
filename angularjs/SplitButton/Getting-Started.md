---
layout: post
title: Getting-Started
description: getting started 
platform: Angular-1
control: Split Button
documentation: ug
---

# Getting Started 

This section explains briefly about how to create a **Split Button** in your application with **JavaScript**.The **HTML** button element and the **&lt;UL&gt;, &lt;LI&gt;** are easily configured as **Essential JavaScript Split Button** control.  The basic rendering of **Essential JavaScript Split** **Button** is achieved by using default functionality. Initially the **targetID** is a mandatory one, without this field it does not act as normal button on two sides.


![](/js/SplitButton/Getting-Started_images/Getting-Started_img1.png)

## Split Button Creation

1. Create an **HTML** file and add the following template to **HTML** file for **Split Button** creation.
2. Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called **ejangular**. To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.


{% highlight html %}

<!doctype html>
<html lang="en" ng-app="SplitButtn">
<head>
    <title>Getting Started Essential JS</title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="SplitButton">
    <!--add button element here-->
</body>
</html>


{% endhighlight %}

N> jQuery.easing external dependency has been removed from version 14.3.0.49 onwards. Kindly include this jQuery.easing dependency for versions lesser than 14.3.0.49 in order to support animation effects.

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Properties can be bind to ejSplitButton control using the prefix e- and particular property name as shown as below

Adding button element and **&lt;UL&gt;, &lt;LI&gt;** element for **Split** **Button** rendering.

{% highlight html %}
<button id="save" ej-splitbutton e-showroundedcorner="true" e-targetid="menu1" e-text="Save" e-width="width" e-height="height" ></button>                        
<ul id="menu1">
    <li><a href="#">Open..</a></li>
    <li><a href="#">Save</a></li>
    <li><a href="#">Delete</a></li>
</ul>
{% endhighlight %}


Add the angular module in script section as mentioned below.

{% highlight javascript %}

<script type="text/javascript">
            
    angular.module('SplitButtn', ['ejangular'])
        .controller('SplitButton', function ($scope) {
            $scope.width = "120px";
            $scope.height = "50px";
    });
</script>

{% endhighlight %}

Output of above steps

![](/js/SplitButton/Getting-Started_images/Getting-Started_img2.png) 

