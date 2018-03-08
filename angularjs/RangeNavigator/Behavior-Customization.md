---
layout: post
title: Behavior-Customization
description: Behavior Customization
platform: AngularJS
control: RangeNavigator
documentation: ug
---

# Behavior Customization

**RangeNavigator** allows you to customize the control using events. You can change the range for selected data of the **RangeNavigator** using events.

## Deferred update

If you set **enableDeferredUpdate**to true, the **rangeChanged** event gets fired after dragging and dropping the slider. By default the **enableDeferredUpdate**is true. If **enableDeferredUpdate**is false then the **rangeChanged** event gets fired while dragging the slider.


{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RangeApp">
    <head>
        <title>Essential Studio for AngularJS: RangeNavigator</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="RangeCtrl">
       <div id="rangecontainer">
       <ej-rangenavigator e-enabledeferredupdate="true">
       </ej-rangenavigator>
       </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                });
    </script>
   </body>
</html>


{% endhighlight %}


![](Behavior-Customization_images/Behavior-Customization_img1.png) 

## Destroy Method 

`_destroy`: function

This method is used to destroy the **RangeNavigator** widget. 

{% highlight html %}

<div id="rangeContainer">
    <ej-rangenavigator></ej-rangenavigator>
</div>
<script>
    // Destroys range navigator
     $("#rangeContainer").ejRangeNavigator("_destroy");
</script>

{% endhighlight %}

## Handle Events

**load**: function

This event is fired when **RangeNavigator** is loading. A parameter **sender** is passed to the handler. Using **sender.model**, you can access the RangeNavigator properties. 

{% highlight html %}

<body ng-controller="RangeCtrl">
    <div id="rangecontainer">
        <ej-rangenavigator e-load=loaded></ej-rangenavigator>
    </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.loaded="onLoad"
        });
        function onLoad(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

**loaded:** function

This event is handled when the **RangeNavigator** gets loaded. A parameter **sender** is passed to the handler. Using **sender.model**, you can access the RangeNavigator properties. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RangeApp">
    <head>
        <title>Essential Studio for AngularJS: RangeNavigator</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="RangeCtrl">
       <div id="rangecontainer">
       <ej-rangenavigator e-loaded=loaded></ej-rangenavigator>
       </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.loaded="load"
                });
        function load(sender) {
            sender.model.isResponsive = false;
              }
    </script>
   </body>
</html>



{% endhighlight %}


**rangeChanged**: function

This event gets fired whenever the selected range changes in **RangeNavigator**. A parameter **sender** is passed to the handler. Using sender.selectedRangeSettings, you can access the start and end value of range for the selected region. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RangeApp">
    <head>
        <title>Essential Studio for AngularJS: RangeNavigator</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="RangeCtrl">
       <div id="rangecontainer">
       <ej-rangenavigator e-rangechanged=rangeChanged></ej-rangenavigator>
       </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.rangeChanged="range"
                });
        function range(sender) {
               console.log(sender.selectedRangeSettings.start);
              }
    </script>
   </body>
</html>


{% endhighlight %}

**selectedRangeStart** : function

This event is fired when starting to change the slider position in **RangeNavigator**. A parameter **sender** is passed to the handler. Using sender.selectedRangeSettings, you can access the start value of range for the selected region. 

{% highlight html %}

<body ng-controller="RangeCtrl">
    <div id="rangecontainer">
        <ej-rangenavigator e-selectedrangestart=rangeStart></ej-rangenavigator>
    </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.rangeStart="onSelectedRangeStart"
        });
        function onSelectedRangeStart(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

**selectedRangeEnd** : function

This event is fired when selection ends in **RangeNavigator**. A parameter **sender** is passed to the handler. Using sender.selectedRangeSettings, you can access the end value of range for the selected region. 

{% highlight html %}

<body ng-controller="RangeCtrl">
    <div id="rangecontainer">
        <ej-rangenavigator e-selectedrangeend=rangeEnd></ej-rangenavigator>
    </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.rangeEnd="onSelectedRangeEnd"
        });
        function onSelectedRangeEnd(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

**scrollStart** : function

This event is fired when starting to change the scrollbar position of **RangeNavigator**. A parameter **sender** is passed to the handler. Using sender.data startRange and sender.data endRange, you can access the scrollbar position starting and ending range value on changed scrollbar. 

{% highlight html %}

<body ng-controller="RangeCtrl">
    <div id="rangecontainer">
        <ej-rangenavigator e-scrollstart=scrollStart></ej-rangenavigator>
    </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.scrollStart="onScrollStart"
        });
        function onScrollStart(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

**scrollEnd** : function

This event is fired while ending the change in scrollbar position of **RangeNavigator**. A parameter **sender** is passed to the handler. Using data oldRange and data newRange, you can access the scrollbar position old and new range values on changing scrollbar. 

{% highlight html %}

<body ng-controller="RangeCtrl">
    <div id="rangecontainer">
        <ej-rangenavigator e-scrollend=scrollEnd></ej-rangenavigator>
    </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.scrollEnd="onScrollEnd"
        });
        function onScrollEnd(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

**scrollChanged** : function

This event is fired when changing the scrollbar position of **RangeNavigator**. A parameter **sender** is passed to the handler. Using data oldRange and data newRange, you can access the old and new range values of changed scrollbar position. 

{% highlight html %}

<body ng-controller="RangeCtrl">
    <div id="rangecontainer">
        <ej-rangenavigator e-scrollchanged=scrollChange></ej-rangenavigator>
    </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.scrollChange="onScrollChange"
        });
        function onScrollChange(sender) {
            // do something
        }
    </script>
