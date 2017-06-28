---
layout: post
title: Editing
description: editing
platform: AngularJS
control: TreeGrid
documentation: ug
---

# Editing

The TreeGrid control provides built-in support for editing cell items. 

## Cell Editing

Update the task details through cell editing by setting [`editMode`](/api/js/ejtreegrid#editsettingseditmodespan-classtype-signature-type-stringstringspan "editSettings.editMode") as `cellEditing`.

The following code example shows you how to enable `cellEditing` in TreeGrid control.

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

The output of the TreeGrid with `cellEditing` is as follows.

![](Editing_images/Editing_img1.png)

