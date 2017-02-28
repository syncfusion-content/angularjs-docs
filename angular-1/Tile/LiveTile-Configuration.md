---
layout: post
title: LiveTile-Configuration
description: livetile configuration
platform: Angular-1
control: Tile
documentation: ug
---

# LiveTile Configuration

Live Tiles are used to display the current or up to date information like scores, stocks, weather, etc. You can enable Live Tile using livetile-enabled property set as true. The livetile-type property allows you to specify the type of animation while updating the information in Tile. 

There are three types of Tile animation supported: Flip, Slide and Carousel.

The livetile-imageurl property sets background image for Live Tile. This property accepts array values so you can specify the image url's for all the Tile components that are used in single Live Tile. 

You can specify time interval for each Tile ej-livetile property. Time interval is given in milliseconds. The default value is 2000.

Refer to the following code examples.

{% highlight html %}

     <div class="e-tile-group" id="groupLiveTile">
        <div class="e-tile-column">
            <div id="tile6" ej-tile e-tilesize="medium" e-allowselection="true" e-imageposition="center" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/games.png'
                 e-text="Play">
            </div>
            <div class="e-tile-small-col-2">
                <div id="tile2" ej-tile e-imageposition="center" e-allowselection="true" e-tilesize="small" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/alerts.png'>
                </div>
                <div id="tile3" ej-tile e-imageposition="center" e-allowselection="true" e-livetile-updateinterval="3000" e-tilesize="small" e-livetile-enabled="true" e-livetile-type="flip" e-livetile-imageurl="liveImage1">
                </div>
                <div id="tile4" ej-tile e-livetile-updateinterval="3500" e-allowselection="true" e-livetile-enabled="true" e-livetile-type="flip" e-livetile-imageurl="liveImage2" e-tilesize="small">
                </div>
                <div id="tile5" ej-tile e-tilesize="small" e-badge-enabled="true" e-allowselection="true" e-badge-value="10" e-imageposition="center" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/messages.png'>
                </div>
            </div>
            <div id="tile6" ej-tile e-tilesize="medium" e-imageposition="fill" e-allowselection="true" e-livetile-updateinterval="5000" e-livetile-enabled="true" e-livetile-type="slide" e-livetile-imageurl="liveImage3" e-text="People">
            </div>
            <div id="tile7" ej-tile e-tilesize="medium" e-allowselection="true" e-imageposition="center" e-livetile-updateinterval="4000" e-livetile-enabled="true" e-livetile-type="slide" e-livetile-imageurl="liveImage4" e-text="Photo">
            </div>
            <div id="tile8" ej-tile e-tilesize="wide" e-allowselection="true" e-imageposition="center" e-livetile-enabled="true" e-livetile-type="carousel" e-livetile-imageurl="liveImage5" e-text="Weather">
            </div>
        </div>
    </div>

{% endhighlight %}

{% highlight js %}    
   
      $scope.liveImage1 = ['http://js.syncfusion.com/ug/web/content/tile/alerts.png', 'http://js.syncfusion.com/ug/web/content/tile/bing.png', 'http://js.syncfusion.com/ug/web/content/tile/camera.png'];
      $scope.liveImage2 = ['http://js.syncfusion.com/ug/web/content/tile/alerts.png', 'http://js.syncfusion.com/ug/web/content/tile/bing.png', 'http://js.syncfusion.com/ug/web/content/tile/camera.png'];
      $scope.liveImage3 = ['http://js.syncfusion.com/ug/web/content/tile/people_1.png', 'http://js.syncfusion.com/ug/web/content/tile/people_2.png', 'http://js.syncfusion.com/ug/web/content/tile/people_3.png'];
      $scope.liveImage4 = ['http://js.syncfusion.com/ug/web/content/tile/pictures.png', 'http://js.syncfusion.com/ug/web/content/tile/photo_1.png', 'http://js.syncfusion.com/ug/web/content/tile/photo_2.png', 'http://js.syncfusion.com/ug/web/content/tile/pictures.png', 'http://js.syncfusion.com/ug/web/content/tile/photo_1.png'];
      $scope.liveImage5 = ['http://js.syncfusion.com/ug/web/content/tile/weather.png', 'http://js.syncfusion.com/ug/web/content/tile/weather_1.png', 'http://js.syncfusion.com/ug/web/content/tile/weather_2.png'];
 
{% endhighlight %}

![](LiveTile_images/livetile_image.png)