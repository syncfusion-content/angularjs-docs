---
layout: post
title: Data-Binding
description: data binding
platform: AngularJS
control: Gantt
documentation: ug
---
# Data Binding

Data binding is the process that establishes a connection between the application and different kinds of data sources such as business objects. And it is possible to bind local data and remote data in Gantt.

## Local Data Binding

In Local Data Binding, datasource for rendering the Gantt control is retrieved from the same application locally.

Two types of Data Binding are possible with Gantt control, 

* Hierarchical datasource binding
* Self-referential data binding (Flat data)

### Hierarchical data-source binding


The following code example explains how to bind the hierarchical data in Gantt.

{% highlight javascript %}
<script>
var  taskDetails = [{
    taskID: 1,
    taskName: "Design",
    startDate: new Date("02/10/2014"),
    endDate: new Date("02/14/2014"),
    baselineStartDate: new Date("02/10/2014"),
    baselineEndDate: new Date("02/12/2014"),
    duration: 5,
    subtasks: [
        {
            taskID: 2,
            taskName: "Software Specification",
            startDate: new Date("02/10/2014"),
            endDate: new Date("02/12/2014"),
            baselineStartDate: new Date("02/10/2014"),
            baselineEndDate: new Date("02/12/2014"),
            duration: 4,
            progress: "60",
            resourceId: [2]
        },
        {
            taskID: 3,
            taskName: "Develop prototype",
            startDate: new Date("02/10/2014"),
            endDate: new Date("02/12/2014"),
            baselineStartDate: new Date("02/10/2014"),
            baselineEndDate: new Date("02/12/2014"),
            duration: 4,
            progress: "70",
            resourceId: [3]
        },
        //...
    ]
}];
  angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.taskDetails="taskDetails";
          });  
<script>

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
     e-datasource= "taskDetails"
           e-taskidmapping= "taskID"
            e-tasknamemapping= "taskName"
            e-schedulestartdate= "02/01/2014"
            e-scheduleenddate= "03/14/2014"
            e-startdatemapping= "startDate"
            e-durationmapping= "duration"
            e-progressmapping= "progress"
            e-childmapping= "subtasks"
            e-treecolumnindex= 1
      >
   </div>

{% endhighlight %}

The output of the above steps is as follows.

![](Data-Binding_images/Data-Binding_img1.png)

It is also possible to set the datasource to Gantt using ejDataManager. The following code example explains how to assign the ejDataManager instance to Gantt.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      e-datasource= "taskDetails"
      //...
      >
   </div>
<script>
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.taskDetails = ej.DataManager(dataManger);
        });
</script>

{% endhighlight %}

### Self-referential data binding (Flat data)

Gantt can be rendered from self-referential data structures, by mapping the task ID and parent task ID fields.

* Task ID field- This field must contain unique values to identify the nodes. It should be mapped to the `e-taskidmapping` property.
* Parent task ID field- This field must contain values to identify the parent nodes. It should be mapped to the `e-parenttaskidmapping` property.

{% highlight javascript %}

<script>
var projectData = [
    { taskID: 1, taskName: "Task 1", startDate: "02/03/2014", endDate: "03/07/2014", duration: 5},    
    { taskID: 2, pId: 1, taskName: "Child Task 1", startDate: "02/03/2014", endDate: "02/07/2014", duration: 5},
    { taskID: 3, pId: 1, taskName: "Child Task 2", startDate: "02/03/2014", endDate: "02/07/2014", duration: 5, progress: "100" },
    { taskID: 22, pId: 2, taskName: "Sub Child Task 1", startDate: "02/03/2014", endDate: "02/07/2014", duration: 5 },
    { taskID: 23, pId: 2, taskName: "Sub Child Task 2", startDate: "02/03/2014", endDate: "02/07/2014", duration: 5, progress: "100" },
    { taskID: 12, pId: 22, taskName: "Inner Child Task 1", startDate: "02/03/2014", endDate: "02/07/2014", duration: 5},
    { taskID: 13, pId: 22, taskName: "Inner Child Task 2", startDate: "02/03/2014", endDate: "02/07/2014", duration: 5, progress: "100"},
    { taskID: 4, taskName: "Task 2", startDate: "02/03/2014", endDate: "02/07/2014", duration: 5, progress: "100"},
    { taskID: 5, pId: 4, taskName: "Child Task 1", startDate: "02/03/2014", endDate: "02/07/2014", duration: 5, progress: "100" },
    { taskID: 6, pId: 4, taskName: "Child Task 2", startDate: "02/07/2014", endDate: "02/07/2014", duration: 5},
    { taskID: 7, pId: 6, taskName: "Sub Child Task 1", startDate: "02/07/2014", endDate: "02/07/2014", duration: 5},
    { taskID: 8, pId: 7, taskName: "Inner Child Task 1", startDate: "02/10/2014", endDate: "02/12/2014", duration: 3, progress: "60"},
    { taskID: 9, pId: 7, taskName: "Inner Child Task 2", startDate: "02/10/2014", endDate: "02/12/2014", duration: 3, progress: "100" },
    { taskID: 10, taskName: "Task 3", startDate: "02/13/2014", endDate: "02/14/2014", duration: 2, progress: "100"},
    { taskID: 11, taskName: "Task 4", startDate: "02/14/2014", endDate: "02/14/2014", duration: 0, }];
 angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.taskDetails="projectData";
          });  
</script>

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
     e-datasource= "taskDetails"
           e-taskidmapping= "taskID"
           e-parenttaskidmapping= "pId",
           e-enablevirtualization= "true",
            e-highlightweekends="true",
            e-includeweekend= false,
            e-tasknamemapping= "taskName"
            e-schedulestartdate= "02/01/2014"
            e-scheduleenddate= "03/14/2014"
            e-startdatemapping= "startDate"
            e-enddatemapping= "endDate",
            e-durationmapping= "duration"
            e-progressmapping= "progress"
            e-childmapping= "subtasks"
            e-treecolumnindex= 1
      >
   </div>

{% endhighlight %}

The following screenshot shows the output of the above steps.

![](Data-Binding_images/Data-Binding_img2.png)

## Remote data

It is possible to load remote data in Gantt by using ej.DataManager. You can assign the web service data as an ej.DataManager instance to the datasource property. The following example explains how to load the remote data in Gantt.

{% highlight javascript %}

<script>
    var dataManger = ej.DataManager({
        url: "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders",
        offline: true
    });
     angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.dataManger="dataManger";
          });  
</script>
<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
   //...
   e-datasource= "dataManger"
 >
   </div>
</body>
{% endhighlight %}

