---
layout: post
title: template-support
description: template-support
platform: AngularJS
control: Tile
documentation: ug
---

## Template support with Tile Component  

To customize the Tile images with template feature by using imageTemplateId property of Tile component. Add the below mentioned code to the corresponding view page.

{% highlight html %}

  <div class="e-tile-group" id="groupTile">
    <div class="e-tile-column">
        <div id="tile1" ej-tile e-tilesize="wide" e-text="Windows Store" e-imagetemplateid="imageTemplate" e-imageposition="fill">
        </div>
    </div>
    <div id="imageTemplate">
        <div id="appimage">
        </div>
        <div class="tileMargin">
            <span class="caption">Google Search</span><br />
            <span class="description">The world’s information</span><br />
            <span class="sub">Free</span>
        </div>
    </div>
  </div>
   
{% endhighlight %}

Add the following styles to customize the tile images with template support.

{% highlight html %}

 <style>
        #appimage {
            background-image: url("http://js.syncfusion.com/UG/mobile/content/google.png");
            background-position: center center;
            background-repeat: no-repeat;
            background-size: 50% auto;
            display: table-cell;
            width: 45%;
        }

        .tileMargin {
            display: table-cell;
            padding-top: 25px;
        }

        .e-tile-template {
            display: table;
            height: 100%;
            width: 100%;
        }
    </style>
   
{% endhighlight %}

Run the above code to get the following output.

![](Template_images\Template_img1.png)

