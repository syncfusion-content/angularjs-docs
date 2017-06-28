---
layout: post
title: Summary-Type
description: summary type
platform: Angular-1
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Summary Type

I> This feature is applicable only for Relational datasource only at Client Mode.

Allow us to specify the required [`layout`](/api/js/ejpivotgrid#members:layout) that PivotGrid should use in its summary cells. “Sum” is the default summary type. Following summary types that are supported:

* Sum
* Average
* Count
* Min
* Max

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
                    summaryType: ej.PivotAnalysis.SummaryType.Average
                },
                {
                    fieldName: "Quantity",
                    fieldCaption: "Quantity",
                    summaryType: ej.PivotAnalysis.SummaryType.Sum
                }
            ]
        };
 
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        $scope.datasource = dataSource;
    });
</script>

{% endhighlight %}

{% include image.html url="/angular-1/PivotGrid/Getting-Started_images/purejssummarytype.png" %}


