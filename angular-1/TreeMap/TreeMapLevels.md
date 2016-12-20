---
layout: post
title: TreeMapLevels
description: treemaplevels
platform: Angular 1.0
control: TreeMap
documentation: ug
---

# TreeMapLevels

The levels of **TreeMap** can be categorized into two types as,

* FlatLevel
* Hierarchical Level

## Flat Level

### GroupPath

You can use `e-groupPath` property for every flat level of the **TreeMap** control. It is a path to a field on the source object that serves as the **“Group”** for the level specified. You can group the data based on the `e-groupPath` in the **TreeMap** control. When the `e-groupPath` is not specified, then the items are not grouped and the data is displayed in the order specified in the `e-dataSource`.

### GroupGap

You can use `e-groupGap` property to separate the items from every flat level and to differentiate the levels mentioned in the **TreeMap** control.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-datasource=populationdata e-colorValuePath="Growth" e-weightvaluepath="Population">
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



![](TreeMapLevels_images/TreeMapLevels_img1.png)

## Hierarchical Level

**TreeMap** Hierarchical level is used to define levels for hierarchical data collection that contains tree-structured data.

{% highlight html %}

   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-datasource=populationdata  e-weightvaluepath="Population">
     </ej-treemap>
     </div>
      <script>
       var population_data =  [
            {Region: "Southern Asia", Growth: 1.32, Population: 1749046000 },
            {Region: "Eastern Asia", Growth: 0.57, Population: 1620807000 },
            {Region: "South-Eastern Asia", Growth: 1.20, Population: 618793000 },
            {Region: "Western Asia", Growth: 1.98, Population: 245707000 },
            {Region: "Central Asia", Growth: 1.43, Population: 64370000 },
            {Region: "South America", Growth: 1.06, Population: 406740000 },
            {Region: "Northern America", Growth: 0.85, Population: 355361000 },
            {Region: "Central America", Growth: 1.40, Population: 167387000 },         
            {Region: "Eastern Africa", Growth: 2.89, Population: 373202000 },
            {Region: "Western Africa", Growth: 2.78, Population: 331255000 },
            {Region: "Northern Africa", Growth: 1.70, Population: 210002000 },
            {Region: "Middle Africa", Growth: 2.79, Population: 135750000 },
            {Region: "Southern Africa", Growth: 0.91, Population: 60425000 }
            
        ];

           angular.module('TreemapApp', ['ejangular'])
                .controller('TreemapCtrl', function ($scope) {
                    $scope.populationdata=population_data;
                        });
    </script>
    </body>
</html>

       


{% endhighlight %}



![](TreeMapLevels_images/TreeMapLevels_img2.png)

