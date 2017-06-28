---
layout: post
title:  context menu 
description: context menu 
documentation: ug
platform: AngularJS
keywords: context menu ,kanban context menu 
---

# Context Menu  

Context menu is used to improve user action with Kanban using popup menu. It can be shown by defining `contextMenuSettings.enable` as true. Context menu has option to add default items in `contextMenuSettings.menuItems` and customized items in [`contextMenuSettings.customMenuItems`.

## Default Context Menu items

Please find the below table for default context menu items and its actions.

<table>
        <tr>
            <th>
                Section 
            </th>
            <th>
               Context menu items 
            </th>
            <th>
                Action
            </th>
        </tr>
        <tr>
            <td rowspan="2">
                Header 
            </td>
            <td>
                Hide Column
            </td>
            <td>
               Hide the current column 
            </td>
        </tr>
        <tr>
            <td>
                Visible Columns
            </td>
            <td>
                Show the column if already hidden 
            </td>
        </tr>
       <tr>
            <td>
                Content
            </td>
            <td>
                Add Card 
            </td>
             <td>
                Start Add new card 
            </td>
        </tr>
        <tr>
            <td rowspan="10">
                Card
            </td>
            <td>
               Edit Card 
            </td>
            <td>
               Start Edit in current card 
            </td>
        </tr>
        <tr>
            <td>
               Delete Card 
            </td>
            <td>
                Delete the current card 
            </td>
        </tr>
        <tr>
            <td>
                Top of Row
            </td>
            <td>
                Move the card to Top of Row
            </td>
        </tr>
        <tr>
            <td>
               Bottom of Row
            </td>
            <td>
                Move the card to Bottom of Row
            </td>
        </tr>
        <tr>
            <td>
               Move Up
            </td>
            <td>
                Move the card in Up direction 
            </td>
        </tr>
        <tr>
            <td>
               Move Down
            </td>
            <td>
               Move the card in Down direction
            </td>
        </tr>
        <tr>
            <td>
                Move Left
            </td>
            <td>
                Move the card in Left direction
            </td>
        </tr>
        <tr>
            <td>
               Move Right
            </td>
            <td>
                Move the card in Right direction
            </td>
        </tr>
        <tr>
            <td>
              Move Swimlane
            </td>
            <td>
                Move the card to Swim lane which is chosen from given list
            </td>
        </tr>
         <tr>
            <td>
              Print Card
            </td>
            <td>
                Print the specific card
            </td>
        </tr>
    </table>

    
The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-contextmenusettings-enable="true">
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

![](Context_images/context_img1.png)

![](Context_images/context_img2.png)

## Custom Context Menu

Custom context menu is used to create your own menu item and its action. To add customized context menu items, you need to use `contextMenuSettings.customMenuItems` property and to bind required actions for this, use `contextClick` event.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-fields-swimlanekey="Assignee" e-fields-tag="Tags" e-contextmenusettings-enable="true" e-contextmenusettings-menuitems=[] e-contextmenusettings-custommenuitems="custommenuitems">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Testing" e-key="Testing"></div>
        </div>
        <script>
            angular.module('KanbanApp', ['ejangular'])
                .controller('KanbanCtrl', function ($scope) {
                    $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
                    $scope.custommenuitems = [{ text: "Clear Selection" }];
                });
        </script>
</body>
</html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Context_images/context_img3.png)

## Sub Context Menu

Sub context menu is used to add customized sub menu to the custom context menu item. To add a sub context menu, you need to use `contextMenuSettings.subMenu` property and to bind required actions for this, use `contextClick` event.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-fields-swimlanekey="Assignee" e-fields-tag="Tags" e-editsettings-allowediting="true" e-editsettings-allowadding="true" e-contextmenusettings-enable="true" e-contextmenusettings-menuitems=[] e-contextmenusettings-custommenuitems="custommenuitems" e-contextclick="contextclick">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Testing" e-key="Testing"></div>
        </div>
        <div e-editsettings-edititems>
            <div e-editsettings-edititem e-field="Id"></div>
            <div e-editsettings-edititem e-field="Status" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Assignee" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Estimate" e-edittype="numericedit"></div>
            <div e-editsettings-edititem e-field="Summary" e-edittype="textarea"></div>
        </div>
    </div>
    <script>
        angular.module('KanbanApp', ['ejangular'])
            .controller('KanbanCtrl', function ($scope) {
                $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
                $scope.custommenuitems = [{ text: "Clear Selection" }];
                $scope.contextclick = function (args) {
                    if (args.text == "Clear Selection")
                        this.KanbanSelection.clear();
                };
            });
    </script>
</body>
</html>

{% endhighlight %}


The following output is displayed as a result of the above code example.

![](Context_images/context_img4.png)