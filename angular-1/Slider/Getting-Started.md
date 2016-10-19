---
layout: post
title: Getting-Started
description: getting started
platform: js
control: Slider
documentation: ug
---

# Getting Started

This section explains briefly about how to create a Slider in your application with **AngularJS**. The following examples shows how to use slider control.

## Create the Slider Widget in angularJS

Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called **ejangular**. To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.

Create a new HTML file and include the below code:

<table>
<tr>
<td>
<!doctype html><br/><br/><html lang="en" ng-app="sliderApp"><br/><br/><head><br/><br/><title>Essential Studio for JavaScript : Angular JS Support for Slider </title><br/><br/><!-- Style sheet for default theme (flat azure) --><br/><br/><link href="http://cdn.syncfusion.com/14.3.0.49/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" /><br/><br/><!--Scripts--><br/><br/><script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script><br/><br/><script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"></script><br/><br/><script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script><br/><br/><script type="text/javascript" src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js "></script><br/><br/><script src="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.widget.angular.min.js"></script><br/><br/><!--Add custom scripts here --><br/><br/></head><br/><br/><body ng-controller="SliderCtrl"><br/><br/><!--Add the slider element and controller--><br/><br/></body><br/><br/></html><br/><br/></td></tr>
</table>
The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Properties can be bind to ejSlider control using the prefix e- and particular property name as shown as below.

<table>
<tr>
<td>
<div id="BasicSlider" ej-slider e-height="20" e-width="500"></div><br/><br/></td></tr>
</table>
To render the ejSlider using angular directive, we need to inject the **ejangular** module with modules.

<table>
<tr>
<td>
<script><br/><br/>angular.module('sliderApp', ['ejangular'])<br/><br/>.controller('SliderCtrl', function ($scope) {<br/><br/>});<br/><br/></script><br/><br/></td></tr>
</table>
The following screenshot displays a default slider using angularJS

![](Getting-Started_images/GettingStarted_img1.jpeg)


## Data Binding

The **Slider** supports the data binding. When a widget’s model attribute is bound to a scope variable, it was bound in one way.

We have listed the properties of Slider widget that supports the two way binding:

<table>
<tr>
<td>
Widget<br/><br/></td><td>
Supported Property<br/><br/></td></tr>
<tr>
<td>
ejSlider<br/><br/></td><td>
Value,<br/><br/>values<br/><br/></td></tr>
</table>
Please use the below code to bind the slider in Two-way binding.

<table>
<tr>
<td>
<div class="angularbind"><br/><br/><div id="control"><br/><br/><div id="Slider" ej-slider e-width="width" e-value="sliderValue" e-height="height"></div><br/><br/></div><br/><br/><span>Slider value</span><br/><br/><div id="binding"><br/><br/><input type="text" name="slider" class="input ejinputtext" ng-model="sliderValue" /><br/><br/></div><br/><br/></div><br/><br/></td></tr>
</table>
<table>
<tr>
<td>
angular.module('sliderApp', ['ejangular']).controller('SliderCtrl', function ($scope) {<br/><br/>$scope.sliderValue = 60;<br/><br/>$scope.width = "300";<br/><br/>$scope.height = "18"<br/><br/>});<br/><br/></td></tr>
</table>
In the above sample, Slider value was bind in two way method. Changes made in the slider will reflect to the textbox in vice versa.

Execute the above to render the following output.

![](Getting-Started_images/GettingStarted_img2.jpeg)


