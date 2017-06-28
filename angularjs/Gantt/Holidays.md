---
layout: post
title: Holidays
description: holidays
platform: AngularJS
control: Gantt
documentation: ug
---

# Holidays

Holidays in Gantt control is used to highlight the non-working days in Gantt control and it can be initialized with Gantt control by using the following code example.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
   //...
    e-holidays="holidays" 
    >
   </div>
   <script>
   var holidays= [{
            day: "2/11/2014",
            label: " Public holiday",
            background: "yellowgreen "
        }]
    angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.holidays="holidays";
          });  
</script>
</body>
   
{% endhighlight %}

The following screenshot shows the output of Holidays in Gantt control.

![](Holidays_images/Holidays_img1.png)

