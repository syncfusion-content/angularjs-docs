---
layout: post
title:  Editing
description: Editing
documentation: ug
platform: Angular-1
keywords: editing,kanban editing
---

# Editing

The Kanban control has support for dynamic insertion, updating and deletion of cards. 

Set `allowEditing` and `allowAdding` property as true to enable editing/inserting respectively. The primary key for the data source should be defined in `primaryKey`, for editing to work properly. 

You can start the edit action by double clicking the particular card. Similarly, you can add new card to Kanban either by double clicking the particular cell or on an external button which is bound to call `addCard` method of Kanban. 

Deletion of the card is possible by using `deleteCard` by passing primary key as attribute.

N> In Kanban, the `primary key` column will be automatically set to `read only` while editing the card which is to avoid duplicate entry in the cards.

## Configuring Edit Items

You need to configure the list of data source fields that are allowable in editing state using `editItems` property. The `field` property of `editItems` needs to be mapped with data source fields.

You can map the data source field as title to edit form using `title` property of `fields`. By default, it’s mapped with `primaryKey`.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>    
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-editsettings-allowediting="true" e-editsettings-allowadding="true">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>            
            <div e-column e-headertext="Done" e-key="Close"></div>
        </div>
        <div e-editsettings-edititems>
            <div e-editsettings-edititem e-field="Id"></div>
            <div e-editsettings-edititem e-field="Status" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Assignee" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Estimate" e-edittype="numericedit" e-editparams="params"></div>
            <div e-editsettings-edititem e-field="Summary" e-edittype="textarea" e-editparams="textparams"></div>
        </div>      
    </div>
    <script>
        angular.module('KanbanApp', ['ejangular'])
            .controller('KanbanCtrl', function ($scope) {
                $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
                $scope.textparams = { height: 100, width: 200 };
                $scope.params = { decimalPlaces: 2 };
            });
    </script>
</body>
</html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img1.png)

## Edit modes

### Dialog

Set `editMode` as `dialog` to edit data using a dialog box, which displays the fields associated with the data card being edited. Default value is `dialog`.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-editsettings-allowediting="true" e-editsettings-allowadding="true">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>            
            <div e-column e-headertext="Done" e-key="Close"></div>
        </div>
        <div e-editsettings-edititems>
            <div e-editsettings-edititem e-field="Id"></div>
            <div e-editsettings-edititem e-field="Status" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Assignee" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Estimate" e-edittype="numericedit" e-editparams="params"></div>
            <div e-editsettings-edititem e-field="Summary" e-edittype="textarea" e-editparams="textparams"></div>
        </div>      
    </div>
    <script>
        angular.module('KanbanApp', ['ejangular'])
            .controller('KanbanCtrl', function ($scope) {
                $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
                $scope.textparams = { height: 100, width: 200 };
                $scope.params = { decimalPlaces: 2 };
            });
    </script>
</body>
</html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img2.png)

### Dialog Template Form

You can edit any of the fields pertaining to a single card of data and apply it to a template so that the same format is applied to all the other cards that you may edit later. 

Using this template support, you can edit the fields that are not bound to `editItems`.

To edit the cards using Dialog template form, set `editMode` as `dialogtemplate` and specify the template id to `dialogTemplate` property of `editSettings`.

N> 1. `value` attribute is used to bind the corresponding field value while editing.
N> 2. `name` attribute is used to get the changed field values while save the edited card.

The following code example describes the above behavior.

