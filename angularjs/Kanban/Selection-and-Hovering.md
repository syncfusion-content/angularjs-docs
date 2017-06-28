---
layout: post
title: Selection and Hovering
description: Selection and Hovering
documentation: ug
platform: AngularJS
keywords: selection, hovering,kanban selection, hovering
---

# Selection and Hovering

Selection provides an interactive support to highlight the card that you select. Selection can be done through simple Mouse down or Keyboard interaction. To enable selection, set `allowSelection` as true.

You can see the mouse hovering effect on the corresponding cards using `allowHover` property. By default selection and hovering is `true`.

## Types of Selection

Two types of selections available in Kanban are,

1.	Single
2.	Multiple

### Single Selection

To enable single selection by setting `selectionType` property as single.

### Multiple Selection

Multiple selections is an interactive support to select a group of cards in Kanban by mouse or keyboard interactions. To enable multiple selections by set `selectionType` property as `multiple`.

You can select multiple random cards below key press.

<table>
<tr>
<th>
Keys</th><th>
Description</th></tr>
<tr>
<td>
Ctrl + mouse left</td><td>
To select multiple random cards.</td></tr>
<tr>
<td>
Shift + mouse left </td><td>
To continuous cards select.</td></tr>
</table>

To unselect selected cards, by press “Shift + mouse left” click on selected row.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-fields-tag="Tags" e-selectiontype="multiple">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
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

![](Selection_images/selection_img1.png)