---
layout: post
title: Selection
description: selection
platform: AngularJS
control: TreeGrid
documentation: ug
---

# Selection

The tree grid control provides support for row and cell selections.                  

## Row selection

You can enable or disable the row selection in tree grid using the `e-allowselection` property. By default, row selection is enabled in tree grid.
The following code example shows how to disable the row selection in tree grid.                                        


{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-allowselection="false">
    </div>
</body>

{% endhighlight %}

The output of the tree grid with row selection is as follows:

![](Selection_images/Selection_img1.png)

### Selecting a row at initial load

You can select a row at initial load by setting the index of row to the `e-selectedrowindex` property. This is demonstrated as follows.
                     


{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... e-selectedrowindex="3">
    </div>
</body>

{% endhighlight %}

### Multiple row selection

You can also select multiple rows by setting the `e-selectionsettings.selectionType` to `multiple`. More than one row can be selected by holding down `CTRL` key and clicking the rows.
The following code example explains how to enable multiple selection in tree grid.               

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

The output of the tree grid with multiple row selection is as follows:

![](Selection_images/Selection_img2.png)

To enable multiple selection, set the `e-selectionsettings.selectionType` property to `multiple` or enumeration value `ej.TreeGrid.SelectionType.Multiple`.      

### Selecting a row programmatically 

You can select a row programmatically by setting the row index value to the `e-selectedrowindex` property.                             
The following code shows how to select a row programmatically with button click action.       

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

You can select cells in tree grid by setting the `e-selectionsettings.selectionMode` property to `cell`.
The following code sample helps you to enable the cell selection in tree grid.                                                    

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

The output of the tree grid with cell selection is as follows:

![](Selection_images/Selection_img3.png)

### Multiple cell selection

You can also select multiple cells by setting the `e-selectionsettings.selectionType` property to `multiple`. 
Multiple selection can be done by holding the `CTRL` key and clicking required cells. 
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

The output of the tree grid with multiple cell selection is as follows:

![](Selection_images/Selection_img4.png)

### Selecting cells programmatically 

You can select the cells programmatically using the `selectCells` public method. This is demonstrated as follows.


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

     $("#selectCells").click(function (args) {
            //create TreeGrid object
            var TreeGridObj = $("#TreeGridContainer").data("ejTreeGrid");
            cellIndex = [{ rowIndex: 2, cellIndex: 1 }, {rowIndex:3,cellIndex:1}];
            TreeGridObj.selectCells(cellIndex);
     })
{% endhighlight %}

## Checkbox selection

Tree grid supports checkbox selection. To enable the checkbox selection, set the `e-selectionsettings.selectionType` property to `checkbox` and the `e-selectionsettings.selectionMode` property to `row`. When checkbox selection is enabled, the checkbox column will be displayed as the left most column by default.
### Column header checkbox

You can select or unselect all the tree grid rows using column header checkbox. To enable this, set the `e-selectionsettings.enableSelectAll` property to `true`. The following code sample explains how to enable the column header checkbox.

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

The output of the tree grid with checkbox enabled in column header is as follows:

![](Selection_images/Selection_img5.png)

### Hierarchy selection
You can select the rows hierarchically using checkboxes in tree grid by enabling the `e-selectionsettings.enableHierarchySelection` property.
In this selection the hierarchy between the records will be retained, where the child records are selected by selecting its parent record’s checkbox and parent record checkbox is selected by checking all of its child items.                                           

The following code sample explains enabling hierarchy selection in tree grid.             

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

The output of the tree grid with hierarchy selection enabled is as follows:

![](Selection_images/Selection_img6.png)

### Checkbox column

You can change the default index of the checkbox column and display the checkboxes in any of the existing column. To enable the checkbox in any of the column, set the  `showCheckbox` property to true in the column object.

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

The output of the tree grid with checkbox enabled in task name column is as follows:

![](Selection_images/Selection_img7.png)