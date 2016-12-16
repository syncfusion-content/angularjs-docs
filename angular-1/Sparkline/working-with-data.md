---
layout: post
title: Data binding
description: Learn how to bind Sparkline with local data.
platform: Angular 1.0
control: Sparkline
documentation: ug
---

# Working with Data

You can bind data to the sparkline in two ways 

1. You can bind the data to the Sparkline by using `e-dataSource` property and then you need to map the **X** and **Y** value with **xName** and **yName** properties respectively.

{% highlight javascript %}
<html ng-app="syncApp">
     <head>
         <script type="text/javascript" src="http://cdn.syncfusion.com/js/assets/external/jquery-2.1.4.min.js"></script>
         <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
         <script src="https://cdn.syncfusion.com/14.2.0.26/js/web/ej.web.all.min.js"></script>
         <script src="https://cdn.syncfusion.com/14.2.0.26/js/common/ej.widget.angular.min.js"></script>
     </head>
<body ng-controller="sparkline">
<div id="column" ej-sparkline e-datasource="sparklinedata" e-xname="employeeId" e-yname="sales"></div>
<script>
    var var sparklinedata = [
{ employeeId: 1, sales: 25 },
{ employeeId: 2, sales: 28 },
{ employeeId: 3, sales: 34 },
{ employeeId: 4, sales: 32 },
{ employeeId: 5, sales: 40 },
{ employeeId: 6, sales: 32 },
{ employeeId: 7, sales: 35 },
{ employeeId: 8, sales: 55 },
{ employeeId: 9, sales: 38 },
{ employeeId: 10, sales: 30 }]; 
  
   angular.module('syncApp',['ejangular']).controller("sparkline",function($scope){    
    $scope.sparklinedata = sparklinedata;
});
</script>
</body>
</html>

{% endhighlight %}


![](Working-with-Data_images/Working-with-Data_img1.png); 

2.You can also bind an array of data to Sparkline by using `e-dataSource` property.

{% highlight javascript %}

<html ng-app="syncApp">
     <head>
         <script type="text/javascript" src="http://cdn.syncfusion.com/js/assets/external/jquery-2.1.4.min.js"></script>
         <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
         <script src="https://cdn.syncfusion.com/14.2.0.26/js/web/ej.web.all.min.js"></script>
         <script src="https://cdn.syncfusion.com/14.2.0.26/js/common/ej.widget.angular.min.js"></script>
     </head>
<body ng-controller="sparkline">
<div id="column" ej-sparkline e-datasource="sparklinedata"></div>
<script>
    var data = [2, 6, -1, 1, 12, 5, -2, 7, -3, 5, 8, 10, ];	 
  
   angular.module('syncApp',['ejangular']).controller("sparkline",function($scope){    
    $scope.sparklinedata = data;
});
</script>
</body>
</html>

{% endhighlight %}


![](Working-with-Data_images/Working-with-Data_img2.png); 




