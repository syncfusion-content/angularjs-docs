---
layout: post
title: Localization
description: Localization
platform: AngularJS
control: Tile
documentation: ug
---

# Localization

The Tile component provides option to localize its strings, it is used to adapting the Tile to a particular local language. By default, the Tile will use the US English (en-US) as its language.

N> The culture name has to be specified in a standard format such as [Language Code]-[County/Region Code].

To localize the Tile strings with your own localization, copy the default language informations and localize the strings in the values column. For example, to localize the Tile in Italian language (“it-IT”).

{% highlight javascript %}
     
     ej.Tile.Locale["it-IT"] = {
        captionText: "testo" 
    };

{% endhighlight %}
   
Set the locale property of the Tile to the new language.

{% highlight html %}

 <div id="tile" ej-tile e-tilesize="medium" e-imageposition="center" e-imageurl='http://js.syncfusion.com/ug/web/content/tile/camera.png' e-caption="caption" e-locale="it-IT">
    </div>  

{% endhighlight %}

{% highlight javascript %}
     
  angular.module('TileApp', ['ejangular'])
         .controller('TileCtrl', function ($scope, $document) {
             $scope.caption = { enabled: true };
  });

  ej.Tile.Locale["it-IT"] = {
      captionText: "testo"
  };

{% endhighlight %}

![](Functionality_images/localization.png)