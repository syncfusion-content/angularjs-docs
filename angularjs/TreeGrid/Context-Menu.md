---
layout: post
title: Context-Menu
description: context menu
platform: AngularJS
control: TreeGrid
documentation: ug  
---

# Context Menu

The **Context menu** in tree grid control is used to manipulate (add, edit, and delete) the tree grid rows. In tree grid, context menu can be enabled with the [`e-contextmenusettings`](/api/js/ejtreegrid#contextmenusettingsspan-classtype-signature-type-objectobjectspan "contextMenuSettings") property. The `e-contextmenusettings` property contains two inner properties [`e-showcontextmenu`](/api/js/ejtreegrid#contextmenusettingsshowcontextmenuspan-classtype-signature-type-booleanbooleanspan "contextMenuSettings.showContextMenu") and [`contextMenuItems`](/api/js/ejtreegrid#contextmenusettingscontextmenuitemsspan-classtype-signature-type-arrayarrayspan "contextMenuSettings.contextMenuItems").

The `showContextMenu` property is used to **enable or disable** the context menu, default value for this property is `false`.

The `contextMenuItems` property is used to add the menu items to context menu, this property renders `Add` and `Delete` options by default when the menu items are not provided.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-editsettings="editSettings"
    e-contextmenusettings="contextMenuSettings">
    </div>
    <script>
    var editSettings = {allowEditing: true , editMode:"rowEditing"}
    var contextMenuSettings = {showContextMenu: true 
                                contextMenuItems:[ "add","edit","delete"]},
    angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function($scope) {
            //...
            $scope.editSettings = "editSettings";
            $scope.contextMenuSettings = "contextMenuSettings";
        });
</script>
</body>

{% endhighlight %}

The following screenshot displays the context menu in tree grid control:       

![](Context-Menu_images/Context-Menu_img1.png)

### ContextMenu Customization

Context menu can be customized by adding a new custom menu item to it. In tree grid, context menu can be customized using the [`e-contextmenuopen`](/api/js/ejtreegrid#contextmenuopen "contextMenuOpen") client side event. This event is triggered when the context menu is rendered with mouse right click action. The following properties are available in the event:

* headerText: Displays text for menu item.
* menuId: Provides ID field for the created DOM element for custom menu item.
* iconPath: Image location for menu item.
* eventHandler: Client side event for menu item click.

{% highlight js %}

<body ng-controller="TreeGridCtrl">
    <!--Add  treegrid control here-->
    <div id="TreeGridContainer" ej-treegrid //... 
    e-contextmenusettings="contextMenuSettings" 
    e-contextmenuopen="customMenu">
    </div>
    <script>
        var contextMenuSettings = {
            showContextMenu: true
        }
        function customMenu(args) {
            args.contextMenuItems.push({
                headerText: "Custom Menu",
                menuId: "customMenu",
                iconPath: "url(.../images/customMenu.png)",
                eventHandler: customMenuClick,
            });
        }
        function customMenuClick(args) {
            // ...
        }
        angular.module('listCtrl', ['ejangular'])
            .controller('TreeGridCtrl', function($scope) {
                //...
                $scope.customMenu = "customMenu";
                $scope.contextMenuSettings = "contextMenuSettings";
            });
    </script>
</body>

{% endhighlight %}

The following screenshot displays the customization of context menu in tree grid control:

![](Context-Menu_images/Context-Menu_img2.jpg)