</body>

{% endhighlight %}

## Use of ZoomCoordinates

**RangeNavigator** is used along with the controls like chart and grid to view the selected data. To update chart/grid, whenever the selected range changes in **RangeNavigator**, you can use **rangeChanged** event of **RangeNavigator** and then update the chart/grid with the selected data in this event. 

You can easily update the data for chart by assigning the **zoomFactor** and **zoomPosition** of the **RangeNavigator** to the chart axis.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RangeApp">
    <head>
        <title>Essential Studio for AngularJS: RangeNavigator</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="RangeCtrl">
       <div id="rangecontainer">
       <ej-rangenavigator e-rangechanged="onChartLoaded"></ej-rangenavigator>
         </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                     });
          // setting zoom factor and position for chart axis in rangeChanged event.             
        function onChartLoaded(sender) {
        var chartObj = $("#container").data("ejChart");
        if (chartObj != null) {
            chartObj.model.axes[0].zoomPosition = sender.zoomPosition;
            chartObj.model.axes[0].zoomFactor = sender.zoomFactor;
        }
        $("#container").ejChart("redraw");
    }
    </script>
   </body>
</html>
   


{% endhighlight %}



![](Behavior-Customization_images/Behavior-Customization_img2.png) 

## Thumb Template

You can customize Thumb template by using **leftThumbTemplate** and **rightThumbTemplate** property. You can add the required template as a "div" element with an "id" to the web page and assign the id or assign the HTML string to this property under **navigatorStyleSettings**.

{% highlight html %}

 
 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RangeApp">
    <head>
        <title>Essential Studio for AngularJS: RangeNavigator</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="RangeCtrl">
     <div id="rangecontainer">
       <ej-rangenavigator e-navigatorstylesettings-leftthumbtemplate="left" 
       e-navigatorstylesettings-rightThumbTemplate="right"></ej-rangenavigator>
       </div>
       <script type="text/x-jsrender" id="left" >
       <svg height="24" width="32" style="fill:#DD4A4A;stroke:black;">
       <path d="M2 2 L2 22 L22 22 L32 12 L22 2 Z" />
       </svg>
       </script>
       <script type="text/x-jsrender" id="right">
       <svg height="24" width="32" style="fill:#DD4A4A;stroke:black; ">
       <path d="M2 12 L12 22 L32 22 L32 2 L12 2 Z" />
       </svg>
       </script>
     <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                });
    </script>
   </body>
</html>      



{% endhighlight %}



The following screenshot displays the **RangeNavigator** using thumb template.

![](Behavior-Customization_images/Behavior-Customization_img3.png) 

## Value Axis Settings

You can customize the line, `font` `size`, gridline, tickline, range, `rangePadding` and visibility of **RangeNavigator** axis. To enable the visibility of axis line, you need to set `visible` property of `axisLine` in `valueAxisSettings`. You can customize the axis range by specifying `min`, `max` and `interval` for `range` property. The `majorGridLines` can be enabled by specifying `visible` property. The `size`, `width` and `visible` property of `majorTickLines` is used to customize the axis tick lines. The visibility of valueAxisSettings is enabled by setting `visible` property as true. 

{% highlight html %}

<body ng-controller="RangeCtrl">
    <div id="rangecontainer">
        <ej-rangenavigator  e-valueaxissettings="valueAxisSetting">
        </ej-rangenavigator>
    </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
            $scope.valueAxisSetting = {
                axisLine: {visible: true},
                font: {size: '12px'},
                majorGridLines: {visible: true},
                majorTickLines: {size: 3, visible:false, width:3},
                range:{ min :0 , max :100, interval :10},
                rangePadding: "normal",
                visible: true
            };
        });
    </script>
</body>

{% endhighlight %}

## Selected Range Settings

The start and end range values of selected range can be customized using `start` and `end` property of `selectedRangeSettings`.

{% highlight html %}

<body ng-controller="RangeCtrl">
    <div id="rangecontainer">
        <ej-rangenavigator  e-selectedrangesettings="selectedRange">
        </ej-rangenavigator>
    </div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
            $scope.selectedRange = {
                    start:"01/05/1992",
                    end:"01/05/1993"
            };
        });
    </script>
</body>

{% endhighlight %}

