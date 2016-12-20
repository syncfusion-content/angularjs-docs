---
layout: post
title: Customization
description: customization
platform: Angular 1.0
control: TreeMap
documentation: ug
---

# Customization

**TreeMap** control supports color customization to determine the exact combination of colors for tree nodes displayed in **TreeMap** and tooltip support to display additional information of treemap data.

## Color

You can customize the colors of the leaf nodes of **TreeMap** using the ColorMapping support of the **TreeMap**. 

ColorMapping is categorized into three different types such as,

* uniColorMapping
* rangeBrushColorMapping
* desaturationColorMapping

### Uni Color Mapping

You can color, all the leaf nodes with the same color by setting the `color` value of the `e-uniColorMapping` property of the **TreeMap**.

{% highlight html %}

 
 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-unicolormapping-color="Crimson">
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



![](Customization_images/Customization_img1.png)

### Range Color Mapping

You can group the leaf nodes based on the range of the data’s color values. You can set a unique color for every ranges. To achieve this, specify the `e-to` and `e-from` values as range bound and `e-color` value to fill the leaf nodes of the particular range, through the `e-rangeColorMapping` property of the **TreeMap**.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap>
     <e-rangecolormapping>
     <e-rangecolor e-color="#77D8D8" e-from="0" e-to="1"></e-rangecolor>
     <e-rangecolor e-color="#AED960" e-from="0" e-to="2"></e-rangecolor>
     <e-rangecolor e-color="#FFAF51" e-from="0" e-to="3"></e-rangecolor>
     <e-rangecolor e-color="#F3D240" e-from="0" e-to="4"></e-rangecolor>
     </e-rangecolormapping>
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



![](Customization_images/Customization_img2.png)

### Desaturation Color Mapping

You can differentiate all the leaf nodes using the `e-desaturationColorMapping` property of the **TreeMap**. Differentiation is achieved, even though same color is applied for all the leaf nodes by varying the opacity of the leaf nodes based on the color value specified in the color value range using `e-desaturationColorMapping-rangeMinimum` and `e-desaturationColorMapping-rangeMaximum` value of the data collection. You can also bound the opacity range by setting `e-desaturationColorMapping-from` and `e-desaturationColorMapping-to` property of the `e-desaturationColorMapping`.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-desaturationcolormapping-color="DeepSkyBlue" e-desaturationcolormapping-from="1"
                    e-desaturationcolormapping-to="0.2" e-desaturationcolormapping-rangeminimum="0" e-desaturationcolormapping-rangemaximum="4">
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



![](Customization_images/Customization_img3.png)

## Tooltip

You can enable the tooltip support for the TreeMap by setting the `e-showTooltip` property to true. By default, it takes the property of the bound object that is referred to in the groupPath and displays its content when the corresponding node is tapped. The `e-tooltipTemplate` is a **HTML** element that is used to expose the custom template for the tooltip.

## Leaf Item Setting

You can customize the **Leaf level TreeMap items** using `e-leafItemSettings`. The Label and tooltip values take the property of bound object that is referred in the `e-leafitemsettings-labelPath` when defined.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-datasource=populationdata e-colorValuePath="Growth" e-weightvaluepath="Population"
    e-leafitemsettings-labelpath="Region" e-showtooltip="true" e-tooltiptemplate="template">
      <e-rangecolormapping>
     <e-rangecolor e-color="#77D8D8" e-from="0" e-to="1"></e-rangecolor>
     <e-rangecolor e-color="#AED960" e-from="0" e-to="2"></e-rangecolor>
     <e-rangecolor e-color="#FFAF51" e-from="0" e-to="3"></e-rangecolor>
     <e-rangecolor e-color="#F3D240" e-from="0" e-to="4"></e-rangecolor>
     </e-rangecolormapping>
     <e-levels>
     <e-level e-grouppath="Continent" e-groupgap="5"></e-level>
     </e-levels>
     </ej-treemap>
     </div>
     <script  id="template" type="application/jsrender">
        <div  style="margin-left:17px;margin-top:-45px;">      
            <div style="height:auto;width:auto;background:black;border-radius:3px;opacity:0.6">
                <div style="margin-top:-20px;margin-left:9px;padding-top:3px;margin-right:9px;">
                    <label style="margin-top:-20px;font-weight:normal;font-size:12px;color:white;font-family:Segoe UI;">{{:Region}}</label>
                </div>
                <div style="height:10px;"></div>
                <div style="margin-top:-10px;margin-left:9px;margin-right:9px;padding-bottom:3px;">
                    <label style="margin-top:-10px;font-weight:normal;font-size:14px;color:white;font-family:segoe ui light;">{{:Population}}</label>
                </div>
            </div>
        </div>            
    </script>
    <script>
           angular.module('TreemapApp', ['ejangular'])
                .controller('TreemapCtrl', function ($scope) {
                        });
    </script>
    </body>
</html> 
   
    


{% endhighlight %}



![](Customization_images/Customization_img4.png)

