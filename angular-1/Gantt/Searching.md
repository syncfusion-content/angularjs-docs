---
layout: post
title: Searching
description: searching
platform: Angular-1
control: Gantt
documentation: ug
---
# Searching

The Gantt control for JavaScript has built-in support for searching any content in Gantt.

### Searching for Content Columns

In Gantt we can search the content using the JavaScript method searchItem with search key as parameter. Also, we can integrate the search text box in Gantt toolbar, by adding search toolbar item in toolbarSetting.toolbarItems property.

The following code example shows you how to add search option in Gantt toolbar.

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
                ej.Gantt.ToolbarItems.Search, //TO FIND THE TASK
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

The following screenshot shows the output of searching for string in Gantt control.

![](Searching_images/Searching_img1.png)

