---
layout: post
title: Title
description: title
platform: AngularJS
control: pivotchart
documentation: ug
keywords: ejpivotchart, pivotchart, pivotchart widget, js pivotchart 
---

# Title

## Title Text
By using the [`title.text`](/api/js/ejchart#members:title-text) property, you can add the title text for PivotChart.
 
{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-title="title"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            //Adding Chart title
            $scope.title = {
                text: "PivotChart"
            };
        });
    </script>
</body>

{% endhighlight %}

![](Title_images/Title_img1.png) 

## Title Alignment

By using the [`title.textAlignment`](/api/js/ejchart#members:title-textalignment) property, you can align the PivotChart controls title text to center, far or near.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-title="title"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            //Adding Chart title
            $scope.title = {
                text: "PivotChart", 
                //Change title text alignment
                textAlignment: "near"
            };
        });
    </script>
</body>

{% endhighlight %}

![](Title_images/Title_img2.png) 

## Title Customization
By using the [`title`](/api/js/ejchart#members:title) property, you can add the title text for X-axis and Y-axis. Also title text can be customized by using the [`text`](/api/js/ejchart#members:title-text) and [`font`](/api/js/ejchart#members:title-font) properties. On setting [`enableTrim`](/api/js/ejchart#members:primaryyaxis-enabletrim) to true, title text could be trimmed based on its length.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-primaryXAxis="primaryXAxis"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            //Adding Chart title
            $scope.primaryXAxis = {
                //Customizing X-axis title
                title: {
                    text: "Country",
                    font: {
                        fontFamily: 'Segoe UI',
                        size: '16px',
                        fontWeight: 'bold',
                        color: 'grey',
                    },
                    enableTrim: true
                }
            };
        });
    </script>
</body>

{% endhighlight %}

![](Title_images/Title_img3.png) 
