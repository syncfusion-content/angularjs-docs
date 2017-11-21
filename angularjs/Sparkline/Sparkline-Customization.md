---
layout: post
title: Customization for Essential JavaScript Sparkline
description: Learn how to customize the Sparkline .
platform: AngularJS
control: Sparkline
documentation: ug
---

# Sparkline Customization

This section explains you the customization options available to make changes in the Sparkline for getting better appearance.

## Sparkline background

You can specify the background color for the Sparkline using `e-background` property. When you don't specify the background, it takes "transparent" as background color. 

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container">
        <ej-sparkline e-background="gray"></ej-sparkline>
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
               });
    </script>
</body>

{% endhighlight %} 

![](Sparkline-Customization_images/Sparkline-Customization_img1.png)

## Stroke color and width

You can customize the series border color and width using `e-stroke` and `e-width`. This is applicable for Sparkline types line and area.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container">
        <ej-sparkline e-stroke="green" e-width="3"></ej-sparkline>
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
               });
    </script>
</body>

{% endhighlight %} 

![](Sparkline-Customization_images/Sparkline-Customization_img2.png)

## Sparkline border

You can customize the `e-border` width and height of the Sparkline using `e-border-width` and `e-border-color` properties. This is applicable for column, win-loss and pie series.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container">
        <ej-sparkline e-border-color="green" e-border-width="2"></ej-sparkline>
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
               });
    </script>
</body>

{% endhighlight %} 

![](Sparkline-Customization_images/Sparkline-Customization_img3.png)

## Opacity

By default `e-opacity` of the Sparkline is 1. You can specify the opacity value from 0 to 1. This is applicable for all types of series. 

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container">
        <ej-sparkline e-opacity="0.5"></ej-sparkline>
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
               });
    </script>
</body>

{% endhighlight %} 

![](Sparkline-Customization_images/Sparkline-Customization_img4.png)

## Localization

Sparkline is having support for localization as well. Default culture is "en-US". You can modify the culture using the property `e-locale`.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container">
        <ej-sparkline e-locale="fr-FR"></ej-sparkline>
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
               });
    </script>
</body>

{% endhighlight %} 

## Padding for Sparkline

`e-padding` is used to specify the padding value between the container and Sparkline. By default padding value of the Sparkline is 5. 

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container">
        <ej-sparkline e-padding="20"></ej-sparkline>
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
               });
    </script>
</body>

{% endhighlight %} 

![](Sparkline-Customization_images/Sparkline-Customization_img5.png)

## Canvas support

You can control whether Sparkline has to be rendered as SVG or Canvas. `e-enablecanvasrendering` rendering supports all the functionalities supported in SVG rendering.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container">
        <ej-sparkline e-enablecanvasrendering="true"></ej-sparkline>
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
               });
    </script>
</body>

{% endhighlight %} 

## Themes

You can specify different `e-theme` for Sparkline control.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container">
        <ej-sparkline e-theme="flatdark"></ej-sparkline>
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
        .controller('SparkCtrl', function ($scope) {
               });
    </script>
</body>

{% endhighlight %} 

![](Sparkline-Customization_images/Sparkline-Customization_img6.png)
