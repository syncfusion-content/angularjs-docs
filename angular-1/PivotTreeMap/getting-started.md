---
title: Getting started with PivotTreeMap component	
description: Rendering a basic PivotTreeMap with local data
platform: Angular 1.0
control: pivottreemap
documentation: ug
keywords: ejpivottreemap, pivottreemap, pivottreemap widget, js pivottreemap 
---

# Getting Started

The AngularJS directives are usually included within the `ej.widget.angular.min.js` file and all these directives are usually packed together in a common module known as `ejangular`. For basic details on how to configure Syncfusion widgets in AngularJS framework, refer [here](https://help.syncfusion.com/js/angularjs).

To get start with the PivotTreeMap control in AngularJS framework, the following list of external dependencies are mandatory, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates
* [AngularJS](https://angularjs.org/)

The external AngularJS script file `angular.min.js` can also be accessed from the following installed location. 

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\external

An another mandatory script is `ej.widget.angular.min.js`, which can be accessed from the below specified location.

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\common

## Script/CSS Reference

Create a new HTML file and include the below initial code.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta charset="utf-8" />
        <title> </title>
    </head>
    <body>
    </body>
</html>

{% endhighlight %}

Refer the CSS file from the specific theme folder to your HTML file within the head section as shown below. Refer the built-in available themes from [here](https://help.syncfusion.com/js/theming-in-essential-javascript-components).

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - PivotTreeMap</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
</head>

{% endhighlight %}

Refer the [CDN](https://help.syncfusion.com/js/cdn) script files with other required external dependencies.

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - PivotTreeMap</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
	<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
	<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
</head>

{% endhighlight %}

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use[CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

### Control Initialization

Create the PivotTreeMap control using `ej-pivottreemap` directive and define all its other properties prefixed with `e-` as shown in the below code.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotTreeMapApp">

<body>
	<div ng-controller="PivotTreeMapCtrl">
        <div id="PivotTreeMap1" ej-pivottreemap e-dataSource="dataSource" e-isresponsive="isResponsive" style="min-height: 275px; height: 460px; width: 99%;"></div>
		    
		<!--Tooltip labels can be localized here-->
		<script id="tooltipTemplate" type="application/jsrender">
			<div style="background:White; color:black; font-size:12px; font-weight:normal; border: 1px solid #4D4D4D; white-space: nowrap;border-radius: 2px; margin-right: 25px; min-width: 110px;padding-right: 5px; padding-left: 5px; padding-bottom: 2px ;width: auto; height: auto;">
				<div>Measure(s) : {{:~Measures(#data)}}</div><div>Row : {{:~Row(#data)}}</div><div>Column : {{:~Column(#data)}}</div><div>Value : {{:~Value(#data)}}</div>
			</div>
		</script>   
	</div>
</body>

</html>

{% endhighlight %}

### Populate PivotTreeMap with data

Initializes the OLAP datasource for PivotTreeMap control as shown below.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotTreeMapApp">
<head> <!-- Dependency file references --> </head>
<body>
	<div ng-controller="PivotTreeMapCtrl">
        <div id="PivotTreeMap1" ej-pivottreemap e-dataSource="dataSource" e-isresponsive="isResponsive" style="min-height: 275px; height: 460px; width: 99%;"></div>
		    
		<!--Tooltip labels can be localized here-->
		<script id="tooltipTemplate" type="application/jsrender">
			<div style="background:White; color:black; font-size:12px; font-weight:normal; border: 1px solid #4D4D4D; white-space: nowrap;border-radius: 2px; margin-right: 25px; min-width: 110px;padding-right: 5px; padding-left: 5px; padding-bottom: 2px ;width: auto; height: auto;">
				<div>Measure(s) : {{:~Measures(#data)}}</div><div>Row : {{:~Row(#data)}}</div><div>Column : {{:~Column(#data)}}</div><div>Value : {{:~Value(#data)}}</div>
			</div>
		</script>   
	</div>
<script>
	angular.module('PivotTreeMapApp', ['ejangular']).controller('PivotTreeMapCtrl', function ($scope) {
		$scope.isResponsive = true;
		$scope.dataSource = {
			data: "http://bi.syncfusion.com/olap/msmdpump.dll;Locale identifier=1033;", //data
			catalog: "Adventure Works DW 2008 SE",
			cube: "Adventure Works",
			rows: [
				{
					fieldName: "[Customer].[Customer Geography]"
				}
			],
			columns: [
				{
					fieldName: "[Date].[Fiscal]"
				}
			],
			values: [
				{
					measures: [
						{
							fieldName: "[Measures].[Customer Count]",
						}
					],
					axis: "columns"
				}
			]
		};
	});
</script>
</body>

</html>

{% endhighlight %}

The above code will generate a simple PivotTreeMap with customer count over a period of fiscal years across different customer geographic locations.

![](getting-started_images/Olap.png)