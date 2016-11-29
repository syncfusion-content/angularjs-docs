---
title: Getting Started with ReportViewer component
description: getting started
platform: Angular-1
control: ReportViewer
documentation: ug 
keywords: ejReportViewer, ReportViewer, js ReportViewer 
---

# Getting Started

This section explains briefly about how to create a ReportViewer in your web application with AngularJS.

## Create your first ReportViewer in Angular-1

In this tutorial, you can learn how to create a simple ReportViewer control, Load RDLC Report and Load SSRS Report in your web application with AngularJS.

### Create HTML Page

Create a new HTML file and include the below initial code.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="syncApp">
    <head>
        <meta charset="utf-8" />
        <title> </title>
    </head>
    <body>
    </body>
</html>

{% endhighlight %}

### Add Scripts and Styles

Refer the CSS file from the specific theme folder to your HTML file within the head section as shown below. Please refer to our built-in theme [here](https://help.syncfusion.com/js/theming-in-essential-javascript-components).

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - ReportViewer</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
</head>

{% endhighlight %}

Refer the [CDN](https://help.syncfusion.com/js/cdn) script files with other required external dependencies.

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - ReportViewer</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
</head>

{% endhighlight %}

In the above code, `ej.web.all.min.js`script reference has been added for demonstration purpose. It is not recommended to use this for deployment purpose, as its file size is larger since it contains all the widgets. Instead, you can use[CSG](http://csg.syncfusion.com/# "") utility to generate a custom script file with the required widgets for deployment purpose.

### Add Control in HTML Page

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services and configurations.

Add the following code example in the &lt;body&gt; tag in the HTML page. Set the desired `processingmode`, `reportPath` and `reportServiceUrl` to ReportViewer.

{% highlight html %}

<div ng-controller="GroupingAggregateCrtl">
    <div id="container" ej-reportviewer e-reportserviceurl="reportServiceUrl" e-processingmode="remoteMode" e-isresponsive="true" e-reportpath="rdlReportPath" style="width:100%;height:680px;"> </div>
</div>

<script type="text/javascript">
    angular.module('syncApp', ['ejangular']).controller('GroupingAggregateCrtl', function ($scope, $interval) {
        $scope.reportServiceUrl = 'http://js.syncfusion.com/ejservices/api/RDLReport';
        $scope.remoteMode = ej.ReportViewer.ProcessingMode.Remote;
        $scope.rdlReportPath = 'GroupingAgg.rdl';
    });
</script>

{% endhighlight %}

N> Default RDL Report will be rendered, which is used in the online service. You can obtain sample rdl/rdlc files from Syncfusion installed location (%userprofile%\AppData\Local\Syncfusion\EssentialStudio\{{ site.releaseversion }}\Common\Data\ejReportTemplate).

### Run the Application

Run the sample application and you can see the ReportViewer on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started_img1.png) 

ReportViewer with Grouping Aggregate Report
{:.caption}

## Load SSRS Server Reports

ReportViewer supports to load RDL/RDLC files from SSRS Server. The following steps help you to load reports from SSRS Server.

1.Set the `reportPath` from SSRS and SSRS `reportServerUrl` in the ReportViewer properties.

{% highlight html %}

<div ng-controller="TerritorySalesCrtl">
    <div id="container" ej-reportviewer e-reportserviceurl="reportServiceUrl" e-reportserverurl="ServerUrl" e-processingmode="remoteMode" e-isresponsive="true" e-reportpath="ssrsReportPath" style="width:100%;height:680px;"></div>
</div>

<script type="text/javascript">
    angular.module('syncApp', ['ejangular']).controller('TerritorySalesCrtl', function ($scope, $interval) {
        $scope.ServerUrl = 'http://mvc.syncfusion.com/reportserver';
        $scope.reportServiceUrl = 'http://js.syncfusion.com/ejservices/api/SSRSReport';
        $scope.remoteMode = ej.ReportViewer.ProcessingMode.Remote;
        $scope.ssrsReportPath = "/SSRSSamples2/Territory Sales new";
    });
</script>

{% endhighlight %}

N> The credential information for Report Server is provided in online service. 

2.Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

   ![](Getting-Started_images/Getting-Started_img2.png) 
   
   Report from SSRS
   {:.caption}

## Load RDLC Reports

The ReportViewer has data binding support to visualize the RDLC reports. The following code example helps you to bind data to ReportViewer.

1.Assign the RDLC report path to ReportViewer’s `reportPath` property and set the data sources to the ReportViewer’s `dataSources` property and specify the `processingMode` as local.

{% highlight html %}

<div ng-controller="AreaChartCrtl">
    <div id="container" ej-reportviewer e-reportserviceurl="reportServiceUrl" e-processingmode="localMode" e-isresponsive="true" e-reportpath="rdlcReportPath" e-datasources="dataSource" style="width:100%;height:680px;"></div>
</div>
<script type="text/javascript">
    angular.module('syncApp', ['ejangular']).controller('AreaChartCrtl', function ($scope, $interval) {
        $scope.reportServiceUrl = 'http://js.syncfusion.com/ejservices/api/RDLCReport';
        $scope.localMode = ej.ReportViewer.ProcessingMode.Local;
        $scope.rdlcReportPath = 'AreaCharts.rdlc';
        $scope.dataSource = [{
            value: [
              { SalesPersonID: 281, FullName: 'Ito', Title: 'Sales Representative', SalesTerritory: 'South West', Y2002: 0, Y2003: 28000, Y2004: 3018725 },
              { SalesPersonID: 282, FullName: 'Saraiva', Title: 'Sales Representative', SalesTerritory: 'Canada', Y2002: 25000, Y2003: 14000, Y2004: 3189356 },
              { SalesPersonID: 283, FullName: 'Cambell', Title: 'Sales Representative', SalesTerritory: 'North West', Y2002: 12000, Y2003: 13000, Y2004: 1930885 },
              { SalesPersonID: 275, FullName: 'Blythe', Title: 'Sales Representative', SalesTerritory: 'North East', Y2002: 19000, Y2003: 47000, Y2004: 4557045 },
              { SalesPersonID: 276, FullName: 'Mitchell', Title: 'Sales Representative', SalesTerritory: 'South West', Y2002: 28000, Y2003: 46000, Y2004: 5240075 },
              { SalesPersonID: 277, FullName: 'Carson', Title: 'Sales Representative', SalesTerritory: 'Central', Y2002: 33000, Y2003: 49000, Y2004: 3857163 },
              { SalesPersonID: 278, FullName: 'Vargas', Title: 'Sales Representative', SalesTerritory: 'Canada', Y2002: 11000, Y2003: 14000, Y2004: 1764938 },
              { SalesPersonID: 279, FullName: 'Reiter', Title: 'Sales Representative', SalesTerritory: 'South East', Y2002: 32000, Y2003: 26000, Y2004: 2811012 }
            ],
            name: 'AdventureWorksXMLDataSet'
        }];
    });
</script>

{% endhighlight %}

N> Default RDLC Report will be rendered, which is used in the online service. You can obtain sample rdl/rdlc files from Syncfusion installed location (%userprofile%\AppData\Local\Syncfusion\EssentialStudio\{{ site.releaseversion }}\Common\Data\ejReportTemplate).

2.Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

   ![](Getting-Started_images/Getting-Started_img3.png) 
   
   Area Chart RDLC Report
   {:.caption}

