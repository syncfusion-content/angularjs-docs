---
layout: post
title: customize header
description: customize header
platform: Angular-1
control: ListView
documentation: ug
---

## Customize Header

In **ListView**, you can enable the built-in **Header** support. To show or hide the **Header** in **ListView**, use the **e- showheader** property. By default, **ListView** is rendered with the **Header**. You can set the title for the **Header** by using the **e-headertitle** property.

In some cases, for the purpose of navigation, you may want to show the **Back** button in **ListView Header**. To achieve this, **e-showheaderbackbutton** property is used. By default, **ListView** is not rendered with the header back button in parent page. To customize the text shown in **ListView Header Back** button, the property **e-headerbackbuttontext** is used.

Refer the following code example.

{% highlight html %}


<div ej-listview id="anglistview" e-width="width" e-showheader="header" e-showheaderbackbutton="backbutton" e-headerbackbuttontext="backbuttontext">
                    <ul>
                        <li data-ej-text="Artwork"></li>
                        <li data-ej-text="Abstract"></li>
                        <li data-ej-text="2 Acrylic Mediums"></li>
                        <li data-ej-text="Creative Acrylic"></li>
                        <li data-ej-text="Modern Painting"></li>
                        <li data-ej-text="Canvas Art"></li>
                        <li data-ej-text="Black white"></li>
                        <li data-ej-text="Children"></li>
                        <li data-ej-text="Preschool Crafts"></li>
                        <li data-ej-text="School-age Crafts"></li>
                    </ul>
                </div>


{% endhighlight %}



Add the following script in your code.

{% highlight js %}


syncApp.controller('ListViewCtrl', function ($scope) {
    $scope.width = 400; 
    $scope.header = true;
    $scope.backbuttontext = "Menu";
    $scope.backbutton = true;

});


{% endhighlight %}



Run the code to get the following output

![https://help.syncfusion.com/js/ListView/Customize-Header_images/Customize-Header_img1.png](customizeheader_images\customizeheader_img1.png)

