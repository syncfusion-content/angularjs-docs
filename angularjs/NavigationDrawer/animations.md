---
layout: post
title: animations
description: animations
platform: Angular-1
control: Navigation Drawer
documentation: ug
---

# Animations

You can set the transition type of the Navigation Drawer by using **e-type** property. The possible transition types are slide and overlay.

* Slide - both navigation panel and content page slides towards left/right direction to view the navigation panel items.
* Overlay - Only the navigation panel slides over the content page to view the navigation panel items. That is, part of the content page is hidden under navigation panel.


N> ![C:\Users\ApoorvahR\Desktop\Note.png](animations_images\animations_img1.png)_ Transition slide type works only with fixed position._

The default value is Overlay.

In the HTML page set the e-type and e-position of Navigationdrawer.


{% highlight html %}

    <div ng-controller="NavigationDrawerCtrl">
    <div id="main" style="height:1000px;">
        <div id="navpane" class="ang-navigationdrawer" ej-navigationdrawer e-targetid="drawerTarget"
             e-type="slide" e-direction="left" e-enablelistview=true e-listviewsettings-width="300" e-position="fixed">
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
  
The following screenshot illustrates the output.

![](animations_images\animations_img2.png)

Before target click
{:.caption}

![](animations_images\animations_img3.png)

After target click
{:.caption}

