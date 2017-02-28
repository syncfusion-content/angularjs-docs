---
layout: post
title: Data and Event Binding
description: data and event binding
pltform: AngularJS
control: Datepicker
documentation: ug
---

# Data and Event Binding

## Two way binding 

In AngularJS framework, any changes to view proximately update to model, any changes in model directly updated with view rapidly.With **DatePicker** control, value API enabled with two way binding to achieve this delightful functionality. 

Please refer the below code example,

**HTML View Section:**

{% highlight html %}

     <input id="datepic" ej-datepicker e-value="date.val1" />
     <input id="datepic_2" ej-datepicker e-value="date.val1" />

{% endhighlight %}

**Controller Section:**

{% highlight javascript %}

     $scope.date = {
        val1: new Date("2/12/2016")
     }


{% endhihlight %}

## Event handlers

Component events and captured and processed based on application needs. These events can be registered with scope to enhance the component functionality with AngularJS. Please refer the below code example to check **e-select** event.

**HTML View Section:**

{% highlight html %}

     <input id="datepic_2" ej-datepicker e-select="select" />  

{% endhighlight %}

**Controller Section:**

{% highlight javascript %}

     $scope.select = function (args) {
        // required function
     }


{% endhighlight %}



