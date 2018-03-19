---
layout: post
title: Row with Grid widget for Syncfusion Essential AngularJS
description: How to use and customize the grid row
platform: AngularJS
control: Grid
documentation: ug
--- 
# Row

It represents the record details that are fetched from the datasource.

## Details Template

It provides a detailed view or additional information about each row of the grid. You can render any type of JsRender template and assign the script template ID in the [`e-detailstemplate`](http://help.syncfusion.com/api/js/ejgrid#members:detailstemplate "detailsTemplate") property. And also you can change HTML elements in detail template row into JavaScript controls using the [`e-detailsdatabound`](http://help.syncfusion.com/api/js/ejgrid#events:detailsdatabound "detailsDataBound") event.

By enabling details template, new column will be added in grid with an expander button in it and that can be expanded or collapsed to show or hide the underlying details row respectively.

N> It's a standard way to enclose the template within the `script` tag with `type` as "text/x-jsrender".

The following code example describes the previous behavior.

{% highlight html %}
  <body ng-controller="detailTemplateCtrl">
      <div id="Grid" ej-grid e-datasource="data" e-detailstemplate="detailTemp" e-detailsdatabound="detailgrid">
        <div e-columns>
            <div e-column e-field="EmployeeID" ></div>
            <div e-column e-field="FirstName" ></div>
            <div e-column e-field="Title" ></div>
            <div e-column e-field="City" ></div>
            <div e-column e-field="Country"></div>
        </div>
    </div>
    <script id="tabGridContents" type="text/x-jsrender">
        <div class="tabcontrol" id="Test">
            <ul>
                <li><a href="#gridTab{{"{{"}}:EmployeeID{{}}}}">Stock Grid</a></li>
            </ul>
            <div id="gridTab{{"{{"}}:EmployeeID{{}}}}">
                <div id="detailGrid"></div>
            </div>
        </div>
    </script>
{% endhighlight %}

{% highlight javascript %}
      syncApp.controller('detailTemplateCtrl', function ($scope,$rootScope) {
            $scope.data = window.employeeView;
            $scope.detailTemp= "#tabGridContents",
            $scope.detailgrid = "detailGridData"
     });
     
   function detailGridData(e) {
            var filteredData = e.data["EmployeeID"];
            var data = ej.DataManager(window.ordersView).executeLocal(ej.Query().where("EmployeeID", "equal", parseInt(filteredData), true).take(5));
            e.detailsElement.find("#detailGrid").ejGrid({
                dataSource: data,
                columns: ["OrderID", "EmployeeID", "ShipCity", "ShipCountry", "Freight"]
            });
            e.detailsElement.find(".tabcontrol").ejTab();
        }

{% endhighlight %}

The following output is displayed as a result of previous code example:

![](Row_images/Row_img1.png)


## Row Template

Row template allows you to set the customized look and behavior to grid all rows. The [`e-rowtemplate`](http://help.syncfusion.com/api/js/ejgrid#members:rowtemplate "rowTemplate") property can be used to bind the `ID` of HTML template.              

The following code example describes the previous behavior.

{% highlight html %}
  <div ng-controller="rowTemplateCtrl">
      <div id="Grid" ej-grid e-datasource="data" e-allowscrolling="true" e-rowtemplate="rowTemp" e-scrollsettings="scroll" >
			<div e-columns>
				<div e-column e-field="Photo" e-headertext="Photo" e-width="30"></div>
				<div e-column e-headertext="Employee Details" e-width="70"></div>
			 </div>
		</div>
   </div>
       
<script id="templateData" type="text/x-jsrender">
          <tr>
            <td class="photo">
                <img src="~/../Content/images/Employees/{{"{{"}}:EmployeeID{{}}}}.png" alt="{{"{{"}}:EmployeeID{{}}}}" />
            </td>
            <td class="details">
                <table class="CardTable" cellpadding="3" cellspacing="2">
                    <colgroup>
                        <col width="50%">
                        <col width="50%">
                    </colgroup>
                    <tbody>
                        <tr>
                            <td class="CardHeader">First Name </td>
                            <td>{{:FirstName}} </td>
                        </tr>
                        <tr>
                            <td class="CardHeader">Birth Date
                            </td>
                            <td>{{:BirthDate}}
                            </td>
                        </tr>
                        <tr>
                            <td class="CardHeader">Hire Date
                            </td>
                            <td>{{:HireDate}}
                            </td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>       
    </script>
 
 {% endhighlight %}

{% highlight javascript %}
       syncApp.controller('rowTemplateCtrl', function ($scope,$rootScope) {
            $scope.data = window.employeeData;
            $scope.rowTemp = "#templateData";
            $scope.scroll ={ width: 500, height: 380 }
        });
  {% endhighlight %}

{% highlight css %}
  <style type="text/css" class="cssStyles">
        .photo img
        {
            width: 130px;
			height: 115px;
        }

        .photo, .details
        {
            border-color: #c4c4c4;
            border-style: solid;
        }

        .photo
        {
            border-width: 1px 0px 0px 0px;
        }

        .details
        {
            border-width: 1px 0px 0px 1px;
        }
		 #RowGrid tbody tr td
        {
            vertical-align: middle;
        }

            .details > table
            {
                width: 100%;
            }

        .CardHeader
        {
            font-weight: bolder;
        }
		td
		{
			padding: 2px 2px 3px 2px;
		}
    </style>

{% endhighlight %}

   
The following output is displayed as a result of previous code example:                                                                                                  

![](Row_images/Row_img2.png)
