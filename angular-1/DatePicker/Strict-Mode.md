---
layout: post
title: Strict Mode | TimePicker | AngularJS | Syncfusion
description: strict mode
platform: AngularJS
control: DatePicker
documentation: ug
---

# Strict Mode

Input the valid and invalid value behavior can be personalized with **e-enablestrictmode**. Setting false to this API, we can enter the valid date only and restrict other invalid dates. Providing wrong date will be set to previous value. By setting false invalid date can be entered but with **e-error** class.

Please refer the below code example

{% highlight html %}

     <input id="datepic" ej-datepicker e-enablestrictmode=false /> 

{% endhighlight %}
