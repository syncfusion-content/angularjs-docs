---
layout: post
title: Columns | TreeGrid | Angular | Syncfusion
description:  Learn here all about columns in Syncfusion Essential Angular TreeGrid control, its elements, and more.
platform: angularJS
control: TreeGrid
documentation: ug
---

# Columns in Angular TreeGrid

Column definitions that is specified in the **e-columns** option, defines how to display, format, and edit data in the **e-datasource** in tree grid control. The values in the **e-datasource** can be mapped to the appropriate column using the **‘field’** property of the corresponding column object.                 

## Formatting

The values in each column can be formatted using the **‘format’** property of column object.                               

The following example shows how to specify the numeric format string to display currency, percentage symbols, and date values in a column.          

{% highlight js %}                    
                                                           
<!doctype html>
<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-columns="columns">
    </div>
    <script>
    var columns = [{
            field: "Percentage",
            headerText: "Percentage",
            format: "{0:P0}"
        },
        {
            field: "Currency",
            headerText: "Currency",
            format: "{0:C2}"
        },
        {
            field: "startDate",
            headerText: "Start Date",
            format: "{0:MM/dd/yyyy}"
        },
        {
            field: "endDate",
            headerText: "End Date",
            format: "{0:MM/dd/yyyy hh:mm:ss}"
        }
    ]
    angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function($scope) {
            //...
            $scope.columns = "columns";
        });
</script>
</body>

{% endhighlight %}

Note: For more numeric format strings, refer to this [link](https://msdn.microsoft.com/library/dwhawy9k(v=vs.100).aspx).

For more date format strings, refer to this [link](https://msdn.microsoft.com/library/az4se3k1(v=vs.100).aspx).                         
               
## Headers

### Header text

Using the **e-columns.headerText** property, you can provide title for a specific column. The following code sample shows how to set header text for the columns.

{% highlight js %}

<!doctype html>
<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-columns="columns">
    </div>
    <script>
        var columns = [{
                field: "taskID",
                headerText: "Task Id"
            },
            {
                field: "taskName",
                headerText: "Task Name"
            },
            {
                field: "startDate",
                headerText: "Start Date"
            },
            {
                field: "endDate",
                headerText: "End Date"
            }
        ]
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.columns = "columns";
            });
    </script>
</body>

{% endhighlight %}

### Text wrapping

When the content exceeds the column width, you can wrap the header text or title of the column using the **e-headertextoverflow** property. By default this property is set to **none**. To enable header text wrapping , set the **e-headertextoverflow** property to **‘wrap’**. The following code sample demonstrates this.

{% highlight js %}

<!doctype html>
<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-headertextoverflow="wrap">        
    </div>
</body>

{% endhighlight %}

### Header Template

Using the **e-columns.headerTemplateID** property, you can specify the script element ID, which contains the JsRender template to the specific column.

The following code sample shows how to set the header template.                 

{% highlight html %}

<body ng-controller="TreeGridCtrl">
    <script type="text/x-jsrender" id="resource">
        <div>
            <div class="name">
                <img src="13.4.0.53/themes/web/images/treegrid/icon-03.png" width="20" height="20" />
            </div>
            <div style="position:relative; top:3px;">
                Resources
            </div>
        </div>
    </script>
    <script type="text/x-jsrender" id="projectName">
        <div>
            <div>
                <img src="13.4.0.53/themes/web/images/treegrid/icon-01.png" width="20" height="20" />
            </div>
            <div style="position:relative; top:3px;">
                Task Name
            </div>
        </div>
    </script>
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-columns="columns">
    </div>
    <script>
        var columns = [{
            field: "taskName",
            editType: "stringedit",
            headerTemplateID: "#projectName"
        }, {
            field: "startDate",
            editType: "datepicker"
        }, {
            field: "resourceId",
            editType: "dropdownedit",
            dropdownData: projectResources,
            headerTemplateID: "#resource"
        }, {
            field: "progress",
            editType: "numericedit"
        }]
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.columns = "columns";
            });
    </script>
</body>
    

{% endhighlight %}

The following screenshot depicts column headers with custom templates.

![Angular TreeGrid Header Template](columns_images/angular-treegrid-header-template.png)

## Frozen Columns

Specific columns can be frozen by enabling the **e-columns.isFrozen** property of the respective column object. The columns that are frozen remains static while scrolling the content horizontally. You can also freeze or unfreeze a column during runtime by selecting Freeze or Unfreeze menu item in the column menu. These set of menu options will be displayed in all the columns when the **e-columns.isFrozen** property is enabled in any of the columns. However, you can control the visibility of these menu options in a particular column by enabling or disabling the **e-columns.allowFreezing** property of that specific column.    

{% highlight js %} 

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-showcolumnchooser="true" e-columns="columns">
    </div>
    <script>
        var columns = [{
                field: "taskID",
                headerText: "ID",
                width: 60,
                isFrozen: true,
                allowFreezing: false
            },
            {
                field: "taskName",
                headerText: "Task Name",
                width: 200,
                isFrozen: true
            },
            {
                field: "startDate",
                headerText: "Start Date"
            },
            {
                field: "endDate",
                headerText: "End Date"
            },
            {
                field: "duration",
                headerText: "Duration"
            },
        ]
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.columns = "columns";
            });
    </script>
