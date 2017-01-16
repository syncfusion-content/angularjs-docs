---
title: Getting-Started
description: How to create a rangenavigator, add series, datasource, enable tooltip and other functionalities
platform: Angular 1.0
control: RangeNavigator
documentation: ug
keywords: ejrangenavigator, rangenavigator, rangenavigator widget, js rangenavigator, angular rangenavigator, angularjs rangenavigator, angular 1.0 rangenavigator, angular 1 rangenavigator
---

# Getting Started


This section explains briefly about how to create a **RangeNavigator** in your application with **AngularJS**.

## Create your first RangeNavigator in AngularJS

This section encompasses on how to configure the **ej-rangenavigator** and update the **chart** control for **RangeNavigator’s** selected range. It also helps you to learn how to pass the required data to **RangeNavigator** and customize the scale and selected range for your requirements. In this example, you will look at the steps to configure a RangeNavigator to analyze sales of a product for a particular quarter in a year.



![](Getting-Started_images/Getting-Started_img1.png) 

## Configure RangeNavigator

Getting started with your **ej-rangenavigator** is simple. You can initialize the **ej-rangenavigator** by setting its range values.

You can create an **HTML** file as shown in the following code example.

{% highlight html %}


<!DOCTYPE html>
<html ng-app="RangeApp">
<head>
<script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js" type="text/javascript"></script>
<script src="http://ajax.aspnetcdn.com/ajax/globalize/0.1.1/globalize.min.js"></script>
<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js" type="text/javascript"></script>
<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js" type="text/javascript"></script>
</head>
<body ng-controller="RangeCtrl"></body>
</html>


{% endhighlight %}



1. Create a &lt;div&gt; tag with an id.
2. Set `ej-rangenavigator` attribute to render RangeNavigator control and add `e-rangeSettings` for customize the rangeSettings.


{% highlight html %}

<body ng-controller="RangeCtrl">
<div id="rangecontainer" ej-rangenavigator e-rangeSettings=rangeSetting ></div>
</body>


{% endhighlight %}



3. Add a script tag inside the &lt;Body&gt; tag and add the following code example.  

The following code example renders a **RangeNavigator** with a range from 2010, January 1st to December 31st.

{% highlight html %}

    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.rangeSetting = {
                    start: "2010/1/1", end: "2010/12/31"
                };
            });
    </script>

{% endhighlight %}



The following screen shot displays the **RangeNavigator** with a range from 2010, January 1st to December 31st.



![](Getting-Started_images/Getting-Started_img2.png) 

**Add series**

To add series to **ej-rangenavigator,** you need to set **dataSource** property of **ej-rangenavigator** as shown in the following code example. 

You can create data source for **RangeNavigator** as follows.

{% highlight javascript %}

   <script>
        var Data = [{ "xDate": new Date(2011, 0, 1), "yValue": 10 },
                    { "xDate": new Date(2011, 2, 1), "yValue": 5 },
                    { "xDate": new Date(2011, 4, 1), "yValue": 15 },
                    { "xDate": new Date(2011, 6, 1), "yValue": 25 },
                    { "xDate": new Date(2011, 8, 1), "yValue": 10 },
                    { "xDate": new Date(2011, 10, 1), "yValue": 5 },
                    { "xDate": new Date(2011, 12, 1), "yValue": 15 }];
    </script>
{% endhighlight %}


Now, add the **dataSource** to the **RangeNavigator** and provide the field name to get the values from the **dataSource** in **xName** and **yName** options.

{% highlight javascript %}

<div id="rangecontainer" ej-rangenavigator e-datasource="dataSource" 
e-xname="xDate" e-yname="yValue"></div>
   <script>
   //..
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.dataSource = Data;                
            });
    </script>


{% endhighlight %}


The following screenshot displays a RangeNavigator with the default **"Line"** series type.



![](Getting-Started_images/Getting-Started_img3.png) 

## Tooltip

You can customize **Tooltip** for RangeNavigator using **tooltip** option. You can use **tooltipDisplayMode** option in **tooltip**,to display the tooltip "always" or "ondemand" (displays tooltip only while dragging the sliders). You can also specify label format for tooltip using **labelFormat**.

The following code sample shows how to enable a Tooltip.

{% highlight javascript %}

