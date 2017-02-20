---
layout: post
title: Context-Menu
description: context menu
platform: Angular-1
control: Gantt
documentation: ug
---
# Context Menu

## Default Menu Items

Context menu in Gantt has the following default menu items,

* Task Details
* Add New Task
* Indent
* Outdent
* Delete

The following code example explains how to enable the context menu in Gantt control.

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
        e-enablecontextmenu= "true"   
        >
      </div>
   </body>
</html>

{% endhighlight %}

The following screenshot shows the default context menu in Gantt control.

![](Context-Menu_images/Context-Menu_img1.png)

## Custom Menu Item

It is possible to add a custom context menu item in Gantt control. The following code example explains on how to add the custom context menu item

{% highlight javascript %}

 <body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-contextmenuopen= "contextMenuOpen"   
      >
   </div>
<script>
   function contextMenuOpen(args){           
         args.contextMenuItems.push({
             headerText: "Expand/Collapse",
             menuId: "expand",
             iconPath: "url(Expand-02-WF.png)",
             eventHandler: function() {
                 //event handler for custom menu items
             }
         });
          }
          angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.contextMenuOpen=contextMenuOpen;
          });     
</script>
</body>

{% endhighlight %}

The screenshot of the custom context menu items in Gantt control is as follows.

![](Context-Menu_images/Context-Menu_img2.png)

### Custom menu item with sub menu item

It is possible to create a custom menu item with a sub menu by mapping the parentMenuId property from the contextMenuItems argument in the contextMenuOpen event.

The following code example explains on how to add sub context menu for custom menu items.

{% highlight javascript %}

 <body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-contextmenuopen= "contextMenuOpen"   
      >
   </div>
<script>
   function contextMenuOpen(args){           
        args.contextMenuItems.push({
            headerText: "Expand/Collapse",
            menuId: "expand",
            iconPath: "url(Navigation-Up-02-WF.png)",
            eventHandler: function() {
                //event handler for custom menu items
            }
        });
        args.contextMenuItems.push({
            headerText: "ExpandAll",
            menuId: "expandall",
            parentMenuId: "expand",
            iconPath: "url(Expand-02-WF.png)",
            eventHandler: function() {
                //event handler for custom menu items
            }
        });
        args.contextMenuItems.push({
            headerText: "CollapseAll",
            menuId: "collapseall",
            parentMenuId: "expand",
            iconPath: "url(shrink2.png)",
            eventHandler: function() {
                //event handler for custom menu items
            }
        });
        }
          angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.contextMenuOpen=contextMenuOpen;
          });     
</script>
</body>

{% endhighlight %}

The screenshot of the custom context menu items in Gantt control is as follows.

![](Context-Menu_images/Context-Menu_img3.png)

