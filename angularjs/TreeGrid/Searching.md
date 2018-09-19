---
layout: post
title: Searching
description: Searching
platform: AngularJS
control: TreeGrid
documentation: ug
---

## Searching

The TreeGrid control has an option to search its content using toolbar search box. The toolbar search box can be enabled by using the `toolbarItems` in [`e-toolbarsettings`](/api/angular/ejtreegrid#members:toolbarsettings) property. The following code example explains how to integrate search textbox in toolbar.

{% highlight html %}  
           <div id="angulartreegrid" ej-treegrid e-toolbarsettings="toolbarSettings"></div>            
{% endhighlight %}
{% highlight js %}
var toolbarSettings =
{
    toolbarItems: [        
            ej.TreeGrid.ToolbarItems.Search
        ],
}       
angular.module('listCtrl', ['ejangular'])
       .controller('TreeGridCtrl', function ($scope) {      
              $scope.toolbarSettings = toolbarSettings;
        });
    </script>   
</body>
{% endhighlight %}

The below screenshot shows TreeGrid search with `plan` key word.
![](Searching_images/Searching_img1.png)

## Search Hierarchy Modes

The tree grid supports different types of search mode through the `searchHierarchyMode`of [`e-searchsettings`](/api/angular/ejtreegrid#members:searchsettings-searchhierarchymode) property.

The following are the types of search mode available in the tree grid.

**Parent**: This is the default search hierarchy mode in the tree grid. It displays searched record with its parent records. If the searched records do not have any parent record, it displays only the searched record.

**Child**: Displays the searched record with its child record. If the searched records do not have any child record, it displays only the searched record.

**Both**: Displays the searched record with its both parent and child records. If the searched records do not have any parent and child records, it displays only the searched record.

**None**: Displays only the searched record.

The following code example shows how to set the `searchHierarchyMode` in the tree grid.

{% highlight html %}

<div ej-treegrid id="treegrid" e-searchsettings="searchSettings" //…>
</div>


{% endhighlight %}

{% highlight js %}

     angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function ($scope) {
            $scope.searchSettings = searchSettings;
            //…
        });

{% endhighlight %}

The following image depicts the output of above code example
![](Searching_images/SearchHierarchyModes_img1.png)

The above screenshot shows Tree Grid with `child` search mode.

