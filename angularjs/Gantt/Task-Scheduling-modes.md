---
layout: post
title: Task-scheduling-modes
description: Task scheduling modes
platform: AngularJS
control: Gantt
documentation: ug
---

# Task scheduling modes

The Gantt provides support for automatic and manual task scheduling modes. By using the **e-taskschedulingmode** property, you can change the scheduling mode of the task. The following are the enumeration values that can be set to the **e-taskschedulingmode** property.

* auto
* manual
* custom

## **Automatically** **Scheduled** **tasks**

In this scheduling mode, all tasks in the project will be rendered as automatically scheduled tasks. The tasks will be automatically scheduled based on the factors such as dependencies between the tasks, and non-working days like holidays and weekends. Tasks automatically recalculate the scheduling date when its predecessor task has been affected. But still you can schedule these tasks manually. Summary tasks will also be automatically scheduled, but its start date, end date, and duration values cannot be edited manually. 

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-taskschedulingmode = ej.Gantt.TaskSchedulingMode.Auto
      >
   </div>
</body>

{% endhighlight %}

N> Automatic scheduling mode is the default task scheduling mode in the Gantt.

## **Manually** **Scheduled** **tasks**

In this mode, all the tasks in the project will be rendered as manually scheduled tasks. The tasks will not get rescheduled and dates will not be recalculated automatically based on the factors such as task dependencies and non-working days. Manually scheduled tasks will lie on weekends and holidays, but you can restrict this mode in the predecessor calculation by using the **e-validatemanualtasksonlinking** property. By enabling this property, the dates of manual tasks will recalculate automatically, while its predecessor tasks have been affected.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-taskschedulingmode = ej.Gantt.TaskSchedulingMode.Manual
      e-validatemanualtasksonlinking = "false">
   </div>
</body>

{% endhighlight %}

## **Custom**

Tasks can be either automatically scheduled or manually scheduled, and you can map the scheduling mode from the data source field by using the mapping property **e-taskschedulingmodemapping**.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-taskschedulingmodemapping = "isManual">
   </div>
</body>

{% endhighlight %}

The following screenshot depicts the project with both automatically and manually scheduled tasks:

![](Task-Scheduling-modes_images/Task-Scheduling-modes_img1.png)