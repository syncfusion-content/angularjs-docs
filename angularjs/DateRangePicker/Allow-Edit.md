---
layout: post
title: Allow Edit 
description: Allow Edit
platform: AngularJS
control: DataRangePicker
documentation: ug
---
# Allow Edit

Editing the value of the daterangepicker in the input box can be disabled by setting false value to allowEdit API. By default, this will be true and we can edit the value in input box. Disabling the editing of value in the daterangepicker can be done as mentioned in the code below.

{% highlight html %}

 <div ng-controller="dateRangeCtrl" >
        <input type="text" id="daterange" ej-daterangepicker e-value="value" e-width="300px" e-allowEdit="edit"/>
 </div>

{% endhighlight %}

{% highlight javascript %}

<script>
        angular.module('syncApp', ['ejangular'])
           .controller('dateRangeCtrl', function ($scope) {
               $scope.value = "5/13/2016 - 5/10/2018";
               $scope.edit = false;
           });
</script>

{% endhighlight %}

Run the above code to get the below output.

![](allow-edit_images/allow-edit.png)