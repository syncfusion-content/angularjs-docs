---
layout: post
title: Getting-Started
description: getting started
platform: AngularJS
control: Gantt
documentation: ug
---

# Getting Started

This section explains briefly about how to create a Gantt chart in your application with AngularJS.

## Create your first Gantt in AngularJS

In this tutorial, you can learn how to create a simple Gantt chart, add tasks or subtasks, and set relationship between tasks during the design phase of a software project. The following screenshot displays the desired output after completing this tutorial,

![](/angular-1/Gantt/Getting-Started_images/Getting-Started_img4.png)

## Adding script references
Create an HTML file and add the following template to the HTML file.

{% highlight html %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
   <head>
      <title>Getting Started with Gantt Control for AngularJS</title>
      <!-- style sheet for default theme(flat azure) -->
      <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
      <!--scripts-->    
      <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"></script>
      <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js "></script>
      <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
   </head>
   <body>
      <!--Add  Gantt control here-->
   </body>
</html>

{% endhighlight %}

## Binding Gantt with data
Create data source for ejGantt.

{% highlight javascript %}

    var data = [{
    taskID: 1,
    taskName: "Design",
    startDate: "02/10/2014",
    endDate: "02/14/2014",
    duration: 6,
    subtasks: [{
        taskID: 2,
        taskName: "Software Specification",
        startDate: "02/10/2014",
        endDate: "02/12/2014",
        duration: 4,
        progress: "60",
        resourceId: [2]
    }, {
        taskID: 3,
        taskName: "Develop prototype",
        startDate: "02/10/2014",
        endDate: "02/12/2014",
        duration: 4,
        progress: "70",
        resourceId: [3]
    }, {
        taskID: 4,
        taskName: "Get approval from customer",
        startDate: "02/12/2014",
        endDate: "02/14/2014",
        duration: 2,
        progress: "80",
        predecessor: "3FS",
        resourceId: [1]
    }, {
        taskID: 5,
        taskName: "Design complete",
        startDate: "02/14/2014",
        endDate: "02/14/2014",
        duration: 0,
        predecessor: "4FS"
    }]
}];

{% endhighlight %}

## Initialize Gantt
Add a **&lt;div&gt;** element with in the &lt;Body&gt; tag.

{% highlight html %}

<!doctype html>
<html lang="en" ng-app="listCtrl">
   <head>
      //...
   </head>
   <body ng-controller="GanttCtrl">
      <!--Add  Gantt control here-->    
      <div id="GanttContainer" ej-gantt
         e-datasource="projectData"
         e-taskidmapping="taskID"
         e-tasknamemapping="taskName"
         e-childmapping="subtasks"
         e-startdatemapping="startDate"
         e-enddatemapping="endDate"
         e-progressmapping="progress">
      </div>
      <script>
         angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //Initialize gantt datasource created in the last step
               $scope.projectData = data;
           });
      </script>   
   </body>
</html>


{% endhighlight %}

In the above code snippet, `ej-gantt` denotes the control directive for the Syncfusion's Gantt angular widget and all its properties are prefixed with the letter `e-` (For example, e-datasource).

A Gantt chart is created as shown in the following screen shot.

![](/angular-1/Gantt/Getting-Started_images/Getting-Started_img5.png)

## Enable Toolbar

