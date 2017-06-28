---
layout: post
title: Working-time-range
description: working time range
platform: AngularJS
control: Gantt
documentation: ug
---

# Working Time Range

In Gantt control, working hours in a day for a project can be defined by using **e-dayworkingtime** property. Based on the working hours, automatic date scheduling and duration validations for a task are performed.

The below code snippet explains on how to define the working time range for the project in Gantt,

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-dayworkingtime="dayWorkingTime" 
      >
   </div>
  <script>
    var dayWorkingTime= [
        {"from": "08:00 AM", "to": "12:00 PM"},
        {"from": "01:00 PM", "to": "05:00 PM"}],
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.dayWorkingTime = "dayWorkingTime";
        });
</script>
</body>

{% endhighlight %}

N> 1. Individual tasks can lie between any time within the defined working time range of the project.

N> 1. **e-dayworkingtime** property is used to define the working time for the whole project.

The below demo explains the working time range in Gantt

[Working Time Range](http://js.syncfusion.com/demos/web/#!/bootstrap/gantt/schedulingconcepts/workingtimerange)

The following screen shot shows working time range in Gantt control. 

![](Working-time-range_images/Working-time-range_img1.png)


