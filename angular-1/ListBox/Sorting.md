---
layout: post
title: Sorting
description: sorting support
platform: Angular-1
control: ListBox
documentation: ug
---

# Sorting

We can change ListBox items rendering order either as ascending or descending, by using "SortOrder" property. By default SortOrder will be "None". Please use code as like in below,

 {% highlight html %}

    <div id="control">
        <ul id="selectbike" ej-listbox e-datasource="dataList" e-fields-id="id" e-fields-value="value" e-sortorder="sortOrder" e-width="100%"></ul>
     </div>

 {% endhighlight %} 

 Please use the below javaScript code to get sorted items in listbox.

 {% highlight javascript %}

            $scope.dataList = [
             { empid: "bk1", text: "Aache RTR" }, { empid: "bk2", text: "CBR 150-R" }, { empid: "bk3", text: "CBZ Xtreme" },
             { empid: "bk4", text: "Discover" }, { empid: "bk5", text: "Dazzler" }, { empid: "bk6", text: "Flame" },
             { empid: "bk7", text: "Fazzer" }, { empid: "bk8", text: "FZ-S" }, { empid: "bk9", text: "Pulsar" },
             { empid: "bk10", text: "Shine" }, { empid: "bk11", text: "R15" }, { empid: "bk12", text: "Unicorn" }
                        ];
            $scope.id = "empid";
            $scope.value = "text";
             $scope.sortorder = ej.sortOrder.Descending;

   {% endhighlight %}

   ![](Sorting-Images\img1.png)