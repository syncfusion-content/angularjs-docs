---
layout: post
title: Editing
description: editing
platform: Angular-1
control: Gantt
documentation: ug
---

# Editing

The Gantt control provides built-in support to add, insert and update the tasks. The following are the types of editing available in Gantt,

* Cell Editing
* Normal Editing
* Taskbar Editing
* Predecessor Editing

## Cell Editing

Update the task details through grid cell editing by setting editMode as `cellEditing`.

The following code example shows you how to enable `cellEditing` in Gantt control.

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

The output of Gantt with cellEditing is as follows.

![](Editing_images/Editing_img1.png)

## Normal Editing

Update the task details through edit dialog by setting `editMode` as `normal`.

The following code example shows you how to enable normal editing in Gantt control.

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

The following screenshot shows the output of `normal` editing.

![](Editing_images/Editing_img2.png)

## Taskbar Editing

Update the task details by interactions such as resizing and dragging the taskbar. The following code example shows you how to enable taskbar resizing in Gantt control.

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

You can also enable or disable the progressbar resizing by setting 'e-enableprogressbarresizing'. The following code example shows you to disable this property.

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

## Predecessor Editing

Update the predecessor details of a task using mouse interactions. The following code example shows how to enable predecessor editing.

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

The following screen shot shows the predecessor editing in Gantt control.

![](Editing_images/Editing_img3.png)