{% highlight html %}

    <script id="template" type="text/template">
                        <table cellspacing="10">
                            <tr>
                                <td style="text-align: right;">Id
                                </td>
                                <td style="text-align: left">
                                    <input id="Id" name="Id" value="{{: Id}}" class="e-field e-ejinputtext valid e-disable" style="text-align: right; width: 175px; height: 28px" disabled="disabled" />
                                </td>
                                <td style="text-align: right;">Status
                                </td>
                                <td style="text-align: left">
                                    <select id="Status" name="Status">
                                        <option value="Close">Close</option>
                                        <option value="InProgress">InProgress</option>
                                        <option value="Open">Open</option>
                                    </select>
                                </td>
                            </tr>
                            <tr>
                                <td style="text-align: right;">Estimate
                                </td>
                                <td style="text-align: left">
                                    <input type="text" id="Estimate" name="Estimate" value="{{:Estimate}}" />
                                </td>
                                <td style="text-align: right;">Assignee
                                </td>
                                <td style="text-align: left">
                                    <select id="Assignee" name="Assignee">
                                        <option value="Nancy Davloio">Nancy Davloio</option>
                                        <option value="Andrew Fuller">Andrew Fuller</option>
                                        <option value="Janet Leverling">Janet Leverling</option>
                                        <option value="Margaret hamilt">Margaret hamilt</option>
                                        <option value="Steven walker">Steven walker</option>
                                        <option value="Michael Suyama">Michael Suyama</option>
                                        <option value="Robert King">Robert King</option>
                                        <option value="Laura Callahan">Laura Callahan</option>
                                    </select>
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
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-editsettings="editsetting" e-actioncomplete="complete">
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
                $scope.editsetting = { editMode: "dialogTemplate", allowEditing: "true", allowAdding: "true", dialogTemplate: "#template" };
                $scope.complete = function complete(args) {
                    if ((args.requestType == "beginedit" || args.requestType == "add") && args.model.editSettings.editMode == "dialogtemplate") {
                        $("#Estimate").ejNumericTextbox({ value: parseFloat($("#Estimate").val()), width: "175px", height: "34px", decimalPlaces: 2 });
                        $("#Assignee").ejDropDownList({ width: '175px' });
                        $("#Status").ejDropDownList({ width: '175px' });
                        if (args.requestType == "beginedit" || args.requestType == "add") {
                            $("#Assignee").ejDropDownList("setSelectedValue", args.data['Assignee']);
                            $("#Status").ejDropDownList("setSelectedValue", args.data['Status']);
                        }

                    }
                }
            });
    </script> 
</body>
</html>


{% endhighlight %}

While using template, you can change the elements that are defined in the `template`, to appropriate Syncfusion JS controls based on the column type. This can be achieved by using `actionComplete` event of Kanban. Please refer to about code snippets.

![](Editing_images/editing_img3.png)

### External Form

Set the `editMode` as externalform to open the edit form in outside kanban content.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>   
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-editsettings="editsetting" e-allowscrolling="true" e-scrollsettings-height=500 e-scrollsettings-width=900>
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Done" e-key="Close"></div>
        </div>
        <div e-editsettings-edititems>
            <div e-editsettings-edititem e-field="Id"></div>
            <div e-editsettings-edititem e-field="Status" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Assignee" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Estimate" e-edittype="numericedit" e-editparams="params"></div>
            <div e-editsettings-edititem e-field="Summary" e-edittype="textarea" e-editparams="textparams"></div>
        </div>   
    </div>
    <script>
        angular.module('KanbanApp', ['ejangular'])
            .controller('KanbanCtrl', function ($scope) {
                $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
                $scope.editsetting = { editMode: "ExternalForm", allowEditing: "true", allowAdding: "true" };
            });
    </script>
</body>
</html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img11.png)

Form Position:

Form Position can be customized by setting the `formPosition` property of `editSettings' as "right" or "bottom".

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-editsettings="editsetting" e-allowscrolling="true" e-scrollsettings-height=500 e-scrollsettings-width=900>
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Done" e-key="Close"></div>
        </div>
        <div e-editsettings-edititems>
            <div e-editsettings-edititem e-field="Id"></div>
            <div e-editsettings-edititem e-field="Status" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Assignee" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Estimate" e-edittype="numericedit" e-editparams="params"></div>
            <div e-editsettings-edititem e-field="Summary" e-edittype="textarea" e-editparams="textparams"></div>
        </div>   
    </div>
    <script>
        angular.module('KanbanApp', ['ejangular'])
            .controller('KanbanCtrl', function ($scope) {
                $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
                $scope.editsetting = { editMode: "ExternalForm", allowEditing: "true", allowAdding: "true",formPosition:"bottom" };
            });
    </script>
</body>
</html>
        
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img12.png)

### External Template Form

You can edit any of the fields pertaining to a single card of data and apply it to a template so that the same format is applied to all the other cards that you may edit later. 

Using this template support, you can edit the fields that are not bound to Kanban Edit Items.

To edit the cards using External template form, set `editMode` as `externalformtemplate` and specify the template id to `externalFormTemplate` property of `editSettings].

While using template, you can change the elements that are defined in the template, to appropriate Syncfusion JS controls based on the column type. This can be achieved by using `actionComplete` event of Kanban.

