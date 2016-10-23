---
title: Getting started with PivotGauge component	
description: Rendering a basic PivotGauge with local data
platform: Angular 1.0
control: PivotGauge
documentation: ug
keywords: ejPivotGauge, PivotGauge, PivotGauge widget, js PivotGauge 
---

# Getting Started

The AngularJS directives are usually included within the `ej.widget.angular.min.js` file and all these directives are usually packed together in a common module known as `ejangular`. For basic details on how to configure Syncfusion widgets in AngularJS framework, refer [here](https://help.syncfusion.com/js/angularjs).

To get start with the PivotGauge control in AngularJS framework, the following list of external dependencies are mandatory, 

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
    <title>Getting Started - PivotGauge</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
</head>

{% endhighlight %}

Refer the [CDN](https://help.syncfusion.com/js/cdn) script files with other required external dependencies.

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - PivotGauge</title>
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

This section covers the information that you need to know to populate a simple PivotGauge with Relational data source.

### Control Initialization

Create the PivotGauge control using `ej-PivotGauge` directive and define all its other properties prefixed with `e-` as shown in the below code.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotGaugeApp">

<body>
    <div ng-controller="PivotGaugeCtrl">
        <div id="PivotGauge1" ej-pivotgauge e-dataSource="dataSource" e-enabletooltip="enableTooltip" e-rowscount="rowsCount"
        e-columnscount="columnsCount" e-scales="scales" e-load="loadGaugeTheme" e-backgroundcolor="backgroundColor" e-labelFormatSettings="labelFormatSettings"
        style="min-height: 290px; height: 338px; width: 100%; overflow: auto; position:relative;" />
    </div>
</body>

</html>

{% endhighlight %}

### Populate PivotGauge with data

Let us now see how to populate the PivotGauge control using a sample JSON data as shown below.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotGaugeApp">
<head> <!-- Dependency file references --> </head>
<body>
    <div ng-controller="PivotGaugeCtrl">
        <div id="PivotGauge1" ej-pivotgauge e-dataSource="dataSource" e-enabletooltip="enableTooltip" e-rowscount="rowsCount"
            e-columnscount="columnsCount" e-scales="scales" e-load="loadGaugeTheme" e-backgroundcolor="backgroundColor" e-labelFormatSettings="labelFormatSettings"
            style="min-height: 290px; height: 338px; width: 100%; overflow: auto; position:relative;" />
    </div>
<script>
    var pivot_dataset = [
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
    var dataSource = {
            data: pivot_dataset,
            rows: [
                {
	                fieldName: "Country",
	                fieldCaption: "Country"
                },
                {
	                fieldName: "State",
	                fieldCaption: "State"
                }
            ],
            columns: [
                { 
	                fieldName: "Product",
	                fieldCaption: "Product"
                }
            ],
            values: [
                {
	                fieldName: "Amount",
	                fieldCaption: "Amount"
                },
                {
	                fieldName: "Quantity",
	                fieldCaption: "Quantity"
                }
            ]
    };

    var scale = [{
            showRanges: true,
            radius: 150, showScaleBar: true, size: 1,
            border: {
                width: 0.5
            },
            showIndicators: true, showLabels: true,
            pointers: [{
                showBackNeedle: true,
                backNeedleLength: 20,
                length: 125,
                width: 7
            },
            {
                type: "marker",
                markerType: "diamond",
                distanceFromScale: 5,
                placement: "center",
                backgroundColor: "#29A4D9",
                length: 25,
                width: 15
        }],
        ticks: [{
            type: "major",
            distanceFromScale: 2,
            height: 16,
            width: 1, color: "#8c8c8c"
        }, {
            type: "minor",
            height: 6,
            width: 1,
            distanceFromScale: 2,
            color: "#8c8c8c"
        }],
        labels: [{
            color: "#8c8c8c"
        }],
        ranges: [{
            distanceFromScale: -5,
            backgroundColor: "#fc0606",
            border: {
	            color: "#fc0606"
            }
        }, { 
            distanceFromScale: -5
        }],
        customLabels: [{
                position: { x: 180, y: 290 },
                font: { size: "10px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
        }, {
                position: { x: 180, y: 320 },
                font: { size: "10px", fontFamily: "Segoe UI", fontStyle: "Normal" }, lcolor: "#666666"
        }, {
                position: { x: 180, y: 150 },
                font: { size: "12px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
        }]
    }];

    angular.module('PivotGaugeApp', ['ejangular']).controller('PivotGaugeCtrl', function ($scope) {
        $scpe.dataSource = dataSource;
        $scope.enableTooltip = true;
        $scope.rowsCount = 2;
        $scope.columnsCount = 3;
        $scope.scales = scale;
        $scope.labelFormatSettings = { decimalPlaces: 2 };
        $scope.backgroundColor = "transparent";
    });
</script>
</body>

</html>

{% endhighlight %}

The above code will generate a simple PivotGauge as shown in below figure.

![](getting-started_images/purejs.png)

## OLAP

This section covers the information that you need to know to populate a simple PivotGauge with OLAP data source.

### Control Initialization

Create the PivotGauge control using `ej-PivotGauge` directive and define all its other properties prefixed with `e-` as shown in the below code.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotGaugeApp">

<body>
    <div ng-controller="PivotGaugeCtrl">
        <div id="PivotGauge1" ej-pivotgauge e-dataSource="dataSource" e-enabletooltip="enableTooltip" e-rowscount="rowsCount"
            e-columnscount="columnsCount" e-scales="scales" e-load="loadGaugeTheme" e-backgroundcolor="backgroundColor" e-labelFormatSettings="labelFormatSettings"
            style="min-height: 275px; height: 338px; width: 100%; overflow: auto; position:relative;" />
    </div>
</body>

</html>

{% endhighlight %}

### Populate PivotGauge with data

Initializes the OLAP datasource for PivotGauge control as shown below.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotGaugeApp">
<head> <!-- Dependency file references --> </head>
<body>
    <div ng-controller="PivotGaugeCtrl">
        <div id="PivotGauge" ej-pivotgauge e-dataSource="dataSource" e-enabletooltip="enableTooltip" e-rowscount="rowsCount"
            e-columnscount="columnsCount" e-scales="scales" e-load="loadGaugeTheme" e-backgroundcolor="backgroundColor" e-labelFormatSettings="labelFormatSettings"
            style="min-height: 275px; height: 338px; width: 100%; overflow: auto; position:relative;" />
    </div>

<script>
    var scale = [{
            showRanges: true,
            radius: 150, showScaleBar: true, size: 1,
            border: {
                width: 0.5
            },
            showIndicators: true, showLabels: true,
            pointers: [{ 
                showBackNeedle: true,
                backNeedleLength: 20,
                length: 125,
                width: 7
            },
            {
                type: "marker",
                markerType: "diamond",
                distanceFromScale: 5,
                placement: "center",
                backgroundColor: "#29A4D9",
                length: 25,
                width: 15
            }],
            ticks: [{
                type: "major",
                distanceFromScale: 2,
                height: 16,
                width: 1, color: "#8c8c8c"
            }, {
                type: "minor",
                height: 6,
                width: 1,
                distanceFromScale: 2,
                color: "#8c8c8c"
            }], 

            labels: [{
                color: "#8c8c8c"
            }],
            ranges: [{
                distanceFromScale: -5,
                backgroundColor: "#fc0606",
                border: {
                    color: "#fc0606"
                }
            }, {
                distanceFromScale: -5
            }],      
            customLabels: [{
                position: { x: 180, y: 290 },
                font: { size: "10px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
            }, {
                position: { x: 180, y: 320 },
                font: { size: "10px", fontFamily: "Segoe UI", fontStyle: "Normal" }, lcolor: "#666666"
            }, {
                position: { x: 180, y: 150 },
                font: { size: "12px", fontFamily: "Segoe UI", fontStyle: "Normal" }, color: "#666666"
            }]
    }];

    angular.module('PivotGaugeApp', ['ejangular']).controller('PivotGaugeOlapCtrl', function ($scope) {
        $scope.dataSource = {
            data: "http://bi.syncfusion.com/olap/msmdpump.dll",
            catalog: "Adventure Works DW 2008 SE",
            cube: "Adventure Works",
            rows: [
                {
                    fieldName: "[Date].[Fiscal]",
                    filterItems: { filterType: "include", values: ["[Date].[Fiscal].[Fiscal Year].&amp;[2004]"] }
                },
            ],
            columns: [
                {
                    fieldName: "[Customer].[Customer Geography]"
                }
            ],
            values: [
                {
                    measures: [
                        {
                            fieldName: "[Measures].[Internet Sales Amount]"
                        },
                        {
                            fieldName: "[Measures].[Internet Revenue Status]"
                        },
                        {
                            fieldName: "[Measures].[Internet Revenue Trend]"
                        },
                        { 
                            fieldName: "[Measures].[Internet Revenue Goal]"
                        },
                    ],
                    axis: ej.PivotGauge.AxisName.Columns
                }
            ]
        };
        $scope.dataSource = $scope.dataSource;
        $scope.enableTooltip = true;
        $scope.rowsCount = 2;
        $scope.columnsCount = 3;
        $scope.scales = scale;
        $scope.labelFormatSettings = { decimalPlaces: 2 };
        $scope.backgroundColor = "transparent";
    });
</script>
</body>

</html>

{% endhighlight %}

The above code will generate a simple PivotGauge as shown in below figure.

![](getting-started_images/Olap.png)