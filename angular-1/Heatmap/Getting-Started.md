---
layout: post
title: Getting started with Syncfusion Essential HeatMap for Angular 1.0
description: Getting started walk through to create your first Heat map.
platform: js
control: ejHeatMap
documentation: ug
---

# Getting Started

This section helps to get started of the HeatMap component for AngularJS. 

## Initialize the HeatMap

1\. Create an `HTML` file and add the necessary script references and style sheets in the `Head` tag as shown in the following code example.

{% highlight html %}

<!DOCTYPE html>
<html ng-app="defaultApp">
   <head>
    <link rel="stylesheet" href="http://cdn.syncfusion.com/14.3.0.49/js/web/bootstrap-  theme/ej.web.all.min.css" />
    <script src="https://code.jquery.com/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js" type="text/javascript"></script>
    <script src="https://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js"></script>
    <script src="https://code.angularjs.org/1.4.0-rc.2/angular.min.js"></script>
    <script src="http://cdn.syncfusion.com/14.3.0.49/js/web/ej.web.all.min.js" type="text/javascript"></script>
    <script src="http://js.syncfusion.com/demos/web/scripts/xljsondata.js" type="text/javascript"></script>
    <script src="https://code.angularjs.org/1.4.0-rc.2/angular-route.min.js"></script>
    <script src="http://cdn.syncfusion.com/14.3.0.49/js/common/ej.widget.angular.min.js"></script>
   </head>
   <body>
   </body>
</html>

{% endhighlight %}

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use[CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

## Initialize HeatMap

2\. Add a placeholder `div` element that can be used to initialize the heat map widget as shown below.

{% highlight html %}

<!DOCTYPE html>
<html ng-app="defaultApp">  
    <body ng-controller="heatmapCtrl">
          <ej-heatmap id="HeatMap"  e-height="600px" e-width="100%"></ej-heatmap>
    </body>
</html>

{% endhighlight %}

{% highlight html %}

<!DOCTYPE html>
<html>    
   <body>
      <script>
      var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
      syncApp.controller('heatmapCtrl', function ($scope,$rootScope) {
      });
      </script>
    </body>
</html>

{% endhighlight %}

### Prepare and Populate data

Populate product information in a collection called `ItemsSource`.

### Map data into HeatMap

Now data is ready, next we need to configure data source and map rows and columns to visualize. For that, need to prepare `ItemsMapping` add it in resource and set items source and mapping.
Next we can configure color range for these values using color mapping and also configure items mapping based on items source.

{% highlight html %}
<!DOCTYPE html>
    <html ng-app="defaultApp">
<body ng-controller="heatmapCtrl">
    <ej-heatmap id="HeatMap" e-width="100%" e-height="300px"
                e-itemssource="itemsSource"
                e-heatmapcell-showcontent="showContentValue"
                e-heatmapcell-showcolor="cellColor"
                e-itemsmapping="itemsMapping">
    <e-colormappingcollection>
        <e-colormapping e-value="0" e-color="#8ec8f8"></e-colormapping>
        <e-colormapping e-value="100" e-color="#0d47a1"></e-colormapping>
    </e-colormappingcollection>
    </ej-heatmap>
</body>
</html>

{% endhighlight %}

{% highlight %}

<!DOCTYPE html>
<html>    
   <body>
      <script>
var scope;
var itemsSource = [];
var rows = ["Vegie-spread", "Tofuaa", "Alice Mutton", "Konbu", "Fløtemysost", "Perth Pasties", "Boston Crab Meat", "Raclette Courdavault"];
for (var i = 0; i < 8; i++) {
    itemsSource.push({
        ProductName: rows[i],
        Y2010: getValue(),
        Y2011: getValue(),
        Y2012: getValue(),
        Y2013: getValue(),
        Y2014: getValue(),
        Y2015: getValue(),
        Y2016: getValue(),
        Y2017: getValue(),
        Y2018: getValue()
    });
}
function getValue() {
    return Math.floor((Math.random() * 100) + 1);
}

     var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
syncApp.controller('heatmapCtrl', function ($scope, $rootScope) {
    $scope.itemsSource = itemsSource;
    $scope.itemsMapping = {
        row: { "propertyName": "Year", "displayName": "Year", },
        value: { "propertyName": "Value" },
        columnMapping: [
    { "propertyName": "Y2010", "displayName": "Y2010", columnStyle: { width: 100 } },
    { "propertyName": "Y2011", "displayName": "Y2011", columnStyle: { width: 100 } },
    { "propertyName": "Y2012", "displayName": "Y2012", columnStyle: { width: 100 } },
    { "propertyName": "Y2013", "displayName": "Y2013", columnStyle: { width: 100 } },
    { "propertyName": "Y2014", "displayName": "Y2014", columnStyle: { width: 100 } },
    { "propertyName": "Y2015", "displayName": "Y2015", columnStyle: { width: 100 } },
    { "propertyName": "Y2016", "displayName": "Y2016", columnStyle: { width: 100 } },
    { "propertyName": "Y2017", "displayName": "Y2017", columnStyle: { width: 100 } },
    { "propertyName": "Y2018", "displayName": "Y2018", columnStyle: { width: 100 } },
        ],
        headerMapping: { "propertyName": "ProductName", "displayName": "Product Name", columnStyle: { width: 140 } }
    };
});
      </script>
    </body>
</html>

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img1.png)

## Initialize Legend

A legend control is used to represent range value in a gradient, create a legend with the same color mapping as shown below.
 
{% highlight html %}
<!DOCTYPE html>
    <html ng-app="defaultApp">
<body ng-controller="heatmapCtrl">
    <ej-heatmaplegend id="heatmap_legend" e-isresponsive="true"
                      e-height="50px"
                      e-width="75%">
        <e-colormappingcollection>
            <e-colormapping e-value="0" e-color="#8ec8f8"></e-colormapping>
            <e-colormapping e-value="100" e-color="#0d47a1"></e-colormapping>
        </e-colormappingcollection>
    </ej-heatmaplegend>
</body>
</html>

{% endhighlight %}

{% highlight %}

<!DOCTYPE html>
<html>    
   <body>
      <script>
var scope;
     var syncApp = angular.module("defaultApp", ["ngRoute", "ejangular"]);
syncApp.controller('heatmapCtrl', function ($scope, $rootScope) {
    $scope.legendCollection = ["heatmap_legend"];
});
      </script>
    </body>
</html>

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img2.png)