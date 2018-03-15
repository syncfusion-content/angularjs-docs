---
layout: post
title: Task-Relationship
description: task relationship
platform: AngularJS
control: Gantt
documentation: ug
---

# Task relationship

You can show the relationship between two tasks in the Gantt control. These relationships are categorized into four types based on the start and finish date of the task.

## Start to start(SS)

You cannot start a task until the other task also starts.

![](Task-Relationship_images/Task-Relationship_img1.png)

## Start to finish(SF)

You cannot finish a task until the other task is started.

![](Task-Relationship_images/Task-Relationship_img2.png)

## Finish to start(FS)

You cannot start a task until the other task is completed.

![](Task-Relationship_images/Task-Relationship_img3.png)

## Finish to finish(FF)

You cannot finish a task until the other task is completed.

![](Task-Relationship_images/Task-Relationship_img4.png)

The following code example shows how to show the predecessor in the Gantt control:

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-predecessormapping="predecessor" 
      >
   </div>
</body>
    
{% endhighlight %}

The following screenshot displays the output of the above code:

![](Task-Relationship_images/Task-Relationship_img5.png)

