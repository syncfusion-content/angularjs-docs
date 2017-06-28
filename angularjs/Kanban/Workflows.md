---
layout: post
title:  Workflows
description: Workflows
documentation: ug
platform: AngularJS
keywords: Workflows,kanban Workflows
---

# Workflows 

Workflows can be defined to set the flow of card moving between the Kanban column statuses and it is applicable to drag and drop and context menu features.

You can set `workflows` as array of Objects which consists of `key` and `allowedTransitions` properties. The `allowedTransitions` accepts more than one transition of the specific column key mentioned in `key` property.

If a card is to be dragged to not allowed transition columns , then not supported warning symbol will be displayed for denoting the error.
        
The following code example describes the above Workflow functionality.

{% highlight javascript %}

    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
    <head>
        <title>Essential Studio for AngularJS: Kanban</title>        
    </head>
    <body ng-controller="KanbanCtrl">
        <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id">
            <div e-workflows>
                <div e-workflow e-key="Open" e-allowedtransitions="InProgress"></div>
                <div e-workflow e-key="InProgress" e-allowedtransitions="Testing,Close"></div>
            </div>
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

![](WorkFlows_images/workflows1.png)