---
layout: post
title: Key-Performance-Indicator-KPI
description: key performance indicator (KPI)
platform: AngularJS
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# KPI

Key Performance Indicators (KPIs) are business metric that help to figure out the progress of an enterprise in meeting its business goals.

The different indicators available in KPI are:

* KPI Value: A physical measure or a calculated measure.
* KPI Goal: Defines the target for the measure.
* KPI Status: Evaluates the current status of the value compared to the goal.
* KPI Trend: Evaluate the current trend of the value compared to the goal.

The **“KpiElements”** class in OLAP Base library holds the KPI name and when its object is added to an OlapReport, you can view the resultant information in PivotGrid.

## Client Mode

{% highlight js %}

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
                fieldName: "[Product].[Product Categories]"
            }],
            values: [{
                measures: [{
                    fieldName: "[Measures].[Internet Sales Amount]"
                }, {
                    fieldName: "[Measures].[Growth in Customer Base Trend]"
                }],
                axis: ej.olap.AxisName.Column
            }]
        };
        $scope.datasource = $scope.dataSource;
    })
</script>

{% endhighlight %}


![](KPI_images/ClientSideKPI.png)

## Server Mode

{% highlight c# %}

OlapReport olapReport = new OlapReport();
olapReport.Name = "Sample Report";
olapReport.CurrentCubeName = "Adventure Works";

MeasureElements measureElementColumn = new MeasureElements();
measureElementColumn.Elements.Add(new MeasureElement {
    Name = "Gross Profit"
});

DimensionElement dimensionElementRow = new DimensionElement();
dimensionElementRow.Name = "Date";
dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

KpiElements kpiElement = new KpiElements();
kpiElement.Elements.Add(new KpiElement {
    Name = "Revenue", ShowKPIStatus = true, ShowKPIGoal = false, ShowKPITrend = true, ShowKPIValue = true
});

olapReport.CategoricalElements.Add(kpiElement);
olapReport.CategoricalElements.Add(measureElementColumn);
olapReport.SeriesElements.Add(dimensionElementRow);

{% endhighlight %}

![](KPI_images/kpi.png)

