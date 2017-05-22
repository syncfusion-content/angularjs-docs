---
layout: post
title: Virtual Scrolling
description: virtual scrolling
platform: Angular-1
control: ListView
documentation: ug
---

# Virtual Scrolling

   We can load large data on demand using "e-allowvirtualscrolling" property. By default, "e-allowvirtualscrolling" set as boolean value of **"false"**. When it is set true, list items will be loaded on every scroll action. The number of items to be loaded per request can be specified using the “e-itemrequestcount” property.By default “e-itemrequestcount” value will be 5. We have provided two type of option for virtualScrolling,

## Normal Mode
    This mode allows you to load the list view data while scrolling i.e. each time the scroll bar is scrolled, it will send request to the server to load the data.

## Continuous Mode
    This mode allows you to load the list view data when the scrollbar reaches the end point. In this mode, we can specify the number of items to be loaded per request.

Please refer the following code examples.

 {% highlight html %}

    <div class="listviewsample" ng-controller="ListViewCtrl">
        <div class="content-container-fluid listview-sample">
            <div class="row">
                <div class="cols-sample-area">
                    <div ej-listview id="anglistview" e-width="400" e-height="300" e-query="query" e-datasource="datalist" e-fieldsettings="settings" e-allowvirtualscrolling="true" e-virtualscrollingmode="continuous" >
                      </div>
                   </div>
            </div>
        </div>
    </div>

 {% endhighlight %}

 Add the following script in your code.

 {% highlight js %}

    syncApp.controller('ListViewCtrl', function ($scope, $rootScope) {
    var dataManger = ej.DataManager({              
        url: "http://js.syncfusion.com/ejservices/Wcf/Northwind.svc/"
        });              
       var query = ej.Query().from('Customers');
        $scope.continuous = "continuous";
        $scope.datalist = dataManger;
        $scope.query=query;
        $scope.settings = {
            "text": "CustomerID"
        };
      });

 {% endhighlight %}