---
layout: post
title: Columns with Grid widget for Syncfusion Essential AngularJS
description: How to define the columns and its features
platform: Angular-1
control: Grid
documentation: ug
--- 
# Columns

Column definitions are used as the [`dataSource`](http://help.syncfusion.com/api/js/ejgrid#members:datasource "dataSource") schema in Grid and it plays vital role in rendering column values in required format. Grid operations such as sorting, filtering, editing would be performed based on the column definitions. The [`field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") property of the [`columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns") is necessary to map the datasource values in Grid columns.

N> 1. If the column with [`field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") is not in the datasource, then the column values will be displayed as empty.
N> 2. If the [`field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") name contains "dot" operator then it is considered as complex binding.

## Column Template

HTML templates can be specified in the [`template`](http://help.syncfusion.com/api/js/ejgrid#members:columns-template "template") property of the particular column as a string (HTML element) or ID of the template's HTML element.

You can use JsRender syntax in the template. For more information about JsRender syntax, please refer [this link](http://www.jsviews.com/#jsrapi "this link"). 

N> If [`field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") is not specified, you will not able to perform editing, grouping, filtering, sorting, search and summary functionalities in particular column.

The following code example describes the above behavior.

{% highlight html %}
   <div ng-controller="PhoneListCtrl">
       <div id="Grid" class="ang-grid" ej-grid e-datasource="data" e-allowpaging="true" e-pagesettings-pagesize="4" >
          <div e-columns>
		        <div e-column e-headertext="Photo">
               <img style="width: 75px; height: 70px" ng-src="../Content/images/Employees/{{data.EmployeeID}}.png" alt="{{data.EmployeeID}}" />
            </div>
		        <div e-column e-field="EmployeeID"> </div>
		        <div e-column e-field="FirstName"> </div>
		        <div e-column e-field="LastName"> </div> 
			    <div e-column e-field="Country"> </div>              
	       </div>
	    </div>
   </div>
  
{% endhighlight %}

{% highlight javascript %}
     syncApp.controller('PhoneListCtrl', function ($scope,$rootScope) {
           $scope.data = window.employeeView;
       });
{% endhighlight %}

The following output is displayed as a result of the above code example.

![](columns_images/columns_img1.png)