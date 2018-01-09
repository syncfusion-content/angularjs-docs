---
layout: post
title: Duration Round-Off
description: Rounding off duration
platform: AngularJS
control: Gantt
documentation: ug
---

## Round-off start date, end date and duration value on taskbar editing
In Gantt start date, end date and duration values can be round-off as per current `scheduleHeaderSettings.scheduleHeaderType` value on taskbar resizing and dragging actions. This can be achieved by setting `roundOffDuration` argument value as `true` in `taskbarEditing` event.

The below code example explains how to achieve this requirement. 

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-taskbarEditing="taskbarEditing"
      >
   </div>
   <script>
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
			$scope.taskbarEditing = function (args) {
			args.roundOffDuration= true;
			}
        });
    </script>
</body>

{% endhighlight %}

![](Duration-Round-Off_images/OnResizing_img1.png)

Before resizing

{:.caption}

![](Duration-Round-Off_images/AfterResizing_img2.png)

After resizing

{:.caption} 