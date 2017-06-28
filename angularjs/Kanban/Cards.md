---
layout: post
title:  Cards
description: Cards
documentation: ug
platform: AngularJS
keywords: cards,kanban cards
---

# Cards

## Customization

Cards can be customized with appropriate mapping fields from the database. The customizable mapping properties are listed as follows 

<table>
<tr>
<th>
Mapping Fields</th><th>
Description</th></tr>
<tr>
<td>
{{ 'content' | markdownify }} </td><td> Map the column name to use as content to cards.</td></tr>
<tr>
<td>
{{ 'tag' | markdownify }} </td><td>
Map the column name to use as tag. Multiple tags can be given with comma separated.  E.g. "API","SQL, Database".</td></tr>
<tr>
<td>
{{ 'color' | markdownify }} </td><td>
 Map the column name to use as colors to highlight cards left border.</td></tr>
<tr>
<td>
{{ 'colorMapping' | markdownify }} </td><td>
Map the colors to use with column values which is mapped with `fields.color`.</td></tr>
<tr>
<td>
{{ 'imageUrl' | markdownify }} </td><td>
Map the column name to use as image to cards.</td></tr>
<tr>
<td>
{{ 'primaryKey' | markdownify }} </td><td>
Map the column name to use as primary key to cards.</td></tr>
<tr>
<td>
{{ 'priority' | markdownify }} </td><td>
Map the column name to use as priority to cards.</td></tr>
<tr>
<td>
{{ 'title' | markdownify }} </td><td>
Map the column name to use as title to cards. Default title is  `primaryKey`.</td></tr>
<tr>
<td>
{{ 'allowTitle' | markdownify }} </td><td>
Set as true to enable title for card.</td></tr>
</table>

The following code example describes the above behavior.

{% highlight javascript %}

    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
    <head>
        <title>Essential Studio for AngularJS: Kanban</title>        
    </head>
    <body ng-controller="KanbanCtrl">
        <div id="Kanban" ej-kanban e-datasource="data" e-allowtitle="true" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-fields-priority="RankId"
            e-fields-tag="Tags" e-fields-color="Type" e-fields-imageurl="ImgUrl" e-cardsettings-colormapping="colors">
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
                    $scope.colors = {
                        "#cb2027": "Bug,Story",
                        "#67ab47": "Improvement",
                        "#fbae19": "Epic",
                        "#6a5da8": "Others",
                    };
                });
        </script>
    </body>
    </html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Cards_images/cards_img1.png)

## Template

Templates are used to create custom card layout as per the user convenient. HTML templates can be specified in the `template` property of the `cardSettings` as an ID of the template’s HTML element.

You can use JsRender syntax in the template. For more information about JsRender syntax, please refer this [`link`](https://www.jsviews.com/).

The following code example describes the above behavior.


{% highlight html %}

    <script id="cardtemplate" type="text/x-jsrender">        
            <table>
            <tr>
                <td class="photo">
                    <img src="{{:Priority}}.png">
                </td>            
                <td class="details">
                    <table>
                        <colgroup>
                            <col width="30%">
                            <col width="70%">
                        </colgroup>
                        <tbody>
                            <tr>
                                <td class="CardHeader">   Name: </td>
                                <td>{{:Assignee}}</td>
                            </tr>
                            <tr>
                                <td class="CardHeader">   Task: </td>
                                <td>{{:Type}}</td>
                            </tr>
                        </tbody>
                    </table>
                </td>
            </tr>
            </table> 
        </script>
            
{% endhighlight %}

{% highlight javascript %}

    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
    <head>
        <title>Essential Studio for AngularJS: Kanban</title>        
    </head>
    <body ng-controller="KanbanCtrl">
        <div id="Kanban" ej-kanban e-datasource="data" e-allowtitle="true" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-cardSettings-template="#cardtemplate">
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
        <script id="cardtemplate" type="text/x-jsrender">
            <table>
                <tr>
                    <td class="photo">
                        <img src="{{:Priority}}.png">
                    </td>
                    <td class="details">
                        <table>
                            <colgroup>
                                <col width="30%">
                                <col width="70%">
                            </colgroup>
                            <tbody>
                                <tr>
                                    <td class="CardHeader">   Name: </td>
                                    <td>{{:Assignee}}</td>
                                </tr>
                                <tr>
                                    <td class="CardHeader">   Task: </td>
                                    <td>{{:Type}}</td>
                                </tr>
                            </tbody>
                        </table>
                    </td>
                </tr>
            </table>
        </script>
    </body>
    </html>

{% endhighlight %}

{% highlight css %}

    <!--CSS for card template-->
        <style>
            .e-templatetable {
                width: 100%;
            }

            .details > table {
                margin-left: 2px;
                border-collapse: separate;
                border-spacing: 2px;
                width: 100%;
            }

            .details td {
                vertical-align: top;
            }

            .details {
                padding: 8px 8px 10px 0;
            }

            .photo {
                padding: 8px 6px 10px 6px;
                text-align: center;
            }

            .CardHeader {
                font-weight: bolder;
                padding-right: 10px;
            }
        </style>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Cards_images/cards_img2.png)

