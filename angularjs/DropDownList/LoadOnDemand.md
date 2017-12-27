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

The popup and lists will be generated while click on dropdown icon or text box. For this feature, the loadOnDemand property must be enabled.

{% highlight html %}

    <input id="bookSelect" ej-dropdownlist e-datasource="dataList" e-value="value" e-width="width" e-loadOnDemand="loadOnDemand" />
          
     
{% endhighlight %}

{% highlight javascript %}
  
       var list = [
                    { empid: "cr1", text: "Dodge Avenger", value: "Dodge Avenger" },
                    { empid: "cr2", text: "Chrysler 200", value: "Chrysler 200" },
                    { empid: "cr3", text: "Ford Focus", value: "Ford Focus" },
                    { empid: "cr4", text: "Ford Taurus", value: "Ford Taurus" },
                    { empid: "cr5", text: "Dazzler", value: "Dazzler" },
                    { empid: "cr6", text: "Chevy Spark", value: "Chevy Spark" },
                    { empid: "cr7", text: "Chevy Volt", value: "Chevy Volt" },
                    { empid: "cr8", text: "Honda Fit", value: "Honda Fit" },
                    { empid: "cr9", text: "Honda Crosstour", value: "Honda Crosstour" },
                    { empid: "cr10", text: "Acura RL", value: "Acura RL" },
                    { empid: "cr11", text: "Hyundai Elantra", value: "Hyundai Elantra" },
                    { empid: "cr12", text: "Mazda3", value: "Mazda3" }
];

angular.module('dropdownlistApp', ['ejangular'])
.controller('DropDownCtrl', function ($scope) {
        $scope.dataList = list;
        $scope.value = "Ford Focus";
        $scope.width = "100%";
		$scope.londOnDemand = true;
    });


{% endhighlight %}

![](LoadOnDemand/loadondemand.png)