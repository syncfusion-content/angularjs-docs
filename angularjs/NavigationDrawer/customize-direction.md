---
layout: post
title: customize-direction
description: customize-direction
platform: Angular-1
control: Navigation Drawer
documentation: ug
---

# Customize Direction

By using **e-direction** property, you can set the drawer to be open from right to left direction or left to right direction. The possible direction values are Right, Left and the default value is Left. Refer to the following code example.

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

The following screenshot displays the output by swiping from right to left at the right side end of the screen.

![](customize-direction_images\customize-direction_img1.png) 





