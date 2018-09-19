---
layout: post
title: Editing
description: editing
platform: AngularJS
control: TreeGrid
documentation: ug
---

# Editing

The tree grid control provides built-in support for editing cell items.    

## Cell Editing

Update the task details through cell editing by setting [`editMode`](https://help.syncfusion.com/api/js/ejtreegrid#members:editsettings-editmode "editSettings.editMode") to `cellEditing`.
             
The following code example shows how to enable `cellEditing` in the tree grid control.                               

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-editsettings="editSettings">
    </div>
    <script>
    var editSettings = { allowEditing: true,
            editMode: "cellEditing"}
    angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function($scope) {
            //...
            $scope.editSettings = "editSettings";
        });
</script>
</body>
{% endhighlight %}

The output of the tree grid with `cellEditing` is as follows:                                                                  

![](Editing_images/Editing_img1.png)

### Batch Editing

The batch editing support in the tree grid is used to save all added, edited, and deleted changes to the database with single action. This can be enable by setting the [`editMode`](https://help.syncfusion.com/api/js/ejtreegrid#members:editsettings-editmode) property to `batchEditing`. The following code example shows how to enable the batchEditing in the tree grid control.

{% highlight html %}

<div ej-treegrid id="treegrid" e-editsettings="editSettings">
</div>

{% endhighlight %}

{% highlight js %}

angular.module('listCtrl', ['ejangular'])
       .controller('TreeGridCtrl', function ($scope) {
           $scope.editSettings = { allowEditing: true, editMode: "batchEditing"};
           $scope.rowHeight = 83;
       });

{% endhighlight %}

The output of the tree grid with `batchEditing` is obtained as follows.

![](Editing_images/BatchEdit_img1.png)


In batch editing, the edit mode can be changed to **cell** or **row** or **dialog** with the [`batchEditSettings.editMode`](https://help.syncfusion.com/api/js/ejtreegrid#members:editsettings-batcheditsettings-editmode) property. The following code snippet shows how to set the editMode to row in the [`batchEditSettings`](https://help.syncfusion.com/api/js/ejtreegrid#members:editsettings-batcheditsettings) property.

{% highlight html %}

<ej-treegrid id="TreeGridControl"
    [editSettings]= "editSettings">
</ej-treegrid>

{% endhighlight %}

{% highlight js %}

angular.module('listCtrl', ['ejangular'])
       .controller('TreeGridCtrl', function ($scope) {
           $scope.editSettings = {batchEditSettings:{editMode : ej.TreeGrid.BatchEditMode.Row};
           $scope.rowHeight = 83;
       });

{% endhighlight %}

The output of the tree grid with `batchEditSettings` and `editMode` as `row` is as obtained follows.

![](Editing_images/BatchEdit_img2.png)


N> After modifying all changes in the tree grid, click the save button in the toolbar. The [`actionComplete`](https://help.syncfusion.com/api/js/ejtreegrid#events:actioncomplete) event will be triggered with updated records in the `batchChanges` argument with `requestType` argument as `batchSave`. Using this event, you can update all the modified records to the database.

