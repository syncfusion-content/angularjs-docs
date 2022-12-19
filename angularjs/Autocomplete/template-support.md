---
layout: post
title: Template Support in AngularJS AutoComplete Control | Syncfusion
description: Learn here about Template support in Syncfusion Essential AngularJS AutoComplete control, its elements, and more.
platform: AngularJS
control: Autocomplete
documentation: ug
---

# Template Support in Essential AngularJS AutoComplete

The suggestion list can be customized based on different needs using templates. The desired templates can be defined using the “e-template” property.

{% highlight html %}

  <input type="text" ej-autocomplete e-dataSource="dataList" e-fields-text="text" e-template="template" e-width="100%" />


   <script type="text/javascript">
          var mobileList = [
                { pName: "Galaxy Grand 2", quantity: "3" },
                { pName: "Galaxy S6", quantity: "5" },
                { pName: "IPhone S6", quantity: "8" },
                { pName: "Ipod Mini", quantity: "3" }, 
];
        angular.module('AutoCompleteApp', ['ejangular'])
             .controller('AutocompleteCtrl', function ($scope) {                
                 $scope.dataList = mobileList;
                 $scope.text="pName";
                 $scope.template="<div><div class='product-text'>${pName}</div> <span class='product-quantity' style='font-size:10px'> Quantity : ${quantity}</span></div>";
             });
    </script>



{% endhighlight %}



Run the above code to render the following output. 

![Template Support in AngularJS AutoComplete](template-support_images\template-support_img1.png)

