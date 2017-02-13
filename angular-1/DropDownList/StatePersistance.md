---
layout: post
title: State Persistance with DropDownList widget
description: State Persistence support to DropDownList widget
platform: Angular-1
control: DropDownList
documentation: ug
keywords: Persistence, DropDownList, dropdown, State Persistence
---

# State Persistence

DropDownList stores its model is local storage by defining the property [enablePersistence](http://help.syncfusion.com/api/js/ejdropdownlist#members:enablepersistence).
You can sustain the below given functionalities in DropDownList by enabling persistence property,

* selected items value in the textbox 
* item’s selection state in the popup list 

Widget model will be stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh.
The following properties are not included while maintaining DropDownList’s state in local storage to keep localStorage compact.

* Fields
* Data source
* Query 

{% highlight html %}

 <form id="form1">

	<input type="text" id="dropdown1" ej-dropdownlist e-datasource="data" e-fields-text="text" e-fields-value="value" e-enablepersistence="true" />

	<input type="button" onclick="myFunction()" value="Submit form">

 </form>
     
{% endhighlight %}

{% highlight javascript %}

 	   var items = [{
            text: "Adams",
            value: "emp1"
        }, {
            text: "James",
            value: "emp2"
        }, {
            text: "Maria",
            value: "emp3"
        }, {
            text: "Jessica",
            value: "emp4"
        }, {
            text: "jenneth",
            value: "emp5"
        }];

        angular.module('dropdownlistApp', ['ejangular'])
        .controller('dropdownlistCtrl', function ($scope) {
            $scope.data = items;
        });

        function myFunction() {
            document.getElementById("form1").submit();
        }

{% endhighlight %}