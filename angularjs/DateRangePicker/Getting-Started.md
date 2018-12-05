---
layout: post
title: Getting Started | DataRangePicker | AngularJS | Syncfusion
description: Getting Started
platform: AngularJS
control: DataRangePicker
documentation: ug
---
# Getting Started

This section explains briefly about how to create a DateRangePicker in your application with JavaScript.

Essential JavaScript DateRangePicker provides support to display two calendars within a webpage and allows you to pick a date and even time from the calendar. In this example, you learn how to customize DateRangePicker in real-time application.

## Creating a DateRangePicker

The DateRangePicker widget has built-in features such as keyboard navigation, other navigation with animations and flexible APIs. You can easily create the DateRangePicker widget by using simple input <textbox> element as follows.

1.Create an HTML file and add required scripts and CSS files to render the Essential JavaScript component as given in the [Getting Started](https://help.syncfusion.com/js/control-initialization).

2.Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called ejangular. To render our ej controls in angular, you need to refer the “angular.min.js” and ej.widget.angular.min.js" in your application.

{% highlight html %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" ng-app="BtnCtrl">
   <head>
      <meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8" />
      <!-- Style sheet for default theme (flat azure) -->
      <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/gradient-saffron-dark/ej.web.all.min.css" rel="stylesheet" />
      <!--Scripts-->
      <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
      <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
      <!--Add custom scripts here -->
   </head>
   <body ng-controller="BtnCtrller">
      <!-- Add button element Here -->
      <button id="button1" ej-button e-showroundedcorner="true" e-size="medium" e-text="login"></button>      
   </body>
</html>

{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Properties can be bind to ejDateRangePicker control using the prefix e- and particular property name as shown as below.

{% highlight html %}

<div>
     <input type="text" id="daterange" ej-daterangepicker e-value="value" e-width="300px" />
</div>

{% endhighlight %}

{% highlight javascript %}

<script>
     angular.module('syncApp', ['ejangular'])
        .controller('dateRangeCtrl', function ($scope) {
            $scope.value = "5/28/2016 - 5/28/2018";
              });
</script>

{% endhighlight %}

Run the above code to get the below output.

![Creating a DateRangePicker](getting-started_images/value.png)
