---
layout: post
title: grouped list
description: grouped list
platform: AngularJS
control: ListView
documentation: ug
---

## Grouped List

### First Level Group List

The **ListView** can make a grouped list by setting the **e-enablegrouplist** property as **“True”**. This groups the set of items listed under **ul**. You can identify the grouped items with the header title specified respectively.

Refer the following code example.

{% highlight html %}
    <div ej-listview id="anglistview" e-width="width" e-enablegrouplist="grouplist">
                        <ul data-ej-grouplisttitle="Network">
                            <li data-ej-text="Airplane Mode"></li>
                            <li data-ej-text="Wi-Fi"></li>
                            <li data-ej-text="Notifications"></li>
                            <li data-ej-text="Location Services"></li>
                        </ul>
                        <ul data-ej-grouplisttitle="Apps">
                            <li data-ej-text="Sound"></li>
                            <li data-ej-text="Music"></li>
                            <li data-ej-text="Brightness"></li>
                            <li data-ej-text="Wallpaper"></li>
                        </ul>
                        <ul data-ej-grouplisttitle="Settings">
                            <li data-ej-text="General"></li>
                            <li data-ej-text="Brightness"></li>
                            <li data-ej-text="Wallpaper"></li>
                        </ul>
                    </div>
{% endhighlight %}

Add the following script in your code.



{% highlight js %}

syncApp.controller('ListViewCtrl', function ($scope) {
    $scope.width = 400; 
    $scope.grouplist = true;

});

{% endhighlight %}

Run the codes to get the following output

![https://help.syncfusion.com/js/ListView/Grouped-List_images/firstlevelgrouplist_img1.png](grouplist_images\firstlevelgrouplist_img1.png)

### Nested Child Group List

While selecting a list item that is grouped, you can also render another set of list items. This is achieved by defining the desired **child item list** within the list containing ”PrimaryKeyValue**”.** This **data-ej-primarykey** attribute relates the parent child for identifying its appropriate child when clicking on the parent list item.

Refer the following code examples.

{% highlight html %}
<div ej-listview id="anglistview" e-width="width" e-enablegrouplist="grouplist" e-showheader="header" e-headertitle="title" >
                    <ul data-ej-grouplisttitle="Network">
                        <li data-ej-text="Airplane Mode"></li>
                        <li data-ej-text="Wi-Fi"></li>
                        <li data-ej-text="Notifications"></li>
                        <li data-ej-text="Location Services"></li>
                    </ul>
                    <ul data-ej-grouplisttitle="Apps">
                        <li data-ej-primarykey="1" data-ej-text="Sound">
                            <ul>
                                <li data-ej-text="Ring Tone"></li>
                                <li data-ej-text="Message Tone"></li>
                                <li data-ej-text="Notification Tone"></li>
                            </ul>
                        </li>
                        <li data-ej-text="Brightness"></li>
                        <li data-ej-text="Wallpaper"></li>
                    </ul>
                    <ul data-ej-grouplisttitle="Settings">
                        <li data-ej-text="General"></li>
                        <li data-ej-text="Brightness"></li>
                        <li data-ej-text="Wallpaper"></li>
                    </ul>
                </div>
{% endhighlight %}


Add the following script in your code.

{% highlight js %}

syncApp.controller('ListViewCtrl', function ($scope, $rootScope) {
    $scope.width = 400; 
    $scope.grouplist = true;
    $scope.title = "Favourite";
    $scope.header = true;

});

{% endhighlight %}

Run the codes to get the following output

![https://help.syncfusion.com/js/ListView/Grouped-List_images/nestedchildgrouplist_img1.pn](grouplist_images\nestedchildgrouplist_img1.png)

