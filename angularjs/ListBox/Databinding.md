---
layout: post
title: Syncfusion ListBox Databinding
description: databinding
platform: AngularJS
control: ListBox
documentation: ug
---

# Data binding

## Field mapping

The ListBox component has a field property (object) which holds the properties to map with datasource fields. For example, the field object has a text property which is necessary to map with specific field in the datasource to render the items in the ListBox component.

The field object contains the following [`properties`](http://help.syncfusion.com/js/api/ejlistbox#members:fields) such as text, id, etc. 

## Local data

The local data can be an array of JSON objects which is assigned for the datasource property of ListBox component.

Here the empId and text are fields with it's mapped to the id and value fields of object respectively.

{% highlight html %}

    <div id="control">
        <ul id="selectbike" ej-listbox e-datasource="dataList" e-fields-id="id" e-fields-value="value"></ul>
    </div>    

{% endhighlight %}

{% highlight javascript %}

     $scope.dataList = [
              { empId: "bk1", text: "RTR" }, { empId: "bk2", text: "CBR 150-R" }, { empId: "bk3", text: "CBZ Xtreme" },
              { empId: "bk4", text: "Discover" }, { empId: "bk5", text: "Dazzler" }, { empId: "bk6", text: "Flame" },
              { empId: "bk7", text: "FZ-S" }, { empId: "bk8", text: "Pulsar" },
              { empId: "bk9", text: "Shine" }, { empId: "bk10", text: "R15" }, { empId: "bk11", text: "Unicorn" }
             ];
     $scope.id = "empId";
     $scope.value = "text";

{% endhighlight %}

![FieldSetting Listbox](Databinding_images\Databinding_img1.png)

## Remote data

### OData

[OData](http://helpjs.syncfusion.com/js/datamanager/data-binding) is a standardized protocol for creating and consuming the data. You can retrieve data from OData service by using [ej.DataManager](http://helpjs.syncfusion.com/js/datamanager/getting-started).

Here the CustomerID field is mapped with text property of the field object. The queries can be created using [ej.Query()](http://helpjs.syncfusion.com/js/datamanager/query).

{% highlight html %}

     <div id="control">
        <ul id="selectcustomer" ej-listbox e-datasource="dataList" e-query="query" e-fields-text="text"></ul>
    </div>   

{% endhighlight %}

{% highlight javascript %}

     $scope.dataList = dataManger = ej.DataManager({
                 url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"
             });
     $scope.query = ej.Query().from("Customers").take(10);
     $scope.text = "CustomerID";

{% endhighlight %}

![Alt text](Databinding_images\Databinding_img2.png)

### WebAPI

[ASP.NET Web API](https://msdn.microsoft.com/en-us/library/hh833994%28v=vs.108%29.aspx) is a Framework for building HTTP services. You can retrieve data from ASP.NET Web API by using [ej.DataManager](http://helpjs.syncfusion.com/js/datamanager/getting-started).

{% highlight html %}    

<div id="control">
        <ul id="selectcustomer" ej-listbox e-datasource="dataList" e-fields="fields"></ul>
    </div>   

{% endhighlight %}

{% highlight javascript %}

 $scope.dataList = ej.DataManager({
                 url: "http://mvc.syncfusion.com/UGService/api/Orders",
                 crossDomain: true
             });
 $scope.fields = { text: "CustomerID" };

{% endhighlight %}

N> _In the above data manager configuration, “crossDomain” must be set to true to access the data from Web API._

 {% seealso %} [Cross domain](http://help.syncfusion.com/js/grid/data-binding) {% endseealso %}

![Alt text](Databinding_images\Databinding_img3.png)


### Handling errors

 In remote binding, the server might not return data sometimes due to various reasons. In such cases we need to handle the error properly. We can handle it using the “actionFailure” event. 

{% seealso %} [actionComplete](http://help.syncfusion.com/js/api/ejlistbox#events:actioncomplete) and [actionSuccess](http://help.syncfusion.com/js/api/ejlistbox#events:actionsuccess) {% endseealso %}

{% highlight javascript %}

     <div id="control">
        <ul id="selectcustomer" ej-listbox e-datasource="dataList" e-fields-text="text" e-query="query" e-actionfailure="onFailure"></ul>
    </div>

{% endhighlight %}

{% highlight javascript %}

             $scope.dataList = ej.DataManager({
                 url: "http://mvc.syncfusion.com/Services/Northwnd.svc/",
                 crossDomain: true
             });
             $scope.query = ej.Query().from("Customers");
             $scope.text = "CustomerID";
             $scope.onFailure = function (args) {
                    //handle errors
             };

{% endhighlight %}












