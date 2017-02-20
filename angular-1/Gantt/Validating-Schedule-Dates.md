---
layout: post
title: Validating-Schedule-Dates
description: validating schedule dates
platform: Angular-1
control: Gantt
documentation: ug
---

# Validating Schedule Dates

Validating schedule dates is used to change the schedule start date and end date dynamically. By this support, `e-schedulestartdate` and `e-scheduleenddate` can be automatically updated from the data source. When you change the date of any task item to the date that is beyond `e-schedulestartdate` or `e-scheduleenddate` through cell editing, taskbar editing, dialog editing or toolbar operation, then the `e-schedulestartdate` and `e-scheduleenddate` can be dynamically updated based on that task item’s date.

`PrevTimeSpan` and `NextTimeSpan` toolbar items are used to create new time span based on the schedule mode.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-schedulestartdate= "02/01/2014"
      e-scheduleenddate= "03/14/2016"
      e-toolbarsettings="toolbarSettings" 
      >
   </div>
  <script>
    var toolbarSettings= {
                showToolbar: true,
                    toolbarItems: [
                    ej.Gantt.ToolbarItems.PrevTimeSpan,
                    ej.Gantt.ToolbarItems.NextTimeSpan, ]
            }
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.toolbarSettings = "toolbarSettings";
        });
</script>
</body>

{% endhighlight %}

The following screenshot illustrates the output of the above code.

![](Validating-Schedule-Dates_images/Validating-Schedule-Dates_img1.png)

