---
layout: post
title: Getting-Started
description: getting started
platform: js
control: MaskEdit
documentation: ug
---

# Getting Started

This section explains you briefly on how to create a **MaskEdit** control in your **JavaScript** application.

## Create your first MaskEdit Widget in AngularJS

Essential JavaScript **MaskEdit** control allows you to set the type and format of the input mask that is used in the textbox and also the number of place holders. Using the following guidelines, you can create **MaskEdit** control for a real-time application.

The following screenshot illustrates the functionality of a **MaskEdit**. Using **MaskEdit** control textbox, you can enter only the assigned text format and no other formats. The input mask prevents you from entering invalid characters into the control.

## Create a MaskEdit Control

**Essential** **JavaScript** **MaskEdit** widget provides you built-in features such as character masking, number masking and both together.

Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called  **ejangular****.** To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.

Create an **HTML** file and add the following template to the **HTML** file.

{% highlight html %}
<!doctype html>
<html lang="en" ng-app="MaskCtrl">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for MaskEdit </title>
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

## Add the input elements to create the MaskEdit.

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Properties can be bind to ejMaskEdit control using the prefix "e-" and particular property name as shown as below

{% highlight html %}
<table style="margin: auto">
<tbody>
    <tr>
        <td>
            <span>Enter product key</span>
        </td>
    </tr>
    <tr>
        <td>
         <input id="maskedit" type="text" ej-maskedit e-inputmode="ej.InputMode.Text" e-   maskformat='99-999' e-width="width" />        </td>
    </tr>
</tbody>
</table>
{% endhighlight %}

The following screenshot shows the output of the above code example.

![](Getting-Started_images/GettingStarted_img1.jpeg)


## DataBinding

The **MaskEdit** Textbox supports the data binding. When a widget’s model attribute is bound to a scope variable, it was bound in one way.

We have listed the properties of MaskEdit widget that supports the two way binding:


<table>
<tr>
<td>
**control******<br/><br/></td><td>
**Supported** **properties**<br/><br/></td></tr>
<tr>
<td>
ejMaskEdit<br/><br/></td><td>
Value<br/><br/></td></tr>
</table>

{% highlight html %}
<table style="margin: auto">
<tbody>
<tr>
<td>
    <span>MaskEdit Textbox</span>
</td>
</tr>
<tr>
<td>
    <input id="maskedit" type="text" ej-maskedit e-value="mvalue" e-inputmode="ej.InputMode.Text" e-maskformat='99-999' e-width="width" />
</td>
</tr>
<tr>
<td>
    <input id="maskedit2" type="text" ej-maskedit e-value="mvalue" e-inputmode="ej.InputMode.Text" e-maskformat='99-999' e-width="width" /><br />
</td>
</tr>
</tbody>
</table>
{% endhighlight %}

{% highlight html %}
angular.module('EditCtrl', ['ejangular'])
.controller('EditorsCtrl', function ($scope) {
$scope.mvalue = "12-345";
});
{% endhighlight %}
Execute the above code to render the following output.

![](Getting-Started_images/GettingStarted_img2.jpeg)
