---
layout: post
title: Grouping-Bar
description: grouping bar
platform: Angular-1
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Grouping Bar

## Initialization 

Grouping Bar allows user to dynamically alter the report by filter, sort and remove operations in the PivotGrid control. Based on the Relational datasource and report bound to the PivotGrid control, Grouping Bar will be automatically populated. You can enable Grouping Bar option in PivotGrid by setting the `e-enableGroupingBar` property to true.

### Client Mode

{% highlight js %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-datasource="datasource" e-enableGroupingBar="true" />
</div>
<script>
    var pivot_dataset = []; // Specify Data source
    var dataSource = {
            data: pivot_dataset,
            rows: [{
                fieldName: "Country",
                fieldCaption: "Country",
                sortOrder: ej.PivotAnalysis.SortOrder.Ascending
            }, {
                fieldName: "State",
                fieldCaption: "State",
                sortOrder: ej.PivotAnalysis.SortOrder.Descending
            }],
            columns: [{
                fieldName: "Product",
                fieldCaption: "Product"
            }],
            values: [{
                fieldName: "Amount",
                fieldCaption: "Amount"
            }, {
                fieldName: "Quantity",
                fieldCaption: "Quantity"
            }],
            filters: [{
                fieldName: "Date",
                fieldCaption: "Date",
                filterItems: {
                    filterType: ej.PivotAnalysis.FilterType.Exclude,
                    values: ["FY 2005"]
                }
            }]
        };

    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        $scope.datasource = dataSource;
    });
</script>

{% endhighlight %}

![](Grouping-Bar_images/ClientsideGr.png)


### Server Mode

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-url="url" e-enableGroupingBar="true" />
</div>
<script>
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) 
    {
        $scope.url = "/Relational";
    });
</script>

{% endhighlight %}

![](Grouping-Bar_images/groupingbar.png)

## Searching Values
Search option available in Grouping Bar allows you to search a specific value that needs to be filtered from the list of values inside the filter pop-up window.

![](Grouping-Bar_images/groupingbar-filter.png)

![](Grouping-Bar_images/groupingbar-search.png)

## Filtering Values
Filtering option available in Grouping Bar allows you to select a specific set of values that needs to be displayed in the PivotGrid control. At least one value needed to be in checked state while filtering otherwise “Ok” button will be disabled.

![](Grouping-Bar_images/groupingbar-filter.png)

![](Grouping-Bar_images/groupingbar-filter1.png)

## Sorting Values
Sorting option available in Grouping Bar allows you to arrange headers either in ascending or descending order. Sorting option is applicable for fields available only in Row and Column region. By default, headers are sorted in ascending order. Regarding sorting indicator, up arrow denotes ascending order and down arrow denotes descending order.

![](Grouping-Bar_images/groupingbar-sort.png)

![](Grouping-Bar_images/groupingbar-sort-grid.png)

## Removing Field
Remove option available in the Grouping Bar allows you to completely remove a specific field from the PivotGrid control. Remove operation can be either achieved by clicking remove icon available inside each field or by dragging and dropping field out of Grouping Bar region.

![](Grouping-Bar_images/groupingbar-remove.png)

![](Grouping-Bar_images/groupingbar-remove-grid.png)


