---
layout: post
title: Getting Started with Syncfusion Essential JS Barcode widget
description: How to create one dimensional, two dimensional barcode and customizing the appearance of it.
platform: js
control: Barcode
documentation: ug
---

# Getting Started

This section explains you briefly on how to create one dimensional and two dimensional barcodes and customizing its appearance in your JavaScript application.

## Adding dependencies
The following steps guide you to add a Barcode component.
1.	Create an HTML file and add required scripts and CSS files for rendering Essential JavaScript component as given in the [Getting Started](https://help.syncfusion.com/js/angularjs).
2.	In addition to it for angular implementation, refer the "angular.min.js" and "ej.widgets.angular.min.js" files.

Add the below codes in corresponding tags.

{% highlight html %}

<html ng-app="syncApp">
<head>
    <title>Simple Barcode</title>
    <!-- Add Scripts and CSS for rendering Essential JS components -->
    <link href="css/default-theme/ej.widgets.all.min.css" rel="stylesheet" />
    <script src="scripts/jquery-1.11.3.min.js"></script>
    <script src="scripts/angular.min.js"></script>
    <script src="scripts/ej.web.all.min.js"></script>
    <script src="scripts/ej.widget.angular.min.js"></script>
</head>
<body>
    <div ng-controller="BarcodeCtrl">
        <div id="barcode" ej-barcode e-text="http://www.syncfusion.com">
        </div>
    </div>
</body>
</html>

{% endhighlight %}

## Component initialization

1.	Initialize the ng-app and ng-controller for the application. For adding Barcode component, you have to use **ej-barcode** directive to corresponding element.
2.	Now initialize the control using angular module in script section
 
Add the following in the script section.

{% highlight javascript %}

        angular.module('syncApp', ['ejangular'])
             .controller('BarcodeCtrl', function ($scope) {
                                               });

{% endhighlight %}

Run the above code and you will get output like this.

![](getting-started-images\default.png)

## Data binding

The data for the suggestion list can be populated using the dataSource property. 

{% tabs %}
{% highlight html %}

<html ng-app="syncApp">
<head>
    <title>Simple Barcode</title>
    <!-- Add Scripts and CSS for rendering Essential JS components -->
    <link href="css/default-theme/ej.widgets.all.min.css" rel="stylesheet" />
    <script src="scripts/jquery-1.11.3.min.js"></script>
    <script src="scripts/angular.min.js"></script>
    <script src="scripts/ej.web.all.min.js"></script>
    <script src="scripts/ej.widget.angular.min.js"></script>
</head>
<body>
    <div ng-controller="BarcodeCtrl">
        <div id="barcode" ej-barcode e-text="text_qr">
        </div>
    </div>
</body>
</html>

{% endhighlight %}

{% highlight javascript %}

        angular.module('syncApp', ['ejangular'])
             .controller('BarcodeCtrl', function ($scope) {
			     $scope.text_qr = "http://www.syncfusion.com";
                                               });

{% endhighlight %}
{% endtabs %}