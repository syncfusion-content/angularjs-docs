---
layout: post
title: Layers
description: layers
platform: Angular 1.0
control: Maps
documentation: ug
---

# Layers

Map is maintained through `e-layers` and it can accommodate one or more layers.

## Multilayer

The Multilayer support allows you to load multiple shape files in a single container, enabling maps to display more information.

### Adding Multiple Layers in the Map

The shape layers is the core layer of the map. The multiple layers can be added in the shape layers as `e-subLayers` within the shape layers.

## SubLayer

The subLayer is the collection of shape layers. 

In this example, World Map shape is used as shape data by utilizing the “**WorldMap.json**” file in the following folder structure obtained from downloaded Maps_GeoJSON folder.

..\ Maps_GeoJSON\

You can assign the complete contents in “**WorldMap.json**” file to new JSON object. For better understanding, a JS file “**WorldMap.js”** is already created to store JSON data in JSON object “usMap”

**[usa.js]**

{% highlight javascript %}

    var world_map = //Paste all the content copied from the JSON file// 

{% endhighlight %}

{% highlight javascript %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
    <head>
        <title>Essential Studio for AngularJS: Maps</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="MapsCtrl">
      <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-shapedata=world_map  e-shapesettings-fill="#9CBF4E"  e-shapesettings-strokethickness="0.5"
              e-shapesettings-stroke="white" >
              <e-sublayers>
              <e-sublayer e-shapedata=usMap  e-shapesettings-fill="orange"  e-shapesettings-strokethickness="0.5"
              e-shapesettings-stroke="white" >
              </e-sublayers>
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


![](/js/Maps/Layers_images/Layers_img1.png)

