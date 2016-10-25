---
layout: post
title: Getting started | ListBox | JavaScript | Syncfusion
description: Getting started with listbox widget in angularjs
platform: Angular-1
control: ListBox
documentation: ug
---


## Getting Started
The ListBox widget that contains a list of selectable items. It performs exceptionally well with thousands of items and supports checkboxes, template, single and multiple selection, keyboard navigation and virtual scrolling.
This section explains briefly about how to create a web ListBox in your application with Angular JavaScript by step-by-step instructions. The following screenshot illustrates the functionality of a ListBox widget.


![](Getting_Started_images\Getting-Started_img1.png)

## Create a ListBox widget in AnularJS

Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called **ejangular**. To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.

Create a new HTML file and include the below code:

{% highlight html %}

<!DOCTYPE html>
<html lang="en" ng-app="listboxApp">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for Listbox </title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.1.0.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="ListboxCtrl">
    <!--Add necessary HTML elements-->
</body>
</body>
</html>


{% endhighlight %}



The ng-app directive explains the root element (&lt;html&gt; or &lt;body&gt; tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter.  This object is used to bind the controller with view.   

Properties can be bind to ejListBox control using the prefix e- and particular property name as shown as below

Create UL and LI elements and add in the body tag as below.

{% highlight html %}

<div>
    <ul id="list1" ej-listbox>
        <li>Audi A4</li>
        <li>Audi A5</li>
        <li>Audi A6</li>
        <li>Audi A7</li>
        <li>Audi A8</li>
        <li>BMW 501</li>
        <li>BMW 502</li>
        <li>BMW 503</li>
        <li>Batch</li>
        <li>BMW 507</li>
        <li>BMW 3200</li>
        <li>Cut</li>
    </ul>
</div>


{% endhighlight %}



To render the ejListBox using angular directive, we need to inject the **ejangular** module with modules.

{% highlight js %}

    <script>
        angular.module('listboxApp', ['ejangular'])
         .controller('ListboxCtrl', function ($scope) {
         });
    </script>



{% endhighlight %}



## Data binding

The **Listbox** supports the data binding feature. When a widget’s model attribute is bound to a scope variable, it can reflect the changes both ways.

The below table depicts the properties of **ListBox** widget that supports model binding:

<table>
<tr>
<td>
<b>control</b></td><td>
<b>Supported properties</b></td></tr>
<tr>
<td>
ejListbox</td><td>
valuedataSource</td></tr>
</table>


Please use the below code the bind the **ListBox** in two-way support.

{% highlight html %}

<div class="content-container-fluid">
    <div class="row">
        <div class="cols-sample-area">
            <div class="frame">
                <div class="ctrllabel">Select a car</div>
                <div class="angularbind">
                    <div id="control">
                        <div>
                            <ul id="Ul1" ej-listbox e-datasource="datalist" e-fields-id="id" e-fields-text="text" e-value="value"></ul>
                        </div>
                    </div>
                    <div id="binding">
                        <input type="text" id="listValue" class="input ejinputtext" ng-model="value" />
                    </div>
                    <h6><span style="font-style: italic; font-weight: normal; margin: 5px; text-align: center">Note:Two Way Angular Support</span></h6>
                </div>
            </div>
        </div>
    </div>
</div>


{% endhighlight %}



{% highlight js %}

        angular.module('listboxApp', ['ejangular'])
         .controller('ListboxCtrl', function ($scope) {
    $scope.dataList= [
           { bikeId: "bk1", bikeName: "Apache RTR" },
           { bikeId: "bk2", bikeName: "CBR 150-R" },
           { bikeId: "bk3", bikeName: "CBZ Xtreme" },
           { bikeId: "bk4", bikeName: "Discover" },
           { bikeId: "bk5", bikeName: "Dazzler" },
           { bikeId: "bk6", bikeName: "Flame" },
           { bikeId: "bk7", bikeName: "Fazer" },
           { bikeId: "bk8", bikeName: "FZ-S" },
           { bikeId: "bk9", bikeName: "Pulsar" },
           { bikeId: "bk10", bikeName: "Shine" },
           { bikeId: "bk11", bikeName: "R15" },
           { bikeId: "bk12", bikeName: "Unicorn" }
    ];


$scope.value = "Dazzler";
         });


{% endhighlight %}


Here the ngModel directive binds an input, select, textarea (or custom form control) to a property on the scope using [NgModelController](https://docs.angularjs.org/api/ng/type/ngModel.NgModelController), which is created and exposed by this directive. 

Run the above code to render the following output. 

![](Getting_Started_images\databinding_img1.png)



## Selection

The ListBox widget also supports the item selection. 

{% highlight html %}

<div>
    <ul id="listbox" ej-listbox e-datasource="datalist" e-fields-id="id" e-fields-text="text" e-selectedindex="2"></ul>
</div>



{% endhighlight %}



Run the above code to render the following output. 

![](Getting_Started_images\selection_img1.png)




