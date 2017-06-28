---
layout: post
title:  Filtering
description: Filtering
documentation: ug
platform: Angular-1
keywords: filtering,kanban filtering
---

# Filtering

Filtering allows to filter the collection of cards from `dataSource` which meets the predefined `query` in the quick filters collection. To enable filtering, define `filterSettings` collection with display `text` and `ej.Query`. 

You can also define display tip to describe filter definition to user using property `description`. If the `description` property is not defined, given [`text`](https://help.syncfusion.com/api/js/ejkanban#members:filtersettings-text) will act as display tip.

We can also customize filter option through external button or `customToolbarItems` by using `filterCards()` method.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>   
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Done" e-key="Close"></div>
        </div>
        <div e-filtersettings>
            <div e-filtersetting e-text="Janet Issues" e-query="query1" e-description="Displays issues which matches the assignee as 'Janet Leverling'"></div>
            <div e-filtersetting e-text="InProgress Issues" e-query="query2" e-description="Display the issues of 'In Progress'"></div>
        </div>	
    </div>
    <script>
        angular.module('KanbanApp', ['ejangular'])
            .controller('KanbanCtrl', function ($scope) {
                $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
                $scope.query1 = new ej.Query().where('Assignee', 'equal', 'Janet Leverling');
                $scope.query2 = new ej.Query().where('Status', 'equal', 'InProgress');
            });
    </script>
</body>
</html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Filtering_images/filter_img1.png)