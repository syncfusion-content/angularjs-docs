---
layout: post
title: Critical-feature
description: Critical-feature
platform: AngularJS
control: Gantt
documentation: ug
---
# Critical path

The critical path in a project is indicated by a single task or a series of tasks in the project. It describes the calculated start date or end date of the project. If a task in a critical path is delayed, then the entire project will be delayed.

The critical path can be enabled in the Gantt by using the built-in toolbar button or **showCriticalPath** method.

## Using toolbar icon

You can enable or disable the critical path in the Gantt by using the toolbar button which is enabled in the Gantt toolbar by using the following code example:

{% highlight html %}
 

<!doctype html>
<html lang="en" ng-app="listCtrl">
   <head>
      //...
   </head>
   <body ng-controller="GanttCtrl">
      <!--Add  Gantt control here-->    
      <div id="GanttContainer" ej-gantt
         //...
         e-toolbarsettings= "toolbarSettings"
         >
      </div>
      <script>
         var toolbarSettings = {
         showToolbar: true,
         toolbarItems: [
             //..
             ej.Gantt.ToolbarItems.CriticalPath,
         ],
     },
     angular.module('listCtrl', ['ejangular'])
     .controller('GanttCtrl', function($scope) {
         //...              
         $scope.load = load;
         $scope.toolbarSettings = toolbarSettings;
     });                    
      </script>
   </body>
</html>

{% endhighlight %}

![](criticalfeature_images/criticalfeature_img1.jpeg)


## Using method

You can enable the critical path by using the **showCriticalPath****()** method with parameter as **true**. The critical path can be disabled by using the same method with parameter as **false**.

{% highlight html %}
 
<script>                   
$("#buttonon").click(function(args) {
    ganttObj = $("#GanttContainer").data("ejGantt");
    ganttObj.showCriticalPath(true);
})
$("#buttonoff").click(function(args) {
    ganttObj = $("#GanttContainer").data("ejGantt");
    ganttObj.showCriticalPath(false);
})             
</script>

{% endhighlight %}

![](criticalfeature_images/criticalfeature_img2.jpeg)


## Customizing critical path background

You can customize the critical task background by setting custom color codes to the critical task elements’ class names as follows:

Taskbar–.e-ganttchart .e-criticaltaskbar 

Progressbar–.e-ganttchart .e-criticalprogressbar     

Connector line–.e-ganttchart .e-criticalconnectorline       

Connector line left arrow– .e-ganttchart .e-criticalconnectorlineleftarrow  

Connector line right arrow–  .e-ganttchart .e-criticalconnectorlinerightarrow 

{% highlight html %}

<style>
    .e-ganttchart .e-criticaltaskbar {
        background-color: #ffb366!important;
        border-color: gray!important
    }
    
    .e-ganttchart .e-criticalprogressbar {
        background-color: #ff99cc!important;
        border-color: #b35900!important
    }
    
    .e-ganttchart .e-criticalconnectorline {
        background-color: #b800e6!important;
    }
    
    .e-ganttchart .e-criticalconnectorlineleftarrow {
        border-right-color: #b800e6!important;
    }
    
    .e-ganttchart .e-criticalconnectorlinerightarrow {
        border-left-color: #b800e6!important;
    }
</style>

{% endhighlight %}

![](criticalfeature_images/criticalfeature_img3.jpeg)


