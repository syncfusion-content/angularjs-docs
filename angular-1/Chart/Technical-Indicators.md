---
layout: post
title: Technical Indicators
description: What are the different types of technical indicators supported in Essential Chart for financial analysis.
platform: Angular 1.0
control: Chart
documentation: ug
---

# Technical Indicators

EjChart control supports 10 types of technical indicators. 

## Bind data to render the indicator

You can bind the series `e-series-datasource` to the indicator by setting the specific series name to the indicator by using the `e-indicators-seriesName` property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="High" e-low="Low" e-open="Open" e-close="Close" e-name="Hilo" e-type="hiloopenclose"></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        //Set Hilo series dataSource to indicator using seriesName
                        seriesName: "Hilo"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>



{% endhighlight %}


Also, you can add data to the indicator directly by using the `dataSource` option of the indicator.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        //Add dataSource to indicator directly
                    dataSource: chartData,
                    xName: "xDate",
                    high: "High",
                    low: "Low",
                    open: "Open",
                    close: "Close",                
                    //  ...
                     }];
                   });
        </script>
    </body>
</html>


{% endhighlight %}

	
## Indicator Types

### Accumulation Distribution

To create an Accumulation Distribution indicator, set the `indicators.type` as **"accumulationdistribution"**. Accumulation Distribution require **‘volume’** field additionally with the `dataSource` to calculate the signal line.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" e-volume="volume"></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "accumulationdistribution"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img1.png)




### Average True Range (ATR)

You can create an ATR indicator by setting the `indicators.type` as **"atr"** in the `e-indicators`. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "atr"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img2.png)




### Bollinger Band 

Bollinger Band indicator is created by setting the `indicators.type` as **"bollingerband"**. It contains three lines, namely upper band, lower band and signal line. Bollinger Band default value of the period is 14 and standardDeviations is 2.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "bollingerband"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>
{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img3.png)


### Exponential Moving Average (EMA)

To render an EMA indicator, you have to set the `indicators.type` as **"ema"**.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "ema"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img4.png)



### Momentum 

Momentum Technical indicator is created by setting the `indicators.type` as **"momentum"**. The momentum indicator renders two lines, namely upper band and signal line. Upper band always rendered at the value 100 and the signal line is calculated based on the momentum of the data.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "momentum"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>
{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img5.png)




### Moving Average Convergence Divergence (MACD)

To render an MACD indicator, you have to set the `indicators.type` as **"macd"**.  MACD indicator contains MACD line, Signal line and Histogram column. Histogram is used to differentiate MACD and signal line.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "macd"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>


{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img6.png)


#### macdType

By using the `macdType` enumeration property, you can change the MACD rendering as *line*, *histogram* or *both*. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        type: "macd",
                        macdType:"histogram"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>
        


{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img7.png)


### Relative Strength Index (RSI)

To render the RSI indicator, set the `indicators.type` as **"rsi"**. It contains three lines, namely upper band, lower band and signal line. Upper and lower band always render at value 70 and 30 respectively and signal line is calculated based on the **RSI** formula.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "rsi"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>

{% endhighlight %}


![](Technical-Indicators_images/Technical-Indicators_img8.png)


### Simple Moving Average (SMA)

To render the SMA indicator, you should specify the `indicators.type` as **"sma"**.  

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "sma"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img9.png)



### Stochastic 

For the Stochastic indicator, you need to set the `indicators.type` as **"stochastic"**. The Stochastic indicator renders four lines namely, upper line, lower line, stochastic line and the signal line. Upper line always rendered at value 80 and the lower line is rendered at value 20. Stochastic and Signal Lines are calculated based on the stochastic formula.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "stochastic"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img10.png)


### Triangular Moving Average (TMA)

To render the TMA indicator, you should specify the `indicators.type` as **"tma"**. 

{% highlight html %}
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                        seriesName: "hilo",
                         //Set indicator type
                        type: "tma"
                        //  ...
                     }];
                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img11.png)


## Enable Tooltip 

To display the indicator tooltip, use `visible` option of the `indicators.tooltip`. Also, you can change and customize the tooltip color, border, format and font properties similar to the series tooltip.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="ChartApp">
    <head>
        <title>Essential Studio for AngularJS: Chart</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="ChartCtrl">
        <div id="container" ej-chart  e-indicators="indicators">
        <e-series>
        <e-series e-datasource="dataSource" e-xname="xDate" e-high="high" e-low="low" e-open="open" 
        e-close="close" e-name="hilo" e-type="hiloopenclose" ></e-series>
        </e-series>
        </div>
        <script>
                angular.module('ChartApp', ['ejangular'])
                .controller('ChartCtrl', function ($scope) {
                  $scope.indicators=[{
                                     //  ...
                             tooltip: {
                                  //Enable tooltip for indicator
                              visible: true
                                       }
                                    }];
                                   });
        </script>
    </body>
</html>

{% endhighlight %}

![](Technical-Indicators_images/Technical-Indicators_img12.png)



