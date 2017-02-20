---
layout: post
title: Toolbar
description: toolbar
platform: Angular-1
control: TreeGrid
documentation: ug
---

# Toolbar

TreeGrid control contains toolbar options for adding, deleting and editing the records. You can customize the TreeGrid toolbar by using [`e-toolbarsettings`](/api/js/ejtreegrid#toolbarsettingsspan-classtype-signature-type-objectobjectspan "toolbarSettings") property. 

In TreeGrid by using [`rowPosition`](/api/js/ejtreegrid#editsettingsrowpositionspan-classtype-signature-type-stringstringspan "editSettings.rowPosition") property, the index position for the newly added row can be provided. Default value of the `rowPosition` property is `top`. The enumeration values for `rowPosition` properties are,

* top
* bottom
* aboveSelectedRow
* belowSelectedRow

You can enable toolbar for TreeGrid, using the following code example.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-editsettings="editSettings" 
    e-toolbarsettings="toolbarSettings">
    </div>
    <script>
    var  editSettings= {
        //...
        rowPosition: "aboveSelectedRow"
    },
    var  toolbarSettings= {
        showToolbar: true,
        toolbarItems: [
            ej.TreeGrid.ToolbarItems.Add,
            ej.TreeGrid.ToolbarItems.Edit,
            ej.TreeGrid.ToolbarItems.Delete,
            ej.TreeGrid.ToolbarItems.Update,
            ej.TreeGrid.ToolbarItems.Cancel,
            ej.TreeGrid.ToolbarItems.ExpandAll
            ej.TreeGrid.ToolbarItems.CollapseAll
        ],
    }
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.editSettings = "editSettings";
                $scope.toolbarSettings = "toolbarSettings";
            });
    </script>
</body>

{% endhighlight %}

The following screenshot displays the toolbar option in TreeGrid control.

![](Toolbar_images/Toolbar_img1.png)

