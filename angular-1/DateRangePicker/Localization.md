---
layout: post
title: Localization
description: Localization
platform: Angular-1
control: DataRangePicker
documentation: ug
---
# Localization

DateRangePicker has been provided with Built-in localization support, so that it will be able adapt based on culture specific locale defined for it. To get the DateRangePicker for different localizations, add the required scripts in your code and can bind different values of localization using locale keyword. Please check the below snippets for scripts and usage of localization in DateRangePicker . You can get the script required for localization from getting started.

{% highlight html %}

<div ng-controller="dateRangeCtrl" >
        <input type="text" id="daterange" ej-daterangepicker e-value="value" e-locale="locale"   e-width="300px" />
</div>

{% endhighlight %}

{% highlight javascript %}

<script>
      angular.module('syncApp', ['ejangular'])
      .controller('dateRangeCtrl', function ($scope) {
      $scope.value ="1/1/2017 - 2/2/2017";
      $scope.locale= "vi-VN";
      });

</script>

{% endhighlight %}

Run the above code to get the below output.

![](localization/localization.png)