---
layout: post
title: Editing
description: editing
platform: AngularJS
control: Gantt
documentation: ug
---

# Editing

The Gantt control provides built-in support to add, insert, and update the tasks. The following are the types of editing available in the Gantt:

* Cell editing
* Normal editing
* Taskbar editing
* Predecessor editing

## Cell editing

Update the task details through the grid cell editing by setting the editMode to `cellEditing`.

The following code example shows how to enable the `cellEditing` in the Gantt control:

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
   //...
    e-editsettings="editSettings" 
    >
   </div>
   <script>
   var editSettings= {
            allowEditing: true,
            editMode: "cellEditing"
        }
    angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.editSettings="editSettings";
          });  
</script>
</body>

{% endhighlight %}

The output of the Gantt with cellEditing is as follows:

![](Editing_images/Editing_img1.png)

## Normal editing

Update the task details through the edit dialog by setting the `editMode` to `normal`.

The following code example shows how to enable normal editing in the Gantt control:

{% highlight javascript %}


<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-editsettings="editSettings" 
      >
   </div>
  <script>
    var editSettings = {
        allowEditing: true,
        editMode: "normal"
    }
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.editSettings = "editSettings";
        });
</script>
</body>

{% endhighlight %}

The following screenshot shows the output of `normal` editing:

![](Editing_images/Editing_img2.png)

## Taskbar editing

Update the task details by interactions such as resizing and dragging the taskbar. The following code example shows how to enable taskbar resizing in the Gantt control:

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-allowganttchartediting="true"
      >
   </div>
</body>

{% endhighlight %}

You can also enable or disable the progressbar resizing by setting 'e-enableprogressbarresizing'. Refer to the following code example, to disable this property:

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-enableprogressbarresizing="false"
      >
   </div>
</body>

{% endhighlight %}

## Predecessor editing

Update the predecessor details of the task using mouse interactions. The following code example shows how to enable predecessor editing:

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-allowganttchartediting="true"
      e-predecessormapping= "predecessor"
      >
   </div>
</body>
{% endhighlight %}

The following screenshot shows the predecessor editing in the Gantt control:

![](Editing_images/Editing_img3.png)

