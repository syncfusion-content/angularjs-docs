---
layout: post
title: TreeMap-Elements
description: treemap elements
platform: AngularJS
control: TreeMap
documentation: ug
---

# TreeMap Elements

TreeMap contains various elements such as,

* Legend
* Headers
* Labels

## Legend

You can set the color value of **leaf nodes** using `e-treeMapLegend`. This legend is appropriate only for the **TreeMap** whose leaf nodes are colored using `e-rangeColorMapping`.

You can set `e-showLegend` property value to **“true”** to enable or disable legend visibility.

### TreeMap Legend

You can decide the size of the legend icons by setting `e-iconWidth` and `e-iconHeight` properties of the `e-treeMapLegend` property avail in **TreeMap**.

### Label for Legend

You can customize the labels of the **legend item** using `e-legendLabel` property of `e-rangeColorMapping`. 

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-datasource=populationdata e-colorValuePath="Growth" e-weightvaluepath="Population"
     e-showlegend="true" e-itemslayoutmode="squarified" e-legendsettings-height="40" 
     e-legendsettings-width="700">
     <e-rangecolormapping>
     <e-rangecolor e-color="#77D8D8" e-from="0" e-to="1" e-legendlabel="Range1"></e-rangecolor>
     <e-rangecolor e-color="#AED960" e-from="0" e-to="2" e-legendlabel="Range2"></e-rangecolor>
     <e-rangecolor e-color="#FFAF51" e-from="0" e-to="3" e-legendlabel="Range3"></e-rangecolor>
     <e-rangecolor e-color="#F3D240" e-from="0" e-to="4" e-legendlabel="Range4"></e-rangecolor>
     </e-rangecolormapping>
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

![](TreeMap-Elements_images/TreeMap-Elements_img1.png)


### Interactive Legend

The legends can be made interactive with an arrow mark indicating the exact range color in the legend when the mouse hovers over the corresponding treemap items. You can enable this option by setting `e-legendsettings-mode` property in `e-legendSettings` value as “interactive” and default value of `mode` property is “default” to enable the normal legend.

#### Title for Interactive Legend

You can provide the title for interactive legend by using `e-legendsettings-title` property in `ej-treemap`.

#### Label for Interactive Legend

You can provide the left and right labels to interactive legend by using `e-legendsettings-leftLabel` and `e-legendsettings-rightLabel` properties in `ej-treemap`. 


{% highlight html %}

   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-showlegend="true" e-legendsettings-height="15" e-legendsettings-width="150" 
     e-legendsettings-mode="interactive" e-legendsettings-title="population" 
     e-legendsettings-leftLabel="0.5M" e-legendsettings-righlabel="40M" e-legendsettings-dockposition="top">
     //...
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

![](TreeMap-Elements_images/Interactive_Legend.png)


## Header

You can set headers for each level by setting the `e-showHeader` property of the each **TreeMap** levels. The `e-headerHeight` property helps to set the height of the header and Group path value determines the header value. You can customize the default header appearance by setting the `e-headerTemplate` of the **TreeMap** levels.

{% highlight html %}

   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap >
    //...
     <e-levels>
     <e-level e-grouppath="Continent" e-groupgap="2" e-headerheight="25" 
     e-headertemplate="headertemplate"></e-level>
     </e-levels>
     </ej-treemap>
     </div>
     <script  id="headertemplate" type="application/htmlrender">
     <div style="background-color: white; margin:5px">
     <label style="color:black;font-size:large;" >{{:header}}</label><br />            
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



![](TreeMap-Elements_images/TreeMap-Elements_img2.png)


## Customizing the header

The text in the header can be customized by triggering the event `e-headerTemplateRendering` of the **TreeMap**. This event is triggered before rendering the header template. 
{% highlight html %}

   <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap >
    //...
     <e-levels>
     <e-level e-grouppath="Continent" e-groupgap="2" e-headerheight="25" 
     e-headertemplaterendering="loadTemplate"></e-level>
     </e-levels>
     </ej-treemap>
     </div>        
     <script>
     angular.module('TreemapApp', ['ejangular'])
     .controller('TreemapCtrl', function ($scope) {
                        });
    </script>
    <script>
        function loadTemplate(sender) {
        //...                   
        }
    </script>   
   </body>
  </html>  

{% endhighlight %}

![](TreeMap-Elements_images/TreeMap-Elements_img4.png)


## Label

You can also set labels for the leaf nodes by setting the `e-showLabels` property as true. Group path value is displayed as a label for leaf nodes. You can customize the default label appearance by setting the `e-labelTemplate` of the **TreeMap** levels.

{% highlight html %}

    
  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-leafitemsettings-labelpath="Region" e-leafitemsettings-showlabels="true" 
     e-legendsettings-height="40" e-legendsettings-width="700">
     //...
     <e-levels>
     <e-level e-grouppath="Continent" e-showlabels="true" e-groupgap="2" e-headerheight="20" 
     e-headertemplate="headertemplate" e-labelposition="topleft" ></e-level>
     </e-levels>
     </ej-treemap>
     </div>
     <script  id="headertemplate" type="application/htmlrender">
     <div style="background-color: white; margin:5px">
     <label style="color:black;font-size:large;" >{{:header}}</label><br />            
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



![](TreeMap-Elements_images/TreeMap-Elements_img3.png)

## Customizing the Overflow labels

You can handle the label overflow, by specifying any one of the following values to the property `e-leafItemSettings-textOverflow`as

**None**       - By specifying textOverflow as “none”, it displays the default label text.
**Hide**       - By specifying textOverflow as “hide”, You can hide the label, when it exceeds the header width.
**Wrap**       - By specifying textOverflow as “wrap”, you can wrap the label text.
**Wrapbyword** - By specifying textOverflow as “wrapbyword”, you can wrap the label text by word.


{% highlight html %}

    
  <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="TreemapApp">
    <head>
        <title>Essential Studio for AngularJS: TreeMap</title>
        <!--CSS and Script file References -->
    </head> 
    <body ng-controller="TreemapCtrl">
     <div id="mapContainer" style="align-content:center;width: 800px; height: 400px;">
     <ej-treemap e-leafitemsettings-labelpath="Region" e-leafitemsettings-showlabels="true" e-leafitemsettings-textoverflow="Wrap">
     //...
     <e-levels>
     <e-level e-grouppath="Continent" e-showlabels="true" e-groupgap="2" e-headerheight="20" 
     e-headertemplate="headertemplate" e-labelposition="topLeft" ></e-level>
     </e-levels>
     </ej-treemap>
     </div>
     <script  id="headertemplate" type="application/htmlrender">
     <div style="background-color: white; margin:5px">
     <label style="color:black;font-size:large;" >{{:header}}</label><br />            
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

