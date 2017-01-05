---
layout: post
title: Layout
description: layout
platform: Angular 1.0
control: TreeMap
documentation: ug
---

# Layout

You can decide on the visual representation of nodes belonging to all the treemap levels using the `e-itemsLayoutMode` property of the TreeMap.

There are four different **TreeMap** layouts such as

* Squarified
* SliceAndDiceAuto
* SliceAndDiceHorizontal
* SliceAndDiceVertical

## Squarified

**Squarified** layout creates rectangles with best aspect ratio.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-datasource=populationdata e-colorValuePath="Growth" e-weightvaluepath="Population"
     e-itemslayoutmode="squarified">
     <e-levels>
     <e-level e-grouppath="Continent" e-groupgap="5"></e-level>
     </e-levels>
     </ej-treemap>
     </div>
     <script>
     angular.module('TreemapApp', ['ejangular'])
     .controller('TreemapCtrl', function ($scope) {
                        });
    </script>
    </body>
</html> 

{% endhighlight %}



![](Layout_images/Layout_img1.png)

## SliceAndDiceAuto

**SliceAndDiceAuto** layout creates rectangles with high aspect ratio and displays them sorted both horizontally and vertically.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-datasource=populationdata e-colorValuePath="Growth" e-weightvaluepath="Population"
     e-itemslayoutmode="sliceanddiceauto">
     <e-levels>
     <e-level e-grouppath="Continent" e-groupgap="5"></e-level>
     </e-levels>
     </ej-treemap>
     </div>
     <script>
     angular.module('TreemapApp', ['ejangular'])
     .controller('TreemapCtrl', function ($scope) {
               });
    </script>
    </body>
</html> 


{% endhighlight %}



![](Layout_images/Layout_img2.png)

## SliceAndDiceHorizontal

**SliceAndDiceHorizontal** layout creates rectangles with high aspect ratio and displays them sorted horizontally.

{% highlight html %}

   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-datasource=populationdata e-colorValuePath="Growth" e-weightvaluepath="Population"
     e-itemslayoutmode="sliceanddicehorizontal">
     <e-levels>
     <e-level e-grouppath="Continent" e-groupgap="5"></e-level>
     </e-levels>
     </ej-treemap>
     </div>
     <script>
      angular.module('TreemapApp', ['ejangular'])
      .controller('TreemapCtrl', function ($scope) {
               });
    </script>
    </body>
</html> 



{% endhighlight %}



![](Layout_images/Layout_img3.png)

## SliceAndDiceVertical

**SliceAndDiceVertical** layout creates rectangles with high aspect ratio and displays them sorted vertical.

{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-datasource=populationdata e-colorValuePath="Growth" e-weightvaluepath="Population"
     e-itemslayoutmode="sliceanddicevertical">
     <e-levels>
     <e-level e-grouppath="Continent" e-groupgap="5"></e-level>
     </e-levels>
     </ej-treemap>
     </div>
     <script>
     angular.module('TreemapApp', ['ejangular'])
     .controller('TreemapCtrl', function ($scope) {
                        });
    </script>
    </body>
</html> 



{% endhighlight %}



![](Layout_images/Layout_img4.png)

