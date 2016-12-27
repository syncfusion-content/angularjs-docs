---
title: Getting Started for Essential JavaScript Sparkline
description: How to create a sparkline.
platform: Angular 1.0
control: Sparkline
documentation: ug
keywords: ejsparkline, sparkline, sparkline widget, js sparkline, angular sparkline, angularjs sparkline, angular 1.0 sparkline, angular 1 sparkline
---

# Getting Started

This section explains you the steps required to populate the Sparkline with data. This section covers only the minimal features that you need to know to get started with the Sparkline.

## Adding script reference

Create an **HTML** page and add the scripts references in the order mentioned in the following code example.

{% highlight html %}

<!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="SparkApp">
    <head>
    <title>Essential Studio for AngularJS: Sparkline</title>
    <!-- Essential Studio for JavaScript  theme reference -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!-- Essential Studio for JavaScript  script references -->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>    
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js" type="text/javascript"></script>
    <!-- Add your custom scripts here -->
    </head>
    <body ng-controller="SparkCtrl">
    </body>
    </html>

{% endhighlight %}

In the above code, ej.web.all.min.js script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use ['CSG'](http://csg.syncfusion.com/) utility to generate a custom script file with the required widgets for deployment purpose.

## Initialize Sparkline

Add a **div** container to render the Sparkline.

{% highlight html %}


<body ng-controller="SparkCtrl">
    <div id="container" ej-sparkline>
    </div>
</body>

{% endhighlight %}

Initialize the Sparkline by using the ej-sparkline attribute. The Sparkline is rendered to the container with default size. You can also customize the Sparkline dimension by setting the width and height.

{% highlight html %}

<body ng-controller="SparkCtrl">
    <div id="container" ej-sparkline e-size="sparksize">
    </div>
    <script>
        angular.module('SparkApp', ['ejangular'])
            .controller('SparkCtrl', function ($scope) {
                $scope.sparksize = {
                    height: 100,
                    width: 400
                };
            });
    </script>
</body>

{% endhighlight %}

Now, the Sparkline is rendered with some auto-generated random values and with default Line type. 

![](Getting-Started_images/Getting-Started_img1.png)