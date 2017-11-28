---
layout: post
title: Public Methods and Events
description: Public Methods and Events
platform: AngularJS
control: TreeMap
documentation: ug
---


## Methods

### refresh()


Method to reload treemap with updated values.


{% highlight html %}
 
<div id="treeMap">
    <ej-treemap></ej-treemap>
</div>

{% endhighlight %}

{% highlight js %}
 
var tree = $("#treeMap").data("ejTreeMap");
tree.refresh();
   
{% endhighlight %}



## Events

### treeMapItemSelected


Triggers on treemap item selected.


{% highlight html %}

<div ng-controller="angularTreeMap">
    <div id="container" style="width: 100%" e-treeMapItemSelected="onTreeMapItemSelected"></div>
</div>

{% endhighlight %}

{% highlight js %}

angular.controller('angularTreeMap', function ($scope) {    
    $scope.onTreeMapItemSelected = "TreeMapItemSelected";    
});
 
function TreeMapItemSelected(){
    // Do Something
}

{% endhighlight %}



### drillStarted


Triggers when drilldown is started



{% highlight html %}
 
<div ng-controller="angularTreeMap">
    <div id="container" style="width: 100%" e-drillStarted="onDrillStarted"></div>
</div>

{% endhighlight %}


{% highlight js %}

angular.controller('angularTreeMap', function ($scope) {    
    $scope.onDrillStarted = "DrillStarted";    
});
 
DrillStarted(sender) {

  // do something 

  }
{% endhighlight %}  

### drillDownItemSelected


Triggers on treemap  drilldown  item  selected.




{% highlight html %}
 
 <div ng-controller="angularTreeMap">
    <div id="container" style="width: 100%" e-DrillDownItemSelected="onDrillDownItemSelected"></div>
</div>

{% endhighlight %}


{% highlight js %}

angular.controller('angularTreeMap', function ($scope) {    
    $scope.onDrillDownItemSelected = "DrillDownItemSelected";    
});
 
DrillDownItemSelected(sender) {

  // do something 

  }

{% endhighlight %}

### headerTemplateRendering


Triggers before rendering the treemap drilldown header template



{% highlight html %}
 
 <div ng-controller="angularTreeMap">
    <div id="container" style="width: 100%" e-headerTemplateRendering="onHeaderTemplateRendering"></div>
</div>

{% endhighlight %}


{% highlight js %}

angular.controller('angularTreeMap', function ($scope) {    
    $scope.onHeaderTemplateRendering = "HeaderTemplateRendering";    
});
 
HeaderTemplateRendering(sender) {

  // do something 

  }

{% endhighlight %}


### refreshed


Triggers after refreshing the treemap items.


 
{% highlight html %}
 
 <div ng-controller="angularTreeMap">
    <div id="container" style="width: 100%" e-refreshed="onRefreshed"></div>
</div>

{% endhighlight %}


{% highlight js %}


angular.controller('angularTreeMap', function ($scope) {    
    $scope.onRefreshed = "Refreshed";    
});
 
Refreshed(sender) {

  // do something 

  }

{% endhighlight %}


### treeMapGroupSelected


Triggers when the group selection is performed on treemap items.


{% highlight js %}
 
 <div ng-controller="angularTreeMap">
    <div id="container" style="width: 100%" e-treeMapGroupSelected="onTreeMapGroupSelected"></div>
</div>

{% endhighlight %}


{% highlight js %}

angular.controller('angularTreeMap', function ($scope) {    
    $scope.onTreeMapGroupSelected = "TreeMapGroupSelected";    
});
 
TreeMapGroupSelected(sender) {

  // do something 

  }

{% endhighlight %}



