---
layout: post
title: Selection with Grid widget for Syncfusion Essential AngularJS
description: How to enable selection and its functionalities
platform: AngularJS
control: Grid
documentation: ug
--- 
# Selection

Selection provides an interactive support to highlight the row, cell, or column that you select. Selection can be done through simple mouse down or keyboard interaction. To enable selection, set the [`e-allowselection`](http://help.syncfusion.com/api/js/ejgrid#members:allowselection "allowSelection") to `true`.          

## Types of Selection

Two types of selections available in grid are:                              

1. Single 
2. Multiple 

### Single Selection

Single selection is an interactive support to select a specific row, cell, or column in grid by mouse or keyboard interactions. To enable single selection, set the [`e-selectiontype`](http://help.syncfusion.com/api/js/ejgrid#members:selectiontype "selectionType") property to `single` and also set the [`e-allowselection`](http://help.syncfusion.com/api/js/ejgrid#members:allowselection "allowSelection") property to `true`.                                                               

### Multiple Selections

Multiple selections is an interactive support to select a group of rows, cells, or columns in grid by mouse or keyboard interactions. To enable multiple selections, set the [`e-selectiontype`](http://help.syncfusion.com/api/js/ejgrid#members:selectiontype "selectionType") property to `multiple` and also set the [`e-allowselection`](http://help.syncfusion.com/api/js/ejgrid#members:allowselection "allowSelection") property to `true`.        

## Row Selection

Row selection is enabled by setting the [`selectionMode`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings-selectionmode "selectionMode") property of the [`e-selectionsettings`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings "selectionSettings") as `row`. For random row selection, press **"Ctrl + mouse left"** click and for continuous row selection press **"Shift + mouse left"** click the grid rows. To unselect selected rows, press **"Ctrl + mouse left"** click the selected row.

The following code example describes the previous behavior.

{% highlight html %}
 <div ng-controller="rowSelectionCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowselection="true" e-selectionsettings="selectionMode" e-selectiontype="multiple">   
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="ShipCity"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
           </div>
     </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
    syncApp.controller('rowSelectionCtrl', function ($scope,$rootScope) {
       //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
         $scope.data = window.gridData;
		 $scope.selectionMode = { selectionMode: ["row"] };
      });
{% endhighlight %}

The following output is displayed as a result of previous code example:                 

![](selection_images/selection_img1.png)


## Cell Selection

Cell selection is enabled by setting [`selectionMode`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings-selectionmode "selectionMode") property of [`e-selectionsettings`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings "selectionSettings") as `cell`. For random cell selection, press **"Ctrl + mouse left"** click and for continuous cell selection, press **"Shift + mouse left"** click on the grid cells. To unselect the cells, press **"Ctrl + mouse left"** on selected cell click.

The following code example describes the previous behavior.

{% highlight html %}
 <div ng-controller="cellSelectionCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowselection="true" e-selectionsettings="selectionMode" e-selectiontype="multiple">
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="ShipCity"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
          </div>
     </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
     syncApp.controller('cellSelectionCtrl', function ($scope,$rootScope) {
       //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        $scope.data = window.gridData;
		$scope.selectionMode = { selectionMode: ["cell"] };
      });
{% endhighlight %}


The following output is displayed as a result of previous code example:              

![](selection_images/selection_img2.png)

## Column Selection

The [Column selection](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings-selectionmode "Column selection") can be enabled by setting the [`selectionMode`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings-selectionmode "selectionMode") property of the [`e-selectionsettings`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings "selectionSettings") as `column`. For random column selection, press **"Ctrl + mouse left click"** and for continuous column selection, press **"Shift + mouse left click"** on the top of the column header. To unselect selected columns, press **"Ctrl + mouse left click"** on top of the selected column header.

The following code example describes the previous behavior.                                      

{% highlight html %}
<div ng-controller="columnSelectionCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowselection="true" e-selectionsettings="selectionMode" e-selectiontype="multiple">
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="ShipCity"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
          </div>
     </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
      syncApp.controller('columnSelectionCtrl', function ($scope,$rootScope) {
       //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            $scope.data = window.gridData;
		    $scope.selectionMode = { selectionMode: ["column"] };
      });
{% endhighlight %}

The following output is displayed as a result of previous code example:                      

![](selection_images/selection_img4.png)                                                                                                                               


## Touch options

While using grid in the [touch](http://help.syncfusion.com/api/js/ejgrid#members:enabletouch "touch") device environment, there is an option for multi selection through single tap on the row and it will show a popup with multi-selection symbol. Single tap the icon to enable multi selection.                       

The following code example describes the previous behavior. 

{% highlight html %}
<div ng-controller="selectListCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-enabletouch="true" e-allowselection="true" e-selectiontype="multiple">                     
          <div e-columns>
             <div e-column e-field="OrderID" ></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="ShipCity"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>                                                                                     
          </div>
     </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
      syncApp.controller('selectListCtrl', function ($scope,$rootScope) {
       //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        $scope.data = window.gridData;
      });
{% endhighlight %}

The following output is displayed as a result of the previous code example:

![](selection_images/selection_img5.png)


## Toggle Selection

The Toggle selection allows you to perform selection and unselection of the particular row, cell or column. To enable toggle selection, set the [`enableToggle`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings-enabletoggle "enableToggle") property of the [`e-selectionsettings`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings "selectionSettings") to `true`. If you click the selected row, cell, or column then it will be unselected and vice versa. 

N> To clear the multi selection after it has been enabled, click the any selected row (without pressing Ctrl key); it will clear the multi selection. To deselect the row, click the same row after the multi selection has been cleared.               
The following code example describes the previous behavior.    

{% highlight html %}
<div ng-controller="toggleListCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowselection="true" e-selectionsettings="Settings">
          <div e-columns>
             <div e-column e-field="OrderID" ></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="ShipCity"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
          </div>
     </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
      syncApp.controller('toggleListCtrl', function ($scope,$rootScope) {
       //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        $scope.data = window.gridData;
		$scope.Settings = {enableToggle: true };
      });
{% endhighlight %}


## Drag Selection

The Drag selection allows you to perform selection of the particular rows or cells by performing mouse dragging.  To enable drag selection, set [`allowDragSelection`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings-allowDragSelection "allowDragSelection") property of the [`e-selectionsettings`](http://help.syncfusion.com/api/js/ejgrid#members:selectionsettings "selectionSettings") to `true`. Now you can select the cells or rows in the Grid by dragging the mouse. 

N> Set the [`e-selectiontype`](http://help.syncfusion.com/api/js/ejgrid#members:selectiontype "selectionType") property to `multiple` to select multiple cells in Grid by mouse dragging. 

The following code example describes the previous behavior. 

{% highlight html %}
<div ng-controller="toggleListCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowselection="true" e-selectionsettings="Settings" e-selectiontype="multiple">
          <div e-columns>
             <div e-column e-field="OrderID" ></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="ShipCity"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
          </div>
     </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
      syncApp.controller('toggleListCtrl', function ($scope,$rootScope) {
       //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        $scope.data = window.gridData;
		$scope.Settings = {selectionMode: ["cell"], allowDragSelection: true };
      });
{% endhighlight %}

The following output is displayed as a result of previous code example: 

![](selection_images/Selection_img7.png)
