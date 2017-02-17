---
layout: post
title: Change-Splitter-position
description: change splitter position
platform: Angular-1
control: Gantt
documentation: ug
---

# Change Splitter position

In Gantt control, Splitter separates the TreeGrid section from the Chart section,and is possible to change the position of the Splitter while loading the Gantt by using the `e-splitterposition` property, thereby varying the width of the TreeGrid and Chart sections in the control.  `e-splitterposition` property denotes the percentage of the TreeGrid section’s width to be rendered and this property supports both pixels and percentage values.

The following code example explains how to define the `e-splitterposition` property in the Gantt.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-splitterposition= "50%" // (or) e-splitterposition=”650”  (or)  e-splitterposition=“650px” 
      >
   </div>
</body>

{% endhighlight %}

![](/augular-1/Gantt/How-to/Change-Splitter-position_images/Change-Splitter-position_img2.png)

Gantt with 30 % splitter position
{:.caption}

![](/augular-1/Gantt/How-to/Change-Splitter-position_images/Change-Splitter-position_img3.png)

Gantt with 50% splitter position
{:.caption}

![](/augular-1/Gantt/How-to/Change-Splitter-position_images/Change-Splitter-position_img4.png)

Gantt with 600px splitter position
{:.caption}

