---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: AngularJS
control: Maps
documentation: ug
---


## Methods

### navigateTo(latitude, longitude, level)

Method for navigating to specific shape based on latitude, longitude and zoom level, you can use `navigateTo` method.



{% highlight html %}
 
<div id="Map1">
    <ej-map></ej-map>
</div>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.navigateTo();
   
{% endhighlight %}


### pan(direction)

Method to perform map panning, you can use `pan` method.


{% highlight html %}
 
<div id="Map1">
    <ej-map></ej-map>
</div>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.pan();
   
{% endhighlight %}

### refresh()

Method to reload the map, you can use `refresh` method.

{% highlight html %}
 
<div id="Map1">
    <ej-map></ej-map>
</div>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.refresh();
   
{% endhighlight %}


### refreshLayers()

Method to reload the shapeLayers with updated values, you can use `refreshLayers` method.

{% highlight html %}
 
<div id="Map1">
    <ej-map></ej-map>
</div>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.refreshLayers();
   
{% endhighlight %}


### refreshNavigationControl(navigation)

Method to reload the navigation control with updated values, you can use `refreshNavigationControl` method.


{% highlight html %}
 
<div id="Map1">
    <ej-map></ej-map>
</div>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.refreshNavigationControl();
   
{% endhighlight %}


### zoom(level, isAnimate)

Method to perform map zooming, you can use `zoom` method.


{% highlight html %}
 
<div id="Map1">
    <ej-map></ej-map>
</div>

{% endhighlight %}

{% highlight js %}
 
var map = $("#Map1").data("ejMap");
map.zoom();
   
{% endhighlight %}



## Events

### MarkerSelected

Triggered on selecting the map markers, you can use `MarkerSelected` event.



{% highlight html %}

<div ng-controller="Map">
    <div id="container" style="width: 100%" e-markerSelected="onMarkerSelected"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('Map', function ($scope) {    
    $scope.onMarkerSelected = "MarkerSelected";    
});
 
function MarkerSelected(){
    // Do Something
}

{% endhighlight %}


### MouseLeave

Triggers while leaving the hovered map shape, you can use `MouseLeave` event.


{% highlight html %}

<div ng-controller="Map">
    <div id="container" style="width: 100%" e-mouseleave="onMouseLeave"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('Map', function ($scope) {    
    $scope.onMouseLeave = "MouseLeave";    
});
 
function MouseLeave(){
    // Do Something
}

{% endhighlight %}


### MouseOver

Triggers while hovering the map shape, you can use `MouseOver` event.


{% highlight html %}

<div ng-controller="Map">
    <div id="container" style="width: 100%" e-mouseover="onMouseOver"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('Map', function ($scope) {    
    $scope.onMouseOver = "MouseOver";    
});
 
function MouseOver(){
    // Do Something
}

{% endhighlight %}


### RenderComplete

Triggers once map render completed, you can use `RenderComplete` event.


{% highlight html %}

<div ng-controller="Map">
    <div id="container" style="width: 100%" e-rendercomplete="OnRenderComplete"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('Map', function ($scope) {    
    $scope.OnRenderComplete = "RenderComplete";    
});
 
function RenderComplete(){
    // Do Something
}

{% endhighlight %}

### Panned

Triggers when map panning ends, you can use `Panned` event.


{% highlight html %}

<div ng-controller="Map">
    <div id="container" style="width: 100%" e-panned="onPanned"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('Map', function ($scope) {    
    $scope.onPanned = "Panned";    
});
 
function Panned(){
    // Do Something
}

{% endhighlight %}


### ShapeSelected

Triggered on selecting the map shapes, you can use `ShapeSelected` event.


{% highlight html %}

<div ng-controller="Map">
    <div id="container" style="width: 100%" e-shapeSelected="onShapeSelected"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('Map', function ($scope) {    
    $scope.onShapeSelected = "ShapeSelected";    
});
 
function ShapeSelected(){
    // Do Something
}

{% endhighlight %}


### ZoomedIn

Triggered when map is zoomed-in, you can use `ZoomedIn` event.



{% highlight html %}

<div ng-controller="Map">
    <div id="container" style="width: 100%" e-zoomedIn="onZoomedIn"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('Map', function ($scope) {    
    $scope.onZoomedIn = "ZoomedIn";    
});
 
function ZoomedIn(){
    // Do Something
}

{% endhighlight %}


### ZoomedOut

Triggers when map is zoomed out, you can use `ZoomedOut` event.



{% highlight html %}

<div ng-controller="Map">
    <div id="container" style="width: 100%" e-zoomedOut="onZoomedOut"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('Map', function ($scope) {    
    $scope.onZoomedOut = "ZoomedOut";    
});
 
function ZoomedOut(){
    // Do Something
}

{% endhighlight %}
