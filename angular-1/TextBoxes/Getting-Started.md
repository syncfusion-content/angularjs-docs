---
layout: post
title: Getting-Started
description: getting started
platform: js
control: TextBoxes
documentation: ug
---

# Getting Started

This section explains briefly about how to create a **EJ** **TextBox** control in your application with **JavaScript**. From the following steps you can learn how to create and use **EJ** **TextBox** in your application. Here we have showcased the Textbox controls.

![](Getting-Started_images/GettingStarted_img1.jpeg)


## Create Textboxes Widgets

Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called **ejangular**. To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.

Create an **HTML** file and add the following template to the HTML file for Textbox widget creation.

<table>
<tr>
<td>
<!doctype html><br/><br/><html lang="en" ng-app="EditCtrl"><br/><br/><head><br/><br/><title>Essential Studio for JavaScript : Angular JS Support for Textboxes </title><br/><br/><!-- Style sheet for default theme (flat azure) --><br/><br/><link href="http://cdn.syncfusion.com/14.3.0.49/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" /><br/><br/><!--Scripts--><br/><br/><script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script><br/><br/><script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"></script><br/><br/><script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script><br/><br/><script type="text/javascript" src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js "></script><br/><br/><script src="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.widget.angular.min.js"></script><br/><br/><!--Add custom scripts here --><br/><br/></head><br/><br/><body><br/><br/><!--Add the Textbox elements here--><br/><br/></body><br/><br/></html><br/><br/></td></tr>
</table>
The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Properties can be bind to ejTextboxes control using the prefix e- and particular property name as shown as below

Add the input elements

<table>
<tr>
<td>
<table class="sample" style="margin: auto"><br/><br/><tbody><br/><br/><tr><br/><br/><td><br/><br/><span>Numeric Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="numeric" type="text" ej-numerictextbox e-value="nvalue" /><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><span>Percentage Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="percent" type="text" ej-percentagetextbox e-value="pvalue" /><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><span>Currency Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="currency" type="text" ej-currencytextbox e-value="cvalue" /><br/><br/></td><br/><br/></tr><br/><br/></tbody><br/><br/></table><br/><br/></td></tr>
</table>
Set the value in the controller

<table>
<tr>
<td>
angular.module('EditCtrl', ['ejangular'])<br/><br/>.controller('EditorsCtrl', function ($scope) {<br/><br/>$scope.nvalue = 600;<br/><br/>$scope.pvalue = 400;<br/><br/>$scope.cvalue = 400; <br/><br/>});<br/><br/></td></tr>
</table>
Execute the above code to render the following output

![](Getting-Started_images/GettingStarted_img2.jpeg)


## Set the MinValue, MaxValue and Value in Textoxes

You can set the **“****minValue****”,** **“****maxValue****”** and **“****value****”** in Numeric, Percentage and Currency text boxes for maintaining the range in Textboxes widgets. In this scenario, you have to enter the values between the given ranges. The following code example illustrates how to achieve this.

<table>
<tr>
<td>
table class="sample" style="margin: auto"><br/><br/><tbody><br/><br/><tr><br/><br/><td><br/><br/><span>Numeric Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="numeric" type="text" ej-numerictextbox e-value="100" e-maxvalue="1000" /><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><span>Percentage Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="percent" type="text" ej-percentagetextbox e-value="50" e-maxvalue="1000" /><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><span>Currency Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="currency" type="text" ej-currencytextbox e-value="20" e-maxvalue="1000" /><br/><br/></td><br/><br/></tr><br/><br/></tbody><br/><br/></table><br/><br/></td></tr>
</table>
The following screenshot shows the output for the above code

![](Getting-Started_images/GettingStarted_img3.jpeg)


## Set the Strict Mode option

You can set the “**StrictMode****”** **option** to restrict entering values defined outside the range. The following code example illustrates how to set strict mode option.

<table>
<tr>
<td>
table class="sample" style="margin: auto"><br/><br/><tbody><br/><br/><tr><br/><br/><td><br/><br/><span>Numeric Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="numeric" type="text" ej-numerictextbox e-value="100" e-maxvalue="1000" e-enablestrictmode="true" /><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><span>Percentage Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="percent" type="text" ej-percentagetextbox e-value="50" e-maxvalue="1000" e-enablestrictmode="true" /><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><span>Currency Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="currency" type="text" ej-currencytextbox e-value="20" e-maxvalue="1000" e-enablestrictmode="true" /><br/><br/></td><br/><br/></tr><br/><br/></tbody><br/><br/></td></tr>
</table>
<table>
<tr>
<td>
angular.module('EditCtrl', ['ejangular'])<br/><br/>.controller('EditorsCtrl', function ($scope) {<br/><br/>});<br/><br/></td></tr>
</table>
The following screenshot show the output the for the above code

![](Getting-Started_images/GettingStarted_img4.jpeg)


## Data Binding

The EJ Textbox supports the data binding. When a widget’s model attribute is bound to a scope variable, it has been bound in one way.

We have listed the properties of **Textbox** widget that supports two way binding:

<table>
<tr>
<td>
**control******<br/><br/></td><td>
**Supported** **properties**<br/><br/></td></tr>
<tr>
<td>
ejNumericTextbox<br/><br/>ejCurrencyTextbox<br/><br/>ejPercentageTextbox<br/><br/></td><td>
Value<br/><br/><br/><br/></td></tr>
</table>
Please use the below code to bind the Textbox in two-way support.

<table>
<tr>
<td>
<table class="sample" style="margin: auto"><br/><br/><tbody><br/><br/><tr><br/><br/><td><br/><br/><span>Numeric Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="numeric" type="text" ej-numerictextbox e-value="nvalue" /><br/><br/></td><br/><br/></tr><br/><br/><tr> <br/><br/><td><br/><br/><input type="text" class="input ejinputtext" ng-model="nvalue" /><br /><br/><br/></td><br/><br/><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><span>Percentage Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="percent" type="text" ej-percentagetextbox e-value="pvalue" /><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input type="text" class="input ejinputtext" ng-model="pvalue" /><br /><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><span>Currency Textbox</span><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input id="currency" type="text" ej-currencytextbox e-value="cvalue" /><br/><br/></td><br/><br/></tr><br/><br/><tr><br/><br/><td><br/><br/><input type="text" class="input ejinputtext" ng-model="cvalue" /><br /><br/><br/></td><br/><br/></tr> <br/><br/></tbody><br/><br/></table><br/><br/></td></tr>
</table>
<table>
<tr>
<td>
angular.module('EditCtrl', ['ejangular'])<br/><br/>.controller('EditorsCtrl', function ($scope) {<br/><br/>$scope.nvalue = 600;<br/><br/>$scope.pvalue = 400;<br/><br/>$scope.cvalue = 400; <br/><br/>});<br/><br/></td></tr>
</table>
In the above sample, Textbox value was bind in two way method. Changes made in the textbox will reflect to another textbox.

Run the above code to render the following output.

![](Getting-Started_images/GettingStarted_img5.jpeg)


