---
layout: post
title: Behavior Settings
description: behavior settings
platform: AngularJS
control: Datepicker
documnetation: ug
---

# Behavior Settings

## Set Value

**DatePicker** value API is two way binding enabled API that can be accessed by using **“e-value attribute”**. This API value could be set either as a Date object or a formatted string. Adding this **e-value** to element that resides inside the form/ng-form will add the all required AngularJS attributes (ng-model, ng-update-on, etc,.) and required form validation classes. To know more about AngularJS validation with DatePicker please refer here.

Please check with the below code example,

**HTML view section:**

{% highlight html %}

     <input id="datepic" ej-datepicker e-value="date.val1" />

{% endhighlight %}

**Controller Section:**

{% highlight javascript %}

     angular.module("myApp", ['ejangular']).controller("datepicker", function ($scope) {
        $scope.date = { val1: new Date("12/1/2016"), val2: "" }

     })


{% endhighlight %}

Here both two DatePicker e-value API is bounded to scope variable “dateValue”, since **e-value** is two way binding enabled API, change in one DatePicker will change another DatePicker value.

## Get Value

DatePicker value could be accessed by using DatePicker instance as given below.

{% highlight javascript %}

     var obj = $("#datepic").ejDatePicker("instance");
     alert(obj.option("value"));

{% endhighlight %}

## Date Ranges

Date selection can be restricted using our offered APIs **e-minDate** and **e-maxDate**, which is used to set the minimum date that can be selected and maximum date range that can be chosen. 

These APIs value can be updated directly in inline, else via scope also. Please check with the below code example.

**Html View Section:**

{% highlight html %}

     <input id="datepic" ej-datepicker e-maxdate="date.max" e-mindate="date.min" e-value="date.val1" />

{% endhighlight %}

**Controller Section:**

{% highlight javascript %}

    $scope.date = {
        min: new Date("1/11/2016"),
        val1: new Date("2/12/2016"),
        max: new Date("3/13/2016")
    }

{% endhighlight %}

## HighlightWeekends 

Weekends of DatePicker can be highlighted on DatePicker to differentiate the weekends from rest of the days. This is Boolean type API and it can be attained using **e-highlightweekend** API like below code example

**HTML View Section:**

{% highlight html %}

     <input id="datepic" ej-datepicker e-highlightweekend=true />

{% endhighlight %}


