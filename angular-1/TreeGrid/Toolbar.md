---
layout: post
title: Toolbar
description: toolbar
platform: Angular-1
control: TreeGrid
documentation: ug
---

In TreeGrid we can show/hide the Toolbar by using [`toolbarSettings.showToolbar`](https://help.syncfusion.com/api/js/ejtreegrid#members:toolbarsettings-showtoolbar "showToolbar") property.We can add default toolbar items by [`toolbarSettings.toolbarItems`](https://help.syncfusion.com/api/js/ejtreegrid#members:toolbarsettings-toolbaritems "toolbarItems"). User can also create a custom toolbar items by using [`toolbarSettings.customToolbarItems`](https://help.syncfusion.com/api/js/ejtreegrid#members:toolbarsettings-customToolbarItems "customToolbarItems").

## Default Toolbar Items
Using TreeGrid default toolbar items we can perform below operations.

* **Add**- To add new task.

* **Edit**-To edit a selected task.

* **Delete**- To delete a selected task.
		   
* **Cancel**- To cancel the edited changes in a task.
		   
* **Update**- To save the edited changes in a task.
		   
* **ExpandAll**- To expand all the TreeGrid rows.
		   
* **CollapseAll**- To collapse all the TreeGrid rows.
		   
* **PdfExport**- To export TreeGrid in Pdf format.
		   
* **ExcelExport**- To export TreeGrid in Excel format.

We can enable TreeGrid toolbar by using below code example:
{% highlight js %}
    <body ng-controller="TreeGridCtrl">                
           <div id="angulartreegrid" ej-treegrid e-toolbarsettings="toolbarSettings"></div>            
    <script>       
        var toolbarSettings =
            {
        showToolbar: true,
        toolbarItems: [
            ej.TreeGrid.ToolbarItems.Add,
            ej.TreeGrid.ToolbarItems.Edit,
            ej.TreeGrid.ToolbarItems.Delete,
            ej.TreeGrid.ToolbarItems.Update,
            ej.TreeGrid.ToolbarItems.Cancel,
            ej.TreeGrid.ToolbarItems.ExpandAll,
            ej.TreeGrid.ToolbarItems.CollapseAll,
	    ej.TreeGrid.ToolbarItems.PdfExport,
            ej.TreeGrid.ToolbarItems.ExcelExport
        ],
            }       
        angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function ($scope) {      
            $scope.toolbarSettings = toolbarSettings;
        });
    </script>   
</body>
{% endhighlight %}
The following screenshot displays the toolbar option in TreeGrid control.

![](Toolbar_images/Toolbar_img1.png)

N> To perform add,edit,delete,cancel,update using Toolbar items we need to enable add/edit/delete using [`editSettings`](https://help.syncfusion.com/api/js/ejtreegrid#members:editsettings "editSettings").
  
## Custom Toolbar Items

CustomToolbarItems allows us to insert custom icons and custom template in TreeGrid toolbar. By using below properties we can customize TreeGrid toolbar as per our requirement.

* **text**- To insert the custom icons in toolbar using CSS class name selector.

* **templateID**-To insert the custom icons in toolbar using script templates. Using this property we can bind HTML elements and other EJ controls to TreeGrid toolbar.

* **tooltipText**-Displays tooltip text for the custom icons. 

To insert EJ Controls in TreeGrid toolbar we need to initiate the control in [`create`](https://help.syncfusion.com/api/js/ejtreegrid#events:create "create") client side event.In [`toolbarClick`](https://help.syncfusion.com/api/js/ejtreegrid#events:toolbarclick "toolbarclick") client side event we can bind actions to the custom toolbar items.

{% highlight html %}
<body ng-controller="TreeGridCtrl">
    <script id="ColumnVisibility" type="text/ng-template">
        <input id="dropdownContainer" />
    </script>                
           <div id="angulartreegrid" ej-treegrid 
                     e-toolbarsettings="toolbarSettings"                    
                     e-create="create"
                     e-toolbarclick="toolbarClick">
            </div>            
    <script>       
        var toolbarSettings =
            {
                showToolbar: true,
                customToolbarItems: [
                            { templateID: "#ColumnVisibility", tooltipText: "Column Visibility" },
                            { text: "Reset", tooltipText: "Reset" }],
            }       
        angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function ($scope) {           
            $scope.toolbarClick= function (args) {
                if (args.itemName == "Reset") {
                    //we can bind the custom actions here
                }
            },
            $scope.create= function (args) {
                //Here we can append custom EJ controls
                $("#dropdownContainer").ejDropDownList({});
            }            
            $scope.toolbarSettings = toolbarSettings;
        });
    </script>
    <style type="text/css" class="cssStyles">
        #angulartreegrid_ColumnVisibility {
            padding-top: 2px;
            padding-bottom: 0px;
        }

        .Reset:before {
            content: "\e677";
        }
    </style>
</body>
	{% endhighlight %}
![](Toolbar_images/Toolbar_img2.png)


