---
layout: post
title: legend
description: Learn how to add and customize the legnds in Sunburst Chart.
platform: Angular-1
control: SunburstChart
documentation: ug
---

## Legend
The legend is used to represent the first level of items in the Sunburst Chart.The `legend` can be initialized using the below code snippet

{% highlight HTML %}

<div id="container" ej-sunburstchart e-legend-visible="true" >					
</div>

 {% endhighlight %}

![](Legend_images/Legend_img1.png)

## Legend Icon 

You can specify different shapes of legend icon by using the `e-legend-shape` property of the legend. By default, legend shape is **Circle**. The Sunburst chart has some predefined shapes such as:
* Circle
* Cross
* Diamond
* Pentagon
* Rectangle
* Triangle

{% highlight HTML %}

<div id="container" ej-sunburstchart e-legend-visible="true" e-legend-shape="pentagon" >					
</div>

{% endhighlight %}

![](Legend_images/Legend_img2.png)
 
## Positioning the Legend

By using the `position` property, you can position the legend at left, right, top or bottom of the chart. 

{% highlight HTML %}

<div id="container" ej-sunburstchart e-legend-visible="true" e-legend-position="top" >					
</div>

{% endhighlight %}

![](Legend_images/Legend_img3.png)
 
### Customization

## Legend Item Size and border
You can change the size of the legend items by using the `e-legend-itemstyle-width` and `e-legend-itemstyle-height` propertys. To change the legend item border, use `e-legend-border`property of the legend .

{% highlight HTML %}
<div id="container" ej-sunburstchart e-legend-visible="true" e-legend-position="top" e-legend-itemstyle-height="13"
 e-legend-itemstyle-width="13" e-legend-border-color="#FF0000" e-legend-itemstyle-width="1">					
</div>

{% endhighlight %}

![](Legend_images/Legend_img4.png)

## Legend Size

By default, legend takes 20% of the height horizontally when it was placed on the top or bottom position and 20% of the width vertically while placing on the left or right position of the chart. You can change this default legend size by using the `e-legend-size` property of the legend.

{% highlight HTML %}

<div id="container" ej-sunburstchart e-legend-visible="true" e-legend-position="top" e-legend-size-height="75" e-legend-size-width="200">					
</div>

{% endhighlight %}

 ![](Legend_images/Legend_img5.png)

## Legend Row and Colums

You can arrange the legend items horizontally and vertically by using the `e-legend-rowCount` and `e-legend-columnCount` properties of the legend.
•	When only the rowCount is specified, the legend items are arranged according to the rowCount and number of columns may vary based on the number of legend items.
•	When only the columnCount is specified, the legend items are arranged according to the columnCount and number of rows may vary based on the number of legend items.
•	When both the properties are specified, then the one which has higher value is given preference. For example, when the rowCount is 4 and columnCount is 3, legend items are arranged in 4 rows.
•	When both the properties are specified and have the same value, the preference is given to the columnCount when it is positioned at the top/bottom position. The preference is given to the rowCount when it is positioned at the left/right position.
 
{% highlight HTML %}

<div id="container" ej-sunburstchart e-legend-visible="true" e-legend-position="top" e-legend-rowcount="2" e-legend-columncount="3" >					
</div>

{% endhighlight %}

![](Legend_images/Legend_img6.png)
 
## LegendInteractivity

You can select a specific category while clicking on corresponding legend item through `e-legend-clickAction` property. 

It has three types of action
*	ToggleSegmentSelection
*	ToggleSegmentVisiblity
*	None

## ToggleSegmentSelection

Used to highlight specific category while clicking on legend item

{% highlight HTML %}

<div id="container" ej-sunburstchart  e-legend-clickaction="toggleSegmentSelection" >					
</div>

{% endhighlight %}

![](Legend_images/Legend_img7.png)
 
## Toggle Segment Visibility

Used to disable the specific category while clicking on legend item.

{% highlight HTML %}

<div id="container" ej-sunburstchart  e-legend-clickaction="toggleSegmentVisibility" >					
</div>

{% endhighlight %}


![](Legend_images/Legend_img8.png)


