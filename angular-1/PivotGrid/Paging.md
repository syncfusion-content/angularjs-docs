---
layout: post
title: Paging
description: paging
platform: Angular-1
control: pivotgrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, pivotgrid widget, js pivotgrid 
---

# Paging

I> This feature is applicable only for OLAP data source.

## Pager 

Paging helps to improve the rendering performance of the PivotGrid control by dividing large amount of data into sections and displaying one section at a time. You can enable Paging option in PivotGrid by setting the [`enablePaging`](/api/js/ejpivotgrid#members:enablePaging) property to true. You can provide the page size and current page details for each axis in [`pagerOptions`](/api/js/ejpivotgrid#members:pagerOptions) property.

In-order to initialize a **Pager**, first you need to define a **div** tag with an appropriate **id** attribute which acts as a container for the widget. Then you need to initialize the widget using `ej-pivotpager` directive and define all its other properties prefixed with `e-` as shown in the below code.

Inside the **ej-pivotpager** directive, the enumeration property `e-mode` needs to be set to **ej.PivotPager.Mode.Both** in-order to display both categorical pager and series pager. The other enumerations such as **ej.PivotPager.Mode.Categorical** and **ej.PivotPager.Mode.Series** will display only categorical pager and series pager respectively.


{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-datasource="datasource" e-enablePaging="true" style="height: 350px; width: 100%; float: left; overflow: auto" />
    <div id="PivotPager1" ej-pivotpager e-mode="mode" e-targetcontrolid="PivotGrid1" style="margin-top: 10px; overflow: auto" />
</div>
<script>
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) {
        $scope.dataSource = {
            ///...
            pagerOptions: {
            categoricalPageSize: 4,
            seriesPageSize: 4,
            categoricalCurrentPage: 1,
            seriesCurrentPage: 1
            }
        };
        $scope.datasource = $scope.dataSource;
        $scope.mode = ej.PivotPager.Mode.Both;
    })
</script>

<div id="PivotGrid1"></div>

{% endhighlight %}


Following are the navigation options available in Pager.

* Move First - Navigates to the first page.
* Move Last - Navigates to the last page. 
* Move Previous - Navigates to the previous page from the current page.
* Move Next - Navigates to the next page from the current page.
* Numeric Box - Navigates to the desired page by entering an appropriate page number in numeric value.

![](Paging_images/paging.png)


## Virtual Scrolling

Virtual Scrolling is a technique that allows user to view the PivotGrid information page by page with the use of vertical and horizontal scrollbar. You can enable Virtual Scrolling option in PivotGrid by setting the `e-enableVirtualScrolling` property to true. You can provide the page size and current page details for each axis in [`pagerOptions`](/api/js/ejpivotgrid#members:pagerOptions) property. 

{% highlight html %}

<div ng-controller="PivotGridCtrl">
    <div id="PivotGrid1" ej-pivotgrid e-datasource="datasource" e-enableVirtualScrolling="true" />
</div>
<script>
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) {
        $scope.dataSource = {
            ///...
            pagerOptions: {
            categoricalPageSize: 4,
            seriesPageSize: 4,
            categoricalCurrentPage: 1,
            seriesCurrentPage: 1
            }
        };
        $scope.datasource = $scope.dataSource;
    })
</script>

{% endhighlight %}

![](Paging_images/virtual-scrolling.png)

## Page Settings

The properties associated to paging are:

* EnablePaging – This property is used to enable/disable paging in PivotClient control.
* PagerOptions.CategoricalPageSize - Specifies the number of categorical columns to be displayed within a page of the PivotClient control.
* PagerOptions.SeriesPageSize - Specifies the number of series rows to be displayed within a page of the PivotClient control.
* PagerOptions.CategoricalCurrentPage - Sets the current page of the categorical axis in PivotClient control.
* PagerOptions.SeriesCurrentPage - Sets the current page of the series axis in PivotClient control.

For client mode, page setting for categorical and series axes are mandatorily needed to be set in data source property by using the following properties.

{% highlight html %}

<script>
    angular.module("PivotGridApp",["ejangular"]).controller('PivotGridCtrl', function ($scope) {
        $scope.dataSource = {
            ///...
            pagerOptions: {
            categoricalPageSize: 4,
            seriesPageSize: 4,
            categoricalCurrentPage: 1,
            seriesCurrentPage: 1
            }
        };
        $scope.datasource = $scope.dataSource;
    })
</script>

{% endhighlight %}

For server mode, the page settings for categorical and series axes are done only through OlapReport object, created inside WebAPI or WCF file.

{% highlight c# %}

OlapReport olapReport = new OlapReport();
olapReport.CurrentCubeName = "Adventure Works";
olapReport.EnablePaging = true;
olapReport.PagerOptions.SeriesPageSize = 4;
olapReport.PagerOptions.CategorialPageSize = 5;

{% endhighlight %}