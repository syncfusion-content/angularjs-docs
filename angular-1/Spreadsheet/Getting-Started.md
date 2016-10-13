---
title: Getting Started for Angular 1.0 Spreadsheet
description: How to create a Spreadsheet with data source, apply format and export it as excel file.
platform: Angular 1.0
control: Spreadsheet
documentation: Ug
keywords: 
---
# Getting started

This section explains you the steps required to populate the Spreadsheet with data, format, and export it as excel file. This section covers only the minimal features that you need to know to get started with the Spreadsheet.

## Adding Script Reference

Create an HTML page and add the scripts references in the order mentioned in the following code example.

{% highlight html %}

<!DOCTYPE html>
<html  ng-app="defaultApp">
   <head>
    <link rel="stylesheet" href="http://cdn.syncfusion.com/14.3.0.49/js/web/bootstrap-  theme/ej.web.all.min.css" />
    <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
    <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js"></script>
    <script src="https://code.angularjs.org/1.4.0-rc.2/angular.min.js"></script>
    <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js" type="text/javascript"></script>
    <script src="http://js.syncfusion.com/demos/web/scripts/xljsondata.js" type="text/javascript"></script>
    <script src="https://code.angularjs.org/1.4.0-rc.2/angular-route.min.js"></script>
    <script src="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.widget.angular.min.js"></script>
   </head>
   <body>
   </body>
</html>

{% endhighlight %}

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use[CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

N> For details about Spreadsheet internal and external dependencies refer following [`link`](http://help.syncfusion.com/js/spreadsheet/dependencies "link")

## Initialize Spreadsheet

Add a `div`container to render the Spreadsheet.

{% highlight html %}

<!DOCTYPE html>
<html ng-app="defaultApp">  
    <body ng-controller="SpreadsheetCtrl">
          <div id="Spreadsheet" ej-spreadsheet></div>
    </body>
</html>

{% endhighlight %}

Initialize the Spreadsheet by using the ejSpreadsheet method. The Spreadsheet is rendered based on default `width` and `height`. You can also customize the Spreadsheet dimension by setting the [`width`](http://help.syncfusion.com/js/api/ejspreadsheet#members:scrollsettings-width "width") and [`height`](http://help.syncfusion.com/js/api/ejspreadsheet#members:scrollsettings-height "height") property in [`scrollSettings`](http://help.syncfusion.com/js/api/ejspreadsheet#members:scrollsettings "scrollSettings").

{% highlight html %}

<!DOCTYPE html>
<html>    
   <body>
      <script>
      var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
      syncApp.controller('SpreadsheetCtrl', function ($scope,$rootScope) {
      });
      </script>
    </body>
</html>

{% endhighlight %}

Now, the Spreadsheet is rendered with default row and column count.

![](Getting-Started_images/Getting-Started_img1.png)

## Populate Spreadsheet with data

Now, this section explains how to populate JSON data to the Spreadsheet. You can set`dataSource`property in `sheet`settings to populate JSON data in Spreadsheet.

{% highlight html %}

<body ng-controller="SpreadsheetCtrl">
    <div id="Spreadsheet" ej-spreadsheet e-sheets="sheetData"></div>
</body>
   <script>
    var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
    syncApp.controller('SpreadsheetCtrl', function ($scope,$rootScope) {
    $scope.sheetData = [{ rangeSettings: [{ dataSource: window.defaultData, startCell:'A1' }] }];
    });
   </script>
   
{% endhighlight %}

![](Getting-Started_images/Getting-Started_img2.png)

N> For more details about `data binding` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/data-binding "link")

## Apply Conditional Formatting

Conditional formatting helps you to apply formats to a cell or range with certain color based on the cells values. You can use [`allowConditionalFormats`](http://help.syncfusion.com/js/api/ejspreadsheet#members:allowconditionalformats "allowConditionalFormats") property to enable/disable Conditional formats.

To apply conditional formats for a range use `cFormatRule` property. The following code example illustrates this,

{% highlight html %}

<body ng-controller="SpreadsheetCtrl">
    <div id="Spreadsheet" ej-spreadsheet e-sheets="sheetData" e-loadcomplete="loadComplete"></div>
</body>
   <script>
    var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
    syncApp.controller('SpreadsheetCtrl', function ($scope,$rootScope) {
	$scope.loadComplete = loadComplete;
     });
     function loadComplete(args) {	  
      this.XLCFormat.setCFRule({ "action": "greaterthan", "inputs": ["10"], "color": "redft", "range": "D2:D8" });
     }
   </script>
   
{% endhighlight %}

![](Getting-Started_images/Getting-Started_img3.png)

N> For more details about `Conditional Formatting` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/data-presentation#conditional-formatting "link")

## Export Spreadsheet as Excel File

The Spreadsheet can save its data, style, format into an excel file. To enable save option in Spreadsheet set [`allowExporting`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings-allowexporting "allowExporting") option in [`exportSettings`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings "exportSettings") as `true`. Since Spreadsheet uses server side helper to save documents set [`excelUrl`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings-excelurl "excelUrl") in [`exportSettings`](http://help.syncfusion.com/js/api/ejspreadsheet#members:exportsettings "exportSettings") option. The following code example illustrates this,

{% highlight html %}

<body ng-controller="SpreadsheetCtrl">
    <div id="Spreadsheet" ej-spreadsheet e-sheets="sheetData" e-exportsettings-excelurl="excelurl"></div>
</body>
<script>
    var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
    syncApp.controller('SpreadsheetCtrl', function ($scope,$rootScope) {
    $scope.excelurl = "http://js.syncfusion.com/demos/ejservices/api/JSXLExport/ExportToExcel";
      });
</script>

{% endhighlight %}

Use shortcut `Ctrl + S` to save Spreadsheet as excel file.

N> 1. For more details about `Export` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/open-and-save#save "link")
N> 2. For more details about `Server Configuration` refer following [`link`](http://help.syncfusion.com/js/spreadsheet/open-and-save#server-configuration "link")
