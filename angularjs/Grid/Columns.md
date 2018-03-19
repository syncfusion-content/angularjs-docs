---
Layout: Post
Title: Columns with Grid widget for the Syncfusion Essential AngularJS
Description: How to define columns and its features
Platform: AngularJS
Control: Grid
Documentation: UG
--- 
# Columns

Column definitions are used as the [`e-datasource`](http://help.syncfusion.com/api/js/ejgrid#members:datasource "dataSource") schema in Grid and it plays vital role in rendering column values in required format. Grid operations such as sorting, filtering, editing would be performed based on column definitions. The [`e-field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") property of the [`e-columns`](http://help.syncfusion.com/api/js/ejgrid#members:columns "columns") is necessary to map the datasource values in Grid columns.

N> 1. If the column with the [`e-field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") is not in the datasource, then the column values will be displayed as empty.
N> 2. If the [`e-field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") name contains "dot" operator, then it is considered as complex binding.

## Column Template

HTML templates can be specified in the [`e-template`](http://help.syncfusion.com/api/js/ejgrid#members:columns-template "template") property of particular column as a string (HTML element) or ID of the template's HTML element.

You can use the "ng-template" to define template column and declare image template with the Angular directive "ng-src".

N> If [`e-field`](http://help.syncfusion.com/api/js/ejgrid#members:columns-field "field") is not specified, you will be unable to edit, group, filter, sort, search, and summary functionalities in a particular column.

The following code example describes the previous behavior.

{% highlight html %}
   <div ng-controller="columnTemplateCtrl">
       <div id="Grid" ej-grid e-datasource="data" e-allowpaging="true" e-pagesettings-pagesize="4" >
          <div e-columns>
		        <div e-column e-headertext="Photo">
                   <img style="width: 75px; height: 70px" ng-src="../Content/images/Employees/{{"{{"}}:data.EmployeeID{{}}}}.png" alt="{{"{{"}}:data.EmployeeID{{}}}}" />
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
     syncApp.controller('columnTemplateCtrl', function ($scope,$rootScope) {
        //The datasource "window.employeeView" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
           $scope.data = window.employeeView;
       });
{% endhighlight %}

The following output is displayed as the result of previous code example:

![](columns_images/columns_img1.png)