## Tooltip

You can enable HTML tooltip for Kanban card elements by setting `enable` property as true in `tooltipSettings`.

The following code example describes the above behavior.

{% highlight javascript %}

    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
    <head>
        <title>Essential Studio for AngularJS: Kanban</title>
    </head>
    <body ng-controller="KanbanCtrl">
        <div id="Kanban" ej-kanban e-datasource="data" e-allowtitle="true" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-fields-tag="Tags" e-tooltipSettings-enable="true">
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

![](Cards_images/cards_img3.png)

### Tooltip Template

By making use of template feature with tooltip, all the field names that are mapped from the `dataSource` can be accessed to define the `template` tooltip for card. The `tooltipSettings.enable` must be enabled first.

The following code example describes the tooltip template.

{% highlight html %}

    <script id="tooltipTemp" type="text/x-jsrender">
            <div class='e-kanbantooltiptemplate'>
                <table>
                    <tr>
                        <td class="photo">
                            <img src="{{:ImgUrl}}">
                        </td>
                        <td class="details">
                            <table>
                                <colgroup>
                                    <col width="30%">
                                    <col width="70%">
                                </colgroup>
                                <tbody>
                                    <tr>
                                        <td class="CardHeader">Assignee:</td>
                                        <td>{{:Assignee}}</td>
                                    </tr>
                                    <tr>
                                        <td class="CardHeader">Type:</td>
                                        <td>{{:Type}}</td>
                                    </tr>                                
                                    <tr>
                                        <td class="CardHeader">Estimate:</td>
                                        <td>{{:Estimate}}</td>
                                    </tr>                                
                                    <tr>
                                        <td class="CardHeader">Summary:</td>
                                        <td>{{:Summary}}</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                </table>
            </div>
    </script>

{% endhighlight %}

{% highlight javascript %}

    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
    <head>
        <title>Essential Studio for AngularJS: Kanban</title>  
    </head>
    <body ng-controller="KanbanCtrl">
        <div id="Kanban" ej-kanban e-datasource="data" e-allowtitle="true" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-fields-tag="Tags" e-tooltipsettings-enable="true" e-tooltipsettings-template="#tooltipTemp">
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

{% highlight css %}

    <!--toolTip template releated css -->
    <style> 
        .details >table {
            width: 100%;
            margin-left:2px;           
            border-collapse: separate;
            border-spacing: 1px;
        }
        .e-kanbantooltiptemplate {
            width: 250px;
            padding: 3px;
        }
        .e-kanbantooltiptemplate > table {
            width: 100%;
        }
        .e-kanbantooltiptemplate td {
            vertical-align: top;
        }
        td.details {
            padding-left: 10px;
        }
        .CardHeader {
            font-weight: bolder;
        }
    </style>

{% endhighlight %}

 
The following output is displayed as a result of the above code example.

![](Cards_images/cards_img4.png)