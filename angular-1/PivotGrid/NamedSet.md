---
layout: post
title: Named Set
description: named set
platform: Angular-1
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Named Sets

Named sets is a multidimensional expression (MDX) that returns a set of dimension members, which can be created by combining cube data, arithmetic operators, numbers and functions.

## Client Mode

You can bind the Named Sets in PivotGrid by setting it's unique name in the [`fieldName`](/api/js/ejpivotgrid#members:datasource-rows-fieldname) property either in row or column axis and [`isNamedSets`](/api/js/ejpivotgrid#members:datasource-columns-isnamedsets) boolean property to "true".

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-datasource="datasource" />
</div>
<script>
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) {
        $scope.dataSource = {
            data: "http://bi.syncfusion.com/olap/msmdpump.dll", //data source
            catalog: "Adventure Works DW 2008 SE",
            cube: "Adventure Works",
            rows: [{
                fieldName: "[Date].[Fiscal]"
            }],
            columns: [{
                fieldName: "[Core Product Group]",
                isNamedSets: true
            }],
            values: [{
                measures: [{
                    fieldName: "[Measures].[Internet Sales Amount]",
                }],
                axis: "columns"
            }]
        };
        $scope.datasource = $scope.dataSource;
    })
</script>

{% endhighlight %}

![](KPI_images/namedset.png)


## Server Mode

You can add Named Sets in the PivotGrid by using NamedSetElement Class in the OlapReport. 

{% highlight C# %}

OlapReport olapReport = new OlapReport();
olapReport.Name = "Customer Report";
olapReport.CurrentCubeName = "Adventure Works";

DimensionElement dimensionElementRow = new DimensionElement();
dimensionElementRow.Name = "Date";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

MeasureElements measureElementColumn = new MeasureElements();
measureElementColumn.Elements.Add(new MeasureElement {
Name = "Internet Sales Amount"
});

NamedSetElement dimensionElementColumn = new NamedSetElement();
dimensionElementColumn.Name = "Core Product Group";

olapReport.CategoricalElements.Add(dimensionElementColumn);
olapReport.CategoricalElements.Add(measureElementColumn);
olapReport.SeriesElements.Add(dimensionElementRow);

{% endhighlight %}

![](KPI_images/servernamedset.png)


