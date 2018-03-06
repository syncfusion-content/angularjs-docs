---
layout: post
title: Datalabel Customization
description: Learn how to customize datalabels in Sunburst Chart.
platform: AngularJS
control: SunburstChart
documentation: ug
---

# Data Labels 

Sunburst data labels are used to display the data related to the segment. It helps to provide the information about the data points to the users.
You can enable or disable the data labels by setting the `visible` property of the `e-datalabelsettings` to true as shown in the below code

{% highlight js %}

<div id="container" ej-sunburstchart e-datalabelsettings-visible="true" >					
</div>

 {% endhighlight %}

![](DataLabel_images/DataLabel_img1.png)

## Label Overflow mode

When you represent huge data with data labels, they may intersect each other. You can avoid this using the `e-datalabelsettings-labelOverflowMode` property.

The following properties are used to avoid the overlapping.
*	Trim – To trim the large data labels.
*	Hide – To hide the overlapped data labels.
The following code shows how to set Hide and Trim mode.

{% highlight js %}

<div id="container" ej-sunburstchart e-datalabelsettings-labeloverflowmode="hide" >					
</div>

 {% endhighlight %}

![](DataLabel_images/DataLabel_img2.png) 

{% highlight js %}


<div id="container" ej-sunburstchart e-datalabelsettings-labeloverflowmode="trim" >					
</div>

 {% endhighlight %}

![](DataLabel_images/DataLabel_img3.png)

## Label Rotation Mode
You can rotate the data label by using `e-datalabelsettings-labelRotationMode` property. By default, the labelRotationMode is set as **angle**. 

The following code shows how to set labelRotationMode as normal and angle.

{% highlight js %}

<div id="container" ej-sunburstchart e-datalabelsettings-labelrotationmode="normal" >					
</div>

 {% endhighlight %}

![](DataLabel_images/DataLabel_img4.png)

{% highlight js %}

<div id="container" ej-sunburstchart e-datalabelsettings-labelrotationmode="angle" >					
</div>

{% endhighlight %}

![](DataLabel_images/DataLabel_img5.png)
 
## Customizing the data labels
You can customize the appearance of the data point using the `font` property.


{% highlight js %}

<div id="container" ej-sunburstchart e-datalabelsettings-font-color="black" 
e-datalabelsettings-font-fontWeight="bold" e-datalabelsettings-font-size="15px">					
</div>

{% endhighlight %}

![](DataLabel_images/DataLabel_img6.png)

## Sunburst Chart Title & Subtitle

### Title & TextAlignment

By using the title option, you can add the `e-title-text` as well as customize its `e-title-border`, `e-title-background` and `e-title-font`.

You can change the title alignment to center, far and near by using the `e-title-textAlignment` property of the Title.

{% highlight js %}

<div id="container" ej-sunburstchart e-title-visible="true" e-title-textalignment="near" e-title-text="" 
e-title-border-color="blue" e-title-border-width="2" e-title-font-size="15px"
e-title-font-fontFamily="Arial" e-title-font-fontStyle="bold" e-title-font-fontWeight="normal">					
</div>

{% endhighlight %}

### Sub Title & TextAlignment

By using the subTitle option, you can add the `e-title-subTitle-text` as well as customize its `e-title-subTitle-border`, `e-title-subTitle-background` and `e-title-subTitle-font`.

{% highlight js %}

<div id="container" ej-sunburstchart e-title-subTitle-visible="true" e-title-subTitle-textalignment="near" e-title-subTitle-text="" 
e-title-subTitle-border-color="blue" e-title-subTitle-border-width="2" e-title-subTitle-font-size="15px"
e-title-subTitle-font-fontFamily="Arial" e-title-subTitle-font-fontStyle="bold" e-title-subTitle-font-fontWeight="normal">					
</div>

{% endhighlight %}
