---
layout: post
title: Events and Methods
description: Learn how to add Events and Methods in Sparkline.
platform: AngularJS
control: Sparkline
documentation: ug
---

# Methods and Events

## Methods

### redraw()

This methods redraws the entire sparkline. You can call `redraw()` whenever you update, add or remove points from the data source or whenever you want to refresh the UI.

{% highlight html %}

<div id="container">
    <ej-sparkline></ej-sparkline>
</div>
<script>
    // Destroys range navigator
     $("#container").ejRangeNavigator("redraw");
</script>

{% endhighlight %}

## Events

### load

The `load` event is fired before loading the sparkline.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container" >
        <ej-sparkline e-load=load></ej-sparkline>
    </div>
    <script>
      angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
                $scope.load="onLoad"
        });
        function onLoad(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

### loaded

The `loaded` event is fired after sparkline in loaded.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container" >
        <ej-sparkline e-loaded=loaded></ej-sparkline>
    </div>
    <script>
      angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
                $scope.loaded="onLoaded"
        });
        function onLoaded(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

### tooltipInitialize

Fires before rendering trackball tooltip. You can use `tooltipInitialize` event to customize the text displayed in trackball tooltip.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container" >
        <ej-sparkline e-tooltipinitialize="tooltip"></ej-sparkline>
    </div>
    <script>
      angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
                $scope.tooltip="onTooltipInitialize"
        });
        function onTooltipInitialize(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

### seriesRendering

Fires before rendering a series. The `seriesRendering` event is fired for each series in Sparkline.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container" >
        <ej-sparkline e-seriesrendering="seriesrendering"></ej-sparkline>
    </div>
    <script>
      angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
                $scope.seriesrendering="onSeriesRender"
        });
        function onSeriesRender(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

### pointRegionMouseMove

The `pointRegionMouseMove` event is fired when mouse is moved over a point.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container" >
        <ej-sparkline e-pointregionmousemove="regionmousemove"></ej-sparkline>
    </div>
    <script>
      angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
                $scope.regionmousemove="onRegionMouseMove"
        });
        function onRegionMouseMove(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

### pointRegionMouseClick

The `pointRegionMouseClick` event is fired on clicking a point in sparkline. You can use this event to handle clicks made on points.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container" >
        <ej-sparkline e-pointregionmouseclick="regionmouseclick"></ej-sparkline>
    </div>
    <script>
      angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
                $scope.regionmouseclick="onRegionMouseClick"
        });
        function onRegionMouseClick(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

### sparklineMouseMove

The `sparklineMouseMove` is fired on moving mouse over the sparkline.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container" >
        <ej-sparkline e-sparklinemousemove="sparklinemousemove"></ej-sparkline>
    </div>
    <script>
      angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
                $scope.sparklinemousemove="onSparklineMouseMove"
        });
        function onSparklineMouseMove(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

### sparklineMouseLeave

The `sparklineMouseLeave` event is fired on moving mouse outside the sparkline.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container" >
        <ej-sparkline e-sparklinemouseleave="sparklinemouseleave"></ej-sparkline>
    </div>
    <script>
      angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
                $scope.sparklinemouseleave="onSparklineMouseLeave"
        });
        function onSparklineMouseLeave(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}