---
layout: post
title: Getting-Started
description: getting started
platform: AngularJS
control: PercentageTextbox
documentation: ug
---

# Getting Started

This section explains briefly about how to create a **PercentageTextBox** control in your application with **JavaScript**. From the following steps you can learn how to create and use **PercentageTextBox**  in your application. Here we have showcased the Textbox controls.

![](Getting-Started_images/Getting-Started_img1.jpeg)


## Create Textboxes Widgets

Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called **ejangular**. To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.

Create an **HTML** file and add the following template to the HTML file for Textbox widget creation.

{% highlight html %}
<!doctype html>
<html lang="en" ng-app="EditCtrl">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for Percentage Textbox </title>
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
    <!--Add the Textbox elements here-->
</body>
</html>

{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Properties can be bind to ejPercentageTextbox control using the prefix e- and particular property name as shown as below

Add the input elements

{% highlight html %}
<table  style="margin: auto">
<tbody>
<tr>
    <td>
        <span>Percentage Textbox</span>
    </td>
</tr>
<tr>
    <td>
        <input id="percent" type="text" ej-percentagetextbox e-value="pvalue" />
    </td>
</tr>
</tbody>
</table>
{% endhighlight %}

Set the value in the controller

{% highlight html %}
angular.module('EditCtrl', ['ejangular'])
           .controller('EditorsCtrl', function ($scope) {
               $scope.pvalue = 400;
           });
{% endhighlight %}

Execute the above code to render the following output

![](Getting-Started_images/Getting-Started_img2.jpeg)


## Set the MinValue, MaxValue and Value in Textboxes

You can set the **“****minValue****”,** **“****maxValue****”** and **“****value****”** in Numeric, Percentage and Currency text boxes for maintaining the range in Textboxes widgets. In this scenario, you have to enter the values between the given ranges. The following code example illustrates how to achieve this.

{% highlight html %}
<table style="margin: auto">
<tbody>
<tr>
    <td>
        <span>Percentage Textbox</span>
    </td>
</tr>
<tr>
    <td>
        <input id="percent" type="text" ej-percentagetextbox e-value="50" e-maxvalue="1000" />
    </td>
</tr>
</tbody>
</table>
{% endhighlight %}

The following screenshot shows the output for the above code

![](Getting-Started_images/Getting-Started_img3.jpeg)


## Set the Strict Mode option

You can set the “**StrictMode****”** **option** to restrict entering values defined outside the range. The following code example illustrates how to set strict mode option.

{% highlight html %}
<table  style="margin: auto">
<tbody>
<tr>
    <td>
        <span>Percentage Textbox</span>
    </td>
</tr>
<tr>
    <td>
        <input id="percent" type="text" ej-percentagetextbox e-value="50" e-maxvalue="1000" e-enablestrictmode="true" />
    </td>
</tr>
</tbody>
</table>
{% endhighlight %}

{% highlight html %}
angular.module('EditCtrl', ['ejangular'])
           .controller('EditorsCtrl', function ($scope) {
           });
{% endhighlight %}

The following screenshot show the output the for the above code

![](Getting-Started_images/Getting-Started_img4.jpeg)


## Data Binding

The EJ Textbox supports the data binding. When a widget’s model attribute is bound to a scope variable, it has been bound in one way.

We have listed the properties of **Textbox** widget that supports two way binding:




<table>
<tr>
<td>
<b>control</b><br/><br/></td><td>
<b>Supported properties</b><br/><br/></td></tr>
<tr>
<td>
ejPercentageTextbox<br/><br/></td><td>
Value<br/><br/><br/><br/></td></tr>
</table>
Please use the below code to bind the Textbox in two-way support.

{% highlight html %}
<table style="margin: auto">
<tbody>
<tr>
    <td>
        <span>Percentage Textbox</span>
    </td>
</tr>
<tr>
    <td>
        <input id="percent" type="text" ej-percentagetextbox e-value="pvalue" />
    </td>
</tr>
<tr>
    <td>
        <input type="text" class="input ejinputtext" ng-model="pvalue" /><br />
    </td>
</tr>

</tbody>
</table>
{% endhighlight %}

{% highlight html %}
angular.module('EditCtrl', ['ejangular'])
           .controller('EditorsCtrl', function ($scope) {
               $scope.pvalue = 400;
           });
{% endhighlight %}

In the above sample, Textbox value was bind in two way method. Changes made in the textbox will reflect to another textbox.

Run the above code to render the following output.

![](Getting-Started_images/Getting-Started_img5.jpeg)
