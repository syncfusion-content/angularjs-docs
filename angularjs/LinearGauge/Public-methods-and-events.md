---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: AngularJS
control: Linear Gauge
documentation: ug
---

##Events


### DrawBarPointers

Triggers while the bar pointer are being drawn on the gauge, you can use `DrawBarPointers` event.


{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-drawBarPointers="onDrawBarPointers"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onDrawBarPointers = "DrawBarPointers";    
});
 
function DrawBarPointers(){
    // Do Something
}

{% endhighlight %}

### DrawCustomLabel

Triggers while the customLabel are being drawn on the gauge, you can use `DrawCustomLabel` event.

{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-drawCustomLabel="onDrawCustomLabel"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onDrawCustomLabel = "DrawCustomLabel";    
});
 
function DrawCustomLabel(){
    // Do Something
}

{% endhighlight %}







### DrawIndicators

Triggers while the Indicator are being drawn on the gauge, you can use `DrawIndicators` event.


{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-drawIndicators="onDrawIndicators"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onDrawIndicators = "DrawIndicators";    
});
 
function DrawIndicators(){
    // Do Something
}

{% endhighlight %}





### DrawLabels

Triggers while the label are being drawn on the gauge, you can use `DrawLabels` event.


{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-drawLabels="onDrawLabels"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onDrawLabels = "DrawLabels";    
});
 
function DrawLabels(){
    // Do Something
}

{% endhighlight %}




### DrawMarkerPointers

Triggers while the marker are being drawn on the gauge, you can use `DrawMarkerPointers` event.


{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-drawMarkerPointers="onDrawMarkerPointers"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onDrawMarkerPointers = "DrawMarkerPointers";    
});
 
function DrawMarkerPointers(){
    // Do Something
}

{% endhighlight %}



### DrawRange

Triggers while the range are being drawn on the gauge, you can use `DrawRange` event.


{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-drawRange="onDrawRange"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onDrawRange = "DrawRange";    
});
 
function DrawRange(){
    // Do Something
}

{% endhighlight %}






### DrawTicks

Triggers while the ticks are being drawn on the gauge, you can use `DrawTicks` event.


{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-drawTicks="onDrawTicks"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onDrawTicks = "DrawTicks";    
});
 
function DrawTicks(){
    // Do Something
}

{% endhighlight %}






### Init

Triggers when the gauge is initialized, you can use `Init` event.



{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-init="onInit"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onInit = "Init";    
});
 
function Init(){
    // Do Something
}

{% endhighlight %}




### Load

Triggers while the gauge start to Load, you can use `Load` event.


{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-load="onLoad"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onLoad = "Load";    
});
 
function Load(){
    // Do Something
}

{% endhighlight %}





### MouseClick

Triggers when the left mouse button is clicked, you can use `MouseClick` event.



{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-mouseClick="onMouseClick"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onMouseClick = "MouseClick";    
});
 
function MouseClick(){
    // Do Something
}

{% endhighlight %}







### MouseClickMove

Triggers when clicking and dragging the mouse pointer over the gauge pointer, you can use `MouseClickMove` event.


{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-mouseClickMove="onMouseClickMove"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onMouseClickMove = "MouseClickMove";    
});
 
function MouseClickMove(){
    // Do Something
}

{% endhighlight %}






### MouseClickUp


Triggers when the mouse click is released, you can use `MouseClickUp` event.



{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-mouseClickUp="onMouseClickUp"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onMouseClickUp = "MouseClickUp";    
});
 
function MouseClickUp(){
    // Do Something
}

{% endhighlight %}






### RenderComplete

Triggers while the rendering of the gauge completed, you can use `RenderComplete` event.


{% highlight html %}

<div ng-controller="LinearGauge">
    <div id="container" style="width: 100%" e-renderComplete="onRenderComplete"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('LinearGauge', function ($scope) {    
    $scope.onRenderComplete = "RenderComplete";    
});
 
function RenderComplete(){
    // Do Something
}

{% endhighlight %}


## Methods


### destroy()

