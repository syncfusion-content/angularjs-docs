---
layout: post
title: Virutual-Scrolling
description: Virutual-Scrolling
platform: AngularJS
control: ListBox
documentation: ug
---

# Virtual Scrolling

 The ListBox component provides support to load its data on demand via scrolling behavior to improve the application’s performance. This can be achieved using `allowVirtualScrolling` property. There are two ways to load data based on the scrolling type.

1. Normal scrolling

2. Continuous Scrolling

The scrolling type can be defined via `virtualScrollMode` property.

## **Normal Scrolling**

This mode allows you to load the list box data while scrolling i.e. each time the scroll bar is scrolled, it will send request to the server to load the data.

{% highlight javascript %}

     <div id="control">
        <ul id="selectcustomer" ej-listbox e-datasource="dataList" e-fields-text="text" e-query="query" e-allowvirtualscrolling="true"></ul>
    </div>

{% endhighlight %}

{% highlight javascript %}

             $scope.dataList = ej.DataManager({
                 url: "http://mvc.syncfusion.com/Services/Northwnd.svc/",
                 crossDomain: true
             });
             $scope.query = ej.Query().from("Customers");
             $scope.text = "CustomerID";

{% endhighlight %}

N> _By default, the value of “virtualScrollMode” property is normal._

![Alt text](Databinding_Images\Databinding_img5.png)

## **Continuous Scrolling**

This mode allows you to load the list box data when the scrollbar reaches the end point. In this mode, we can specify the number of items to be loaded per request.

The number of items to be loaded per request can be specified using the “itemRequestCount” property.

{% highlight javascript %}

     <div id="control">
        <ul id="selectcustomer" ej-listbox e-datasource="dataList" e-fields-text="text" e-query="query" e-allowvirtualscrolling="true" e-itemrequestcount="15" e-virtualscrollmode="virtualmode"></ul>
     </div>

{% endhighlight %}

{% highlight javascript %}

             $scope.dataList = ej.DataManager({
                 url: "http://mvc.syncfusion.com/Services/Northwnd.svc/",
                 crossDomain: true
             });
             $scope.query = ej.Query().from("Customers");
             $scope.text = "CustomerID";
             $scope.virtualmode = ej.VirtualScrollMode.Continuous;

{% endhighlight %}

N> _The “itemRequestCount” property will work only when “virtualScrollMode” is “continuous”._

![Alt text](Databinding_Images\Databinding_img7.png)

