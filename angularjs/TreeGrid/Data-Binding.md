---
layout: post
title: Data-Binding
description: data binding
platform: Angular-1
control: TreeGrid
documentation: ug
---

# Data Binding

Data Binding is the process that establishes a connection between the application and different kinds of data sources such as business objects.

## Local Data Binding

In Local Data Binding, datasource for rendering the TreeGrid control is retrieved from the same application locally.

Two types of Data Binding are possible with TreeGrid control, 

* Hierarchical Datasource Binding
* Self-Referential Data Binding (Flat Data)

### Hierarchy Datasource Binding

The following code example shows you how to bind the hierarchical local data into the TreeGrid control.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-datasource="dataSource" 
    e-childmapping="subtasks"
    e-treecolumnindex="1"
    e-columns="columns">
    </div>
    <script>
     var columns = [ { field:"taskID", headerText:"Task Id", width:"45"},
                    { field:"taskName", headerText:"Task Name"},
                    { field:"startDate", headerText:"Start Date"},
                    { field:"endDate", headerText:"End Date"},
    ]
    var projectData = [
                    {
                    taskID: 1,
                    taskName:"Planning",
                    startDate:"02/03/2014",
                    endDate:"02/07/2014",
                    progress: 100,
                    duration:5,
                    subtasks: [
                    {
                        taskID: 2,
                        taskName:"Plan timeline",
                        startDate:"02/03/2014",
                        endDate:"02/07/2014",
                        duration: 5,
                        progress: 100
                     },
                     {
                        taskID: 3,
                        taskName:"Plan budget",
                        startDate:"02/03/2014",
                        endDate:"02/07/2014",
                        duration: 5,
                        progress: 100
                        },
                        //...
            ]},
            //...
            ];
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.dataSource = "projectData";
                $scope.columns = "columns";
            });
    </script>
</body>

{% endhighlight %}

The output of the above steps is as follows:

![](Data-Binding_images/Data-Binding_img1.png)

###Self-Referential Data Binding (Flat Data)

TreeGrid is rendered from Self-Referential data structures by providing two fields: **ID** field and **parent ID** field.

* **ID Field** - This field contains unique values used to identify nodes. Its name is assigned to the [`e-idmapping`](/api/js/ejtreegrid#idmappingspan-classtype-signature-type-stringstringspan "idMapping") property.
* **Parent ID Field** - This field contains values that indicate parent nodes. Its name is assigned to the [`e-parentidmapping`](/api/js/ejtreegrid#parentidmappingspan-classtype-signature-type-stringstringspan "parentIdMapping") property.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-datasource="dataSource" 
    e-childmapping="subtasks"
    e-treecolumnindex="1"
    e-idmapping="taskID"
    e-parentidmapping="pId"
    >
    </div>
    <script>
     var columns = [   { field: "taskID", headerText: "Task Id", width: "45" },
                    { field: "taskName", headerText: "Task Name" },
                    { field: "startDate", headerText: "Start Date" },
                    { field: "endDate", headerText: "End Date" },
                    { field: "duration", headerText: "Duration" },
                    { field: "progress", headerText: "Progress" }
    ]
    var projectData = [
         {
             taskID: 1,
             taskName: "Task 1",
             startDate: "02/03/2014",
             endDate: "03/07/2014",
             duration: 5
         },
         {
             taskID: 2,
             pId: 1,
             taskName: "Child Task 1",
             startDate: "02/03/2014",
             endDate: "02/07/2014",
             duration: 5
         },
         {
             taskID: 3,
             pId: 1,
             taskName: "Child Task 2",
             startDate: "02/03/2014",
             endDate: "02/07/2014",
             duration: 5,
             progress: "100"
         },
         {
             taskID: 22,
             pId: 2,
             taskName: "Sub Child Task 1",
             startDate: "02/03/2014",
             endDate: "02/07/2014",
             duration: 5
         },
         {
             taskID: 23,
             pId: 2,
             taskName: "Sub Child Task 2",
             startDate: "02/03/2014",
             endDate: "02/07/2014",
             duration: 5,
             progress: "100"
         },    
         //...
     ];
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.dataSource = "projectData";
                $scope.columns = "columns";
            });
    </script>
</body>

{% endhighlight %}

The following screenshot shows the output of the above steps,

![](Data-Binding_images/Data-Binding_img2.png)

