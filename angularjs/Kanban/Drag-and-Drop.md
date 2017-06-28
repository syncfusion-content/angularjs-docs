---
layout: post
title:  Drag and Drop
description: Drag and Drop
documentation: ug
platform: Angular-1
keywords: drag and drop,kanban drag and drop
---

# Drag and Drop

By default `allowDragAndDrop` is true.Cards can be transited from one column to another column, by dragging and dropping. And it has drop position indicator which enables easier positioning of cards

N> To transit cards to other swim lanes through Drag and Drop, please refer [here](https://help.syncfusion.com/angular-1/kanban/swimlanes#drag-and-drop-between-swim-lanes).

## Prioritization of cards

Prioritizing cards is easy with drag-and-drop re-ordering that helps you to categorize most important work at the top.Cards can be categorized with priority by mapping specific database field into `priority` property.

`RankId` defined in the dataSource which is consist priority of cards. The `RankId` will be changed while card ordering changes through `Drag and Drop` and `Editing`.

The following code example describes the above behavior.

{% highlight javascript %}

    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
    <head>
        <title>Essential Studio for AngularJS: Kanban</title>        
    </head>
    <body ng-controller="KanbanCtrl">
        <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-fields-priority="RankId">
            <div e-columns>
                <div e-column e-headertext="Backlog" e-key="Open"></div>
                <div e-column e-headertext="In Progress" e-key="InProgress"></div>
                <div e-column e-headertext="Testing" e-key="Testing"></div>
                <div e-column e-headertext="Done" e-key="Close"></div>
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

![](Drag_and_Drop_images/drag_and_drop_img1.png)
