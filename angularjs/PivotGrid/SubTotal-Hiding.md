---
layout: post
title:  SubTotal Hiding
description: SubTotal Hiding
platform: AngularJS
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Sub Total Hiding

N> This feature is applicable only for Relational data source.

You can hide the **Sub Total** for respective fields in rows and columns by setting the property `showSubTotal` to `false`

## Client Mode

{% highlight html %}

<script>
    var pivot_dataset = []; // Specify Data source
    var dataSource = {
            data: pivot_dataset,
            columns: [
                {
                    fieldName: "Country",
                    fieldCaption: "Country",
                    showSubTotal: false,
                }
            ],
            ///...
        };
 
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        $scope.datasource = dataSource;
    });
</script>

{% endhighlight %}


## Server Mode


{% highlight c# %}

private PivotReport BindDefaultData()
{
    PivotReport pivotSetting = new PivotReport();
    pivotSetting.PivotRows.Add(new PivotItem { FieldMappingName = "Date", FieldHeader = "Date", TotalHeader = "Total", ShowSubTotal = false });
    pivotSetting.PivotRows.Add(new PivotItem { FieldMappingName = "Product", FieldHeader = "Product", TotalHeader = "Total", ShowSubTotal = true });
    pivotSetting.PivotColumns.Add(new PivotItem { FieldMappingName = "Country", FieldHeader = "Country", TotalHeader = "Total", ShowSubTotal = false });
    pivotSetting.PivotCalculations.Add(new PivotComputationInfo { CalculationName = "Amount", Description = "Amount", FieldHeader = "Amount", FieldName = "Amount", Format = "C", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum });
    return pivotSetting;
}

{% endhighlight %}

![](SubTotal-Hiding_images/SubTotal.png)
