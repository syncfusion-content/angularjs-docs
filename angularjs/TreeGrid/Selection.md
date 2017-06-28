---
layout: post
title: Selection
description: selection
platform: AngularJS
control: TreeGrid
documentation: ug
---

# Selection

The TreeGrid control provides support for row and cell selections. 

## Row selection

You can enable or disable the row selection in TreeGrid, using `e-allowselection` property. By default row selection is enabled in TreeGrid.
The following code example shows you to disable the row selection in TreeGrid.


{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-allowselection="false">
    </div>
</body>

{% endhighlight %}

The output of the TreeGrid with row selection is as follows.

![](Selection_images/Selection_img1.png)

### Selecting a row at initial load

You can select a row at initial load by setting the index of the row to the `e-selectedrowindex` property.

Find the following code for selecting a row at initial load.


{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-selectedrowindex="3">
    </div>
</body>

{% endhighlight %}

### Multiple row selection

It is also possible to select multiple rows by setting `e-selectionsettings.selectionType` as `multiple`. You can select more than one row by holding down `CTRL` key and to click on the rows. 
The following code example explains how to enable multiple selection in TreeGrid.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-selectionsettings= "selectionSettings"
    >
    </div>
    <script>
         var selectionSettings= {
                     selectionType: "ej.TreeGrid.SelectionType.Multiple"                                 
               }
    angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function($scope) {
            //...
            $scope.selectionSettings = "selectionSettings";
        });
</script>
</body>

{% endhighlight %}

The output of the TreeGrid with multiple row selection is as follows.

![](Selection_images/Selection_img2.png)

To enable multiple selection, you can set `e-selectionsettings.selectionType` property either as `multiple` or enumeration value `ej.TreeGrid.SelectionType.Multiple`.

### Selecting a row programmatically 

You can select a row programmatically by setting the row index value to `e-selectedrowindex` property. 
The following code shows on how to select a row programmatically with button click action,

{% highlight html %}

    <html>
        <body>
        <button id="selectRow">SelectRow</button>
        //...
         <div id="TreeGridContainer" ej-treegrid //...
    >
    </div>
        </body>
    </html>

{% endhighlight %}

{% highlight js %}
    
     $("#selectRow").click(function (args) {
         $("#TreeGridContainer ").ejTreeGrid("option", "selectedRowIndex", 4);           
     })

{% endhighlight %}

## Cell selection

You can select cells in TreeGrid by setting `e-selectionsettings.selectionMode` property as `cell`.
Find the code example below to enable the cell selection in TreeGrid.

{% highlight html %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-selectionsettings= "selectionSettings"
    >
    </div>
    <script>
         var selectionSettings=  {
           selectionMode: "ej.TreeGrid.SelectionType.Cell",                                 
         }
    angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function($scope) {
            //...
            $scope.selectionSettings = "selectionSettings";
        });
</script>
</body>

{% endhighlight %}

The output of the TreeGrid with cell selection is as follows.

![](Selection_images/Selection_img3.png)

### Multiple cell selection

You can also select multiple cell by setting `e-selectionsettings.selectionType` property as `multiple`. 
Multiple selection can be done by holding the `CTRL` key and to click the required cells. 
The following code example shows you to select multiple cells.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-selectionsettings= "selectionSettings"
    >
    </div>
    <script>
         var selectionSettings=  {
            selectionType: "ej.TreeGrid.SelectionType.Multiple",
            selectionMode: "ej.TreeGrid.SelectionType.Cell",
        }
    angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function($scope) {
            //...
            $scope.selectionSettings = "selectionSettings";
        });
</script>
</body>

{% endhighlight %}

The output of the TreeGrid with multiple cell selection is as follows.

![](Selection_images/Selection_img4.png)

### Selecting cells programmatically 

You can select the cells programmatically using `selectCells` public method. Find the code example below for selecting TreeGrid cells programmatically


{% highlight html %}
    <html>
        <body>
         <button id="selectcells">SelectCells</button>
         //...
         <div id="TreeGridContainer" ej-treegrid //... >
         </div>
        </body> 
    </html>
{% endhighlight %}

{% highlight js %}  

     $("#selectcells").click(function (args) {
            //create TreeGrid object
            var TreeGridObj = $("#TreeGridContainer").data("ejTreeGrid");
            cellIndex = [{ rowIndex: 2, cellIndex: 1 }, {rowIndex:3,cellIndex:1}];
            TreeGridObj.selectCells(cellIndex);
     })
{% endhighlight %}

## Checkbox selection

TreeGrid supports checkbox selection and to enable the checkbox selection, you need to set `e-selectionsettings.selectionType` property to `checkbox` and `e-selectionsettings.selectionMode` property as `row`. By default, checkbox column will be displayed as the left most column, on enabling the checkbox selection in TreeGrid.

### Column header checkbox

It is possible to select/unselect all the TreeGrid rows using column header checkbox. To enable this you need to set, `e-selectionsettings.enableSelectAll` property as `true`. The following code snippet explains how to enable the column header checkbox,

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-selectionsettings= "selectionSettings"
    >
    </div>
    <script>
         var selectionSettings=  {
                     selectionType: "ej.TreeGrid.SelectionType.Checkbox",
                     selectionMode: "ej.TreeGrid.SelectionType.Row",
                     enableSelectAll: true,                        
                 },
    angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function($scope) {
            //...
            $scope.selectionSettings = "selectionSettings";
        });
</script>
</body>
{% endhighlight %}

The output of the TreeGrid with checkbox enabled in column header

![](Selection_images/Selection_img5.png)

### Hierarchy selection
It is possible to select the rows hierarchically using checkboxes in TreeGrid by enabling the `e-selectionsettings.enableHierarchySelection` property.
In this selection the hierarchy between the records will be retained, where the child records will get selected on selecting its parent record’s checkbox and parent record checkbox will get selected on checking all of its child items. 

Following code snippet explains on enabling hierarchy selection in TreeGrid.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-selectionsettings= "selectionSettings"
    >
    </div>
    <script>
    var selectionSettings = {
            selectionType: "ej.TreeGrid.SelectionType.Checkbox",
            selectionMode: " ej.TreeGrid.SelectionType.Row",
            enableHierarchySelection: true,
        },
        angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function($scope) {
            //...
            $scope.selectionSettings = "selectionSettings";
        });
</script>
</body>

{% endhighlight %}

The output of the TreeGrid with hierarchy selection enabled

![](Selection_images/Selection_img6.png)

### Checkbox column

It is possible to change the default index of the checkbox column and we can display the checkboxes in any of the existing column. And to enable the checkbox in any of the column, we need to set `showCheckbox` property as true in the column object.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-selectionsettings= "selectionSettings"
    e-columns= "columns"
    >
    </div>
    <script>
    var selectionSettings = {
            selectionType: "ej.TreeGrid.SelectionType.Checkbox",
            selectionMode: " ej.TreeGrid.SelectionType.Row",
        },
        var columns = [{
                field: "taskID",
                headerText: "Task Id",
                editType: "numericedit"
            },
            {
                field: "taskName",
                headerText: "Task Name",
                editType: "stringedit",
                showCheckbox: true
            },
        ]
    angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function($scope) {
            //...
            $scope.selectionSettings = "selectionSettings";
            $scope.columns = "columns";
        });
</script>
</body>
{% endhighlight %}

The output of the TreeGrid with checkbox enabled in task name column.

![](Selection_images/Selection_img7.png)