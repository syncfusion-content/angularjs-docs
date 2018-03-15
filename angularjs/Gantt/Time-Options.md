---
layout: post
title: Time-Options
description: time options
platform: AngularJS
control: Gantt
documentation: ug
---

# Time options

Start date and end date in the data source defines the starting point and ending point of a task in the project. The two data types are:

* Date
* Datetime

The datetime data type for start date and end date defines the exact starting point and ending point of a task along with time details of a day. There are two types of time scales available based on working hours:

* `TimeScale8Hours`  for 8 hour working scale
* `TimeScale24Hours` for 24 hour working scale

Use the following code example for setting different time scales of working hours:

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-workingtimescale=ej.Gantt.workingTimeScale.TimeScale24Hours
      >
   </div>
</body>

{% endhighlight %}

Use the following code example to include time options in start date and end date of a task:

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-datasource= "taskDetails"
                e-taskidmapping= "taskID"
                e-tasknamemapping= "taskName"
                e-startdatemapping= "startDate"
                e-progressmapping= "progress"
                e-durationmapping= "duration"
                e-enddatemapping= "endDate"
                e-childmapping= "subtasks"
                e-treecolumnindex= 1
                e-dateformat= "M/d/yyyy hh:mm:ss tt"
                e-schedulestartdate= new Date("02/01/2014 00:00:00 AM")
                e-scheduleenddate= new Date("03/14/2016 00:00:00 PM")
                e-workingtimescale= ej.Gantt.workingTimeScale.TimeScale24Hours
      >
   </div>
  <script>
     var taskDetails = [{
            taskID: 1,
            taskName: "Planning",
            startDate: "02/03/2014 08:00:00 AM",
            endDate: "02/07/2014 05:00:00 PM",
            subtasks: [
             { 
                 taskID: 2,
                 taskName: "Plan timeline", 
                 startDate: "02/03/2014 08:00:00 AM", 
                 endDate: "02/07/2014 05:00:00 PM",
                 duration: 5, 
                 progress: "100" 
             },
             {
                taskID: 3, 
                taskName: "Plan budget", 
                startDate: "02/03/2014 08:00:00 AM", 
                endDate: "02/07/2014 05:00:00 PM", 
                duration: 5, 
                progress: "100"
             },
             { 
                taskID: 4, 
                taskName: "Allocate resources",
                startDate: "02/03/2014 08:00:00 AM",
                endDate: "02/07/2014 05:00:00 PM", 
                duration: 5, 
                progress: "100"
              },
              { 
                taskID: 5, 
                taskName: "Planning complete", 
                startDate: "02/07/2014 08:00:00 AM", 
                endDate: "02/07/2014 05:00:00 PM", 
                duration: 0,
               }
        ]}];
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.taskDetails = "taskDetails";
        });
</script>
</body>

{% endhighlight %}

Execute the above code to render the following output:

![](Time-Options_images/Time-Options_img1.png)

