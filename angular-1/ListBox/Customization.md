---
layout: post
title: Customization
description: Customization
platform: Angular-1
control: ListBox
documentation: ug
---

# Customization

## Applying Rounded Corner

To use [showRoundedCorner](https://help.syncfusion.com/api/js/ejlistbox#members:showroundedcorner) property to add the rounded borders for the ListBox component. By default, showRoundedCorner property is disabled in ListBox.

{% highlight html %}

    <div id="control">
        <ul id="selectcustomer" ej-listbox e-datasource="dataList" e-fields-text="text" e-showroundedcorner="true"></ul>
    </div>
     
{% endhighlight %}

{% highlight js %}

     $scope.dataList = [
                          { empid: "cr1", text: "Dodge Avenger" },
                          { empid: "cr2", text: "Chrysler 200" },
                          { empid: "cr3", text: "Ford Focus" },
                          { empid: "cr4", text: "Ford Taurus", },
                          { empid: "cr5", text: "Dazzler", },
                          { empid: "cr6", text: "Chevy Spark", },
                          { empid: "cr7", text: "Chevy Volt", },
                          { empid: "cr8", text: "Honda Fit", },
                          { empid: "cr9", text: "Honda Crosstour", },
                          { empid: "cr10", text: "Acura RL", },
                          { empid: "cr11", text: "Hyundai Elantra", },
                          { empid: "cr12", text: "Mazda3", }
             ];
	
{% endhighlight %}

![](Customization_Images/rounded_corner.png)

I> The browser support details for rounded corner is given [here](http://www.w3schools.com/cssref/css3_pr_border-radius.asp).

## Enable/Disable the ListBox component

The [enabled](https://help.syncfusion.com/api/js/ejlistbox#members:enabled) property is used to indicate whether the component can respond to the user interaction or not. You can disable it by setting as false to this property. When the component as disabled state, you cannot interact with the component.

N> you can also use [enable()](https://help.syncfusion.com/api/js/ejlistbox#methods:enable)  or [disable()](https://help.syncfusion.com/api/js/ejlistbox#methods:disable) methods.

{% highlight html %}

   <div id="control">
        <ul id="selectcustomer" ej-listbox e-datasource="dataList" e-fields-text="text" e-enabled="false"></ul>
    </div>
     
{% endhighlight %}

{% highlight js %}

     $scope.dataList = [
                          { empid: "cr1", text: "Dodge Avenger" },
                          { empid: "cr2", text: "Chrysler 200" },
                          { empid: "cr3", text: "Ford Focus" },
                          { empid: "cr4", text: "Ford Taurus", },
                          { empid: "cr5", text: "Dazzler", },
                          { empid: "cr6", text: "Chevy Spark", },
                          { empid: "cr7", text: "Chevy Volt", },
                          { empid: "cr8", text: "Honda Fit", },
                          { empid: "cr9", text: "Honda Crosstour", },
                          { empid: "cr10", text: "Acura RL", },
                          { empid: "cr11", text: "Hyundai Elantra", },
                          { empid: "cr12", text: "Mazda3", }
             ];
	
{% endhighlight %}

![](Customization_Images/disabled.png)

N> you can disable/enable the single or multiple list items by using [disableItemsByIndices](https://help.syncfusion.com/api/js/ejlistbox#methods:disableitemsbyindices) and [enableItemsByIndices](https://help.syncfusion.com/api/js/ejlistbox#methods:enableitemsbyindices) method.

