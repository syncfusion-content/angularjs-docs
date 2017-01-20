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

I> This feature is applicable only for Relational datasource only at Client Mode.

Allow us to specify the required number format that PivotGrid should use in its values by setting the `format` option. Following number formats that are supported:

* number
* decimal
* currency
* percentage
* date
* time
* scientific
* accounting
* fraction


{% highlight html %}

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

![](Number-Format_images/Numberformat.png)