N> 1. `value` attribute is used to bind the corresponding field value while editing. 
N> 2. `name` attribute is used to get the changed field values while save the edited card. 

The following code example describes the above behavior.

{% highlight html %}
       
    <script id="template" type="text/template">
                    <table cellspacing="10">
                        <tr>
                            <td style="text-align:left;">Id
                            </td>
                            <td style="text-align: left">
                                <input id="Id" name="Id" value="{{: Id}}" class="e-field e-ejinputtext valid e-disable" style="text-align: right; width: 175px; height: 28px" disabled="disabled" />
                            </td>
                            </tr>
                            <tr>
                            <td style="text-align: left;">Status
                            </td>
                            <td style="text-align: left">
                                  <select id="Status" name="Status">
                                    <option value="Close">Close</option>
                                    <option value="InProgress">InProgress</option>
                                    <option value="Open">Open</option>
                                    <option value="Testing">Testing</option>
                                    <option value="Validate">Validate</option>
                                </select>
                            </td>
                        </tr>
                            <tr>
                             <td style="text-align: left;">Assignee
                            </td>
                            <td style="text-align: left">
                                <select id="Assignee" name="Assignee">
                                    <option value="Nancy Davloio">Nancy Davloio</option>
                                    <option value="Andrew Fuller">Andrew Fuller</option>
                                    <option value="Janet Leverling">Janet Leverling</option>
                                    <option value="Margaret hamilt">Margaret hamilt</option>
                                    <option value="Steven walker">Steven walker</option>
                                    <option value="Michael Suyama">Michael Suyama</option>
                                    <option value="Robert King">Robert King</option>
                                    <option value="Laura Callahan">Laura Callahan</option>
                                </select>
                            </td>
                        </tr>                      
                        <tr>
                            <td style="text-align: left;">Priority
                            </td>
                            <td style="text-align: left">
                                <input id="Priority" name="Priority" value="{{: Priority}}" class="e-field e-ejinputtext valid" style="width: 175px; height: 28px" />
                            </td>
                        </tr>
                        <tr>
                            <td style="text-align: left;">Summary
                            </td>
                            <td style="text-align: left">
                                <textarea id="Summary" name="Summary" class="e-ejinputtext"  value="{{: Summary}}" style="width: 270px; height: 95px">{{: Summary}}</textarea>
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
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Essential Studio for JavaScript">
    <meta name="author" content="Syncfusion">
    <!-- Essential Studio for JavaScript  theme reference -->
    <link href="http://cdn.syncfusion.com/14.4.0.15/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!-- Essential Studio for JavaScript  script references -->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script src="http://cdn.syncfusion.com/14.4.0.15/js/web/ej.web.all.min.js"></script>
    <script src="http://cdn.syncfusion.com/14.4.0.15/js/common/ej.widget.angular.min.js" type="text/javascript"></script>
    <script src="http://js.syncfusion.com/demos/web/scripts/jsonkanbandata.js" type="text/javascript"></script>
    <!-- Add your custom scripts here -->
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-editsettings="editsetting" e-actioncomplete="complete" e-allowscrolling="true" e-scrollsettings-height=500 e-scrollsettings-width=900>
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
                $scope.editsetting = { editMode: "ExternalFormTemplate", allowEditing: "true", allowAdding: "true", externalFormTemplate: "#template" };
                $scope.complete = function complete(args) {
                    if ((args.requestType == "beginedit" || args.requestType == "add") && args.model.editSettings.editMode == "externalformtemplate") {
                        $("#Assignee").ejDropDownList({ width: '175px' });
                        $("#Status").ejDropDownList({ width: '175px' });
                        if(args.requestType == "beginedit" || args.requestType == "add" ){
                            $("#Assignee").ejDropDownList("setSelectedValue", args.data['Assignee']);
                            $("#Status").ejDropDownList("setSelectedValue", args.data['Status']);
                        }                
                    }                    
                }
            });
    </script>
    <script id="template" type="text/template">
        <table cellspacing="10">
            <tr>
                <td style="text-align:left;">
                    Id
                </td>
                <td style="text-align: left">
                    <input id="Id" name="Id" value="{{: Id}}" class="e-field e-ejinputtext valid e-disable" style="text-align: right; width: 175px; height: 28px" disabled="disabled" />
                </td>
            </tr>
            <tr>
                <td style="text-align: left;">
                    Status
                </td>
                <td style="text-align: left">
                    <select id="Status" name="Status">
                        <option value="Close">Close</option>
                        <option value="InProgress">InProgress</option>
                        <option value="Open">Open</option>
                        <option value="Testing">Testing</option>
                        <option value="Validate">Validate</option>
                    </select>
                </td>
            </tr>
            <tr>
                <td style="text-align: left;">
                    Assignee
                </td>
                <td style="text-align: left">
                    <select id="Assignee" name="Assignee">
                        <option value="Nancy Davloio">Nancy Davloio</option>
                        <option value="Andrew Fuller">Andrew Fuller</option>
                        <option value="Janet Leverling">Janet Leverling</option>
                        <option value="Margaret hamilt">Margaret hamilt</option>
                        <option value="Steven walker">Steven walker</option>
                        <option value="Michael Suyama">Michael Suyama</option>
                        <option value="Robert King">Robert King</option>
                        <option value="Laura Callahan">Laura Callahan</option>
                    </select>
                </td>
            </tr>
            <tr>
                <td style="text-align: left;">
                    Priority
                </td>
                <td style="text-align: left">
                    <input id="Priority" name="Priority" value="{{: Priority}}" class="e-field e-ejinputtext valid" style="width: 175px; height: 28px" />
                </td>
            </tr>
            <tr>
                <td style="text-align: left;">
                    Summary
                </td>
                <td style="text-align: left">
                    <textarea id="Summary" name="Summary" class="e-ejinputtext" value="{{: Summary}}" style="width: 270px; height: 95px">{{: Summary}}</textarea>
                </td>
            </tr>
        </table>
    </script>
