---
layout: post
title: Map-Elements
description: map elements
platform: Angular 1.0
control: Maps
documentation: ug
---

# Map Elements

Map control contains a set of map elements such as shapes, bubbles, markers, legend, labels and data items that can be visualized with the customized appearance showing additional information on the map by using the bound data.

## Markers

Markers are notes used to leave some message on the map. 

There are two ways to set marker for map.

1. Marker and marker template

2. Adding marker objects to map.

### Markers and Marker Template 

The `e-markers` property has a list of objects that contains the data for Annotation. By default, it displays the bound data at the specified latitude and longitude. The `e-markerTemplate` property is used for customizing the template for markers.	

{% highlight html %}

   
   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
    <head>
        <title>Essential Studio for AngularJS: Maps</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="MapsCtrl">
      <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-markers=markers e-markertemplate="template">
              </e-layer>
        </e-layers>
    </div>
     <div  id="template" style="display: none;">
        <div>
            <div  style="background-image:url(http://js.syncfusion.com/demos/web/Images/map/pin.png);margin-left:3px;height:40px;width:25px;margin-top:-15px;">
	   	   </div>
        </div>
    </div>  
    <script>
     var markers = [
        { latitude: 37.0000, longitude: -120.0000, city: "California" },
        { latitude: 40.7127, longitude: -74.0059, city: "New York" },
        { latitude: 42, longitude: -93, city: "Iowa" }            
    ];
        angular.module('MapsApp', ['ejangular'])
            .controller('MapsCtrl', function ($scope) {
                $scope.markers=markers;
                        });
    </script>
    </body>
</html>  

   

{% endhighlight %}



![](/Map-Elements_images/Map-Elements_img1.png)

### Adding Marker objects to the map

Without datasource, n number of markers can be added to shape layers with `e-markers` property. Each marker object contains the following list of properties.

* `e-label` - Text that displays some information about the annotation in text format.
* `e-latitude` - Latitude point determine the Y-axis position of annotation.
* `e-longitude` - Longitude point determine the X-axis position of annotation.



{% highlight html %}

  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
    <head>
        <title>Essential Studio for AngularJS: Maps</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="MapsCtrl">
      <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-markers=markers e-markertemplate="template">
              </e-layer>
        </e-layers>
    </div>
      <div  id="template" style="display: none;">
        <div>
            <div style="margin-left:8px;height:45px;width:120px;margin-top:-23px;">					
	           <label class="label1" style="color:black;margin-left:15px;font-weight:normal">{{:city}}</label>				 			 
	        </div>
        </div>
    </div>  
    <script>
     var markers = [
        { latitude: 37.0000, longitude: -120.0000, city: "California" },
        { latitude: 40.7127, longitude: -74.0059, city: "New York" },
        { latitude: 42, longitude: -93, city: "Iowa" }            
    ];
        angular.module('MapsApp', ['ejangular'])
            .controller('MapsCtrl', function ($scope) {
                $scope.markers=markers;
                        });
    </script>
    </body>
</html>  


{% endhighlight %}



![](/Map-Elements_images/Map-Elements_img2.png)

## Bubbles

Bubbles in the **Maps** control represent the underlying data values of the map. Bubbles are scattered throughout the map shapes that contain bound values.

Bubbles are included when data binding and the `e-bubbleSettings` is set to the shape layers. 

### Properties


<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
maxValue</td><td>
String</td><td>
Get or sets the maximum height and width of the bubble.</td></tr>
<tr>
<td>
minValue</td><td>
String</td><td>
Gets or sets the minimum height and width of the bubble.</td></tr>
<tr>
<td>
colorValuePath</td><td>
String</td><td>
Get or sets the field value that is to be fetched from data for each bubble used for determining the bubble color.</td></tr>
<tr>
<td>
valuePath</td><td>
String</td><td>
Gets or sets the field value that is to be fetched from data for each bubble.</td></tr>
<tr>
<td>
colorMappings</td><td>
Collection of RangeColorMapping</td><td>
Gets or sets the tree map colors.</td></tr>
<tr>
<td>
Color</td><td>
String</td><td>
Gets or sets the fill color for bubbles.</td></tr>
<tr>
<td>
showTooltip</td><td>
Boolean</td><td>
Enable or disable the tooltip for bubbles.</td></tr>
<tr>
<td>
tooltipTemplate</td><td>
String</td><td>
Gets or sets the tooltip template for bubbles.</td></tr>
</table>

### Add Bubbles to the Map

To add bubbles to a map, the bubble marker setting is added to the shape file layer. Create the Model and ViewModel as illustrated in the Data Binding topic and add the following code. Also set the `e-bubblesettings-maxValue`, `e-bubblesettings-minValue`, and `e-bubblesettings-valuePath` properties as illustrated in the following code sample.

N> Tooltip and Color Mappings for bubble is to be set as similar to the tooltip and color mappings set in the layers and shapeSettings. For more details, refer to the Tooltip and Color Mappings section.



