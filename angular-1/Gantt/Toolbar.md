---
layout: post
title: Toolbar
description: toolbar
platform: Angular-1
control: Gantt
documentation: ug
---

# Toolbar

Gantt control contains toolbar options for editing, searching, expanding and collapsing all records, indent, out dent, delete and add task. You can enable toolbar using the following code example.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-toolbarsettings="toolbarSettings" 
      >
   </div>
  <script>
    var toolbarSettings= {
               showToolbar: true,
            toolbarItems: [
                ej.Gantt.ToolbarItems.Add, //TO ADD THE NEW TASK 
                ej.Gantt.ToolbarItems.Edit, //TO MODIFY THE SELECTED TASK DETAILS
                ej.Gantt.ToolbarItems.Delete, //TO DELETE THE SELECTED TASK
                ej.Gantt.ToolbarItems.Update, //TO SAVE THE MODIFIED TASK DETAILS
                ej.Gantt.ToolbarItems.Cancel, //TO CANCEL THE MODIFIED TASK DETAILS
                ej.Gantt.ToolbarItems.Indent, //TO INDENT THE SELECTED TASK 
                ej.Gantt.ToolbarItems.Outdent, //TO OUTDENT THE SELECTED TASK
                ej.Gantt.ToolbarItems.ExpandAll, //TO EXPAND ALL THE TASKS IN GANTT
                ej.Gantt.ToolbarItems.CollapseAll, //TO COLLAPSE ALL THE TASK IN GANTT
                ej.Gantt.ToolbarItems.Search, //TO FIND THE TASK
                ej.Gantt.ToolbarItems.PrevTimeSpan, //TO SHIFT THE PROJECT TO PREVIOUS TIME SCALE
                ej.Gantt.ToolbarItems.NextTimeSpan //TO SHIFT THE PROJECT TO NEXT TIME SCALE
            ],
            }
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.toolbarSettings = "toolbarSettings";
        });
</script>
</body>

{% endhighlight %}

The following screenshot shows the toolbar option in Gantt control.

![](Toolbar_images/Toolbar_img1.png)