</body>
</html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img13.png)

## Cell edit type and its params

The edit type of bound column can be customized using `editType` property of `editItems`. The following Essential JavaScript controls are supported built-in by `editType`. And also you can define the model for all the edit types controls while editing through `editParams` property of `editItems`.

The following table describes `editType` and their corresponding `editParams` of the specific data type of the column.

<table>
<tr>
<th>
EditType</th><th>
EditParams</th>
<th>
Description</th>
<th>
Example</th>
</tr>
<tr>
<td>
Numeric</td><td>
{{ '[ejTextBoxes](https://help.syncfusion.com/api/js/ejtextboxes)' | markdownify }} </td>
<td>
control for integers, double, and decimal data’s</td>
<td>
editParams: { decimalPlaces: 2}</td>
</tr>
<tr>
<td>
String</td><td>
HTML Textbox</td>
<td>
HTML Textbox</td>
<td>
-</td>
</tr>
<tr>
<td>
DatePicker </td><td>
{{ '[ejDatePicker](https://help.syncfusion.com/api/js/ejdatepicker)' | markdownify }} </td>
<td>
control for date data</td>
<td>
editParams: { buttonText : "Now" }</td>
</tr>
<tr>
<td>
DateTimePicker </td><td>
{{ '[ejDateTimePicker](https://help.syncfusion.com/api/js/ejdatetimepicker)' | markdownify }} </td>
<td>
control for date data-time data</td>
<td>
editParams: { enabled: true }</td>
</tr>
<tr>
<td>
DropDown </td><td>
{{ '[ejDropDownList](https://help.syncfusion.com/api/js/ejdropdownlist)' | markdownify }} </td>
<td>
control for list of data</td>
<td>
editParams: { allowGrouping: true }</td>
</tr>
<tr>
<td>
RTE </td><td>
{{ '[ejRTE](https://help.syncfusion.com/api/js/ejrte)' | markdownify }} </td>
<td>
control for customizing text in RTE format</td>
<td>
editParams: { allowResize: true }</td>
</tr>
<tr>
<td>
TextArea </td><td>
HTML TextArea</td>
<td>
Control for multi-line plain-text editing</td>
<td>
editParams:{height:100,width:200}</td>
</tr>
</table>

N> 1. If `editType` is not set, then by default it will display HTML textbox while editing a card.

The following code example describes the above behavior.