{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
    <head>
        <title>Essential Studio for AngularJS: Maps</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="MapsCtrl">
      <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer  e-shapedata=usMap e-shapedatapath="name" e-shapepropertypath="name" e-datasource=datasource e-enablemousehover="true"
            e-shapesettings-fill="#9CBF4E" e-shapesettings-strokethickness="0.5" e-shapesettings-stroke="white" e-bubblesettings-showbubble="true"
            e-bubblesettings-minvalue="20" e-bubblesettings-maxvalue="40" e-bubblesettings-color="#C99639" e-bubblesettings-valuepath="population">
              </e-layer>
        </e-layers>
    </div>
     <script>
         angular.module('MapsApp', ['ejangular'])
            .controller('MapsCtrl', function ($scope) {
                $scope.datasource=[
                    { name: "California", population: "38332521" },
                    { name: "New York", population: "19651127" },
                    { name: "Iowa", population: "3090416" }
                ];
                        });
    </script>
    </body>
</html>  
    
{% endhighlight %}



![](/Map-Elements_images/Map-Elements_img3.png)

## Legend

A legend is a key used on a map that contains swatches of symbols with descriptions. It provides valuable information for interpreting what the map is displaying and can be represented in various colors, shapes or other identifiers based on the data. It gives a breakdown of what each symbol represents throughout the map.

### Visibility

The Legends can be made visible by setting the `e-showLegend` property of legendSettings to true. 

### Positioning of the Legend

The legend can be positioned in two ways.

1. Absolute Position.

2. Dock Position.

#### Absolute Position

Based on the margin values of X and Y-axes, the Map legends can be positioned with the support of `e-legendsettings-positionx` and `e-legendsettings-positiony` properties available in `e-legendsettings`. For positioning the legend based on margins corresponding to a map, `e-legendsettings-position` value is set as ‘_none_’.

#### Dock Position

The map legends can be positioned in following locations within the container.

1. topLeft

2. topCenter

3. topRight

4. centerLeft

5. center

6. centerRight

7. bottomLeft

8. bottomRight

9. bottomCenter

10. bottomRight

11. none

You can set this option by using `e-legendsettings-position` property 

### Legend Size

The map legend size can be modified by using the `e-legendsettings-height` and `e-legendsettings-width` properties

### Legend for Shapes

The Layer shape type legends can be generated for each color mappings in shape settings. 

N> Here, Equal Color Mapping code sample for shapeSettings with color mappings is referred.



{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
    <head>
        <title>Essential Studio for AngularJS: Maps</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="MapsCtrl">
      <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-legendsettings-showlegend="true" e-legendsettings-position="bottomLeft" e-legendsettings-height="30" e-legendsettings-width="70">
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



![](/Map-Elements_images/Map-Elements_img4.png)

### Interactive Legend

The legends can be made interactive with an arrow mark indicating the exact range color in the legend when the mouse hovers over the corresponding shapes. You can enable this option by setting `e-legendsettings-mode` property  value as “interactive” and default value of `e-legendsettings-mode` property is “default” to enable the normal legend.

#### Title for Interactive Legend

You can provide the title for interactive legend by using `e-legendsettings-title` property 

#### Label for Interactive Legend

You can provide the left and right labels to interactive legend by using `e-legendsettings-leftlabel` and `e-legendsettings-rightlabel` properties. 

N> Here, Range Color Mapping code snippet for shapeSettings with color mappings is referred.



{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
    <head>
        <title>Essential Studio for AngularJS: Maps</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="MapsCtrl">
      <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-legendsettings-showlegend="true" e-legendsettings-position="topLeft" e-legendsettings-dockonmap="true" 
             e-legendsettings-height="15" e-legendsettings-width="150" e-legendsettings-mode="interactive" e-legendsettings-title="population"
             e-legendsettings-leftlabel="0.5M" e-legendsettings-rightlabel="40M">
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



![](/Map-Elements_images/Map-Elements_img5.png)

### Bubble Legend

A bubble legend feature is used to provide the key (legend) for another map element bubble. You can activate the Bubble legend by setting the enum `e-legendsettings-type`  as “bubble” and this enables you to easily identify what value a particular bubble is representing.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
    <head>
        <title>Essential Studio for AngularJS: Maps</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="MapsCtrl">
      <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-shapedata=usMap e-legendsettings-showlegend="true" e-legendsettings-type="bubble" e-bubblesettings-showbubble="true"
            e-bubblesettings-valuepath="population" e-bubblesettings-minvalue="20" e-bubblesettings-maxvalue="40">
             <div e-bubblesettings-colormappings-rangecolormapping>
              <e-bubblerangecolormap e-from="500000" e-to="1000000" e-color="#9CBF4E" e-range="10688">
               </e-bubblerangecolormap>
               <e-bubblerangecolormap e-from="1000001" e-to="5000000" e-color="#45D6BD" e-range="19390">
               </e-bubblerangecolormap>
               <e-bubblerangecolormap e-from="5000001" e-to="10000000" e-color="#FF567C" e-range="18718">
               </e-bubblerangecolormap>
                <e-bubblerangecolormap e-from="10000001" e-to="40000000" e-color="#470F52" e-range="30716">
               </e-bubblerangecolormap>
              </div>
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



![](/Map-Elements_images/Map-Elements_img6.png)