<div id="rangecontainer" ej-rangenavigator
         e-tooltipsettings="tooltip"></div>
    <script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.tooltip = {
                    visible: true,
                    labelFormat: "MMM/yyyy",
                    tooltipDisplayMode: "always",
                  };
            });
    </script>


{% endhighlight %}

The following screenshot displays the label format **Tooltip** in RangeNavigator:

![](Getting-Started_images/Getting-Started_img4.png) 

## Update Chart

You can use **ej-rangenavigator** with controls such as **chart** and **grid** to view the range of data selected in **ej-rangenavigator**. 

In order to update **chart**, whenever the selected range changes in **ej-rangenavigator**, you need to use **e-rangechanged** event of **ej-rangenavigator** and then update the **chart** with the selected data in this event. 

You can create a chart with line series using the following code sample.

1. Create a &lt;div&gt; tag with an id.



{% highlight html %}

<body>
<div id="container" ej-chart e-title-text=titletext>
        <e-series>
            <e-series e-name="Sales" e-type="line" e-tooltip="tooltipoptions" e-datasource=dataSource e-xname="xDate" e-yname="yValue">
            </e-series>
        </e-series>
    </div>
    <script>
        var chartData = [{ "xDate": new Date(2011, 0, 1), "yValue": 10 },
                       { "xDate": new Date(2011, 2, 1), "yValue": 5 },
                       { "xDate": new Date(2011, 4, 1), "yValue": 15 },
                       { "xDate": new Date(2011, 6, 1), "yValue": 25 },
                       { "xDate": new Date(2011, 8, 1), "yValue": 10 },
                       { "xDate": new Date(2011, 10, 1), "yValue": 5 },
                       { "xDate": new Date(2011, 12, 1), "yValue": 15 }];

        angular.module('RangeApp', ['ejangular'])
            .controller('RangeCtrl', function ($scope) {
                $scope.dataSource = chartData;
                $scope.titletext = "Sales Analysis";
            });
    </script>
</body>


{% endhighlight %}



You can update the chart with the selected data using the **e-rangechanged** event of **ej-rangenavigator**.

{% highlight javascript %}

<div id="rangecontainer" ej-rangenavigator e-datasource="dataSource" e-xname="xDate" e-yname="yValue"
         e-rangechanged="onrangechanged"
         e-tooltipsettings="tooltip"></div>

<script>
//...datasource
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.dataSource = chartData;
                $scope.tooltip = {
                    visible: true,
                    labelFormat: "MMM/yyyy",
                    tooltipDisplayMode: "always",
                  };
            });

        function onrangechanged(sender) {
            var chartobj = $("#container").data("ejChart");
            if (chartobj != null) {
                chartobj.model.series[0].dataSource = sender.selectedData;
                $("#container").ejChart("redraw");
            }
        }
</script>
{% endhighlight %}


The following screenshot displays how a RangeNavigator is updated when a selected range is changed.



![](Getting-Started_images/Getting-Started_img5.png) 

## Set value type

**ej-rangenavigator** can also be used with numerical values. You can specify the data type using **valueType** option. 

You can create a **dataSource** for Chart Series with integer Values using the following code sample.

{% highlight javascript %}


    window.chartData = [
    { "xDate": 0, "yValue": 10 },
    { "xDate": 50, "yValue": 5 },
    { "xDate": 100, "yValue": 15 },
    { "xDate": 150, "yValue": 25 },
    { "xDate": 200, "yValue": 10 },
    { "xDate": 250, "yValue": 5 },
    { "xDate": 300, "yValue": 15 },
    ];


{% endhighlight %}

Now, you can set the **dataSource** for Chart Series and **valueType** property to "numeric" as given in the following code example.

{% highlight javascript %}

<div id="rangecontainer" ej-rangenavigator>
        <div e-series>
            <e-series e-datasource="dataSource" e-valuetype="numeric" e-xname="xDate" 
            e-yname="yValue" e-type="line"></e-series>
        </div>
</div>
<script>
        angular.module('RangeApp', ['ejangular'])
        .controller('RangeCtrl', function ($scope) {
                $scope.dataSource = window.chartData;
        });
</script>


{% endhighlight %}


The following screenshot displays a RangeNavigator with numerical values:



![](Getting-Started_images/Getting-Started_img6.png) 

