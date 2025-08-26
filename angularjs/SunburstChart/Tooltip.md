---
layout: post
title: Tooltip
description: Learn how to add Tooltip to Sunburstchart .
platform: ts
control: Sunburst Chart
documentation: ug
---

# Tooltip  

ToolTip allows you to display any information over a sunburst segment. It appears when mouse hovered over or touch any chart segment. By default, it displays the corresponding segment category name and its value

{% highlight js %}

<div id="container" ej-sunburstchart e-tooltip-visible="true">					
</div>

{% endhighlight %}

![mouse hovered over or touch any chart segment.](Tooltip_images/Tooltip_img1.png)

## Tooltip Template   

HTML elements can be displayed in the tooltip by using the `e-tooltip-template` property of the tooltip. The template property takes the value of the id attribute of the HTML element. You can use the **#point.x#** and **#point.y#** as place holders in the HTML element to display the x and y values of the corresponding point.

You can add a <div> element to set the `background` for the Sunburst chart and attach the styles to the HTML page such as height and  width.

{% highlight js %}

<div id="Tooltip" style="display: none;">
        <div id="value" style="background-color:red;padding-top:3px;padding-right:3px">
            <div>
                <label id="efpercentage" style="color:white">
                    &nbsp;&nbsp;Category:&nbsp;#point.x#
                   <br />&nbsp;&nbsp;Value:#point.y#
                </label>
            </div>
        </div>
    </div>

<div id="container" ej-sunburstchart e-tooltip-visible="true" e-tooltip-template="Tooltip">					
</div>


{% endhighlight %}

![to display the x and y values of the corresponding point.](Tooltip_images/Tooltip_img2.png)

## Customize the appearance of tooltip

The fill and border options are used to customize the background color and border of the tooltip respectively. The font option in the tooltip is used to customize the font of the tooltip text.


{% highlight js %}

<div id="container" ej-sunburstchart e-tooltip-visible="true" e-tooltip-border-color="blue"
e-tooltip-border-width="2" e-tooltip-fill="green" e-tooltip-font-family="Arial" e-tooltip-font-style="bold" e-tooltip-font-size="12px" e-tooltip-font-opacity="0.5" >		

{% endhighlight %}