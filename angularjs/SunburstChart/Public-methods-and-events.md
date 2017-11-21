---
layout: post
title: Public Methods and Events
description: What are the different modes of selection present in the Sunburst Chart
platform: AngularJS
control: SunburstChart
documentation: ug
---

## Methods


### redraw()

`redraw` the entire sunburst. You can call this method whenever you update, add or remove points from the data source or whenever you want to refresh the UI.



{% highlight html %}
 
<div id="SunburstCtrl">
    <ej-sunburstchart></ej-sunburstchart>
</div>

{% endhighlight %}


{% highlight js %}
 
var sun = $("#SunburstCtrl").data("ejSunburstChart");
sun.redraw();
   
{% endhighlight %}

### destroy ()

`destroy` the sunburst



{% highlight html %}
 
<div id="SunburstCtrl">
    <ej-sunburstchart></ej-sunburstchart>
</div>

{% endhighlight %}

{% highlight js %}
 
var sun = $("#SunburstCtrl").data("ejSunburstChart");
sun.destroy();
   
{% endhighlight %}



## Events

### Load

Fires before loading, you can use `Load` event.



{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-load="onLoad"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onLoad = "Load";    
});
 
function Load(){
    // Do Something
}

{% endhighlight %}



### PreRender

Fires before rendering sunburst, you can use `PreRender` event. 


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-preRender="onPreRender"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onPreRender = "PreRender";    
});
 
function PreRender(){
    // Do Something
}

{% endhighlight %}


### Loaded

Fires after rendering sunburst, you can use `Loaded` event.  


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-loaded="onLoaded"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onLoaded = "Loaded";    
});
 
function Loaded(){
    // Do Something
}

{% endhighlight %}


### DataLabelRendering

Fires before rendering the data label, you can use `DataLabelRendering` event. 


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-dataLabelRendering="onDataLabelRendering"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onDataLabelRendering = "DataLabelRendering";    
});
 
function DataLabelRendering(){
    // Do Something
}

{% endhighlight %}

### SegmentRendering

Fires before rendering each segment, you can use `SegmentRendering` event. 


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-segmentRendering="onSegmentRendering"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onSegmentRendering = "SegmentRendering";    
});
 
function SegmentRendering(){
    // Do Something
}

{% endhighlight %}

### TitleRendering

Fires before rendering sunburst title, you can use `TitleRendering` event.  


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-titleRendering="onTitleRendering"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onTitleRendering = "TitleRendering";    
});
 
function TitleRendering(){
    // Do Something
}

{% endhighlight %}



### TooltipInitialize





Fires during initialization of tooltip, you can use `TooltipInitialize` event.  


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-tooltipInitialize="onTooltipInitialize"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onTooltipInitialize = "TooltipInitialize";    
});
 
function TooltipInitialize(){
    // Do Something
}

{% endhighlight %}


### PointRegionClick

Fires after clicking the point in sunburst, you can use `PointRegionClick` event. 


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-pointRegionClick="onPointRegionClick"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onPointRegionClick = "PointRegionClick";    
});
 
function PointRegionClick(){
    // Do Something
}

{% endhighlight %}

### PointRegionMouseMove

Fires while moving the mouse over sunburst points, you can use `PointRegionMouseMove` event. 


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-pointRegionMouseMove="onPointRegionMouseMove"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onPointRegionMouseMove = "PointRegionMouseMove";    
});
 
function PointRegionMouseMove(){
    // Do Something
}

{% endhighlight %}


### DrillDownClick

Fires when clicking the point to perform drilldown, you can use `DrillDownClick` event.  


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-drillDownClick="onDrillDownClick"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onDrillDownClick = "DrillDownClick";    
});
 
function DrillDownClick(){
    // Do Something
}

{% endhighlight %}

### DrillDownBack

Fires when resetting drilldown points, you can use `DrillDownBack` event.  



{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-drillDownBack="onDrillDownBack"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onDrillDownBack = "DrillDownBack";    
});
 
function DrillDownBack(){
    // Do Something
}

{% endhighlight %}


### DrillDownReset


Fires after resetting the sunburst points, you can use `DrillDownReset` event.  


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-drillDownReset="onDrillDownReset"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onDrillDownReset = "DrillDownReset";    
});
 
function DrillDownReset(){
    // Do Something
}

{% endhighlight %}

### LegendItemRendering


Fires before rendering the legend item, you can use `LegendItemRendering` event. 


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-legendItemRendering="onLegendItemRendering"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onLegendItemRendering = "LegendItemRendering";    
});
 
function Load(){
    // Do Something
}

{% endhighlight %}

### LegendItemClick


Fires when clicking the legend item, you can use `LegendItemClick` event.


{% highlight html %}

<div ng-controller="SunburstCtrl">
    <div id="container" style="width: 100%" e-legendItemClick="onLegendItemClick"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('SunburstCtrl', function ($scope) {    
    $scope.onLegendItemClick = "LegendItemClick";    
});
 
function LegendItemClick(){
    // Do Something
}

{% endhighlight %}