`Destroy` the linear gauge all events bound using this._on will be unbind automatically and bring the control to pre-init state.


 {% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.destroy();
</script>

{% endhighlight %}


### getBarDistanceFromScale()

To get bar distance from scale in number, you can use `getBarDistanceFromScale` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getBarDistanceFromScale();
</script>

{% endhighlight %}


### getBarPointerValue()

To get Bar Pointer Value in number, you can use `getBarPointerValue`method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getBarPointerValue();
</script>

{% endhighlight %}

### getBarWidth()

To get Bar Width in number, you can use `getBarWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getBarWidth();
</script>

{% endhighlight %}



### getCustomLabelAngle()

To get CustomLabel Angle in number, you can use `getCustomLabelAngle` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getCustomLabelAngle();
</script>

{% endhighlight %}



### getCustomLabelValue()

To get CustomLabel Value in string, you can use `getCustomLabelValue` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getCustomLabelValue();
</script>

{% endhighlight %}


### getLabelAngle()

To get Label Angle in number, you can use `getLabelAngle` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getLabelAngle();
</script>

{% endhighlight %}




### getLabelPlacement()

To get LabelPlacement in number, you can use `getLabelPlacement` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getLabelPlacement();
</script>

{% endhighlight %}


### getLabelStyle()

To get LabelStyle in number, you can use `getLabelStyle` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getLabelStyle();
</script>

{% endhighlight %}




### getLabelXDistanceFromScale()

To get Label XDistance From Scale in number, you can use `getLabelXDistanceFromScale` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getLabelXDistanceFromScale();
</script>

{% endhighlight %}




### getLabelYDistanceFromScale()
To get PointerValue in number, you can use `getLabelXDistanceFromScale` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getLabelYDistanceFromScale();
</script>

{% endhighlight %}






### getMajorIntervalValue()

To get Major Interval Value in number, you can use `getMajorIntervalValue` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getMajorIntervalValue();
</script>

{% endhighlight %}


### getMarkerStyle()

To get MarkerStyle in number, you can use `getMarkerStyle` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getMarkerStyle();
</script>

{% endhighlight %}



### getMaximumValue()

To get Maximum Value in number, you can use `getMaximumValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getMaximumValue();
</script>

{% endhighlight %}


### getMinimumValue()

To get PointerValue in number, you can use `getMinimumValue` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getMinimumValue();
</script>

{% endhighlight %}

### getMinorIntervalValue()

To get Minor Interval Value in number, you can use `getMinorIntervalValue` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getMinorIntervalValue();
</script>

{% endhighlight %}


### getPointerDistanceFromScale()

To get Pointer Distance From Scale in number, you can use `getPointerDistanceFromScale` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getPointerDistanceFromScale();
</script>

{% endhighlight %}

### getPointerHeight()

To get PointerHeight in number, you can use `getPointerHeight` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getPointerHeight();
</script>

{% endhighlight %}


### getPointerPlacement()

To get Pointer Placement in String, you can use `getPointerPlacement` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getPointerPlacement();
</script>

{% endhighlight %}

### getPointerValue()

To get PointerValue in number, you can use `getPointerValue` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getPointerValue();
</script>

{% endhighlight %}


### getPointerWidth()

To get PointerWidth in number, you can use `getPointerWidth` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getPointerWidth();
</script>

{% endhighlight %}


### getRangeBorderWidth()

To get Range Border Width in number, you can use `getRangeBorderWidth` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getRangeBorderWidth();
</script>

{% endhighlight %}


### getRangeDistanceFromScale()

To get Range Distance From Scale in number, you can use `getRangeDistanceFromScale` method.




{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getRangeDistanceFromScale();
</script>

{% endhighlight %}


### getRangeEndValue()

To get Range End Value in number, you can use `getRangeEndValue` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getRangeEndValue();
</script>

{% endhighlight %}



### getRangeEndWidth()

To get Range End Width in number, you can use `getRangeEndWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getRangeEndWidth();
</script>

{% endhighlight %}




### getRangePosition()

To get Range Position in number, you can use `getRangePosition` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getRangePosition();
</script>

{% endhighlight %}



### getRangeStartValue()

To get Range Start Value in number, you can use `getRangeStartValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getRangeStartValue();
</script>

{% endhighlight %}







### getRangeStartWidth()

To get Range Start Width in number, you can use `getRangeStartWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getRangeStartWidth();
</script>

{% endhighlight %}



### getScaleBarLength()

To get ScaleBarLength in number, you can use `getScaleBarLength` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getScaleBarLength();
</script>

{% endhighlight %}


### getScaleBarSize()

To get Scale Bar Size in number, you can use `getScaleBarSize` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getScaleBarSize();
</script>

{% endhighlight %}


### getScaleBorderWidth()

To get Scale Border Width in number, you can use `getScaleBorderWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getScaleBorderWidth();
</script>

{% endhighlight %}

### getScaleDirection()

To get Scale Direction in number, you can use `getScaleDirection` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getScaleDirection();
</script>

{% endhighlight %}



### getScaleLocation()

To get Scale Location in object, you can use `getScaleLocation` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getScaleLocation();
</script>

{% endhighlight %}




### getScaleStyle()

To get Scale Style in string, you can use `getScaleStyle` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getScaleStyle();
</script>

{% endhighlight %}



### getTickAngle()

To get Tick Angle in number, you can use `getTickAngle` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getTickAngle();
</script>

{% endhighlight %}



### getTickHeight()

To get Tick Height in number, you can use `getTickHeight` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getTickHeight();
</script>

{% endhighlight %}

### getTickPlacement()

To get getTickPlacement in number, you can use `getTickPlacement` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getTickPlacement();
</script>

{% endhighlight %}


### getTickStyle()

To get Tick Style in string, you can use `getTickStyle` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getTickStyle();
</script>

{% endhighlight %}


### getTickWidth()

To get Tick Width in number, you can use `getTickWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getTickWidth();
</script>

{% endhighlight %}

### getTickXDistanceFromScale()

To get get Tick XDistance From Scale in number, you can use `getTickXDistanceFromScale` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getTickXDistanceFromScale();
</script>

{% endhighlight %}



### getTickYDistanceFromScale()

To get Tick YDistance From Scale in number, you can use `getTickYDistanceFromScale` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.getTickYDistanceFromScale();
</script>

{% endhighlight %}



### scales()

Specifies the scales, you can use `scales` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.scales();
</script>

{% endhighlight %}

### setBarDistanceFromScale()

To set setBarDistanceFromScale, you can use `setBarDistanceFromScale` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setBarDistanceFromScale();
</script>

{% endhighlight %}

### setBarPointerValue()

To set setBarPointerValue, you can use `setBarPointerValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setBarPointerValue();
</script>

{% endhighlight %}


### setBarWidth()

To set setBarWidth, you can use `setBarWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setBarWidth();
</script>

{% endhighlight %}


### setCustomLabelAngle()

To set setCustomLabelAngle, you can use `setCustomLabelAngle` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setCustomLabelAngle();
</script>

{% endhighlight %}


### setCustomLabelValue()

To set setCustomLabelValue, you can use `setCustomLabelValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setCustomLabelValue();
</script>

{% endhighlight %}



### setLabelAngle()

To set setLabelAngle, you can use `setLabelAngle` method.

{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setLabelAngle();
</script>

{% endhighlight %}



### setLabelPlacement()

To set setLabelPlacement, you can use `setLabelPlacement` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setLabelPlacement();
</script>

{% endhighlight %}

### setLabelStyle()

To set setLabelStyle, you can use `setLabelStyle` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setLabelStyle();
</script>

{% endhighlight %}


### setLabelXDistanceFromScale()

To set setLabelXDistanceFromScale, you can use `setLabelXDistanceFromScale` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setLabelXDistanceFromScale();
</script>

{% endhighlight %}



### setLabelYDistanceFromScale()

To set setLabelYDistanceFromScale, you can use `setLabelYDistanceFromScale` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setLabelYDistanceFromScale();
</script>

{% endhighlight %}


### setMajorIntervalValue()

To set setMajorIntervalValue, you can use `setMajorIntervalValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setMajorIntervalValue();
</script>

{% endhighlight %}



### setMarkerStyle()

To set setMarkerStyle, you can use `setMarkerStyle` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setMarkerStyle();
</script>

{% endhighlight %}




### setMaximumValue()

To set setMaximumValue, you can use `setMaximumValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setMaximumValue();
</script>

{% endhighlight %}


### setMinimumValue()

To set setMinimumValue, you can use `setMinimumValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setMinimumValue();
</script>

{% endhighlight %}



### setMinorIntervalValue()

To set setMinorIntervalValue, you can use `setMinorIntervalValue` method.



{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setMinorIntervalValue();
</script>

{% endhighlight %}


### setPointerDistanceFromScale()

To set setPointerDistanceFromScale, you can use `setPointerDistanceFromScale` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setPointerDistanceFromScale();
</script>

{% endhighlight %}




### setPointerHeight()

To set PointerHeight, you can use `setPointerHeight` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setPointerHeight();
</script>

{% endhighlight %}




### setPointerPlacement()

To set setPointerPlacement, you can use `setPointerPlacement` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setPointerPlacement();
</script>

{% endhighlight %}




### setPointerValue()

To set PointerValue, you can use `setPointerValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setPointerValue();
</script>

{% endhighlight %}




### setPointerWidth()

To set PointerWidth, you can use `setPointerWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setPointerWidth();
</script>

{% endhighlight %}




### setRangeBorderWidth()

To set setRangeBorderWidth, you can use `setRangeBorderWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setRangeBorderWidth();
</script>

{% endhighlight %}




### setRangeDistanceFromScale()

To set setRangeDistanceFromScale, you can use `setRangeDistanceFromScale` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setRangeDistanceFromScale();
</script>

{% endhighlight %}




### setRangeEndValue()

To set setRangeEndValue, you can use `setRangeEndValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setRangeEndValue();
</script>

{% endhighlight %}




### setRangeEndWidth()

To set setRangeEndWidth, you can use `setRangeEndWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setRangeEndWidth();
</script>

{% endhighlight %}



### setRangePosition()

To set setRangePosition, you can use `setRangePosition` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setRangePosition();
</script>

{% endhighlight %}


### setRangeStartValue()

To set setRangeStartValue, you can use `setRangeStartValue` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setRangeStartValue();
</script>

{% endhighlight %}




### setRangeStartWidth()

To set setRangeStartWidth, you can use `setRangeStartWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setRangeStartWidth();
</script>

{% endhighlight %}





### setScaleBarLength()

To set setScaleBarLength, you can use `setScaleBarLength` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setScaleBarLength();
</script>

{% endhighlight %}



### setScaleBarSize()

To set setScaleBarSize, you can use `setScaleBarSize` method.

{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setScaleBarSize();
</script>

{% endhighlight %}



### setScaleBorderWidth()

To set setScaleBorderWidth, you can use `setScaleBorderWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setScaleBorderWidth();
</script>

{% endhighlight %}




### setScaleDirection()

To set setScaleDirection, you can use `setScaleDirection` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setScaleDirection();
</script>

{% endhighlight %}



### setScaleLocation()

To set setScaleLocation, you can use `setScaleLocation` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setScaleLocation();
</script>

{% endhighlight %}





### setScaleStyle()

To set setScaleStyle, you can use `setScaleStyle` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setScaleStyle();
</script>

{% endhighlight %}


### setTickAngle()

To set setTickAngle, you can use `setTickAngle` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setTickAngle();
</script>

{% endhighlight %}

### setTickHeight()

To set setTickHeight, you can use `setTickHeight` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setTickHeight();
</script>

{% endhighlight %}



### setTickPlacement()

To set setTickPlacement, you can use `setTickPlacement` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setTickPlacement();
</script>

{% endhighlight %}

### setTickStyle()

To set setTickStyle, you can use `setTickStyle` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setTickStyle();
</script>

{% endhighlight %}



### setTickWidth()

To set setTickWidth, you can use `setTickWidth` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setTickWidth();
</script>

{% endhighlight %}


### setTickXDistanceFromScale()

To set setTickXDistanceFromScale, you can use `setTickXDistanceFromScale` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setTickXDistanceFromScale();
</script>

{% endhighlight %}


### setTickYDistanceFromScale()

To set setTickYDistanceFromScale, you can use `setTickYDistanceFromScale` method.


{% highlight html %}
 
<div id="LinearGauge1">
    <ej-lineargauge></ej-lineargauge>
</div>

<script>
    var linear = $("#LinearGauge1").data("ejLinearGauge");
    linear.setTickYDistanceFromScale();
</script>

{% endhighlight %}



