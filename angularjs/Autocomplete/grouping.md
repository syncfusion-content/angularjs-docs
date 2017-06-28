---
layout: post
title: grouping
description: grouping
platform: angular-1
control: Autocomplete
documentation: ug
---

## Grouping

The suggestion list items can be grouped by providing a header for each set of items. The grouping will be defined based on the **e-groupby** in fields object.

Here the category field is mapped with **e-groupby** field.

{% highlight html %}


<input type="text" ej-autocomplete e-datasource="dataList" e-filtertype="filtertype" e-fields-text="text" e-fields-groupby="category" e-width="100%" />

<script type="text/javascript">
         var countries = [
                { text: "Australia", category: "A" }, { text: "Antarctica", category: "A" },
                { text: "Bangladesh", category: "B" }, { text: "Belgium", category: "B" },
                { text: "Canada", category: "C" }, { text: "China", category: "C" },
                { text: "Denmark", category: "D" }, { text: "Dominica", category: "D" },
                { text: "Europe", category: "E" }, { text: "Egypt", category: "E" },
                { text: "India", category: "I" }, { text: "Indonesia", category: "I" },
                { text: "France", category: "F" }, { text: "Finland", category: "F" },
                { text: "Germany", category: "G" }, { text: "Greece", category: "G" },
                { text: "Japan", category: "J" }, { text: "Jordan", category: "J" },
                { text: "Madagascar", category: "M" }, { text: "Midway Islands", category: "M" },
                { text: "Nepal", category: "N" }, { text: "Netherlands", category: "N" },
                { text: "Qatar", category: "Q" }, { text: "Romania", category: "R" },
                { text: "Scotland", category: "S" }, { text: "Tibet", category: "T" },
                { text: "Zambia", category: "Z" }, { text: "Zimbabwe", category: "Z" }
        ];
        angular.module('AutoCompleteApp', ['ejangular'])
             .controller('AutocompleteCtrl', function ($scope) {                
                 $scope.dataList = countries;
                 $scope.text="text";
                 $scope.category="category";
                 $scope.filtertype=ej.FilterType.Contains;
             });
    </script>


{% endhighlight %}





Run the above code to render get the following output. 



![](grouping_images\grouping_img1.png)

