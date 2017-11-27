---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: AngularJS
control: BulletGraph	
documentation: ug
---

## Methods


### destroy ()

To destroy the bullet graph


{% highlight html %}
 
<div id="bullet1">
    <ej-bulletgraph></ej-bulletgraph>
</div>

{% endhighlight %}

{% highlight js %}
 
var bullet = $("#bullet1").data("ejBulletGraph");
bullet.destroy();
   
{% endhighlight %}


### redraw()

To redraw the bullet graph


{% highlight html %}
 
<div id="bullet1">
    <ej-bulletgraph></ej-bulletgraph>
</div>

{% endhighlight %}

{% highlight js %}
 
var bullet = $("#bullet1").data("ejBulletGraph");
bullet.redraw();
   
{% endhighlight %}




### setComparativeMeasureSymbol()


To set the value for comparative measure in bullet graph.


{% highlight html %}
 
<div id="bullet1">
    <ej-bulletgraph></ej-bulletgraph>
</div>

{% endhighlight %}

{% highlight js %}
 
var bullet = $("#bullet1").data("ejBulletGraph");
bullet.setComparativeMeasureSymbol();
   
{% endhighlight %}


### setFeatureMeasureBarValue()


To set the value for feature measure bar.


{% highlight html %}
 
<div id="bullet1">
    <ej-bulletgraph></ej-bulletgraph>
</div>

{% endhighlight %}

{% highlight js %}
 
var bullet = $("#bullet1").data("ejBulletGraph");
bullet.setFeatureMeasureBarValue();
   
{% endhighlight %}


## Events


### DrawCaption

Fires on rendering the caption of bullet graph.

{% highlight html %}

<div ng-controller="angularBullet">
    <div id="container" style="width: 100%" e-drawCaption="onDrawCaption"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('angularBullet', function ($scope) {    
    $scope.onDrawCaption = "DrawCaption";    
});
 
function DrawCaption(){
    // Do Something
}

{% endhighlight %}







### DrawCategory

Fires on rendering the category.


{% highlight html %}

<div ng-controller="angularBullet"> 
    <div id="container" style="width: 100%" e-drawCategory="onDrawCategory"></div>
</div>

{% endhighlight %}

{% highlight js %}
 

angular.controller('angularBullet', function ($scope) {    
    $scope.onDrawCategory = "DrawCategory";    
});

function DrawCategory(){
    // Do Something
}

{% endhighlight %}


### DrawComparativeMeasureSymbol


Fires on rendering the comparative measure symbol.


{% highlight html %}
 
<div ng-controller="angularBullet">
    <div id="container" style="width: 100%" e-drawComparativeMeasureSymbol="onDrawComparativeMeasureSymbol"></div>
</div>

{% endhighlight %}

{% highlight js %}


angular.controller('angularBullet', function ($scope) {    
    $scope.onDrawComparativeMeasureSymbol = "DrawComparativeMeasureSymbol";    
});
 
function DrawComparativeMeasureSymbol(){
    // Do Something
}

{% endhighlight %}





### DrawFeatureMeasureBar

Fires on rendering the feature measure bar.


{% highlight html %}
 
<div ng-controller="angularBullet">
    <div id="container" style="width: 100%" e-drawFeatureMeasureBar="onDrawFeatureMeasureBar"></div>
</div>

{% endhighlight %}

{% highlight js %}


angular.controller('angularBullet', function ($scope) {    
    $scope.onDrawFeatureMeasureBar = "DrawFeatureMeasureBar";    
}); 

function DrawFeatureMeasureBar(){
    // Do Something
}

{% endhighlight %}






### DrawIndicator


Fires on rendering the indicator of bullet graph.


{% highlight html %}

<div ng-controller="angularBullet"> 
    <div id="container" style="width: 100%" e-drawIndicator="onDrawIndicator"></div>
</div>

{% endhighlight %}

{% highlight js %}


angular.controller('angularBullet', function ($scope) {    
    $scope.onDrawIndicator = "DrawIndicator";    
}); 
 
function DrawIndicator(){
    // Do Something
}

{% endhighlight %}






### DrawLabels


Fires on rendering the labels.



{% highlight html %}

<div ng-controller="angularBullet"> 
    <div id="container" style="width: 100%" e-drawLabels="onDrawLabels"></div>
</div>

{% endhighlight %}

{% highlight js %}


angular.controller('angularBullet', function ($scope) {    
    $scope.onDrawLabels = "DrawLabels";    
}); 
 
function onDrawLabels(){
    // Do Something
}

{% endhighlight %}


### DrawTicks

Fires on rendering the ticks.



{% highlight html %}

<div ng-controller="angularBullet"> 
    <div id="container" style="width: 100%" e-drawTicks="onDrawTicks"></div>
</div>

{% endhighlight %}

{% highlight js %}


angular.controller('angularBullet', function ($scope) {    
    $scope.onDrawTicks = "DrawTicks";    
}); 
 
function DrawTicks(){
    // Do Something
}

{% endhighlight %}


### DrawQualitativeRanges


Fires on rendering the qualitative ranges.



{% highlight html %}

<div ng-controller="angularBullet"> 
    <div id="container" style="width: 100%" e-drawQualitativeRanges="onDrawQualitativeRanges"></div>
</div>

{% endhighlight %}

{% highlight js %}
 

angular.controller('angularBullet', function ($scope) {    
    $scope.onDrawQualitativeRanges = "DrawQualitativeRanges";    
}); 

function DrawQualitativeRanges(){
    // Do Something
}

{% endhighlight %}






### Load

Fires on loading bullet graph.



{% highlight html %}

<div ng-controller="angularBullet"> 
    <div id="container" style="width: 100%" e-load="onLoad"></div>
</div>

{% endhighlight %}

{% highlight js %}


angular.controller('angularBullet', function ($scope) {    
    $scope.onLoad = "Load";    
}); 
 
function Load(){
    // Do Something
}

{% endhighlight %}


