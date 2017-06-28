---
layout: post
title: dimensions
description: dimensions
platform: AngularJS
control: ListView
documentation: ug
---

## Dimensions

To customize the **ListView** dimensions, **e-width** and **e-height** properties are used.

Refer to the following code examples.

{% highlight html %}

<div ej-listview id="anglistview" e-width="width" e-height="height">
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
    $scope.height = 600;
});


{% endhighlight %}

Run the code to get the following output

![https://help.syncfusion.com/js/ListView/Dimensions_images/Dimensions_img1.png](dimensions_images\dimensions_img1.png)



