---
layout: post
title: Chart Title
description: How to customize the chart title.
platform: Angular 1.0
control: Chart
documentation: ug
---

# Chart Title & Subtitle

## Title

By using the title option, you can add the `e-title-text` as well as customize its `e-title-border`,  `e-title-background` and `e-title-font`.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-title-text= "Efficiency of oil-fired power production" 
        e-title-background="lightblue" e-title-border-color="blue" e-title-border-width="2" 
        e-title-border-opacity="0.5"  e-title-border-cornerradius="4" e-title-font-fontfamily="Arial" 
        e-title-font-fontstyle="italic"  e-title-font-fontweight="normal" e-title-font-size="23px" >
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Title_images/Chart-Title_img1.png)


We can trim, wrap and wrapAndTrim to the chart title using textOverflow property. The original text will be displayed as tooltip on mouse hover.


{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-title-text= "Efficiency of oil-fired power production"  
        e-title-enabletrim="true"  e-title-maximumwidth="15" e-title-textoverflow="trim" >
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Title_images/Chart-Title_img5.png)


### Title Alignment

You can change the title alignment to *center*, *far* and *near* by using the `e-title-textAlignment` property of the chart title. 

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-title-text= "Efficiency of oil-fired power production"
        e-title-textalignment="near">
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %} 

![](Chart-Title_images/Chart-Title_img2.png)


## Add Subtitle to the chart

By using the subTitle option, you can add the `e-title-subTitle` to the chart title and customize its `e-title-subtitle-border`,  `e-title-subtitle-background` color and `e-title-subtitle-font`. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-title-subtitle-text= "( in a week )"  
        e-title-subtitle-background="lightblue" 
        e-title-subtitle-border-color="blue" e-title-subtitle-border-width="2" 
        e-title-subtitle-border-opacity="0.5"  e-title-subtitle-border-cornerradius="4" 
        e-title-subtitle-font-fontfamily="Arial" e-title-subtitle-font-fontstyle="italic"
        e-title-subtitle-font-fontweight="normal" e-subtitle-title-font-size="23px" >
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Title_images/Chart-Title_img3.png)

We can trim, wrap and wrapAndTrim to the chart subtitle using textOverflow property. The original text will be displayed as tooltip on mouse hover.

{% highlight html %}

 <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-title-subtitle-text= "( in  a  week )"  
        e-title-subtitle-enabletrim="true"  e-title-subtitle-maximumwidth="50"
        e-title-subtitle-textoverflow="wrap" >
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Chart-Title_images/Chart-Title_img6.png)

### Subtitle Alignment

You can change the subtitle alignment to *center*, *far* and *near* by using the `e-title-subtitle-textAlignment` property of the subTitle.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart e-title-subtitle-text= "( in  a  week )" 
         e-title-subtitle-textalignment="center" >
        </div>
        <script>
        angular.module('ChartApp', ['ejangular'])
        .controller('ChartCtrl', function ($scope) {
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Chart-Title_images/Chart-Title_img4.png)

