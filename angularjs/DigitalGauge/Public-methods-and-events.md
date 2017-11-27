---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: AngularJS
control: Digital Gauge
documentation: ug
---

## Methods


### destroy()


To `destroy` the digital gauge


{% highlight html %}
 
<div id="Gauge1">
    <ej-digitalgauge></ej-digitalgauge>
</div>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.destroy();
   
{% endhighlight %}


### exportImage(fileName, fileType)


To `export` Digital Gauge as Image


{% highlight html %}
 
<div id="Gauge1">
    <ej-digitalgauge></ej-digitalgauge>
</div>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.exportImage();
   
{% endhighlight %}


### getPosition(itemIndex)

Gets the location of an item that is displayed on the gauge.


{% highlight html %}
 
<div id="Gauge1">
    <ej-digitalgauge></ej-digitalgauge>
</div>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.getPosition();
   
{% endhighlight %}


### getValue(itemIndex)


ClientSideMethod `getValue` Gets the value of an item that is displayed on the gauge


{% highlight html %}
 
<div id="Gauge1">
    <ej-digitalgauge></ej-digitalgauge>
</div>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.getValue();
   
{% endhighlight %}



### refresh()


`Refresh` the digital gauge widget



{% highlight html %}
 
<div id="Gauge1">
    <ej-digitalgauge></ej-digitalgauge>
</div>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.refresh();
   
{% endhighlight %}


### setPosition(itemIndex, value)

ClientSideMethod `Set Position` Sets the location of an item to be displayed in the gauge


{% highlight html %}
 
<div id="Gauge1">
    <ej-digitalgauge></ej-digitalgauge>
</div>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.setPosition();
   
{% endhighlight %}


### setValue(itemIndex, value)

ClientSideMethod `SetValue` Sets the value of an item to be displayed in the gauge.

{% highlight html %}
 
<div id="Gauge1">
    <ej-digitalgauge></ej-digitalgauge>
</div>

{% endhighlight %}

{% highlight js %}
 
var gauge = $("#Gauge1").data("ejDigitalGauge");
gauge.setValue();
   
{% endhighlight %}




## Events



### Init

Triggers when the gauge is initialized.


{% highlight html %}

<div ng-controller="DigitalGaugeCtrl">
    <div id="container" style="width: 100%" e-init="onInit"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('DigitalGaugeCtrl', function ($scope) {    
    $scope.onInit = "Init";    
});
 
function Init(){
    // Do Something
}

{% endhighlight %}




### ItemRendering

Triggers when the gauge `item rendering`.


{% highlight html %}

<div ng-controller="DigitalGaugeCtrl">
    <div id="container" style="width: 100%" e-itemRendering="onItemRendering"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('DigitalGaugeCtrl', function ($scope) {    
    $scope.onItemRendering = "Init";    
});
 
function ItemRendering(){
    // Do Something
}

{% endhighlight %}



### Load


Triggers when the gauge is start to `load`.



{% highlight html %}

<div ng-controller="DigitalGaugeCtrl">
    <div id="container" style="width: 100%" e-load="onLoad"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('DigitalGaugeCtrl', function ($scope) {    
    $scope.onLoad = "Load";    
});
 
function Load(){
    // Do Something
}

{% endhighlight %}





### RenderComplete


Triggers when the gauge render is completed.




{% highlight html %}

<div ng-controller="DigitalGaugeCtrl">
    <div id="container" style="width: 100%" e-renderComplete="onRenderComplete"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('DigitalGaugeCtrl', function ($scope) {    
    $scope.onRenderComplete = "RenderComplete";    
});
 
function RenderComplete(){
    // Do Something
}

{% endhighlight %}



