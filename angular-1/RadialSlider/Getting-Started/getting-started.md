---
layout: post
title: Getting-Started
description: Getting Started
platform: aspnet-core
control: RadialSlider
documentation: ug
---

# Getting Started

This section helps to get started of the RadialSlider component for AngularJS. 

![](getting-started-images\default.png)

## Adding a dependency 
The following steps guide you to add a RadialSlider component.
1.	Create an HTML file and add required scripts and CSS files for rendering Essential JavaScript component as given in the Getting Started. 
2.	In addition to it for AngularJS implementation, refer the “angular.min.js” and “ej.widgets.angular.min.js” files.

## Create your first Radial Slider control AngularJS
Create a div element that is a container for Radial Slider. You can Refer to the following code example.

{% highlight html %}

        <html ng-app="syncApp">
        <head>
        <title>Simple Dialog with content</title>
        <!-- Add Scripts and CSS for rendering Essential JS components --> 

        <link href="css/default-theme/ej.widgets.all.min.css" rel="stylesheet" />
     <script src="scripts/jquery-1.11.3.min.js"></script>
     <script src="scripts/angular.min.js"></script>
     <script src="scripts/ej.web.all.min.js"></script>
        <script src="scripts/ej.widget.angular.min.js"></script>
        </head>
        <body>
        <div ng-controller="radialSliderCtrl">
        <div class="content-container-fluid">
            <div class="row">
                <div class="cols-sample-area">
                    <div class="control">
                        <div id="angularRadialSlider" ej-radialslider e-value="sliderValue" e-innercircleimageurl="../content/images/radialslider/chevron-right.png"></div>
                    </div>
                </div>
            </div>
        </div>
      </div>

        <body>

        </html>


{% endhighlight %}


Component initialization
1.	Initialize the ng-app and ng-controller for the application. For adding RadialSlider component, you have to use ej-radialslider directive to corresponding element.
2.	Now initialize the control using angular module in script section

{% highlight javascript %}

        angular.module('syncApp', ['ejangular'])
             .controller('radialSliderCtrl', function ($scope) {
                 $scope.sliderValue = 60;
             });

{% endhighlight %}

The above code will give following output.

![](getting-started-images\default.png)

