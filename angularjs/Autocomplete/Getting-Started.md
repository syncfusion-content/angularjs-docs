---
layout: post
title: Getting-Started with AngularJS Autocomplete Control | Syncfusion
description: Learn here about Getting Started with Syncfusion Essential AngularJS Autocomplete control, its elements, and more.
platform: AngularJS
control: Autocomplete 
documentation: ug
---

# Getting Started with AngularJS Autocomplete 

The AutoComplete control is a textbox control that provides a list of suggestions based on your query. When you enter text into the text box, the control performs a search operation and provides a list of results. There are several filter types available to perform the search.

This section helps to understand the getting started of the AutoComplete with the step-by-step instructions.

## Create an AutoComplete

Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called ejangular. To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.

Create a new HTML file and include the below code:

{% highlight html %}

<!DOCTYPE html>
<html lang="en" ng-app="syncApp">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for Listbox </title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/13.4.0.53/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/13.4.0.53/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/13.4.0.53/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="AutocompleteCtrl">
    <!--Add necessary HTML elements-->
</body>
</body>
</html>


{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter.  This object is used to bind the controller with view.   

Properties can be bind to ejListBox control using the prefix e- and particular property name as shown as below.

Create INPUT element and add in the body tag as below.


{% highlight html %}
        
       <body ng-controller="AutocompleteCtrl">
    <div class="container">
        <div style="text-align: -webkit-center; font-weight: 700;">
            Car Details</div>
        <div class="row">
            <div class="col-md-2">
                <p style="font-weight: 700;">
                    Car:</p>
            </div>
            <div class="col-md-10">
                <input type="text" ej-autocomplete e-width="50%" />
            </div>
        </div>
        <div class="row">
            <div class="col-md-2">
                <p style="font-weight: 700;">
                    Price:</p>
            </div>
            <div class="col-md-10">
                <input type="text" ej-autocomplete e-width="50%" />
            </div>
        </div>
    </div>
</body>


{% endhighlight %}

To render the ejAutocomplete using angular directive, we need to inject the ejangular module with modules.

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
         .controller('AutocompletexCtrl', function ($scope) {
         });

{% endhighlight %}


![Create HTML File in AngularJS Autocomplete](Getting_Started_Images/autocomplete.png)

## Model binding

The Autocomplete supports the data binding feature. When a widget’s model attribute is bound to a scope variable, it can reflect the changes both ways.

The below table depicts the properties of Autocomplete widget that supports model binding:

<table><tbody><tr><th>control</th><th>Supported properties</th></tr><tr><td>ejAutocomplete</td><td>value<br/>
selectValueByKey
</td></tr></tbody></table>

Add in the $scope value as below.

{% highlight html %}

        
        <body ng-controller="AutocompleteCtrl">
            <div class="container">
                <div style="text-align:-webkit-center;font-weight: 700;">Car Details</div>
                    <div class="row">
                        <div class="col-md-2">
                            <p style="font-weight: 700;">Car:</p>
                        </div>
                        <div class="col-md-2">
                            <p style="font-weight: 700;">{{setName}}</p>
                        </div>
                        <div class="col-md-8">
                            <input type="text" ej-autocomplete e-width="50%" e-value="setName"/>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-2">
                            <p style="font-weight: 700;">Price:</p>
                        </div>
                        <div class="col-md-2">
                            <p style="font-weight: 700;">{{setPrice}}</p>
                        </div>
                        <div class="col-md-8">
                            <input type="text" ej-autocomplete e-width="50%" e-value="setPrice"/>
                        </div>
                    </div>
                </div>
        </body>


{% endhighlight %}

![Model Binding in AngularJS Autocomplete](Getting_Started_Images/modelbinding.png)


## Data binding

The data for the suggestion list can be populated using the dataSource property. 

{% tabs %}
{% highlight html %}

        
        <body ng-controller="AutocompleteCtrl">
            <div class="container">
                <div style="text-align:-webkit-center;font-weight: 700;">Car Details</div>
                    <div class="row">
                        <div class="col-md-2">
                            <p style="font-weight: 700;">Car:</p>
                        </div>
                        <div class="col-md-2">
                            <p style="font-weight: 700;">{{setName}}</p>
                        </div>
                        <div class="col-md-8">
                            <input type="text" ej-autocomplete e-width="50%" e-value="setName" e-datasource="dataList" e-fields="nameField" />
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-2">
                            <p style="font-weight: 700;">Price:</p>
                        </div>
                        <div class="col-md-2">
                            <p style="font-weight: 700;">{{setPrice}}</p>
                        </div>
                        <div class="col-md-8">
                            <input type="text" ej-autocomplete e-width="50%" e-value="setPrice" e-datasource="dataList" e-fields="priceField" e-filtertype="greaterthanorequal"//>
                        </div>
                    </div>
                </div>
                </body>
{% endhighlight %}

{% highlight javascript %}
        var carsList = [{Price:22661.05,Mileage:20105,Cylinder:6,Doors:4,Name:"Acura"},
                    {Price:21725.01,Mileage:13457,Cylinder:6,Doors:2,Name:"Alfa Romeo"},
                    {Price:29142.71,Mileage:31655,Cylinder:4,Doors:2,Name:"Aston Martin"},
                    {Price:30731.94,Mileage:22479,Cylinder:4,Doors:2,Name:"Audi S6"},
                    {Price:33358.77,Mileage:17590,Cylinder:4,Doors:2,Name:"BMW 7"},
                    {Price:30315.17,Mileage:23635,Cylinder:4,Doors:2,Name:"Bentley Mulsanne"},
                    {Price:33381.82,Mileage:17381,Cylinder:4,Doors:2,Name:"Bugatti Veyron"},
                    {Price:30251.02,Mileage:27558,Cylinder:4,Doors:2,Name:"Chevrolet Camaro"},
                    {Price:30166.85,Mileage:25049,Cylinder:4,Doors:2,Name:"Cadillac"}
                    ];
        angular.module('syncApp', ['ejangular'])
            .controller('AutocompleteCtrl', function ($scope) {
                $scope.dataList = carsList;
                $scope.nameField = {text:"Name"};
                $scope.priceField = {text:"Price"};
        });       

{% endhighlight %}
{% endtabs %}

![Data Binding in AngularJS Autocomplete](Getting_Started_Images/databinding.png)

## Enable Popup Button

This button helps you to show all the available suggestions on clicking it.

{% tabs %}
{% highlight html %}
        
        <body ng-controller="AutocompleteCtrl">
            <div class="container">
                <div style="text-align:-webkit-center;font-weight: 700;">Car Details</div>
                    <div class="row">
                        <div class="col-md-2">
                            <p style="font-weight: 700;">Car:</p>
                        </div>
                        <div class="col-md-2">
                            <p style="font-weight: 700;">{{setName}}</p>
                        </div>
                        <div class="col-md-8">
                            <input type="text" ej-autocomplete e-width="50%" e-value="setName" e-datasource="dataList" e-fields="nameField"  e-showpopupbutton="true"/>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-2">
                            <p style="font-weight: 700;">Price:</p>
                        </div>
                        <div class="col-md-2">
                            <p style="font-weight: 700;">{{setPrice}}</p>
                        </div>
                        <div class="col-md-8">
                            <input type="text" ej-autocomplete e-width="50%" e-value="setPrice" e-datasource="dataList" e-fields="priceField" e-showpopupbutton="true" e-filtertype="greaterthanorequal" />
                        </div>
                    </div>
                </div>
            </body>
{% endhighlight %}

{% highlight javascript %}
        var carsList = [{Price:22661.05,Mileage:20105,Cylinder:6,Doors:4,Name:"Acura"},
                    {Price:21725.01,Mileage:13457,Cylinder:6,Doors:2,Name:"Alfa Romeo"},
                    {Price:29142.71,Mileage:31655,Cylinder:4,Doors:2,Name:"Aston Martin"},
                    {Price:30731.94,Mileage:22479,Cylinder:4,Doors:2,Name:"Audi S6"},
                    {Price:33358.77,Mileage:17590,Cylinder:4,Doors:2,Name:"BMW 7"},
                    {Price:30315.17,Mileage:23635,Cylinder:4,Doors:2,Name:"Bentley Mulsanne"},
                    {Price:33381.82,Mileage:17381,Cylinder:4,Doors:2,Name:"Bugatti Veyron"},
                    {Price:30251.02,Mileage:27558,Cylinder:4,Doors:2,Name:"Chevrolet Camaro"},
                    {Price:30166.85,Mileage:25049,Cylinder:4,Doors:2,Name:"Cadillac"}
                    ];
        angular.module('syncApp', ['ejangular'])
            .controller('AutocompleteCtrl', function ($scope) {
                $scope.dataList = carsList;
                $scope.nameField = {text:"Name"};
                $scope.priceField = {text:"Price"};
        });
{% endhighlight %}
{% endtabs %}

![Show PopUp in AngularJS Autocomplete](Getting_Started_Images/showpopup.png)

## Two Way Binding

We have a two way data binding when a model variable is bound to an element that can both change and display the value of the variable. 

{% tabs %}

{% highlight html %}

        
        <body ng-controller="AutocompleteCtrl">
            <div class="container">
                <div style="text-align:-webkit-center;font-weight: 700;">Car Details</div>
                    <div class="row">
                        <div class="col-md-2">
                            <p style="font-weight: 700;">Car:</p>
                        </div>
                        <div class="col-md-2">
                            <p style="font-weight: 700;">{{setName}}</p>
                        </div>
                        <div class="col-md-8">
                            <input type="text" ej-autocomplete e-width="50%" e-value="setName" e-datasource="dataList" e-fields="nameField"  e-showpopupbutton="true" e-select="autoSelect"/>
                        </div>
                    </div>
                    <div class="row">
                        <div class="col-md-2">
                            <p style="font-weight: 700;">Price:</p>
                        </div>
                        <div class="col-md-2">
                            <p style="font-weight: 700;">{{setPrice}}</p>
                        </div>
                        <div class="col-md-8">
                            <input type="text" ej-autocomplete e-width="50%" e-value="setPrice" e-datasource="dataList" e-fields="priceField" e-showpopupbutton="true" e-filtertype="greaterthanorequal" e-select="autoSelect"//>
                        </div>
                    </div>
                </div>
        </body>
{% endhighlight %}
{% highlight javascript %}
                    var carsList = [{Price:22661.05,Mileage:20105,Cylinder:6,Doors:4,Name:"Acura"},
                                {Price:21725.01,Mileage:13457,Cylinder:6,Doors:2,Name:"Alfa Romeo"},
                                {Price:29142.71,Mileage:31655,Cylinder:4,Doors:2,Name:"Aston Martin"},
                                {Price:30731.94,Mileage:22479,Cylinder:4,Doors:2,Name:"Audi S6"},
                                {Price:33358.77,Mileage:17590,Cylinder:4,Doors:2,Name:"BMW 7"},
                                {Price:30315.17,Mileage:23635,Cylinder:4,Doors:2,Name:"Bentley Mulsanne"},
                                {Price:33381.82,Mileage:17381,Cylinder:4,Doors:2,Name:"Bugatti Veyron"},
                                {Price:30251.02,Mileage:27558,Cylinder:4,Doors:2,Name:"Chevrolet Camaro"},
                                {Price:30166.85,Mileage:25049,Cylinder:4,Doors:2,Name:"Cadillac"}
                                ];
                    angular.module('syncApp', ['ejangular'])
                        .controller('AutocompleteCtrl', function ($scope) {
                            $scope.dataList = carsList;
                            $scope.nameField = {text:"Name"};
                            $scope.priceField = {text:"Price"};
                            $scope.autoSelect = function(args) {
                                $scope.setPrice = args.item.Price;
                                $scope.setName = args.item.Name;
                            }
                    });

{% endhighlight %}

{% endtabs %}

![Two Way Binding in AngularJS Autocomplete](Getting_Started_Images/twowaybinding.png)
