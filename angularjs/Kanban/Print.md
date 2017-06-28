---
layout: post
title:  Print with Kanban widget for Syncfusion Essential JS
description: How to enable print option in Kanban
documentation: ug
platform: AngularJS
---

# Print

 Set `allowPrinting` as true, to enable Print icon in the Kanban toolbar.  You can use `print()` method from Kanban instance to print the Kanban.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-allowprinting="true">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Testing" e-key="Testing"></div>
        </div>
    </div>
    <script>
        angular.module('KanbanApp', ['ejangular'])
            .controller('KanbanCtrl', function ($scope) {
                $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
            });
    </script>
</body>
</html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Printing_images/print_img1.png)


