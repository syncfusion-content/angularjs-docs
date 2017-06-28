---
layout: post
title: Selection
description: What are the different modes of selection present in the Sunburst Chart
platform: AngularJS
control: SunburstChart
documentation: ug
---

# Selection 

SunburstChart provides selection support for the points on mouse click. To enable the selection , set the `e-selectionsettings-enable` property to true in the `e-selectionsettings`. 

{% highlight js %}


<div id="container" ej-sunburstchart e-selectionsettings-enable="true" >					
</div>

{% endhighlight %}

![](Selection_images/Selection_img1.png)

 
## Selection Display mode

 You can customize the selected  segment appearance by using *color or opacity*. You can choose between color or opacity using the `e-selectionsettings-type` property in the selection Settings.

*	selectionByColor – To display the selected segment appearance using color.
*	selectionByOpacity – To display the selected segment appearance using opacity.

{% highlight js %}

<div id="container" ej-sunburstchart e-selectionsettings-enable="true" e-selectionsettings-type="color" e-selectionsettings-color="red">
</div>


 {% endhighlight %}

![](Selection_images/Selection_img2.png)

## Selection Mode

Sunburst chart provides multiple option to represent the selected categories. You can select the segment categories by using the `e-selectionsettings-mode` property in selectionSettings
*	Child – To selection the child of selected parent.
*	All – To selection the entire categories in group.
*	Parent – To selection the parent of selected child.
*	Single - To selection single item in the category.

### Child
The following code shows how to set the selection type as child 

{% highlight js %}

<div id="container" ej-sunburstchart e-selectionsettings-enable="true" e-selecitonsettings-mode="child">					
</div>

{% endhighlight %}

![](Selection_images/Selection_img3.png)
 
### Parent

The parent mode can be enabled by using the below code 

{% highlight js %}

<div id="container" ej-sunburstchart e-selectionsettings-enable="true" e-selecitonsettings-mode="parent">					
</div>

{% endhighlight %}

![](Selection_images/Selection_img4.png)
 
### Point

To selection the particular segment, the point mode of the selection settings is used.

{% highlight js %}

<div id="container" ej-sunburstchart e-selectionsettings-enable="true" e-selecitonsettings-mode="point">					
</div>

 {% endhighlight %}

![](Selection_images/Selection_img5.png)
 
### All

The following code snippet is used for the all mode of selection settings

{% highlight js %}
<div id="container" ej-sunburstchart e-selectionsettings-enable="true" e-selecitonsettings-mode="all">					
</div>


{% endhighlight %}

![](Selection_images/Selection_img6.png)

[Click](http://ngjq.syncfusion.com/#/sunburstchart/selection) here to view the online demo sample of Selection in  the Sunburst Chart.
