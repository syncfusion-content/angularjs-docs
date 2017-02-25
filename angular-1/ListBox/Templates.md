---
layout: post
title: Templates
description: templates
platform: Angular-1
control: ListBox
documentation: ug
---

# Template Support

By default you can add any text or image to the ListBox list item. To customize the list items layout or to create your own visualized elements by using template support.

## Template Fields

To create set of div element with common syntax and assign it to the template property. You can add any HTML mark-up element inside the ListBox using this property.

To create the JSON array with text, imagename, role and country which is initialized in the dataSource property. Content template is created by using the corresponding fields and assigned in template property. The content template is customized with images and custom CSS styles to visualize the list items.

{% highlight html %}

    <ul id="selectExperts" ej-listbox e-datasource="dataList" e-template="template"></ul>
    
{% endhighlight %}

{% highlight javascript %}

   $scope.dataList = [
           { text: "Erik Linden", eimg: "3", desig: "Representative", country: "England" }, { text: "John Linden", eimg: "6", desig: "Representative", country: "Norway" },
           { text: "Louis", eimg: "7", desig: "Representative", country: "Australia" }, { text: "Lawrence", eimg: "5", desig: "Representative", country: "India" }
             ];
   $scope.template = '<div><img class="eimg" src="http://js.syncfusion.com/demos/web/content/images/Employees/${eimg}.png" alt="employee"/>' +
                               '<div class="ename"> ${text} </div><div class="desig"> ${desig} </div><div class="cont"> ${country} </div></div>';

{% endhighlight %}

{% highlight css %}

    .eimg {
        margin: 0;
        padding: 3px 10px 3px 3px;
        border: 0 none;
        width: 60px;
        height: 60px;
        float: left;
    }

    .ename {
        font-weight: bold;
        padding: 6px 3px 1px 3px;
    }

    .desig, .cont {
        font-size: smaller;
        padding: 3px 3px -1px 0px;
    }

    #selectExperts li {
        width: 100%;
        height: 70px;
        padding: 5px;
    }
     
{% endhighlight %}

![](Templates_Images\templates_img1.png)

