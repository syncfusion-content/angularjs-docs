---
layout: post
title: Baseline
description: baseline
platform: AngularJS
control: Gantt
documentation: ug
---

# Baseline

Baseline is used to describe the original plan of the task and it can be the same as current duration of the task or different. The following code example shows you how to enable baseline in Gantt control.

{% highlight javascript %}

<!doctype html>
<html lang="en" ng-app="listCtrl">
   <head>
      //...
   </head>
   <body ng-controller="GanttCtrl">
      <!--Add  Gantt control here-->    
      <div id="GanttContainer" ej-gantt
      //...
         e-baselinestartdatemapping= "baselineStartDate"
         e-baselineenddatemapping= "baselineEndDate"
         e-renderbaseline= "true"
         >
      </div>
   </body>
</html>

{% endhighlight %}

The following screenshot shows the baseline in Gantt control.

![](Baseline_images/Baseline_img1.png)

