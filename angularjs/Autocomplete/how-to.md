---
layout: post
title: How to in AngularJS Autocomplete control | Syncfusion
description: Learn here on how to support in Syncfusion AngularJS Autocomplete control, its elements, and more.
platform: AngularJS
control: Autocomplete
documentation: ug
---


# How To in AngularJS Autocomplete

## Set Client Side Validation for Autocomplete?

Since the Autocomplete is a form control, we can set the validation for Autocomplete on form submission. We can use the **e-validationrules** property to set the validation rules and **e-validationmessage** property to display the error message on form validation.



**NOTE**

[jquery.validate.min](http://cdn.syncfusion.com/js/assets/external/jquery.validate.min.js) script file should be referred for validation, for more details, refer[here.](https://jqueryvalidation.org/documentation/)

{% highlight html %}


<!DOCTYPE html>
<html lang="en" ng-app="AutoCompleteApp">
<head>
    <title>Essential Studio for JavaScript : AngularJS Support for Autocomplete</title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/14.4.0.15/js/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.1.1.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.validate.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/14.4.0.15/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/14.4.0.15/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="AutocompleteCtrl">

</html>



{% endhighlight %}



{% highlight html %}


   <form id="form1">
                    <h3>Select Car</h3>
                            <input type="text" ej-autocomplete e-dataSource="dataList" e-multiSelectMode="multiselect" e-width="300" e-validationrules="validRules" e-validationmessage="validMessage" e-watermarktext="select a car" />
                        <input type="submit" value="validate" id="btn" />    

                    </form>


{% endhighlight %}



{% highlight html %}


<script type="text/javascript">
        $.validator.setDefaults({
            ignore: [],
            errorClass: 'e-validation-error',
            errorPlacement: function (error, element) {
                $(error).insertAfter(element.closest(".e-widget"));
            }
            // any other default options and/or rules
        });
        angular.module('AutoCompleteApp', ['ejangular'])
             .controller('AutocompleteCtrl', function ($scope) {                
                 $scope.dataList = carList;
                 $scope.validRules = {
                     required: true
                 };
                 $scope.validMessage = {
                     required: "please select some value"
                 }
             });
    </script>


{% endhighlight %}





![Set client side validation in AngularJS Autocomplete](how-to_images\set-client-side-validation-for-autocomplete_img1.png)

**NOTE**

jQuery predefined error messages to that annotation attribute will be shown when this property is not defined. The below given example explain this behavior of ‘required’ attribute.


### Get the key value of the selected item?



By default, the selected item’s key value will be maintained in the **e-selectvaluebykey** model value. If we take the instance of the autocomplete and in the model, the selected value’s key will be maintained in the **e-selectvalueBykey** property.


{% highlight html %}

  <input type="text" ej-autocomplete e-datasource="dataList" e-fields-key="key" e-fields-text="text" e-selectvaluebykey="keyValue" e-width="30%" />



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

                  $scope.keyValue = "C6";

             });

    </script>
{% endhighlight %}




![Get the key value in AngularJS Autocomplete](how-to_images\get-the-key-value-of-the-selected-item_img1.png)



But when using the remote datasource, we cannot able to maintain the key value in the **e-selectvaluekey** model property. Hence in that case we can use the **e-select** property to get the key value in the select event’s argument.

{% highlight html %}


<input type="text" ej-autocomplete e-datasource="dataList" e-query="query" e-fields-key="key" e-fields-text="text" e-select="onSelect" e-width="205" />

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
                $scope.onSelect= function (args){
                         // Get the key here
                      myKey= args.key;

}
             });
    </script>





{% endhighlight %}