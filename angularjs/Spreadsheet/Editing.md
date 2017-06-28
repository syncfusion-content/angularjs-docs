---
layout: post
title: Editing with Spreadsheet widget for Syncfusion Essential JS
description: How to Edit the Spreadsheet 
platform: AngularJS
control: Spreadsheet
documentation: ug
---

# Editing 

You can edit the contents of a cell directly in the cell. You can also do this by typing in the formula bar. When you edit the cell, Spreadsheet is operating in edit mode. In editing mode formatting options are not available. You can use `e-allowediting` property to enable/disable editing feature.

N> By default `e-allowediting` property is set to true.

## Edit cell content

You can perform this by one of the following ways,

* Double click on the cell to perform editing. This starts the edit mode and positions the cursor at the end of the cell.
* Press F2 Key to edit the active cell.
* Use Formula bar to perform editing.
* Use Backspace and Delete Key to delete the contents of a cell.
* Use "Alt + Enter" keys to perform multi line editing.
* Using [`editCell`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xledit-editcell "editCell") method.

## Save cell content

You can do this by one of the following ways,

* Perform mouse click on any other cell other than the current editing cell.
* Perform Enter/Tab key press on the cell.
* Using [`saveCell`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xledit-savecell "saveCell") method.

N> Edited cells are automatically formatted (right/left/center/Number Formatting) based on cell values.

The following code example describes the above behavior.

{% highlight html %}
<body ng-controller="SpreadsheetCtrl">
     <div id="Spreadsheet" ej-spreadsheet e-loadcomplete="loadComplete" e-sheets="sheetData"></div>
</body>
{% endhighlight %}

{% highlight javascript %}
var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
// the datasource "window.defaultData" is referred from 'http://js.syncfusion.com/demos/web/scripts/xljsondata.min.js'
    syncApp.controller('SpreadsheetCtrl', function ($scope,$rootScope) {
         $scope.sheetData = [{
                rangeSettings: [{ dataSource: window.defaultData }],
            }];
            $scope.loadComplete = loadComplete;
    });
function loadComplete(args) {
    if(!this.isImport) {
        this.XLEdit.editCell(3, 0, true); // if true, it maintains the existing data otherwise it clears the data.
        //this.XLEdit.saveCell();
    }
}
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img1.png)

## Read-Only cells

You can restrict/prevent the editing in the specified range. You can use `e-allowlockCell` property to enable/disable the lock cells. You can do using following ways,

* Using [`lockCells`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:lockcells "lockCells") method to lock the specified range. Then you need to protect the sheet using [`protectSheet`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:protectsheet "protectSheet") method to restrict the editing.
* Using "Lock Cells" option under Changes group of REVIEW tab in ribbon. Then Using "Protect Sheet" option under Changes group of REVIEW tab in ribbon to restrict editing.

The following code example describes the above behavior.

{% highlight html %}
<body ng-controller="SpreadsheetCtrl">
     <div id="Spreadsheet" ej-spreadsheet e-loadcomplete="loadComplete" e-sheets="sheetData" e-allowlockcell="true"></div>
</body>
{% endhighlight %}

{% highlight javascript %}
var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
// the datasource "window.defaultData" is referred from 'http://js.syncfusion.com/demos/web/scripts/xljsondata.min.js'
    syncApp.controller('SpreadsheetCtrl', function ($scope,$rootScope) {
         $scope.sheetData = [{
                rangeSettings: [{ dataSource: window.defaultData }],
            }];
            $scope.loadComplete = loadComplete;
    });
function loadComplete(args) {
    if(!this.isImport) {
        this.protectSheet(false);
        this.lockCells("A1:A5", true);
        this.protectSheet(true);
    }
}
{% endhighlight %}

The following output is displayed as a result of editing in Spreadsheet which is rendered with above code example.

![](Editing_images/Editing_img2.png)

## Events

The following events will trigger when editing and saving the cell. 

* [`cellEdit`](http://help.syncfusion.com/api/js/ejspreadsheet#events:celledit"cellEdit") - Triggered when the cell is edited.
* [`cellSave`](http://help.syncfusion.com/api/js/ejspreadsheet#events:cellsave"cellSave") - Triggered when save the edited cell.

## Data binding

You can bind the data to Spreadsheet using data manager. You can refer [`Data Binding`](http://help.syncfusion.com/angular-1/spreadsheet/data-binding "Data Binding") to know more about this. You can use [`saveBatchChanges`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:savebatchchanges "saveBatchChanges") method to update the changes in server.  

The following code example describes the above behavior.

{% highlight html %}
<body ng-controller="SpreadsheetCtrl">
     <div id="Spreadsheet" ej-spreadsheet e-loadcomplete="loadComplete" e-sheets="sheetData"></div>
</body> 
{% endhighlight %}

{% highlight javascript %}
var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
    var dataManager = ej.DataManager({
                url: "Home/Default",
                adaptor: "UrlAdaptor",
                batchUrl: "Home/BatchUpdate" 
                //  "Home/Default" and "Home/BatchUpdate" referred from the MVC controller.
            });
    syncApp.controller('SpreadsheetCtrl', function ($scope,$rootScope) {
         $scope.sheetData = [{
                        rangeSettings: [{ dataSource: dataManager }],
            }];
            $scope.loadComplete = loadComplete;
    });
function loadComplete(args) {
    if(!this.isImport) {
        this.XLEdit.updateValue("I2", "amazon");
        this.XLEdit.updateValue("J2", "flipkart");
        this.saveBatchChanges(this.getActiveSheetIndex());
    }
}
{% endhighlight %}

The code snippets to specify the BatchUpdate in MVC controller are as follows,

{% highlight c# %}

public ActionResult BatchUpdate( List<ItemDetail> changed,  List<ItemDetail> added,  List<ItemDetail> deleted, string action, string key)
        {
            //Save the batch changes
        }
{% endhighlight %}