Gantt control contains toolbar options to edit, search, expand or collapse all records, indent, outdent, delete, and add a task. You can enable toolbar using the [`e-toolbarSettings`](http://help.syncfusion.com/js/api/ejgantt#members:toolbarsettings "toolbarSettings") property.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      e-toolbarsettings="toolbarsettings">
   </div>
   <script>
      var toolbarsettings={
      showToolbar: true,
      toolbarItems: [
       ej.Gantt.ToolbarItems.Add,
       ej.Gantt.ToolbarItems.Edit,
       ej.Gantt.ToolbarItems.Delete,
       ej.Gantt.ToolbarItems.Update,
       ej.Gantt.ToolbarItems.Cancel,
       ej.Gantt.ToolbarItems.Indent,
       ej.Gantt.ToolbarItems.Outdent,
       ej.Gantt.ToolbarItems.ExpandAll,
       ej.Gantt.ToolbarItems.CollapseAll,
       ej.Gantt.ToolbarItems.Search
      ],
      };
      angular.module('listCtrl', ['ejangular'])
      .controller('GanttCtrl', function ($scope) {
       //Initialize gantt datasource created in the last step
       $scope.toolbarsettings = toolbarsettings;
      });
   </script>   
</body>

{% endhighlight %}

The following screen shot displays a Tool bar in Gantt chart control:

![](/angular-1/Gantt/Getting-Started_images/Getting-Started_img6.png)

N>  Add, edit, delete, Indent, Outent options are enabled when enabling the allowEditing, allowAdding, allowDelete, allowIndent and allowOutdent properties in the e-editSettings.

## Enable Sorting

The Gantt control has sorting functionality to arrange the tasks in ascending or descending order based on a particular column.

### Multicolumn Sorting

Enable the multicolumn sorting in Gantt by setting [`e-allowMultiSorting`](http://help.syncfusion.com/js/api/ejgantt#members:allowmultisorting "allowMultiSorting") as `true`. You can sort multiple columns in Gantt, by selecting the desired column header while holding the `CTRL` key.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      e-allowsorting="true"
      e-allowmultisorting="true">             
   </div>
   <script>
      angular.module('listCtrl', ['ejangular'])
      .controller('GanttCtrl', function ($scope) {
         //...
      });
   </script>
</body>
   
{% endhighlight %}

## Enable Editing

You can enable editing using [`e-editSettings`](http://help.syncfusion.com/js/api/ejgantt#members:editsettings "editSettings") and [`e-allowGanttChartEditing`](http://help.syncfusion.com/js/api/ejgantt#members:allowganttchartediting "allowGanttChartEditing") options.

### Cell Editing

Modify the task details through the grid cell editing by setting the [`editMode`](http://help.syncfusion.com/js/api/ejgantt#members:editsettings-editmode "editSettings.editMode") as [`cellEditing`](http://help.syncfusion.com/js/api/ejgantt#members:editsettings-editmode "cellEditing").

### Normal Editing

Modify the task details through the edit dialog by setting the [`editMode`](http://help.syncfusion.com/js/api/ejgantt#members:editsettings-editmode "editSettings.editMode") as [`normal`](http://help.syncfusion.com/js/api/ejgantt#members:editsettings-editmode "normal").

### Taskbar Editing

Modify the task details through user interaction such as resizing and dragging the taskbar.

### Predecessor Editing

Modify the predecessor details of a task using mouse interactions by setting [`e-allowGanttChartEditing`](http://help.syncfusion.com/js/api/ejgantt#members:allowganttchartediting "allowGanttChartEditing") as `true` and setting the value for `e-predecessorMapping` property.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      e-allowGanttChartEditing="true"
      e-editSettings="editsettings"
      e-predecessorMapping="predecessor">             
   </div>
   <script>
      var editsettings={
          allowEditing: true,
          allowAdding: true,
          allowDeleting: true,
          editMode:"normal",
      };
      angular.module('listCtrl', ['ejangular'])
      .controller('GanttCtrl', function ($scope) {
         $scope.editsettings=editsettings;
      });
   </script>
</body>  

{% endhighlight %}

The following screen shot displays a Gantt chart control with Enable Editing options.

![](/angular-1/Gantt/Getting-Started_images/Getting-Started_img7.png)

N>  Both cellEditing and  normal  editing operations are performed through double-click action.

## Enable Context Menu

You can enable the context menu in Gantt, by setting the [`enableContextMenu`](http://help.syncfusion.com/js/api/ejgantt#members:enablecontextmenu "enableContextMenu") as `true`.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      e-enableContextMenu="true">             
   </div>
   <script>
      angular.module('listCtrl', ['ejangular'])
      .controller('GanttCtrl', function ($scope) {
         //...
      });
   </script>
</body>  
   
{% endhighlight %}

The following screen shot displays Gantt chart in which Context menu option is enabled:

![](/angular-1/Gantt/Getting-Started_images/Getting-Started_img8.png)

## Enable Column Menu

You can enable the column menu in Gantt, by setting the [`e-showColumnChooser`](http://help.syncfusion.com/js/api/ejgantt#members:showcolumnchooser "showColumnChooser") as `true`.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      e-showColumnChooser="true">             
   </div>
   <script>
      angular.module('listCtrl', ['ejangular'])
      .controller('GanttCtrl', function ($scope) {
         //...
      });
   </script>
</body>


{% endhighlight %}

The following screen shot displays Gantt chart in which column chooser option is enabled:

![](/angular-1/Gantt/Getting-Started_images/Getting-Started_img11.png)

## Provide tasks relationship

In Gantt, you have the predecessor support to show the relationship between two different tasks.

* **Start to Start (SS)** - You cannot start a task until the other task also starts.
* **Start to Finish (SF)** - You cannot finish a task until the other task finishes.
* **Finish to Start (FS)** - You cannot start a task until the other task completes.
* **Finish to Finish (FF)** - You cannot finish a task until the other task completes.

You can show the relationship in tasks, by using the [`predecessorsMapping`](http://help.syncfusion.com/js/api/ejgantt#members:predecessormapping "predecessorsMapping")

, as shown in the following code example.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      e-predecessorMapping="predecessor">             
   </div>
   <script>
      angular.module('listCtrl', ['ejangular'])
      .controller('GanttCtrl', function ($scope) {
         //...
      });
   </script>
</body>  
    
{% endhighlight %}

The following screenshot displays the relationship between tasks.

![](/angular-1/Gantt/Getting-Started_images/Getting-Started_img9.png)

## Provide Resources

In Gantt control, you can display and assign the resource for each task. Create a collection of `JSON` object, which contains id and name of the resource and assign it to [`e-resources`](http://help.syncfusion.com/js/api/ejgantt#members:resources "resources") property. Then, specify the field name for id and name of the resource in the resource collection to [`e-resourceIdMapping`](http://help.syncfusion.com/js/api/ejgantt#members:resourceidmapping "resourceIdMapping") and [`e-resourceNameMapping`](http://help.syncfusion.com/js/api/ejgantt#members:resourcenamemapping "resourceNameMapping") options. The name of the field, which contains the actual resources assigned for a particular task in the `e-dataSource` is specified using [`e-resourceInfoMapping`](http://help.syncfusion.com/js/api/ejgantt#members:resourceinfomapping "resourceInfoMapping").

1.Create the resource collection to be displayed in ejGantt

{% highlight javascript %}

 <body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      e-resourceInfoMapping="resourceId"
      e-resourceNameMapping="resourceName"
      e-resourceIdMapping="resourceId"
      e-resources="projectResources">             
   </div>
   <script>
      var projectResources =[{
      resourceId: 1,
      resourceName: "Project Manager"
      },{
      resourceId: 2,
      resourceName: "Software Analyst"
      },{
      resourceId: 3,
      resourceName: "Developer"
      },{
      resourceId: 4,
      resourceName: "Testing Engineer"
      }];
      
      angular.module('listCtrl', ['ejangular'])
      .controller('GanttCtrl', function ($scope) {
         $scope.projectResources=projectResources;
      });
   </script>
</body>   
    

{% endhighlight %}

The following screenshot displays resource allocation for tasks in Gantt chart.

![](/angular-1/Gantt/Getting-Started_images/Getting-Started_img10.png)

By following these steps, you have learned how to provide data source to Gantt chart, how to configure Gantt to set task relationships, assign resources for each task, and add toolbar with necessary buttons.

## Highlight Weekend

In Gantt, weekends can be highlighted by setting the [`e-highlightWeekEnds`](http://help.syncfusion.com/js/api/ejgantt#members:highlightweekends "highlightWeekEnds")

 as `true` or `false`.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      e-highlightWeekEnds="false">             
   </div>
   <script>
      angular.module('listCtrl', ['ejangular'])
      .controller('GanttCtrl', function ($scope) {
         //...
      });
   </script>
</body>  

{% endhighlight %}

The following screen shot displays Gantt chart in which highlight weekends is disabled:

![](/angular-1/Gantt/Getting-Started_images/Getting-Started_img12.png)
