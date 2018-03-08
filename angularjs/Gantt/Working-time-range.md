---
layout: post
title: Working-time-range
description: working time range
platform: AngularJS
control: Gantt
documentation: ug
---

# Working time range

In Gantt control, working hours in a day for the project can be defined by using the **e-dayworkingtime** property. Based on the working hours, automatic date scheduling and duration validations for the task can be performed.

The following code snippet explains how to define the working time range for project in the Gantt control:

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

N> Individual tasks can lie between any time within the defined working time range of the project.

N> The **e-dayworkingtime** property is used to define the working time for the whole project.

The following demo explains the working time range in the Gantt control:

[Working Time Range](http://js.syncfusion.com/demos/web/#!/bootstrap/gantt/schedulingconcepts/workingtimerange)

The following screenshot shows working time range in the Gantt control:

![](Working-time-range_images/Working-time-range_img1.png)


