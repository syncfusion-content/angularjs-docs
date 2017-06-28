---
layout: post
title: Predecessor
description: Predecessor
platform: AngularJS
control: Gantt
documentation: ug
---

# Predecessor

## Predecessor offset with duration units

In Gantt, predecessor offset can be defined with the following duration units, 

* Day
* Hour
* Minute

We can define offset with various offset duration units for predecessors by using below code example

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
   //...
   e-datasource="data"
    e-predecessormapping= "Predecessor"
    >
   </div>
   <script>
   var data = [
    //...
    {
        //...
    Predecessor: "4FS+2d"
    },
    { 
        //...
        Predecessor: "4FS+16h"
    },
    { 
        //...
        Predecessor: "4FS+960m"
    }
];
  angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.data="data";
          });  
</script>
</body>

{% endhighlight %}

The following screen shot depicts the duration unit support in the predecessor offset.

![](Predecessor_images/Predecessor_img1.png)