{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title>   
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-editsettings-allowadding="true" e-editsettings-allowediting="true">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Done" e-key="Close"></div>
        </div>
        <div e-editsettings-edititems>
            <div e-editsettings-edititem e-field="Id"></div>
            <div e-editsettings-edititem e-field="Status" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Assignee" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Estimate" e-edittype="numericedit" e-editparams="numericparams"></div>
            <div e-editsettings-edititem e-field="Summary" e-edittype="rteedit" e-editparams="rteparams"></div>
        </div>
    </div>
    <script>
        angular.module('KanbanApp', ['ejangular'])
            .controller('KanbanCtrl', function ($scope) {
                $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
                $scope.numericparams = { decimalPlaces: 2 };
                $scope.rteparams = { height: 150, minHeight: 100 };
            });
    </script>
</body>
</html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img4.png)

## Column Validation

We can validate the value of the added or edited card cell before saving.

The below validation script files are needed when editing is enabled with validation.

1.	jquery.validate.min.js
2.	jquery.validate.unobtrusive.min.js

N> If you enabled the unobtrusive option, then need to refer the jquery.validate.unobtrusive.min.js
file in your application along with the other script.

### jQuery Validation

You can set validation rules using `validationRules` property of `columns`. The following are jQuery validation methods.

#### List of jQuery validation methods

<table>
<tr>
<th>
Rules</th><th>
Description</th>
</tr>
<tr>
<td>
required</td><td>
Requires an element.</td></tr>
<tr>
<td>
remote</td><td>
Requests a resource to check the element for validity.</td></tr>
<tr>
<td>
minlength</td><td>
Requires the element to be of given minimum length.</td></tr>
<tr>
<td>
maxlength</td><td>
Requires the element to be of given maximum length.</td></tr>
<tr>
<td>
rangelength</td><td>
Requires the element to be in given value range.</td></tr>
<tr>
<td>
min</td><td>
The element requires a given minimum.</td></tr>
<tr>
<td>
max</td><td>
The element requires a given maximum.</td></tr>
<tr>
<td>
range</td><td>
Requires the element to be in a given value range.</td></tr>
<tr>
<td>
email</td><td>
The element requires a valid email.</td></tr>
<tr>
<td>
url</td><td>
The element requires a valid url.</td></tr>
<tr>
<td>
date</td><td>
Requires the element to be a date.</td></tr>
<tr>
<td>
dateISO</td><td>
The element requires an ISO date.</td></tr>
<tr>
<td>
number</td><td>
The element requires a decimal number.</td></tr>
<tr>
<td>
digits</td><td>
The element requires digits only.</td></tr>
<tr>
<td>
creditcard</td><td>
Requires the element to be a credit card number.</td></tr>
<tr>
<td>
equalTo</td><td>
Requires the element to be the same as another.</td></tr>
</table>

Kanban supports all the standard validation methods of jQuery, please refer the jQuery validation documentation [`link`](https://jqueryvalidation.org/) for more information.

The following code example describes the above behavior.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="KanbanApp">
<head>
    <title>Essential Studio for AngularJS: Kanban</title> 
</head>
<body ng-controller="KanbanCtrl">
    <div id="Kanban" ej-kanban e-datasource="data" e-keyfield="Status" e-fields-content="Summary" e-fields-primarykey="Id" e-editsettings-allowadding="true" e-editsettings-allowediting="true">
        <div e-columns>
            <div e-column e-headertext="Backlog" e-key="Open"></div>
            <div e-column e-headertext="In Progress" e-key="InProgress"></div>
            <div e-column e-headertext="Done" e-key="Close"></div>
        </div>
        <div e-editsettings-edititems>
            <div e-editsettings-edititem e-field="Id"></div>
            <div e-editsettings-edititem e-field="Status" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Assignee" e-edittype="dropdownedit"></div>
            <div e-editsettings-edititem e-field="Estimate" e-edittype="numericedit" e-editparams="numericparams" e-validationrules="numericvalidation"></div>
            <div e-editsettings-edititem e-field="Summary" e-edittype="textarea" e-validationrules-required="true"></div>
        </div>
    </div>
    <script>
        angular.module('KanbanApp', ['ejangular'])
            .controller('KanbanCtrl', function ($scope) {
                $scope.data = new ej.DataManager(window.kanbanData).executeLocal(ej.Query().take(30));
                $scope.numericparams = { decimalPlaces: 2 };
                $scope.numericvalidation= { range: [0, 1000] };
            });
    </script>
</body>
</html>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/editing_img5.png)