</body>

{% endhighlight %}

The following screenshot depicts tree grid with frozen columns.

![Angular TreeGrid Frozen Columns](columns_images/angular-treegrid-frozen-columns.png)

You can also freeze all the preceding columns by choosing *Freeze Preceding Columns* option in the column menu.               

![Angular TreeGrid Freeze Preceding Columns](columns_images/angular-treegrid-freeze-preceding-columns.png)

## Resizing

You can resize the column width to view the hidden text of the cell. This feature can be enabled by setting the **allowColumnResize** property to true.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-allowcolumnresize="true">
    </div>
</body>

{% endhighlight %}

## Column Template

Columns can be customized either by using JsRender templates or by AngularJS templates.

Using the **e-columns.templateID** property, you can specify the script element ID, which contains the template for the column. However, enable the **e-columns.isTemplateColumn** property for the specific column to display the custom template instead of default template.

The following code example shows how to define template for the column.

{% highlight html %}

<body ng-controller="TreeGridCtrl">
    <!--Add  TreeGrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-rowheight="50" e-columns="columns">
    </div>
    <script>
        var columns = [{
                field: "taskID",
                headerText: "Task Id",
                width: "45"
            },
            {
                field: "taskName",
                headerText: "Task Name"
            },
            {
                headerText: "Resource",
                isTemplateColumn: true,
                templateID: "columnTemplate",
                textAlign: "center"
            },
            {
                field: "resourceNames",
                headerText: "Resource Name"
            },
        ]
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.columns = "columns";
            });
    </script>
</body>

{% endhighlight %}

![Angular TreeGrid Comlumn Template](columns_images/angular-treegrid-column-template.png)

## Column Menu

Column menu can be displayed in column header by enabling the **‘e-showcolumnchooser’**.

The following are the items displayed in the column menu:

* **Column Chooser**: Displays all the column names. You can enable or disable a column by selecting or deselecting the respective column name in the column chooser menu.
* **Sort Ascending & Sort Descending**: Sorts the items in the column. These menu options will be displayed only when you set the **e-allowsorting** property to true. To perform multilevel sorting, the **‘e-allowmultisorting’** property should be enabled.               
* **Freeze, Unfreeze & Freeze Preceding Columns**: Freezes or unfreezes the columns. These set of menu options will be displayed in all columns when the **e-columns.isFrozen** property is enabled. However, you can control the visibility of these menu options in a particular column by enabling or disabling the **e-columns.allowFreezing** property of that specific column.                         

{% highlight js %}

<body ng-controller="TreeGridCtrl">                  
    <!--Add  TreeGrid control here-->
    <div id="TreeGridContainer" ej-treegrid 
    //... 
    e-showcolumnchooser="true" 
    e-allowsorting= "true" 
    e-allowmultisorting= "true" 
    e-columns="columns">
    </div>
    <script>
        var columns = [
            // ...  
            {
                field: "duration",
                headerText: "Duration",
                visible: false
            }
            // ...  
        ]
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.columns = "columns";
            });
    </script>
</body>

{% endhighlight %}

![Angular TreeGrid Column Menu](columns_images/angular-treegrid-column-menu.png)

## Changing position of expander column

The position of the expander column, which acts as tree column can be changed using the **‘e-treecolumnindex’** property.

The following code example shows how to change the position of the expander column.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-treecolumnindex="2">
    </div>
</body>

{% endhighlight %}

## Visibility

Columns can be hidden on loading by setting the **‘e-columns.visible’** property to false.

The following code example explains how to hide the fourth column.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  TreeGrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-columns="columns">
    </div>
    <script>
        var columns = [{
                field: "taskID",
                headerText: "Task Id",
                width: "45"
            },
            {
                field: "taskName",
                headerText: "Task Name"
            },
            {
                field: "startDate",
                headerText: "Start Date"
            },
            {
                field: "endDate",
                headerText: "End Date",
                visible: false
            },
            {
                field: "progress",
                headerText: "Progress"
            }
        ]
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.columns = "columns";
            });
    </script>
</body>

{% endhighlight %}

![Angular TreeGrid Visibility](columns_images/angular-treegrid-visibility.png)

## Read-only

A column can be made read-only by setting the **e-columns.allowEditing** property to false.      

Note: By setting columns.allowEditing to false, that specific column alone is made as read-only, and by setting editSettings.allowEditing to false, the entire tree grid is made as read-only.

The following code sample demonstrates this.        

{% highlight js %}

<body ng-controller="TreeGridCtrl">
   <!--Add  TreeGrid control here-->
   <div id="TreeGridContainer" ej-treegrid //... e-columns="columns">
   </div>
   <script>
      var columns = [{
              field: "taskID",
              headerText: "Task Id"
          },
          {
              field: "taskName",
              headerText: "Task Name",
              allowEditing: false
          },
          {
              field: "startDate",
              headerText: "Start Date"
          },
          {
              field: "endDate",
              headerText: "End Date"
          }
      ]
      angular.module('listCtrl', ['ejangular'])
          .controller('TreeGridCtrl', function($scope) {
              //...
              $scope.columns = "columns";
          });
   </script>
</body>

{% endhighlight %}