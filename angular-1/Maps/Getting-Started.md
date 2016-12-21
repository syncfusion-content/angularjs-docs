---
title: Getting-Started
description: How to create a maps, add layers, enable tooltip, legend and other functionalities
platform: Angular 1.0
control: Maps
documentation: ug
keywords: ejmaps, maps, maps widget, js maps, angular maps, angularjs maps, angular 1.0 maps, angular 1 maps
---

# Getting Started

This section explains briefly about how to create **Maps** in your application with **AngularJS.**

## Create your first Map in AngularJS

You can configure an **Essential JavaScript** Map in simple steps. In this example, you can learn how to configure USA population map with customized appearance and tooltip.

![](Getting-Started_images/Getting-Started_img1.png)

## Add Libraries

To use ejMap, refer the following libraries in **HTML** page. 

To render the Maps control, the following list of external dependencies are needed, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [Angular](https://angularjs.org/) - angular latest versions
* JsRender

The required angular script as `angular.min.js` and `ej.widget.angular.min.js` which can be available in below [CDN](/js/cdn) links:

* `angular.min.js` - [http://cdn.syncfusion.com/js/assets/external/angular.min.js](http://cdn.syncfusion.com/js/assets/external/angular.min.js)
* `ej.widget.angular.min.js` - [http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js](http://cdn.syncfusion.com/14.3.0.49/js/common/ej.widget.angular.min.js)
* `ej.maps.js`


### Prepare Shape Data

The Shape Data collection describing geographical shape information can be obtained from [GEOJSON format shapes](http://www.syncfusion.com/uploads/user/uploads/Maps_GeoJSON.zip). 

In this example, USA shape is used as shape data by utilizing the “**United States of America.json**” file in the following folder structure obtained from downloaded Maps_GeoJSON folder.

**..\ Maps_GeoJSON\All Countries with States**

You can assign the complete contents in “**United States of America.json**” file to new JSON object. For your better understanding, a JS file “**usa.js**” is already created to store JSON data in JSON object “usMap”.

**[usa.js]**

{% highlight javascript %}

    var usMap = //Paste all the content copied from the JSON file//

{% endhighlight %}

### Prepare DataSource

The datasource is populated with JSON data relative to shape data and stored in JSON object. USA population as datasource is used for better understanding. The “**populationData.js**” file is used to store JSON data in JSON object “**populationData**”.

**[populationData.js]**

{% highlight javascript %}

    var populationData = [
        { name: "California", population: "38332521" },
        { name: "Texas", population: "26448193" },
        { name: "New York", population: "19651127" },
        { name: "Florida", population: "19552860" },
        { name: "Illinois", population: "12882135" },
        { name: "Pennsylvania", population: "12773801" },
        { name: "Ohio", population: "11570808" },
        { name: "Georgia", population: "9992167" },
        { name: "Michigan", population: "9895622" },
        { name: "North Carolina", population: "9848060" },
        { name: "New Jersey", population: "8899339" },
        { name: "Virginia", population: "8260405" },
        { name: "Washington", population: "6971406" },
        { name: "Massachusetts", population: "6692824" },
        { name: "Arizona", population: "6626624" },
        { name: "Indiana", population: "6570902" },
        { name: "Tennessee", population: "6495978" },
        { name: "Missouri", population: "6044171" },
        { name: "Maryland", population: "5928814" },
        { name: "Wisconsin", population: "5742713" },
        { name: "Minnesota", population: "5420380" },
        { name: "Colorado", population: "5268367" },
        { name: "Alabama", population: "4833722" },
        { name: "South Carolina", population: "4774839" },
        { name: "Louisiana", population: "4625470" },
        { name: "Kentucky", population: "4395295" },
        { name: "Oregon", population: "3930065" },
        { name: "Oklahoma", population: "3850568" },
        { name: "Puerto Rico", population: "3615086" },
        { name: "Connecticut", population: "3596080" },
        { name: "Iowa", population: "3090416" },
        { name: "Mississippi", population: "2991207" },
        { name: "Arkansas", population: "2959373" },
        { name: "Utah", population: "2900872" },
        { name: "Kansas", population: "2893957" },
        { name: "Nevada", population: "2790136" },
        { name: "New Mexico", population: "2085287" },
        { name: "Nebraska", population: "1868516" },
        { name: "West Virginia", population: "1854304" },
        { name: "Idaho", population: "1612136" },
        { name: "Hawaii", population: "1404054" },
        { name: "Maine", population: "1328302" },
        { name: "New Hampshire", population: "1323459" },
        { name: "Rhode Island", population: "1051511" },
        { name: "Montana", population: "1015165" },
        { name: "Delaware", population: "925749" },
        { name: "South Dakota", population: "844877" },
        { name: "Alaska", population: "735132" },
        { name: "North Dakota", population: "723393" },
        { name: "District of Columbia", population: "646449" },
        { name: "Vermont", population: "626630" },
        { name: "Wyoming", population: "582658" }
]


{% endhighlight %}

Refer to both shape data and datasource as illustrated in the following code example.

{% highlight javascript %}

    <!-- Shape data file-->
    <script src="usa.js" type="text/javascript"></script>
    
    <!-- Data source file-->
    <script src="populationData.js" type="text/javascript"></script>

{% endhighlight %}

## Initialize Map

1\. Create a **&lt;div&gt;** tag with a specific id and set the height and width to determine the rendering map’s size with `ej-map` attribute.
2\. Create a `e-layers` with parent of `e-layers` inside the mapContainer div.
3\. Set the shapeData attribute value as usMap which containes the USA shape data details. 

{% highlight javascript %}

    <body>
        <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-shapedata=usmap></e-layer>
        </e-layers>        
    </div>
    </body>


{% endhighlight %}

2\. Add a script tag anywhere in the web page and add the following code. 

{% highlight javascript %}

    <script>
        angular.module('MapsApp', ['ejangular'])
            .controller('MapsCtrl', function ($scope) {
                $scope.usmap = usMap;
            });
    </script>

{% endhighlight %}

3\. The final **HTML** file appears as follows.

{% highlight javascript %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="MapsApp">
<head>
    <title>Essential Studio for AngularJS: Maps</title>
    <!-- Essential Studio for JavaScript  theme reference -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!-- Essential Studio for JavaScript  script references -->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>    
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js" type="text/javascript"></script>
    <!-- Shape data file-->
    <script src="usa.js" type="text/javascript"></script>    
    <!-- Data source file-->
    <script src="populationData.js" type="text/javascript"></script>
    <!-- Add your custom scripts here -->
</head>
<body ng-controller="MapsCtrl">
    <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-shapedata=usmap></e-layer>
        </e-layers>
    </div>
        <script>
            angular.module('MapsApp', ['ejangular'])
                .controller('MapsCtrl', function ($scope) {
                    $scope.usmap = usMap;
                });
        </script>
    </body>
</html>

{% endhighlight %}

The above code renders a map, with default properties and shape input provided through data in layers.

![](Getting-Started_images/Getting-Started_img2.png)

## Data Binding in Map

The following properties in shape layers are used for binding data in **Map** control.

* dataSource
* shapeDataPath
* shapePropertyPath

### DataSource

The `dataSource` property accepts collection values as input. For example, the list of objects can be provided as input.

### Shape Data Path

The `shapeDataPath` property used to refer the data ID in dataSource. For example, "populationData" JSON object contains data ids ‘name’ and ‘population’. The `shapeDataPath` and the `shapePropertyPath` properties are related to each other (refer to `shapePropertyPath` for more details).

### Shape Property Path

The `shapePropertyPath` property is similar to the `shapeDataPath` that refers the column name in the `shapeData` property of shape layers to identify the shape. When the values of the `shapeDataPath` property in the `dataSource` property and the value of `shapePropertyPath` in the shapeData property match, then the associated object from the `dataSource` is bound to the corresponding shape.

The **JSON** object “populationData” is used as dataSource in the following code example.

{% highlight html %}

   <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <e-layers>
            <e-layer e-shapedata=usmap e-datasource=datasource e-shapedatapath="name" e-shapepropertypath="name"></e-layer>
        </e-layers>
    </div>
    <script>
        angular.module('MapsApp', ['ejangular'])
            .controller('MapsCtrl', function ($scope) {
                $scope.usmap = usMap;
                $scope.datasource = populationData;
            });
    </script>


{% endhighlight %}

## Customize Map Appearance 

You can customize the shape’s color by using `fill`, `stroke` and `strokeThickness` properties in `shapeSettings`.

{% highlight html %}

    <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <div e-layers>
            <div e-layer e-shapedata=usmap e-datasource=datasource e-shapedatapath='name' e-shapepropertypath='name'
                 e-enableselection="nenableselection" e-enablemousehover="nenablemousehover"
                 e-shapesettings-strokethickness="nstrokethickness" e-shapesettings-fill="shfill" e-shapesettings-stroke="shstroke"
                 e-shapesettings-highlightstroke="shhighlightStroke" e-shapesettings-highlightcolor="shhighlightColor" 
                 e-shapesettings-highlightborderwidth="shhighlightBorderWidth"></div>
        </div>
    </div>
    <script>
        angular.module('MapsApp', ['ejangular'])
            .controller('MapsCtrl', function ($scope) {
                $scope.usmap = usMap;
                $scope.datasource = populationData;
                $scope.nenableselection = false;
                $scope.nenablemousehover = true;
                $scope.nstrokethickness = "0.5";
                $scope.shfill = "#9CBF4E";
                $scope.shstroke = "White";
                $scope.shhighlightStroke= "White";
                $scope.shhighlightColor= "#BC5353";
                $scope.shhighlightBorderWidth= "1";
                
            });
    </script>

{% endhighlight %}



![](Getting-Started_images/Getting-Started_img3.png)

### Customize Map Appearance by Range

The Range color mapping is used to differentiate the shape’s fill based on its underlying value and color ranges. The `from` and `to` properties defines the value ranges and the `gradientColors` property defines the equivalent color ranges respective to their value ranges.

N> The `enableGradient` property value is set to true to apply gradient colors for the maps.



{% highlight html %}

<div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <div e-layers>
            <div e-layer
                 e-shapesettings-valuepath="name" e-shapesettings-enablegradient="shenableGradient" e-shapesettings-colorvaluepath="population">
                <div e-shapesettings-colormappings-rangecolormapping>
                    <e-shaperangecolormap e-from="nfrom1" e-to="nto1" e-gradientcolors="ncolor1">
                    </e-shaperangecolormap>
                    <e-shaperangecolormap e-from="nfrom2" e-to="nto2" e-gradientcolors="ncolor2">
                    </e-shaperangecolormap>
                    <e-shaperangecolormap e-from="nfrom3" e-to="nto3" e-gradientcolors="ncolor3">
                    </e-shaperangecolormap>
                    <e-shaperangecolormap e-from="nfrom4" e-to="nto4" e-gradientcolors="ncolor4">
                    </e-shaperangecolormap>
                </div>
            </div>
        </div>
    </div>
    <script>
        angular.module('MapsApp', ['ejangular'])
            .controller('MapsCtrl', function ($scope) {
                //...
                $scope.shenableGradient = true;

                $scope.nfrom1 = "500000";
                $scope.nto1 = "1000000";
                $scope.ncolor1 =["#9CBF4E", "#B8CE7B"];
                $scope.nfrom2 = "1000001";
                $scope.nto2 = "5000000";
                $scope.ncolor2 = ["#B8CE7B", "#CBD89A"];
                $scope.nfrom3 = "5000001";
                $scope.nto3 = "10000000";
                $scope.ncolor3 = ["#CBD89A", "#DEE2B9"];
                $scope.nfrom4 = "10000001";
                $scope.nto4 = "40000000";
                $scope.ncolor4 = ["#DEE2B9", "#F1ECD8"];
            });
    </script>
    

{% endhighlight %}

The following screenshot illustrates a map with gradient color property enabled.

![](Getting-Started_images/Getting-Started_img4.png)

## Enable Tooltip

The tooltip is displayed only when the `showTooltip` is set to “**True**” in the `layers`. By default, it takes the property of the bound object that is referred in the `valuePath` and displays its content on hovering the corresponding shape. The `tooltipTemplate` property is used for customizing the template for tooltip.	

{% highlight html %}

    <div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <div e-layers>
            <div e-layer e-showtooltip="true">
            </div>
        <div>
    </div>    


{% endhighlight %}

The following screenshot illustrates a map control displaying a Tooltip.

![](Getting-Started_images/Getting-Started_img5.png)

## Legend

A Legend can be made visible by setting the `showLegend` property in `legendSettings`. 

### Interactive Legend

The legends can be made interactive with an arrow mark indicating the exact range color in the legend, when the mouse hovers on the corresponding shape. You can enable this option by setting the `mode` property in the `legendSettings` value as "**interactive**". The default value of `mode` property is "**default**" to enable the normal legend.

#### Title

Use the `title` property to provide title for interactive legend.

#### Label

You can use `leftLabel` and `rightLabel` property to provide left and right labels for interactive legend.

{% highlight html %}
<div id="mapContainer" style="width: 900px; height: 600px;" ej-map>
        <div e-layers>
            <div e-layer 
                 e-legendsettings-showlegend="lshowlegend" e-legendsettings-dockonmap="ldockonmap" 
                 e-legendsettings-height="lheight" e-legendsettings-width="lwidth"
                 e-legendsettings-mode="lmode"
                 e-legendsettings-title="ltitle"
                 e-legendsettings-leftlabel=lleftlabel
                 e-legendsettings-rightlabel=lrightlabel>
            </div>
        </div>
</div>
    <script>
        angular.module('MapsApp', ['ejangular'])
            .controller('MapsCtrl', function ($scope) {
                //..
                $scope.lshowLegend=true;
                $scope.ldockOnMap=true;
                $scope.lheight=18;
                $scope.lwidth=190;
                $scope.lmode="interactive";
                $scope.ltitle= "Population";
                $scope.lleftLabel= "0.5M";
                $scope.lrightLabel= "40M";

               
            });

{% endhighlight %}

The following screenshot illustrates a map displaying an interactive legend.

![](Getting-Started_images/Getting-Started_img6.png)