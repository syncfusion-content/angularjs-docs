---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: AngularJS
control: Gantt
documentation: ug
---

# Appearance and styling

You can customize the look and feel of the Gantt control by applying themes and formatting the schedule header.

## Schedule header customization

You can customize the week header format and day header format in the schedule part of the Gantt control by using the following code example:

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
         e-scheduleheadersettings="scheduleheadersettings"
         >
      </div>
      <script>
        var scheduleheadersettings = {            
            weekHeaderFormat: "MMM yyyy",
            dayHeaderFormat: "d",
            weekendBackground: '#F2F2F2'
        }
        angular.module('listCtrl', ['ejangular'])
          .controller('GanttCtrl', function ($scope) {
              //...
              $scope.scheduleheadersettings = scheduleheadersettings;
          });
    </script> 
   </body>
</html>

{% endhighlight %}

The following screenshot shows the customized format schedule header in the Gantt control:

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)

## Taskbar customization

You can customize the taskbar based on the task information in the Gantt control to highlight the task. The following code example shows how to customize the taskbar in the Gantt control:

{% highlight javascript %}

 <body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-querytaskbarinfo="queryTaskbarInfo"
      >
   </div>
   <script>
      function queryTaskbarInfo(args) {
          //queryTaskbarInfo will be triggered when a taskbar is rendered
      
          if (args.data.level === 0) {
              args.parentTaskbarBackground = "pink";
              args.parentProgressbarBackground = "cyan";
          } else {
              if (args.data.status == "60") {
                  args.progressbarBackground = "red";
              } else if (args.data.status == "70") {
                  args.progressbarBackground = "yellow";
              } else if (args.data.status == "80") {
                  args.progressbarBackground = "green";
              }
          }
      }          
      angular.module('listCtrl', ['ejangular'])
      .controller('GanttCtrl', function ($scope) {
            //...
            $scope.queryTaskbarInfo = queryTaskbarInfo;
        });
   </script> 
</body>

{% endhighlight %}

The following screenshot shows the customized taskbar in the Gantt control:

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)

## Themes

 The following are the types of themes available in the Gantt control:

1.Flat Azure                  
2.Flat Azure dark
3.Flat lime                    
4.Flat lime dark
5.Flat saffron
6.Flat saffron dark
7.Gradient Azure
8.Gradient Azure dark
9.Gradient lime
10.Gradient lime dark
11.Gradient saffron
12.Gradient saffron dark
13.Bootstrap

You can apply the theme (gradient lime) to the Gantt control by using the style sheet from the online link as follows:

{% highlight html %}

    <!DOCTYPE html>

    <html xmlns="http://www.w3.org/1999/xhtml">
        <head>
        <title>Getting Started with Gantt Control for JavaScript</title>
        <!-- style sheet for default theme(gradient lime) -->
        <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" /> 
        //...
    </html>

{% endhighlight %}

The following screenshot shows the Gantt control with `Gradient-lime` theme:

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)

