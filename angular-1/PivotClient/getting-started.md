---
title: Getting started with PivotClient component	
description: Rendering a basic PivotClient with local data
platform: Angular-1
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Getting Started

The AngularJS directives are usually included within the `ej.widget.angular.min.js` file and all these directives are usually packed together in a common module known as `ejangular`. For basic details on how to configure Syncfusion widgets in AngularJS framework, refer [here](https://help.syncfusion.com/js/angularjs).

To get start with the PivotClient control in AngularJS framework, the following list of external dependencies are mandatory, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates
* [AngularJS](https://angularjs.org/)

The external AngularJS script file `angular.min.js` can also be accessed from the following installed location. 

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\external

An another mandatory script is `ej.widget.angular.min.js`, which can be accessed from the below specified location.

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\common

## Script/CSS Reference

Create a new HTML file and include the below initial code.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta charset="utf-8" />
        <title> </title>
    </head>
    <body>
    </body>
</html>

{% endhighlight %}

Refer the CSS file from the specific theme folder to your HTML file within the head section as shown below. Refer the built-in available themes from [here](https://help.syncfusion.com/js/theming-in-essential-javascript-components).

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - PivotClient</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
</head>

{% endhighlight %}

Refer the [CDN](https://help.syncfusion.com/js/cdn) script files with other required external dependencies.

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - PivotClientt</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
</head>

{% endhighlight %}

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use[CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

## Relational

This section covers the information that you need to know to populate a simple PivotClient with Relational data source.

### Control Initialization

Create the PivotClient control using `ej-pivotclient` directive and define all its other properties prefixed with `e-` as shown in the below code.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotClientApp">

<body>
    <div ng-controller="PivotClientCtrl">
        <div id="PivotClient1" ej-pivotclient e-datasource="dataSource" e-customobject="customObject"
            e-rendersuccess='setChartProperties' e-beforeexport="Export" e-savereport="saveReportSettings" e-loadreport="saveReportSettings" e-fetchReport="saveReportSettings" e-title="Relational Browser" style="min-height: 275px;
            min-width: 525px;" />
    </div>
</body>

</html>

{% endhighlight %}

### Populate PivotClient with data

Let us now see how to populate the PivotClient control using a sample JSON data as shown below.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotClientApp">
<head> <!-- Dependency file references --> </head>
<body>
    <div ng-controller="PivotClientCtrl">
        <div id="PivotClient1" ej-pivotclient e-datasource="dataSource" e-customobject="customObject"
            e-rendersuccess='setChartProperties' e-beforeexport="Export" e-savereport="saveReportSettings" e-loadreport="saveReportSettings" e-fetchReport="saveReportSettings" e-title="Relational Browser" style="min-height: 275px;
            min-width: 525px;" />
    </div>
<script>
    angular.module('PivotClientApp', ['ejangular']).controller('PivotClientCtrl', function ($scope) {
        $scope.pivot_dataset = [
                        { Amount: 100, Country: "Canada", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Alberta" },
                        { Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Van", Quantity: 3, State: "British Columbia" },
                        { Amount: 300, Country: "Canada", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Brunswick" },
                        { Amount: 150, Country: "Canada", Date: "FY 2008", Product: "Bike", Quantity: 3, State: "Manitoba" },
                        { Amount: 200, Country: "Canada", Date: "FY 2006", Product: "Car", Quantity: 4, State: "Ontario" },
                        { Amount: 100, Country: "Canada", Date: "FY 2007", Product: "Van", Quantity: 1, State: "Quebec" },
                        { Amount: 200, Country: "France", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Charente-Maritime" },
                        { Amount: 250, Country: "France", Date: "FY 2006", Product: "Van", Quantity: 4, State: "Essonne" },
                        { Amount: 300, Country: "France", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Garonne (Haute)" },
                        { Amount: 150, Country: "France", Date: "FY 2008", Product: "Van", Quantity: 2, State: "Gers" },
                        { Amount: 200, Country: "Germany", Date: "FY 2006", Product: "Van", Quantity: 3, State: "Bayern" },
                        { Amount: 250, Country: "Germany", Date: "FY 2007", Product: "Car", Quantity: 3, State: "Brandenburg" },
                        { Amount: 150, Country: "Germany", Date: "FY 2008", Product: "Car", Quantity: 4, State: "Hamburg" },
                        { Amount: 200, Country: "Germany", Date: "FY 2008", Product: "Bike", Quantity: 4, State: "Hessen" },
                        { Amount: 150, Country: "Germany", Date: "FY 2007", Product: "Van", Quantity: 3, State: "Nordrhein-Westfalen" },
                        { Amount: 100, Country: "Germany", Date: "FY 2005", Product: "Bike", Quantity: 2, State: "Saarland" },
                        { Amount: 150, Country: "United Kingdom", Date: "FY 2008", Product: "Bike", Quantity: 5, State: "England" },
                        { Amount: 250, Country: "United States", Date: "FY 2007", Product: "Car", Quantity: 4, State: "Alabama" },
                        { Amount: 200, Country: "United States", Date: "FY 2005", Product: "Van", Quantity: 4, State: "California" },
                        { Amount: 100, Country: "United States", Date: "FY 2006", Product: "Bike", Quantity: 2, State: "Colorado" },
                        { Amount: 150, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "New Mexico" },
                        { Amount: 200, Country: "United States", Date: "FY 2005", Product: "Bike", Quantity: 4, State: "New York" },
                        { Amount: 250, Country: "United States", Date: "FY 2008", Product: "Car", Quantity: 3, State: "North Carolina" },
                        { Amount: 300, Country: "United States", Date: "FY 2007", Product: "Van", Quantity: 4, State: "South Carolina" }
        ];
        $scope.dataSource = {
            data: $scope.pivot_dataset,
            rows: [
                {
                    fieldName: "Product",
                    fieldCaption: "Product"
                }
            ],
            columns: [
                {
                    fieldName: "Country",
                    fieldCaption: "Country"
                }
            ],
            values: [
                {
                    fieldName: "Amount",
                    fieldCaption: "Amount"
                }
            ]
        };
 
        $scope.customObject = { Language: "en-US" };
    });
    function setChartProperties(args) {
        this.element.find(".titleText").remove();
        this.model.load = "loadTheme";
        if (args._successAction == undefined || args._successAction == "Filter") {
            this._pivotChart.model.legend.rowCount = 2;
            this._pivotChart.model.primaryXAxis = { title: { text: "Fiscal Year" }, labelRotation: 270 };
            this._pivotChart.model.primaryYAxis = { title: { text: "Internet Sales Amount" } };
        }
    }
    function Export(args) {
        args.url = window.baseurl + "api/JSPivotClientExport/ExportPivotClient";
    }
    function saveReportSettings(args) {
        if (args.fetchReportSetting)
            args.fetchReportSetting.url = window.baseurl + "api/OlapClient/FetchReportListFromDB";
        else if (args.loadReportSetting)
            args.loadReportSetting.url = window.baseurl + "api/OlapClient/LoadReportFromDB";
        else
            args.saveReportSetting.url = window.baseurl + "api/OlapClient/SaveReportToDB";
        return args;
    }
</script>
</body>

</html>

{% endhighlight %}

Now, PivotClient is rendered with PivotChart and PivotGrid with "Product" field in Row, "Country" field in Column and "Amount" field in Value section.

![](getting-started_images/purejs.png)

## OLAP

This section covers the information that you need to know to populate a simple PivotClient with OLAP data source.

### Control Initialization

Create the PivotClient control using `ej-pivotclient` directive and define all its other properties prefixed with `e-` as shown in the below code.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotClientApp">

<body>
    <div ng-controller="PivotClientCtrl">
        <div id="PivotClient1" ej-pivotclient e-datasource="dataSource" e-customobject="customObject"
            e-rendersuccess='setChartProperties' e-title="OLAP Browser" e-savereport="saveReportSettings" e-loadreport="saveReportSettings" e-fetchReport="saveReportSettings" e-beforeexport="Export" style="min-height: 275px;
            min-width: 525px;" />
    </div>
</body>

</html>

{% endhighlight %}

### Populate PivotClient with data

Initializes the OLAP datasource for PivotClient control as shown below.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotClientApp">
<head> <!-- Dependency file references --> </head>
<body>
    <div ng-controller="PivotClientCtrl">
        <div id="PivotClient1" ej-pivotclient e-datasource="dataSource" e-customobject="customObject"
            e-rendersuccess='setChartProperties' e-title="OLAP Browser" e-savereport="saveReportSettings" e-loadreport="saveReportSettings" e-fetchReport="saveReportSettings" e-beforeexport="Export" style="min-height: 275px;
            min-width: 525px;" />
    </div>
<script>
    angular.module('PivotClientApp', ['ejangular']).controller('PivotClientPivotCtrl', function ($scope) {
        $scope.datasource = {
            data: "http://bi.syncfusion.com/olap/msmdpump.dll;Locale identifier=1033;", //data
            catalog: "Adventure Works DW 2008 SE",
            cube: "Adventure Works",
            rows: [
                {
                    fieldName: "[Customer].[Customer Geography]"
                }
            ],
            columns: [
                {
                    fieldName: "[Date].[Fiscal]"
                }
            ],
            values: [
                {
                    measures: [
                        {
                            fieldName: "[Measures].[Customer Count]",
                        }                    
                    ],
                    axis: "columns"
                }
            ]
        };
        $scope.customObject = { Language: "en-US" };
        $scope.dataSource = $scope.datasource;
    });
    function setChartProperties(args) {
        this.element.find(".titleText").remove();
        this.model.load = "loadTheme";
        if (args._successAction == undefined || args._successAction == "Filter") {
            this._pivotChart.model.legend.rowCount = 2;
            this._pivotChart.model.primaryXAxis = { title: { text: "Fiscal Year" }, labelRotation: 270 };
            this._pivotChart.model.primaryYAxis = { title: { text: "Customer Count" } };
        }
    }
    function Export(args) {
        args.url = window.baseurl + "api/JSPivotClientExport/ExportPivotClient";
    }
    function saveReportSettings(args) {
        if (args.fetchReportSetting)
            args.fetchReportSetting.url = window.baseurl + "api/OlapClient/FetchReportListFromDB";
        else if (args.loadReportSetting)
            args.loadReportSetting.url = window.baseurl + "api/OlapClient/LoadReportFromDB";
        else
            args.saveReportSetting.url = window.baseurl + "api/OlapClient/SaveReportToDB";
        return args;
    }
</script>
</body>

</html>

{% endhighlight %}

The above code will generate a simple PivotClient with internet sales amount over a period of fiscal years across different customer geographic locations.

![](getting-started_images/Olap.png)