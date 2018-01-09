---
layout: post
title: Load on demand in DropDownList widget
description: Load on demand in DropDownList widget
platform: AngularJS
control: DropDownList
documentation: ug
keywords: loadOnDemand, DropDownList, dropdown

---
## Load On Demand

Load on demand feature allows the DropDownList items load on request from the service/database, during only on click the DropDown icon or DropDownList. This functionality helps to improve performance on control initial rendering time. Because data items load on request. 

The loadOnDemand property is used to enable or disable the load on demand functionality of the DropDownList.

{% highlight html %}

    <input id="bookSelect" ej-dropdownlist e-datasource="dataList" e-value="value" e-width="width" e-loadOnDemand="loadOnDemand" />
          
     
{% endhighlight %}

{% highlight javascript %}
  
       var list = [
                    { id: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
                    { id: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
                    { id: "cr3", text: "Ford Focus", value: "Ford Focus" },
                    { id: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
                    { id: "cr5", text: "Dazzler", value: "Dazzler" },
                    { id: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
                    { id: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
                    { id: "cr8", text: "Honda Fit", value: "Honda Fit" },
                    { id: "cr9", text: "Honda Cross tour", value: "Honda Cross tour" },
                    { id: "cr11", text: "Hyundai Elantra", value: "Hyundai Elantra" },
                    { id: "cr12", text: "Mazda3", value: "Mazda3" }
];

angular.module('dropdownlistApp', ['ejangular'])
.controller('DropDownCtrl', function ($scope) {
        $scope.dataList = list;
        $scope.value = "Ford Focus";
        $scope.width = "100%";
		$scope.loadOnDemand = true;
    });


{% endhighlight %}

![](LoadOnDemand_images/loadondemand.png)