---
layout: post
title: Getting started with DatePicker
description: To get start with DatePicker by adding references.
platform: Angular-1
control: DatePicker
documentation: ug
---
# Getting Started

## A new HTML document and required codes

To get start with DatePicker, create a new HTML file and refer the below specified dependent CSS file as well as scripts files.

**CSS file**

* [ej.web.all.min.css](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css) – includes all widgets styles (To know more about theme refer [Theming in Essential JavaScript Component](http://help.syncfusion.com/js/theming-in-essential-javascript-components#))

**Script files**

* [ej.web.all.min.js](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js )

* [ej.widget.angular.min.js](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js)

**External script files**

* [jQuery](http://jquery.com/#) (from the version 1.7.1 to 3.1.0)

* [angular.min.js](http://cdn.syncfusion.com/js/assets/external/angular.min.js)

N> From V13.4.0.53 onwards, jQuery.globalize.min.js file has been replaced with our script file ej.globalize.min.js to support the globalization for our widgets. For version lower than 13.4.0.53, refer jQuery.globalize.min.js. jQuery.easing external dependency has been removed from version 14.3.0.49 onwards. Kindly include this jQuery.easing dependency for versions lesser than 14.3.0.49 in order to support animation effects.

*Internal script files*

<table>
<tr>
<th>
File </th><th>
Description / Usage </th></tr>
<tr>
<td>
ej.core.min.js<br/><br/></td><td>
Includes only the widget basic functions and Framework features. Must be referred always before using all the JS controls<br/><br/></td></tr>
<tr>
<td>
ej.globalize.min.js<br/><br/></td><td>
To support the globalization.<br/><br/></td></tr>
<tr>
<td>
ej.datepicker.min.js<br/><br/></td><td>
DatePicker plugin.<br/><br/></td></tr>
</table>

N> From V13.4.0.53 onwards, jQuery.globalize.min.js file has been replaced with our script file ej.globalize.min.js to support the globalization for our widgets. For version lower than 13.4.0.53, refer jQuery.globalize.min.js.

You can make use of ‘ej.web.all.min.js’ file which encapsulates all ‘ej’ web components and frameworks in single file.

* [ej.web.all.min.js](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js) – includes all web widgets.

N>  In production, we highly recommend you to use our [custom script generator](http://helpjs.syncfusion.com/js/include-only-the-needed-widgets#) to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [GZip compression](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en#text-compression-with-gzip) in your server. 

A simple HTML file with required CSS and script reference added to create DatePicker

1. Create an HTML file and add required scripts and CSS files to render the Essential JavaScript component as given in the [Getting Started](https://help.syncfusion.com/js/control-initialization).
2. Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called **ejangular**. To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.


{% highlight html %}

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="DatePickCtrl">
    <head>
        <meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8" />
        <!-- style sheet for default theme(flat azure) -->
        <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <!--scripts-->
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js"></script>
        <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    </head>
    <body ng-controller="DatePickCtrller">
        <!--Place input element to create DatePicker-->
        <script>

            // Place your script code here to initialize DatePicker

        </script>
    </body>
    </html>

{% endhighlight %}

## DatePicker Initialization

DatePicker can be created using ‘input’ element

{% highlight html %}
    <!--input element to create DatePicker-->
    <input id="datePicker" ej-datepicker/>
{% endhighlight %}

N>  DatePicker is a form control, so on form submitting its value can be retrieved by its **name**. By default **id** has been treated as name, if ‘name’ attribute is not specified.

## Get / Set value

DatePicker provides an options to configure all its properties and get its value. DatePicker value can be assigned during initialization or at run time. Below code shows how to assign values at initialization.

{% highlight html %}
 <input id="datePicker" ej-datepicker e-value="dateValue" e-dateFormat= "dateFormat"/>
{% endhighlight %}

{% highlight javascript %}
        angular.module('DatePickCtrl', ['ejangular'])
           .controller('DatePickCtrller', function ($scope) {
              $scope.dateValue = new Date(); // sets the current date
              $scope.dateFormat = "yyyy/MM/dd"; // sets the date format
           });
{% endhighlight %}

You can assign values after initialization in DatePicker (‘it helps to get or set value at run time). Let’s consider that going to set date value at button click.

{% highlight html %}
 <input id="datePicker" ej-datepicker e-value="dateValue" e-dateFormat= "dateFormat"/>
 <button ej-button e-text="GetValue" e-click="onClick"></button>
{% endhighlight %}

{% highlight javascript %}
        angular.module('DatePickCtrl', ['ejangular'])
           .controller('DatePickCtrller', function ($scope) {
              $scope.dateValue = new Date(); // sets the current date
              $scope.dateFormat = "yyyy/MM/dd"; // sets the date format
              $scope.onClick = function(e) {
                  $scope.value = new Date("12/12/2012"); //set value
                  alert($scope.value);
              }
           });
{% endhighlight %}

