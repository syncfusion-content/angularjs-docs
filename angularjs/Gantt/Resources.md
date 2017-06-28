---
layout: post
title: Resources
description: resources
platform: AngularJS
control: Gantt
documentation: ug
---

# Resources

Resources are represented by staff, equipment and materials etc. In Gantt control you can show /allocate the resources (human resources) for each task. The following steps explain how to configure Gantt with Resources

**Step 1**: Create a collection of `JSON` object, that contains id and name of the resource and assign it to `e-resources` property.

**Step 2**:  Then, specify the field name for id and name of the resource in the resource collection to `e-resourceidmapping` and `e-resourcenamemapping` properties. 

**Step 3**: The name of the field, which contains the actual resources assigned for a particular task in the dataSource is specified using `e-resourceinfomapping`.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
   //...
   e-resourceinfomapping= "resourceId"
        e-resourcenamemapping= "resourceName"
        e-resourceidmapping= "resourceId"
        e-resources= "projectResources"
        e-showresourcenames= "true">
   </div>
   <script>
   var projectResources = [{
        resourceId: 1,
        resourceName: "Project Manager"
    }, {
        resourceId: 2,
        resourceName: "Software Analyst"
    }, {
        resourceId: 3,
        resourceName: "Developer"
    }, {
        resourceId: 4,
        resourceName: "Testing Engineer"
    }];
    angular.module('listCtrl', ['ejangular'])
           .controller('GanttCtrl', function ($scope) {
               //...
               $scope.projectResources="projectResources";
          });  
</script>
</body>

{% endhighlight %}

The following screenshot shows Gantt control with Resources.

![](Resources_images/Resources_img1.png)

