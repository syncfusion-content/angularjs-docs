---
layout: post
title: data-binding
description: data binding
platform: angular-1
control: Autocomplete
documentation: ug
---

## Data Binding

In order to render the AutoComplete component, the data needs to be bound to it in a proper way. The below sections explains about how to bind either the local or remote data to the AutoComplete component.

### Fields

The AutoComplete component has **e-fields** property (object) which holds the properties to map with datasource fields. For example, the field object has a text property which is necessary to map with specific field in the datasource to render the suggestion items in the AutoComplete component. Or else empty suggestion list appears.

The field object contains the following properties.

* [text](http://help.syncfusion.com/api/js/ejautocomplete)

* [key](http://help.syncfusion.com/api/js/ejautocomplete)

* [groupBy](http://help.syncfusion.com/api/js/ejautocomplete)

* [htmlAttributes](http://help.syncfusion.com/api/js/ejautocomplete)

### Local data

The local data can be an array of JSON objects which is assigned for the Autocomplete component’s **e-datasource** property. Refer the below example.

Here the name and index fields are mapped with text and key properties of the field object respectively.

{% highlight html %}


 <input type="text" ej-autocomplete e-datasource="dataList" e-fields-key="key" e-fields-text="text" e-width="100%" />


<script type="text/javascript">
         var countriesField = [
                { name: "Austria", index: "C1" },
                { name: "Australia", index: "C2" }, { name: "Antarctica", index: "C3" },
                { name: "Bangladesh", index: "C4" }, { name: "Belgium", index: "C5" },
                { name: "Brazil", index: "C6" },
                { name: "Canada", index: "C7" }, { name: "China", index: "C8" },
                { name: "Cuba", index: "C9" },
                { name: "Denmark", index: "C10" }, { name: "Dominica", index: "C11" },
                { name: "Europe", index: "C12" }, { name: "Egypt", index: "C13" },
                { name: "England", index: "C14" },
                { name: "India", index: "C15" }, { name: "Indonesia", index: "C16" }
                ];
        angular.module('AutoCompleteApp', ['ejangular'])
             .controller('AutocompleteCtrl', function ($scope) {                
                 $scope.dataList = countriesField;
$scope.key="index";
$scope.text="name";
             });
    </script>


{% endhighlight %}



Run the above code to render the following output. 

![](data-binding_images\local-data_img1.png)


### Remote data

#### OData

[OData](http://help.syncfusion.com/js/datamanager/data-binding) is a standardized protocol for creating and consuming the data. You can retrieve data from OData service by using [ej.DataManager](http://help.syncfusion.com/js/datamanager/getting-started).

Here the ContactName and SupplierID fields are mapped with text and key properties respectively, of the field object. The queries can be created using [ej.Query()](http://helpjs.syncfusion.com/js/datamanager/query).



{% highlight html %}


<input type="text" ej-autocomplete e-datasource="dataList" e-query="query" e-fields-key="key" e-fields-text="text" e-width="205" />

<script type="text/javascript">
         var dataManger = ej.DataManager({              
                url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"
                });              
                var query = ej.Query().from("Suppliers").select("SupplierID", "ContactName");
        angular.module('AutoCompleteApp', ['ejangular'])
             .controller('AutocompleteCtrl', function ($scope) {                
                 $scope.dataList = dataManger;
$scope.query=query;
$scope.key="SupplierID";
$scope.text="ContactName";
             });
    </script>



{% endhighlight %}



Run the above code to render the following output. 

![](data-binding_images\odata_img1.png)


#### WebAPI

[ASP.NET Web API](https://msdn.microsoft.com/en-us/library/hh833994(v=vs.108).aspx) is a Framework for building HTTP services. You can retrieve data from ASP.NET Web API by using [ej.DataManager](http://helpjs.syncfusion.com/js/datamanager/getting-started).

Here the ContactName field is mapped with text property of the field object.

{% highlight html %}


                            <input type="text" ej-autocomplete e-datasource="dataList" e-fields-text="text" e-fields-key="key"  e-width="205" />

<script type="text/javascript">
        var dataManger = ej.DataManager({
                /* ASP.NET Web API */
                url: "api/Suppliers",
                crossDomain: true
                });        
        angular.module('AutoCompleteApp', ['ejangular'])
             .controller('AutocompleteCtrl', function ($scope) {                
                 $scope.dataList = dataManger;				 
                  $scope.text="ContactName"
                  $scope.key="SupplireID";
             });
    </script>


{% endhighlight %}



Run the above code to render get the following output. 

![](data-binding_images\webapi_img1.png)



NOTE

In the above data manager configuration, “crossDomain” must be set to true to access the data from Web API. [Cross domain](http://helpjs.syncfusion.com/js/grid/data-binding) requests can be possible using ej.DataManager.



#### Handling errors

In remote binding, the server might not return data sometimes due to various reasons. In such cases we need to handle the error properly. We can handle this errorsusing the “[e-actionFailure](http://help.syncfusion.com/api/js/ejautocomplete)” event.


#### See Also

[e-actioncomplete](http://help.syncfusion.com/api/js/ejautocomplete) event

[e-actionsuccess](http://help.syncfusion.com/api/js/ejautocomplete) event

{% highlight html %}


     <input type="text" ej-autocomplete e-datasource="dataList" e-fields-text="text" e-fields-key="key" e-query="query" e-actionfailure="onRequestFailure" e-width="100%" />

<script type="text/javascript">
     var dataManger = ej.DataManager({
                /* Web service host */
                url: "http://mvc.syncfusion.com/Services/"
                });
                /* Query creation */
                var query = ej.Query().from("Suppliers").select("SupplierID", "ContactName");   
        angular.module('AutoCompleteApp', ['ejangular'])
             .controller('AutocompleteCtrl', function ($scope) {                
                 $scope.dataList = dataManger;	
                 $scope.query=query;
                 $scope.key="SupplierID";			 
$scope.text="ContactName";
             });

                function onRequestFailure(args) {
                //Error handler
                }
    </script>


{% endhighlight %}




