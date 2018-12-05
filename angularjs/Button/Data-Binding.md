---
layout: post
title: Data Binding | Button | AngularJS | Syncfusion
description: Data Binding 
platform: AngularJS
control: Button
documentation: ug
---

# Data Binding

## One-way binding

In buttons, One-way binding can be achieved by using "e-" prefixed with the property name. All the properties related to the buttons are one-way bindable. Here, the one-way binding property of the button has been explained with the text property in the below code example.

{% highlight html %}

    <div ng-controller="ButtonCtrl">
    <div>
            <button id="button1" ej-button e-size="large" e-text="text"></button>
    </div>
    <div>
   
{% endhighlight %}

{% highlight javascript %}

    <script>
        angular.module('buttonApp', ['ejangular'])
        .controller('ButtonCtrl', function ($scope) {
            $scope.text = "Click Me";
        });
    </script>
    
{% endhighlight %}

Run the above code to get the below output.

![One-way binding](Data-Binding_images/one-way-binding.png)

## Event Binding

The event binding allows you to add an event handler for a specified event so that your the function will be invoked when that event is triggered. In AngularJS, we can bind functions to events of a button. Please refer the code sample below.

{% highlight html %}

    <div ng-controller="ButtonCtrl">
    <div align="center">
            <button id="button1" ej-button e-size="large" e-text="Click Me" e-click="onClick"></button>
    </div>
    <div>
   
{% endhighlight %}

{% highlight javascript %}

    <script>
            angular.module('buttonApp', ['ejangular'])
            .controller('ButtonCtrl', function ($scope) {
                $scope.onClick = function (e) {
                    alert("Button has been clicked");
                }
            });
    </script>
    
{% endhighlight %}

Run the above code to get the below output.

![Event Binding](Data-Binding_images/event-binding.png)

