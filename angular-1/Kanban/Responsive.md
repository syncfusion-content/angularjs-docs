---
layout: post
title:  Responsive
description: Responsive
documentation: ug
platform: Angular-1
keywords: responsive,kanban responsive
---

# Responsive

The Kanban control has support for responsive behavior based on client browser’s width and height. To enable responsive, `isResponsive` property should be true.There are two modes of responsive layout is available in Kanban based on client width. They are.

* Mobile(<480px)
* Desktop(>480px)

## Mobile Layout

If client width is less than 480px, the Kanban will render in mobile mode. In which, you can see that kanban user interface is customized and redesigned for best view in small screens.To enable responsive, `isResponsive` property should be true.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-imageurl="ImgUrl" e-allowsearching="true" e-fields-content="Summary" e-fields-primarykey="Id" e-isresponsive="true" e-editsettings-allowediting="true" e-editsettings-allowadding="true">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Done" e-key="Close"></div>
        </div>
        <div e-editsettings-edititems>
            <div e-editsettings-edititem e-field="Id"></div>
            <div e-editsettings-edititem e-field="Status" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Assignee" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Estimate" e-edittype="numericedit"></div>
            <div e-editsettings-edititem e-field="Summary" e-edittype="textarea"></div>
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

![](Responsive_images/Responsive_img2.png)


W> IE8 and IE9 does not support responsive kanban. `ej.responsive.css` should be referred to display Responsive Kanban.

![](Responsive_images/Responsive_img3.png)
{:caption}
CRUD in mobile layout

![](Responsive_images/Responsive_img4.png)
{:caption}
Filtering in mobile layout

![](Responsive_images/Responsive_img5.png)
{:caption}
Searching in mobile layout

![](Responsive_images/Responsive_img6.png)

![](Responsive_images/Responsive_img7.png)
{:caption}
Kanban with Swim-lane

## Width

By default, the Kanban is adaptable to its parent container. It can adjust its width of columns based on parent container width. You can also assign width of `columns` in percentage. 

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-imageurl="ImgUrl" e-fields-tag="Tags" e-fields-content="Summary" e-fields-primarykey="Id" e-isresponsive="true">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open" e-width="10%"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress" e-width="10%"></div>
            <div e-column e-headertext="Done" e-key="Close" e-width="10%"></div>
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

N> `allowScrolling` should be false while defining width in percentage.

## Min Width

Min Width is used to maintain minimum width for the Kanban. If the Kanban width is less than `minWidth` then the scrollbar will be displayed to maintain minimum width.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-imageurl="ImgUrl" e-fields-tag="Tags" e-fields-content="Summary" e-fields-primarykey="Id" e-isresponsive="true" e-minwidth="700">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open" e-width="120"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress" e-width="110"></div>
            <div e-column e-headertext="Done" e-key="Close" e-width="110"></div>
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

![](Responsive_images/responsive_img1.png)
