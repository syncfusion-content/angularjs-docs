---
layout: post
title: Columns
description: columns
platform: Angular-1
control: TreeGrid
documentation: ug
---

# Columns

Column definitions, specified in the **e-columns** option, define how the data in the **e-datasource** have to be displayed, formatted and edited in TreeGrid. The values in the **e-datasource** can be mapped to the appropriate column using the **‘field’** property of the corresponding column object.

## Formatting

The values in each column can be formatted using the **‘format’** property of the column object.

The following example shows how to specify the numeric format string to display currency, percentage symbols and date values in a column,

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

Note: For more numeric format strings, please refer this [link](https://msdn.microsoft.com/library/dwhawy9k(v=vs.100).aspx).

For more date format strings, please refer this [link](https://msdn.microsoft.com/library/az4se3k1(v=vs.100).aspx).

## Headers

### Header text

Using **e-columns.headerText** property, you can provide the title for a specific column. The below code snippet is shows how to set header text for the columns,

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

It is possible to wrap the header text or the title for the column, when the content exceeds the column width using the **e-headertextoverflow** property. By default this property is set to **none**. To enable wrapping of header text, you have to set **e-headertextoverflow** property to **‘wrap’**. The below code snippet demonstrates this,

{% highlight js %}

<!doctype html>
<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-headertextoverflow="wrap">
    </div>
</body>

{% endhighlight %}

### Header Template

Using **e-columns.headerTemplateID** property, you can specify the Id of the script element, which contains the JsRender template, to the specific column.

Following code snippet shows how to set the header template,

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

The below screenshot depicts column headers with custom templates,

![](Columns_images/Columns_img1.png)

## Frozen Columns

Specific columns can be frozen by enabling **e-columns.isFrozen** property of the respective column object. The columns which are frozen remain static while scrolling the content horizontally. You can also freeze or unfreeze a column during runtime, by selecting Freeze or Unfreeze menu item in the column menu. These set of menu options will be displayed in all the columns when **e-columns.isFrozen** property is enabled in any of the columns. However you can control the visibility of these menu options in a particular column by enabling/disabling the **e-columns.allowFreezing** property of that specific column.

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

The below screenshot depicts TreeGrid with frozen columns,

![](Columns_images/Columns_img2.png)

It is also possible to freeze all the preceding columns by choosing *Freeze Preceding Columns* option in the column menu.

![](Columns_images/Columns_img3.png)

## Resizing

You can resize the column width to view the hidden text of the cell. This feature can be enabled by setting **allowColumnResize** property to true.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-allowcolumnresize="true">
    </div>
</body>

{% endhighlight %}

## Column Template

Columns can be customized either by using JsRender templates or by AngularJS templates,

Using **e-columns.templateID** property, you can specify the Id of the script element, which contains the template for the column. However, you need to enable **e-columns.isTemplateColumn** property for the specific column to display the custom template instead of default template.

Following code example show how to define template for the column,

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

![](Columns_images/Columns_img4.png)

## Column Menu

Column menu can be displayed in column header by enabling **‘e-showcolumnchooser’**.

Following are the items displayed in the column menu,

* **Column Chooser** – Display all the column names; you can enable or disable a column by select or deselect the respective column name in the column chooser menu.
* **Sort Ascending & Sort Descending** – Used to sort the items in the column. These menu options will be displayed only when you enable **e-allowsorting** property to true. To perform multilevel sorting, the **‘e-allowmultisorting’** property should be enabled.
* **Freeze, Unfreeze & Freeze Preceding Columns** – Used to freeze or unfreeze the columns. These set of menu options will be displayed in all the columns when **e-columns.isFrozen** property is enabled in any of the columns. However you can control the visibility of these menu options in a particular column by enabling/disabling the **e-columns.allowFreezing** property of that specific column.

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

![](Columns_images/Columns_img5.png)

## Changing position of expander column

The position of the expander column, which acts as tree column, can be changed using the **‘e-treecolumnindex’** property,

Following code example shows how to change the position of the expander column,

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-treecolumnindex="2">
    </div>
</body>

{% endhighlight %}

## Visibility

Columns can be hidden on loading by setting the **‘e-columns.visible’** property as false,

Following code example explains how to hide the fourth column,

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

![](Columns_images/Columns_img6.png)

## Read-only

A column can be made read-only by setting the **e-columns.allowEditing** property as false,

Note: By setting columns.allowEditing as false, that specific column alone is made as read only, and by setting editSettings.allowEditing as false, the entire TreeGrid is made read only.

The below code snippet demonstrates this,

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