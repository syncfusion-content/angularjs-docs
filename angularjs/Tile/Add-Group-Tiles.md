---
layout: post
title: Add-Group-Tiles
description: add group tiles
platform: Angular-1
control: Tile
documentation: ug
---

# Add Group Tiles

To make a **Tile** as grouped tile, you can use the following mentioned pre-defined classes.

<table>
<tr>
<th>
Class Name</th><th>
Explanation</th></tr>
<tr>
<td>
e-tile-group</td><td>
To group the column elements</td></tr>
<tr>
<td>
e-tile-column</td><td>
To align the tile in column manner</td></tr>
<tr>
<td>
e-tile-small-col-2</td><td>
To align the small size tiles</td></tr>
</table>

Refer to the following code example for render the Group tiles.

{% highlight html %}

    <div class="e-tile-group">
        <div class="e-tile-column">
               <!— Add tile control here -->
        </div>
    </div>

{% endhighlight %}

To render **column** grouped tile, you need to render the number of tiles inside a **&lt;div&gt;** element with class **e-tile-column**. Then that column group element is appended to a **&lt;div&gt;** with class **e-tile-group**.     

To render **small-col-2** grouped tile, you need to render the number of tiles inside a **&lt;div&gt;** element with class **e-tile-small-col-2**. Then that **small-col-2** group element is appended to a **&lt;div&gt;** with class **e-tile-column**. Then you need to append those column inside the main group **&lt;div&gt;** element.                                                     

Refer the following code examples.

{% highlight html %}
    
    <div class="e-tile-group" id="groupTile">
         <div class="e-tile-column">
              <div id="tile1" ej-tile e-imageposition="fill" e-caption-text="People" e-tilesize="medium" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/people_1.png'
               e-text="People">
              </div>
               <div class="e-tile-small-col-2">
                    <div id="tile2" ej-tile e-imageposition="center" e-tilesize="small" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/alerts.png'>
                    </div>
                    <div id="tile3" ej-tile e-imageposition="center" e-tilesize="small" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/bing.png'>
                    </div>
                    <div id="tile4" ej-tile e-tilesize="small" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/camera.png'>
                    </div>
                    <div id="tile5" ej-tile e-tilesize="small" e-imageposition="center" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/messages.png'>
                    </div>
               </div>
               <div id="tile6" ej-tile e-tilesize="medium" e-imageposition="center" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/games.png' e-text="Play">
               </div>
               <div id="tile7" ej-tile e-tilesize="medium" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/map.png' e-text="Maps">
               </div>
               <div id="tile8" ej-tile e-tilesize="wide" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/sports.png' e-text="Sports" e-imageposition="fill">
               </div>
        </div>
        <div class="e-tile-column">
               <div id="tile9" ej-tile e-tilesize="medium" e-imageposition="fill" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/people_2.png' e-text="People">
               </div>
               <div id="tile10" ej-tile e-tilesize="medium" e-imageposition="center" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/pictures.png' e-text="Photo">
               </div>
               <div id="tile11" ej-tile e-tilesize="wide" e-imageposition="center" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/weather.png' e-text="Weather">
               </div>
               <div id="tile12" ej-tile e-tilesize="medium" e-imageposition="center" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/music.png' e-text="Music">
               </div>
               <div id="tile13" ej-tile e-tilesize="medium" e-imageposition="center" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/favs.png' e-text="Favorites">
               </div>
        </div>
   </div>

{% endhighlight %}

![](Add-Group-Tiles_images/Add-Group-Tiles_img1.png)

