---
layout: post
title: Number format
description: Number format
platform: Angular-1
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Number format 

Allows us to specify the required number format that PivotGrid should use in its values by setting the `format` option. Following number formats that are supported:


* number
* decimal
* currency
* percentage
* date
* time
* scientific
* accounting
* fraction

## RELATIONAL

### Client Mode 

{% highlight js %}

<script>
    var pivot_dataset = []; // Specify Data source
    var dataSource = {
            data: pivot_dataset,
            ///...
            values: [
                {
                    fieldName: "Amount",
                    fieldCaption: "Amount",
                    format: "currency"
                },
                {
                    fieldName: "Quantity",
                    fieldCaption: "Quantity",
                    format: "decimal"
                }
            ]
        };
 
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        $scope.datasource = dataSource;
    });
</script>

{% endhighlight %}

![](Number-Format_images/RelationalClient.png)

### Server Mode

You can set Number Format through the property `Format`. You should specify the format to the property as per the MS standard notation.
 
private PivotReport BindDefaultData()
    {
        
        PivotReport pivotSetting = new PivotReport();
        pivotSetting.PivotRows.Add(new PivotItem { FieldMappingName = "Product", FieldHeader = "Product", TotalHeader = "Total" });
        pivotSetting.PivotColumns.Add(new PivotItem { FieldMappingName = "Country", FieldHeader = "Country", TotalHeader = "Total" });
        //specify the format here
        pivotSetting.PivotCalculations.Add(new PivotComputationInfo { CalculationName = "Amount", Description = "Amount", FieldHeader = "Amount", FieldName = "Amount", Format = "E", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum });
        return pivotSetting;
    }

![](Number-Format_images/RelationalServer.png)

## OLAP

### Client Mode

{% highlight html %}

<script>
    var pivot_dataset = []; // Specify Data source
    var dataSource = {
            data: pivot_dataset,
            ///...
            values: [
                measures: [{
                    fieldName: "[Measures].[Internet Sales Amount]",
                    format: "percent" //Specify the format here
                }],
                axis: "columns"format: "decimal"
            ]
        };
 
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        $scope.datasource = dataSource;
    });
</script>

{% endhighlight %}

![](Number-Format_images/OlapClient.png)

### Server Mode

 OLAP server mode supports the following number formats in addition to the above mentioned formats.
  
* General
* RoundTrip
* FixedPoint
* HexaDecimal

N> You can set the number format through the property `Format`

private OlapReport CreateOlapReport()
{
     OlapReport olapReport = new OlapReport();
     olapReport.CurrentCubeName = "Adventure Works";

     MeasureElements measureElement = new MeasureElements();
     measureElement.Elements.Add(new MeasureElement { UniqueName = "[Measures].[Internet Sales Amount]", Format = NumberFormat.FixedPoint }); //Specify the format here

     DimensionElement dimensionElementRow = new DimensionElement();
     dimensionElementRow.Name = "Date";
     dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

     DimensionElement dimensionElementColumn = new DimensionElement();
     dimensionElementColumn.Name = "Customer";
     dimensionElementColumn.AddLevel("Customer Geography", "Country");

     olapReport.SeriesElements.Add(dimensionElementRow);
     olapReport.CategoricalElements.Add(dimensionElementColumn);
     olapReport.CategoricalElements.Add(measureElement);

     return olapReport;
}

![](Number-Format_images/OlapServer.png)  