---
layout: post
title: Customization | TimePicker | AngularJS | Syncfusion
description: customization
platform: AngularJS
control: DatePicker
documentation: ug
---

# Customization

## Dimensions

Height and width of the DatePicker input box, can be customized based on application needs by means of **e-height** and **e-width**.

{% highlight html %}

     <input id="datepic" ej-datepicker e-height="40px" e-width="200px" />  

{% endhighlight %}

## View levels

**Start** and **Depth level** of the DatePicker calendar can be customized based on application needs. EJ AngularJS DatePicker have four different levels of view. Please check below.

**“month”** – shows the days in month to pick.

**“year”** – shows the months in year to pick.

**“decade”** – shows the years in decade to pick.

**“century”** – shows the decades in century to pick.

**Levels:**

**startLevel** - sets the start view in DatePicker calendar.

**depthLevel** - defines when the DatePicker calendar to return date.

This levels can be set through **e-startlevel**, **e-depthlevel** like below code example.

{% highlight html %}

     <input id="datepic" ej-datepicker e-startlevel="'year'" e-depthlevel="'year'" />

{% endhighlight %}

