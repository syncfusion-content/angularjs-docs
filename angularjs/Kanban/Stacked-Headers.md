---
layout: post
title:  Stacked Headers
description: Stacked Headers
documentation: ug
platform: Angular-1
keywords: stacked headers,kanban stacked headers
---
# Stacked Headers

The stacked headers helps you to group the logical columns in Kanban. It can be shown by setting `showStackedHeader` as true and by defining `stackedHeaderRows`.

## Adding Stacked header columns

To stack columns in stacked header, you need to define `column` property in `stackedHeaderColumns` with field names of visible columns.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-fields-tag="Tags">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Testing" e-key="Testing"></div>
            <div e-column e-headertext="Done" e-key="Close"></div>
        </div>
        <div e-stackedheaderrows>
            <div e-stackedheaderrow>
                <div e-stackedheadercolumns>
                    <div e-stackedheadercolumn e-headertext="Unresolved" e-column="Backlog,In Progress"></div>
                    <div e-stackedheadercolumn e-headertext="Resolved" e-column="Testing,Done"></div>
                </div>
            </div>
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

![](Stacked_Headers_images/stacked_header_img1.png)