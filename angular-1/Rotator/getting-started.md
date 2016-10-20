---
layout: post
title: Getting-Started
description: Getting Started
platform: Angular-1-JS
control: rotator
documentation: ug
---

# Getting Started

This section helps to get started of the Rotator component for AngularJS. 

![](getting-started-images\getting-started1.png)

## Adding dependencies

The following steps guide you to add a **Rotator** component.

1. Create an **HTML** file and add required scripts and CSS files for rendering Essential JavaScript component as given in the [Getting Started](https://help.syncfusion.com/js/angularjs).

2. In addition to it for AngularJS implementation, refer the “angular.min.js” and “ej.widgets.angular.min.js” files.

    {% highlight html %}

        <html ng-app="rotatApp">
        <head>
        <title>Simple Rotator</title>
        <!-- Add Scripts and CSS for rendering Essential JS components --> 

            <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
            <script src="[http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
        </head>
        <body ng-controller="RotatCtrl">
                <!-- Add Rotator component Here -->
            <ul id="sliderContent" ej-rotator />
        </body>
        </html>

    {% endhighlight %}

## Component initialization

1. Initialize the ng-app and ng-controller for the application. For adding Rotator component, you have to use **ej-rotator** directive to corresponding element.

2. Now initialize the component using angular module in script section

    {% highlight javascript %}

        angular.module('rotatApp', ['ejangular']).controller('RotatCtrl', function ($scope) {});

    {% endhighlight %}


## Configure data

To configure images for Rotator component, define data and apply to scope variable as given below.

{% highlight javascript %}

    var list = [
    {text:"Seaview", url:"http://js.syncfusion.com/demos/web/content/images/rotator/seaview.jpg"},
    { text: "Snowfall", url: "http://js.syncfusion.com/demos/web/content/images/rotator/snowfall.jpg" },
    { text: "Tablet", url: "http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" },
    { text: "Nature", url: "http://js.syncfusion.com/demos/web/content/images/rotator/nature.jpg" },
    { text: "Card", url: "http://js.syncfusion.com/demos/web/content/images/rotator/card.jpg" },
    { text: "Bird", url: "http://js.syncfusion.com/demos/web/content/images/rotator/bird.jpg" },
    { text: "Wheat", url: "http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" },
    { text: "Night", url: "http://js.syncfusion.com/demos/web/content/images/rotator/night.jpg" }];

    angular.module('rotatApp', ['ejangular']).controller('RotatCtrl', function ($scope) {
    $scope.animation="slide";
    $scope.data=list;
    });

{% endhighlight %}

## Configuring properties

Declare the rotator properties with prefix “e- “, refer the following code,

{% highlight html %}

    <div class="frame" style="width:600px; height:300px">
    <ul id="sliderContent" ej-rotator e-slideHeight="100%" e-dataSource="data" e-showPlayButton="true" e-isResponsive="true" e-slideWidth="500px"
    e-showCaption="true" e-animationType="animation" e-pagerPosition="TopLeft" e-frameSpace="2px" />
    </div>

{% endhighlight %}



![](getting-started-images\configuring-properties_img1.png)



N> All the Syncfusion component’s properties for Angularis defined using e- prefix followed by the property name.You can find the complete API list from the [API reference](https://help.syncfusion.com/js/api/ejrotator)


