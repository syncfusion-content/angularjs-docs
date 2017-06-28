---
layout: post
title: Localization
description: localization
platform: AngularJS
control: PivotGauge
documentation: ug
keywords: ejPivotGauge, PivotGauge, PivotGauge widget, js PivotGauge 
---

# Localization

## Localization in PivotGauge Control

 We can localize the PivotGauge control texts with a collection of localized strings using **"ej.PivotGauge.Locale"** for different cultures.
 
 N> By default, the PivotGauge control is localized in **"en-US"**.

Following code example illustrates on how to localize PivotGauge based on "French" culture.

{% highlight javascript %}

<div ng-controller="PivotGaugeCtrl">
    <div id="PivotGauge1" ej-pivotgauge e-locale="fr-FR" />
</div>
<script>
    angular.module('PivotGaugeApp', ['ejangular']).controller('PivotGaugeCtrl', function ($scope) {
        //..
    });
    ej.PivotGauge.Locale["fr-FR"] = {
        RevenueGoal: "Objectif de chiffre d'affaires",
        RevenueValue: "Valeur du chiffre d'affaires"
    }
</script>

{% endhighlight %}

Following table localizes the in-built keywords to “French” culture for PivotGauge.

<table>
<tr>
<th>
Keywords</th><th>
Values</th></tr>
<tr>
<td>
RevenueGoal</td><td>
"Objectif de chiffre d'affaires"</td></tr>
<tr>
<td>
RevenueValue</td><td>
"Valeur du chiffre d'affaires ",</td></tr>
</table>

## Localization and Globalization of Cube Info

Content displayed within the PivotGauge control are obtained from the OLAP Cube. So following are the steps that needs to be done to get the localized and globalized Cube content.

To get the localized string based on different cultures, from OLAP Cube, we need to set **"Locale Identifier"** in the connection string to a specific culture. The attribute is set for PivotGauge in Client Mode as shown below

{% highlight javascript %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="PivotGaugeApp">
<head> <!-- Dependency file references --> </head>
<body>
    <div ng-controller="PivotGaugeCtrl">
        <div id="PivotGauge1" ej-pivotgauge />
    </div>
</body>
</html>

{% endhighlight %}

### Populate PivotGauge with DataSource

Initialize the OLAP datasource for PivotGauge widget by using **datasource** property.

{% highlight html %}

<div ng-controller="PivotGaugeCtrl">
    <div id="PivotGauge1" ej-pivotgauge e-dataSource="dataSource" />
</div>
<script>
    var dataSource = {
            data: "http://bi.syncfusion.com/olap/msmdpump.dll;Locale Identifier=1036;"
            //..
    };
    angular.module('PivotGaugeApp', ['ejangular']).controller('PivotGaugeCtrl', function ($scope) {
        //..
        $scope.dataSource = dataSource;
    });
</script>

{% endhighlight %}

For Server Mode, we need to set **"Culture"** and **"OverrideDefaultFormatStrings"** properties in OlapDataManager class to a specific culture along with setting **"Locale Identifier"** in connection string. 

{% highlight C# %}

    //1036 refers to “fr-FR” culture.
    string connectionString = "Data Source=localhost; Initial Catalog=Adventure Works DW; Locale Identifier=1036;";
    DataManager = new OlapDataManager(connectionString);
    DataManager.Culture = new System.Globalization.CultureInfo(1036);
    DataManager.OverrideDefaultFormatStrings = true;

{% endhighlight %}

![](Localization_images/Localization.png) 
