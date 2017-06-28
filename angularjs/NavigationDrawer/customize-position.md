---
layout: post
title: customize-position
description: customize position
platform: AngularJS
control: Navigation Drawer
documentation: ug
---

# Customize Position

**Position** property is used to specify the position whether it is in fixed or relative to the page. When you set a normal value to **e-position** property, it appears within the container. Otherwise, it appears in the whole body .The possible position values are fixed and normal. The Default value is normal.
In the HTML page set the e-position of Navigationdrawer.


{% highlight html %}

    <div ng-controller="NavigationDrawerCtrl">
        <div id="main" style="height:1000px;">
            <div  e-direction="right" e-enablelistview=true e-listviewsettings-width="300" e-position="fixed">
                <ul>
                    <li>Settings</li>
                    <li>Read</li>
                    <li>Help</li>
                    <li>About</li>
                </ul>
            </div>       
        </div>
    </div>

{% endhighlight %}


The following screenshot illustrates the output by swiping from left to right at the left end of the screen.

![](customize-position_images\customize-position_img1.png)

