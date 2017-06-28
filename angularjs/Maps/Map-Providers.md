---
layout: post
title: Map-Providers
description: map providers
platform: AngularJS
control: Maps
documentation: ug
---

# Map Providers

**Map** control support map providers such as OpenStreetMap that can be added to any layers in maps.

## Open Street Map

OpenStreetMap is a map of the entire world. The OpenStreetMap allows you to view, edit and use geographical data in a collaborative way from any place on the Earth.

### Enable OSM

You can enable this feature by setting the `e-layerType` property value as "OSM".

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
    <head>
        <title>Essential Studio for AngularJS: Maps</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="MapsCtrl">
      <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-layertype="osm" 
            e-urltemplate="http://a.tile.openstreetmap.org/level/tileX/tileY.png">
            </e-layer>
        </e-layers>
    </div>
    <script>
        angular.module('MapsApp', ['ejangular'])
        .controller('MapsCtrl', function ($scope) {
                        });
    </script>
    </body>
</html>

{% endhighlight %}

### URL Template

The `e-urltemplate` property determines the format of tile map. You can specify the template for the tile layer. 

![](Map-Providers_images/Map-Providers_img1.png)

## Bing Map

Bing Map is a key feature in accessing the external geospatial imagery services for deep-zoom satellite view. 

### Enable Bing Maps

You can enable this feature by defining the `layerType` as “bing”.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
    <head>
        <title>Essential Studio for AngularJS: Maps</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="MapsCtrl">
      <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-layertype="bing" e-key="// …bingMapKey" e-bingmaptype="aerialwithlabel"></e-layer>
        </e-layers>
    </div>
    <script>
        angular.module('MapsApp', ['ejangular'])
        .controller('MapsCtrl', function ($scope) {
                        });
    </script>
    </body>
</html>

{% endhighlight %}

### Key

The bing Map key is provided as input to this `e-key` property. The Bing Map key can be obtained from [http://www.microsoft.com/maps/create-a-bing-maps-key.aspx](http://www.microsoft.com/maps/create-a-bing-maps-key.aspx).

![](Map-Providers_images/Map-Providers_img2.png)

