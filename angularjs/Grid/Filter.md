---
layout: post
title: Filtering with Grid widget for Syncfusion Essential AngularJS
description: Learn here all about Filtering support in Syncfusion AngularJS Grid control, its elements and more
platform: AngularJS
control: Grid
documentation: ug
--- 
# Filtering in AngularJS Grid

Filtering helps to view particular or related records from dataSource that meets a given filtering criteria. To enable filter, set the `e-allowfiltering` to `true`. 

The Grid supports three types of filter, they are:

1. Filter bar
2. Menu 
3. Excel

And also four types of filter menu is available in all filter types, they are: 

1. String 
2. Numeric 
3. Date 
4. Boolean

The corresponding filter menu is opened based on the column type.

N> 1. When first record data value is empty or null,  specify the [`e-type`](http://help.syncfusion.com/api/js/ejgrid#members:columns-type "type") of column otherwise the filter menu is not opened.  
N> 2. The default filter type is Filter bar, when the `e-allowfiltering` is enabled and the [`filtertype`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") is not set.

The following code example describes the previous behavior.

{% highlight html %}
<div ng-controller="FilteringCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowfiltering="true">
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="CustomerID"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
          </div>
     </div>
 </div>
        
{% endhighlight %}

{% highlight javascript %}
     syncApp.controller('FilteringCtrl', function ($scope,$rootScope) {
       //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
        $scope.data = window.gridData;

     });
{% endhighlight %}

The following output is displayed as a result of previous code example:

![Filtering in AnguarJS Grid ](filtering_images/filtering_img1.png)


## Menu filter

You can enable menu filter by setting the [`e-filtersettings`] of [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") to `menu`. 

There is an option to show or hide the additional filter options in the menu by setting the [`e-filtersettings`] of [`showPredicate`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-showpredicate "filterSettings.showPredicate") to `true` or `false` respectively.

N> For the [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") property you can assign either `string` value ("menu") or `enum` value (`ej.Grid.FilterType.Menu`).

You can also filter a specified range of values by using the `between` operator for the column type `number`, `date`, and `datetime`.

The following code example describes the previous behavior.

{% highlight html %}
<div ng-controller="FilteringmenuCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowfiltering="true" e-filtersettings="filterType" >
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="CustomerID"></div>
             <div e-column e-field="OrderDate" e-format="{0:MM/dd/yyyy}"></div>
             <div e-column e-field="Verified"></div>
          </div>
     </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
   
      syncApp.controller('FilteringmenuCtrl', function ($scope,$rootScope) {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
          $scope.data = window.gridData;
          $scope.filterType = { filterType: "menu" }
      });

{% endhighlight %}


The following output is displayed as a result of previous code example:

![Filtering Numeric Filter in AngularJS Grid](filtering_images/filtering_img2.png)
{:caption}
Numeric Filter

![Filtering String Filter in AngularJS Grid](filtering_images/filtering_img3.png)
{:caption}
String Filter

![Filtering Date Filter in AngularJS Grid](filtering_images/filtering_img4.png)
{:caption}
Date Filter

![Filtering Boolean Filter in AngularJS Grid](filtering_images/filtering_img5.png)

Boolean Filter

## Excel-like filter

You can enable excel menu by setting  the [`e-filtersettings`] of [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterSettings.filterType") to `excel`. The excel menu contains options such as Sort, Clear filter, and submenu for advanced filtering.

The following code example describes the previous behavior.

{% highlight html %}
<div ng-controller="FilteringexcelCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowfiltering="true" e-filtersettings="filterType">
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="CustomerID"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
          </div>
     </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
     syncApp.controller('FilteringexcelCtrl', function ($scope,$rootScope) {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
          $scope.data = window.gridData;
          $scope.filterType = { filterType: "excel" }
      });
{% endhighlight %}

The following output is displayed as a result of previous code example:

![Filtering Excel-like Filter in AngularJS Grid](filtering_images/filtering_img6.png)


### Checkbox list generation:

By default, the checkbox list is generated from distinct values of the filter column from dataSource which gives an option to search and select the required items.

Also on checkbox list generation, if the number of distinct values are greater than 1000, then the excel filter will display only first 1000 values to ensure the best performance on rendering and searching. However this limit has been customized according to your requirement by setting the [`e-filtersettings`] of [`maxFilterChoices`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-maxfilterchoices "filterSettings.maxFilterChoices") with required limit in integer.

N> 1. You can change the dataSource of checkbox list using the excel filter events. 
N> 2. The [`ej.Query`](http://help.syncfusion.com/api/js/ejquery# "ej.Query") of checkbox list can also be changed using excel filter events.

The following code example describes the previous behavior.

{% highlight html %}
<div ng-controller="CheckboxCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowfiltering="true" e-filtersettings="filterType">
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="CustomerID"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
            </div>
       </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
    syncApp.controller('CheckboxCtrl', function ($scope,$rootScope) {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
          $scope.data = window.gridData;
          $scope.filterType = { filterType: "excel",maxFilterChoices : 4 }
      });
{% endhighlight %}

The following output is displayed as a result of previous code example:

![Filtering Checkbox list generation in AngularJS Grid](filtering_images/filtering_img7.png)


### Add current selection to filter checkbox

When you filter the values multiple times on same column, then the previously filtered values on the column will be cleared. So, to retain the old values `Add current selection to filter` checkbox can be used, which is displayed when data is searched in the search bar.

The following image describes the previous behavior:

![Filtering Add current selection to filter checkbox in AngularJS Grid](filtering_images/filtering_img12.png)


### Case Sensitivity

To perform filter operation with case sensitive in excel styled filter menu mode by setting the [`enableCaseSensitivity`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-enablecasesensitivity "enableCaseSensitivity") to `true`.

The following code example describes the previous behavior.

{% highlight html %}
<div ng-controller="EnablecaseCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowfiltering="true" e-filtersettings="filterType">
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="CustomerID"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
          </div>
     </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
     syncApp.controller('EnablecaseCtrl', function ($scope,$rootScope) {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
          $scope.data = window.gridData;
          $scope.filterType = { filterType: "excel", enableCaseSensitivity: true }
      });
{% endhighlight %}

The following output is displayed as a result of previous code example:

![Filtering Case Sensitivity in AngularJS Grid](filtering_images/filtering_img8.png)


## Filter bar

The [`Filterbar`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "Filter bar") row is located next to the column header of grid. You can filter the records with different expressions depending upon the column type. To show the filter bar row, set the [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") to `filterbar`.

List of Filter bar Expressions:

You can enter the below filter expressions manually in the filter bar.

 <table>
        <tr>
            <th>
                Expression
            </th>
            <th>
                Example
            </th>
            <th>
                Description
            </th>
            <th>
                Column Type
            </th>
        </tr>
        <tr>
            <td>
                =
            </td>
            <td>
                = value
            </td>
            <td>
                equal
            </td>
            <td rowspan="5">
                Numeric
            </td>
        </tr>
        <tr>
            <td>
                != 
            </td>
            <td>
                != value
            </td>
            <td>
                notequal
            </td>
           
        </tr>
        <tr>
            <td>
                >
            </td>
            <td>
                > value
            </td>
            <td>
                greaterthan
            </td>
          
        </tr>
        <tr>
            <td>
                <
            </td>
            <td>
                < value
            </td>
            <td>
                lessthan
            </td>
          
        </tr>
        <tr>
            <td>
                >=
            </td>
            <td>
                >= value
            </td>
            <td>
                greaterthanorequal
            </td>
           >
        </tr>
        <tr>
            <td>
                <=
            </td>
            <td>
                <= value
            </td>
            <td>
                lessthanorequal
            </td>
           
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `startswith` operator will be used for string filter
            </td>
            <td>
                String
            </td>
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `equal` operator will be used for Date filter 
            </td>
            <td>
                Date
            </td>
        </tr>
        <tr>
            <td>
                N/A
            </td>
            <td>
                N/A
            </td>
            <td>
                Always `equal` operator will be used for Boolean filter
            </td>
            <td>
                Boolean
            </td>
        </tr>
    </table>
	
	
The following code example describes the previous behavior.

{% highlight html %}
<div ng-controller="FilterbarCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowfiltering="true" e-filtersettings="filterType">
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="CustomerID"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
          </div>
     </div>
 </div>
{% endhighlight %}
   
{% highlight javascript %}

     syncApp.controller('FilterbarCtrl', function ($scope,$rootScope) {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
          $scope.data = window.gridData;
          $scope.filterType = { filterType: "filterbar" }
      });

{% endhighlight %}

The following output is displayed as a result of previous code example:

![Filtering Filter Bar Modes in AngularJS Grid](filtering_images/filtering_img9.png)


Filter bar modes:

This specifies the grid to start the filter action while typing in the filter bar or after pressing the enter key based on the [`filterBarMode`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filterbarmode "filterBarMode").There are two types of [`filterBarMode`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filterbarmode "filterBarMode"), they are:

1. OnEnter
2. Immediate

N> For the [`filterBarMode`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filterbarmode "filterBarMode") property you can assign either `string` value (onenter) or `enum` value (`ej.Grid.FilterBarMode.OnEnter`).

Filter bar message

The filter bar message is supported only for the [`filterType`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-filtertype "filterType") as filterbar. The filtered data with column name is displayed in the grid pager itself. By default the [`showFilterBarStatus`](http://help.syncfusion.com/api/js/ejgrid#members:filtersettings-showfilterbarmessage "showFilterBarMessage") is true.

The following code example describes the previous behavior.

{% highlight html %}
<div ng-controller="FilterbarCtrl">
     <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-allowfiltering="true" e-filtersettings="filterType">
          <div e-columns>
             <div e-column e-field="OrderID"></div>
             <div e-column e-field="EmployeeID"></div>
             <div e-column e-field="CustomerID"></div>
             <div e-column e-field="ShipCountry"></div>
             <div e-column e-field="Freight"></div>
          </div>
       </div>
 </div>
{% endhighlight %}

{% highlight javascript %}
    syncApp.controller('FilterbarCtrl', function ($scope,$rootScope) {
        //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
          $scope.data = window.gridData;
          $scope.filterType = {showFilterBarStatus: true }
      });

{% endhighlight %}

The following output is displayed as a result of previous code example:

![Filtering Filter bar message in AngularJS Grid](filtering_images/filtering_img10.png)


## Filter Operators

The grid controls uses filter operators from the [`ej.DataManager`](http://help.syncfusion.com/api/js/ejdatamanager# "ej.DataManager"), which are used at the time of filtering.

List of Column type and Filter operators

<table>
        <tr>
            <th>
                Column Type
            </th>
            <th>
                Filter Operators
            </th>
        </tr>
        <tr>
            <td rowspan="6">
                Number
            </td>
            <td>
                ej.FilterOperators.greaterThan
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.greaterThanOrEqual
            </td>
        </tr>
        <tr>
       
            <td>
                ej.FilterOperators.lessThan
            </td>
        </tr>
        <tr>
            
            <td>
                ej.FilterOperators.lessThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
        <tr>
            <td rowspan="5">
                String
            </td>
            <td>
                ej.FilterOperators.startsWith
            </td>
        </tr>
        <tr>
          
            <td>
                ej.FilterOperators.endsWith
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.contains
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
        <tr>
            <td rowspan="2">
                Boolean
            </td>
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
            
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
        <tr>
            <td rowspan="6">
                Date
            </td>
            <td>
                ej.FilterOperators.greaterThan
            </td>
        </tr>
        <tr>
            
            <td>
                ej.FilterOperators.greaterThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.lessThan
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.lessThanOrEqual
            </td>
        </tr>
        <tr>
           
            <td>
                ej.FilterOperators.equal
            </td>
        </tr>
        <tr>
          
            <td>
                ej.FilterOperators.notEqual
            </td>
        </tr>
    </table>

## FilterBar Template

Usually, enabling the`e-allowfiltering` will create default textbox in Grid FilterBar. So, Using the [`e-filterbartemplate`] property of `e-columns`, you can render any other controls like AutoComplete, DropDownList, etc., in filterbar to filter the grid data for particular column.  
The three functions of this template are: 

1. `create`:Creates the control at time of initialize.
2. `read`: Reads the Filter value selected.
3. `write`: Renders the control and assign the value selected for filtering.


The following code example describes the previous behavior.

{% highlight html %}
 <div ng-controller="FilterBarCtrl">
        <div id="Grid" ej-grid e-datasource="data" e-allowfiltering="true" e-allowpaging="true">
            <div e-toolbarsetting-showtoolbar=true></div>
            <div e-columns>
                <div e-column e-field="OrderID" e-headertext="Order ID" e-textalign="right" e-width="90"></div>
                <div e-column e-field="CustomerID" e-headertext="CustomerID" e-textalign="left" e-width="90" e-filterbartemplate="filtercustomer"></div>
                <div e-column e-field="EmployeeID" e-headertext="EmployeeID" e-textalign="left" e-width="90" e-filterbartemplate="filteremployee"></div>
                <div e-column e-field="Freight" e-headertext="Freight" e-textalign="left" e-format="{0:C2}" e-width="90" e-filterbartemplate="filterFreight"></div>
                <div e-column e-field="ShipCountry" e-headertext="Ship Country" e-textalign="left" e-width="90"></div>
                <div e-column e-field="Verified" e-headertext="Verified" e-width="90">
            </div>
            </div>
        </div>
    </div>   
{% endhighlight  %}
{% highlight javascript %}
   syncApp.controller('FilterbarCtrl', function ($scope,$rootScope) {
            $scope.data = window.gridData; //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            $scope.filterFreight = {
                write: function (args) {
                    args.element.ejNumericTextbox({ width: "100%", decimalPlaces: 2, focusOut: ej.proxy(args.column.filterBarTemplate.read, this, args) });
                },
                read: function (args) {
                    this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
                },
            }
            $scope.filtercustomer = {
                create: function (args) {
                    return "<input>"
                },
                write: function (args) {
                    var data = ej.DataManager(window.gridData).executeLocal(new ej.Query().select("CustomerID"));
                    args.element.ejAutocomplete({ width: "100%", dataSource: data, enableDistinct: true, focusOut: ej.proxy(args.column.filterBarTemplate.read, this, args) });
                },
                read: function (args) {
                    this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
                },
            }
            $scope.filteremployee = {
                write: function (args) {
                    var data = [{ text: "clear", value: "clear" }, { text: "1", value: 1 }, { text: "2", value: 2 }, { text: "3", value: 3 }, { text: "4", value: 4 },
                        { text: "5", value: 5 }, { text: "6", value: 6 }, { text: "7", value: 7 }, { text: "8", value: 8 }, { text: "9", value: 9 }
                    ]
                    args.element.ejDropDownList({ width: "100%", dataSource: data, change: ej.proxy(args.column.filterBarTemplate.read, this, args) })
                },
                read: function (args) {
                    if (args.element.val() == "clear") {
                        this.clearFiltering(args.column.field);
                        args.element.val("")
                    }
                    this.filterColumn(args.column.field, "equal", args.element.val(), "and", true)
                },
            }
        });
{% endhighlight %}


The following output is displayed as a result of previous code example:

![Filtering FilterBar template in AngularJS Grid](filtering_images/filtering_img11.png)
{:caption}
After Filtering
 
