---
layout: post
title: Enable Persistence 
description: Enable Persistence
platform: AngularJS
control: DataRangePicker
documentation: ug
---
# Enable Persistence

The value of DateRangePicker can be sustained even after form post back and page refreshing by enabling the enablePersistence API as shown in the below code example.

{% highlight html%}

<div ng-controller="DaterangeCtrl">
     <input type="text" id="daterange" ej-daterangepicker e-width="width" e-enablePersistence="enable" />
</div>

{% endhighlight %}

{% highlight javascript %}

<script>
    angular.module('syncApp', ['ejangular'])
       .controller('DateRangeCtrl', function ($scope) {
          $scope.width = "600px";
          $scope.enable = true;
           });
</script>

{% endhighlight %}

Run the above code to get the below output.

![](enable-persistence_images/persistence.png)

The DateRangePicker Model value will be stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh