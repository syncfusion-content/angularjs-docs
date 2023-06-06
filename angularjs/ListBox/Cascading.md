---
layout: post
title: Cascading in AngularJS ListBox Control | Syncfusion
description: Learn here all about cascading support in Syncfusion Essential AngularJS ListBox control, its features, and more.
platform: AngularJS
control: ListBox
documentation: ug
---

# Cascading in AngularJS ListBox

To dynamically populate list items to another list box while selecting the list item in list box. i.e. rendering the child list box based on the item selection in parent list box. This can be achieved by using “cascadeTo” property.

Create an ul elements to render the both parent and child ListBox components as like below.

{% highlight html %}

        <div>
            <ul id="groupsList" ej-listbox e-cascadeto="countryList" e-datasource="data" e-fields="fields"></ul>
        </div>
        <div>
            <ul id="countryList" ej-listbox e-datasource="dataList2" e-loaddataoninit="false" e-fields="fields"></ul>
        </div>
        
{% endhighlight %}

The child ListBox component id should mapping to the “cascadeTo” property of the parent ListBox component. To show the empty data of the child ListBox on component initialization by setting the “loadDataOnInit” property as false.

{% highlight javascript %}
            
             $scope.data = [
                { parentId: 'a', text: "Group A" },
                { parentId: 'b', text: "Group B" },
                { parentId: 'c', text: "Group C" },
                { parentId: 'd', text: "Group D" },
                { parentId: 'e', text: "Group E" },
                { parentId: 'f', text: "Group F" },
                { parentId: 'g', text: "Group G" },
                { parentId: 'h', text: "Group H" },
                { parentId: 'i', text: "Group I" },
                { parentId: 'j', text: "Group J" }
             ];

             $scope.fields = { "value": "parentId", "text": "text" };
             $scope.cascading = "countryList";
             $scope.dataList2 = [{ value: 11, parentId: 'a', text: "Algeria" },
                { value: 12, parentId: 'a', text: "Armenia"},
                { value: 13, parentId: 'a', text: "Bangladesh" },
                { value: 14, parentId: 'a', text: "Cuba"},
                { value: 15, parentId: 'b', text: "Denmark"},
                { value: 16, parentId: 'b', text: "Egypt"},
                { value: 17, parentId: 'c', text: "Finland"},
                { value: 18, parentId: 'c', text: "India"},
                { value: 19, parentId: 'c', text: "Malaysia"},
                { value: 20, parentId: 'd', text: "New Zealand"},
                { value: 21, parentId: 'd', text: "Norway"},
                { value: 22, parentId: 'd', text: "Poland"},
                { value: 23, parentId: 'e', text: "Romania"},
                { value: 24, parentId: 'e', text: "Singapore"},
                { value: 27, parentId: 'f', text: "Falkland Islands"},
                { value: 30, parentId: 'g', text: "Germany"},
                { value: 34, parentId: 'h', text: "Hong Kong"},
                { value: 35, parentId: 'h', text: "Haiti"},
                { value: 36, parentId: 'i', text: "Iceland"},
                { value: 40, parentId: 'j', text: "Japan"},
                { value: 41, parentId: 'j', text: "Jordan"},
             ];
{% endhighlight %}

![Cascading](Cascading_images\Cascading_img1.png)

## Multilevel cascading

Refer to the following code example which is expanded from the above example, to achieve multi-level (three level here) cascading of the ListBox component.

Create an ul elements to render the parent and the child ListBox component as below.

{% highlight html %}
      
    <div id="control">
        <div class="contents">
            <ul id="groupsList" ej-listbox e-cascadeto="cascading" e-datasource="data" e-fields="fields"></ul>
        </div>
        <div class="contents">
            <ul id="countryList" ej-listbox e-cascadeto="firstChild" e-datasource="firstLevelChildData" e-loaddataoninit="false" e-fields="firstChildFields"></ul>
        </div>
        <div class="contents">
            <ul id="productList" ej-listbox e-cascadeto="secondChild" e-datasource="secondLevelChildData" e-loaddataoninit="false" e-fields="secondChildFields"></ul>
        </div>
        <div class="contents">
            <ul id="subProductList" ej-listbox e-datasource="thirdLevelChildData" e-loaddataoninit="false"></ul>
        </div>
    </div>

{% endhighlight %}

The child ListBox component id should mapping to the “cascadeTo” property of the parent ListBox component. To show the empty data of the child ListBox on component initialization by setting the “loadDataOnInit” property as false.

{% highlight javascript %}

        $scope.data = [
                { categoryId: 'a', text: "Clothing" },
                { categoryId: 'b', text: "Furniture" }];

             $scope.firstLevelChildData = [{ subCategoryId: 11, categoryId: 'a', text: "Men" },
                { subCategoryId: 12, categoryId: 'a', text: "Women" },
                { subCategoryId: 13, categoryId: 'b', text: "Home furniture" },
                { subCategoryId: 14, categoryId: 'b', text: "Bedding" }];

             $scope.secondLevelChildData = [{ productId: 101, subCategoryId: 11, text: "men shirts" },
                 { productId: 102, subCategoryId: 11, text: "men pants" },
                 { productId: 103, subCategoryId: 12, text: "Women shirts" },
                 { productId: 104, subCategoryId: 12, text: "Women pants" },
                 { productId: 105, subCategoryId: 13, text: "sofa" },
                 { productId: 106, subCategoryId: 13, text: "chairs" },
                 { productId: 107, subCategoryId: 14, text: "bedsheets" },
                 { productId: 108, subCategoryId: 14, text: "pillows" }];

             $scope.thirdLevelChildData = [{ productId: 101, text: "red men shirts" },
                 { productId: 101, text: "blue men shirts" },
                 { productId: 102, text: "red men pants" },
                 { productId: 102, text: "blue men pants" },
                 { productId: 103, text: "blueWomen shirts" },
                 { productId: 103, text: "red Women shirts" },
                 { productId: 104, text: "red women pants" },
                 { productId: 104, text: "blue women pants" },
                 { productId: 105, text: "red sofa" },
                 { productId: 105, text: "blue sofa" },
                 { productId: 106, text: "red chairs" },
                 { productId: 106, text: "blue chairs" },
                 { productId: 107, text: "red bedsheets" },
                 { productId: 107, text: "blue bedsheets" },
                 { productId: 108, text: "red pillows" },
                 { productId: 108, text: "blue pillows" }];

             $scope.fields = { "value": "categoryId" };
             $scope.firstChildFields = { "value": "subCategoryId" };
             $scope.secondChildFields = { "value": "productId" };
             $scope.cascading = "countryList";
             $scope.firstChild = "productList";
             $scope.secondChild = "subProductList";
             $scope.width = "100%";

{% endhighlight %}

![Multilevel cascading](Cascading_images\Cascading_img2.png)