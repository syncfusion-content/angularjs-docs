---
layout: post
title: targetid
description: targetid
platform: AngularJS
control: Navigation Drawer
documentation: ug
---

# TargetId

**e-targetid** property is used to define the target Id for Navigation Drawer. The drawer opens while you click on the specified target element.

In the HTML page set the e-targetid of Navigationdrawer.

{% highlight html %}

        <div ng-controller="NavigationDrawerCtrl">
        <div id="main" style="height:1000px;">
                <div id="navpane" class="ang-navigationdrawer" ej-navigationdrawer e-targetid="drawerTarget" e-direction="left" e-enablelistview=true e-listviewsettings-width="300" e-position="fixed">
                <ul>
                        <li>Settings</li>
                        <li>Read</li>
                        <li>Help</li>
                        <li>About</li>
                </ul>
                </div>
                <button id="drawerTarget" class="ang-button btn" ej-button style="top:200px;left:600px;position:absolute">Open Drawer</button>
        </div>
        </div>

        
{% endhighlight %}

The following screenshots illustrates the output.

![](targetid_images\targetid_img1.png)

Before target click
{:.caption}



![](targetid_images\targetid_img2.png)

After target click
{:.caption}

