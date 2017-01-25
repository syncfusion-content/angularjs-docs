---
layout: post
title: Layout-Customization
description: layout customization
platform: Angular-1
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Layout Customization

## Control Placement

### Tab View
In Tab View representation, both Grid and Chart will be displayed in separate tabs. This could be set by using the [`controlPlacement`](/api/js/ejpivotclient#members:displaysettings-controlplacement) property under the `e-displaySettings` option.  By default, **Tab** value is set.

{% highlight javascript %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient e-displaySettings="displaySettings" />
</div>
<script>
    angular.module('PivotClientApp', ['ejangular']).controller('PivotClientCtrl', function ($scope) {
            //..
            $scope.displaySettings = {
                    controlPlacement: ej.PivotClient.ControlPlacement.Tab
            };
    });
</script>

{% endhighlight %}

![](Layout-Customization_images/tab.png) 

### Tile View
In Tile View representation, both Grid and Chart will be displayed one above the other, in the same layout. Tile view can be set by using the [`controlPlacement`](/api/js/ejpivotclient#members:displaysettings-controlplacement) property under the `e-displaySettings` option.

{% highlight javascript %}

$scope.displaySettings = {
        controlPlacement: ej.PivotClient.ControlPlacement.Tile
};

{% endhighlight %}

![](Layout-Customization_images/tile-view.png)

## Default View

### Grid View
To display Grid control by default, set [`defaultView`](/api/js/ejpivotclient#members:displaysettings-defaultview) property under `e-displaySettings` option to **Grid**, which is the default value of the property.

{% highlight javascript %}

$scope.displaySettings = {
        defaultView: ej.PivotClient.DefaultView.Grid
};

{% endhighlight %}

![](Layout-Customization_images/grid-view.png)

### Chart View
To display Chart control by default, set the property [`defaultView`](/api/js/ejpivotclient#members:displaysettings-defaultview) property to **Chart**.

{% highlight javascript %}

$scope.displaySettings = {
        defaultView: ej.PivotClient.DefaultView.Chart
};

{% endhighlight %}

![](Layout-Customization_images/Chart-view.png)

## Display Mode

### Grid Only
By setting the [`mode`](/api/js/ejpivotclient#members:displaysettings-mode) property under `e-displaySettings` option to **GridOnly**, PivotGrid component alone will get rendered and PivotChart will not be rendered.

{% highlight javascript %}

$scope.displaySettings = {
        mode: ej.PivotClient.DisplayMode.GridOnly
};

{% endhighlight %}

![](Layout-Customization_images/Grid-only.png)

### Chart Only
By setting the [`mode`](/api/js/ejpivotclient#members:displaysettings-mode) property under `e-displaySettings` option to **ChartOnly**, PivotChart component alone will get rendered and PivotGrid will not be rendered.

{% highlight javascript %}

$scope.displaySettings = {
        mode: ej.PivotClient.DisplayMode.ChartOnly
};

{% endhighlight %}

![](Layout-Customization_images/Chart-only.png)

### Both Chart and Grid
By setting the [`mode`](/api/js/ejpivotclient#members:displaysettings-mode) property under `e-displaySettings` option to **ChartAndGrid**, data is displayed in both Grid and Chart.  This is the default value of the property.

{% highlight javascript %}

$scope.displaySettings = {
        mode: ej.PivotClient.DisplayMode.ChartAndGrid
};

{% endhighlight %}

![](Layout-Customization_images/tile-view.png)

## Toggle Panel
Toggle panel option lets the user to toggle the visibility of Axis Element Builder and Cube Dimension Browser panels in PivotClient with a use of a button. The button could be added to the control by enabling the [`enableTogglePanel`](/api/js/ejpivotclient#members:displaysettings-enabletogglepanel) property under `e-displaySettings` option.  This property is disabled by default.

{% highlight javascript %}

$scope.displaySettings = {
        enableTogglePanel: true
};

{% endhighlight %}

![](Layout-Customization_images/toggle-panel.png)

## Maximized/Full Screen View
Full screen view helps to visualize the PivotGrid and PivotChart controls inside PivotClient precisely according to the browser window size.  By selecting full screen icon in the toolbar, the control which is in the view gets maximized.  Drilldown action can also be performed in both PivotGrid and PivotChart in the maximized view.  This option is enabled by setting the [`enableFullScreen`](/api/js/ejpivotclient#members:displaysettings-enablefullscreen) property under `e-displaySettings` option to true.  The value is false by default.

{% highlight javascript %}

$scope.displaySettings = {
        enableFullScreen: true
};

{% endhighlight %}

![](Layout-Customization_images/fullscreen-icon.png)

The following screenshot shows the maximized view of PivotGrid.

![](Layout-Customization_images/fullscreen-view.png)


## Chart Types
While loading the PivotClient initially, the PivotChart widget can be rendered in any one of the available chart types using the `e-chartType` property.

{% highlight javascript %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient e-chartType="chartType" />
</div>
<script>
    angular.module('PivotClientApp', ['ejangular']).controller('PivotClientCtrl', function ($scope) {
            //..
            $scope.chartType = ej.PivotChart.ChartTypes.Area;
    });
</script>

{% endhighlight %} 

The `e-chartType` property takes Column Chart by default. The types available are Column, Stacking Column, Bar, Stacking Bar, Line, Spline, Step Line, Area, Spline Area, Step Area, Stacking Area, Pie, Funnel and Pyramid.

The Chart Type can also be changed dynamically through the toolbar icon. 

![](Layout-Customization_images/chart-type.png)

![](Layout-Customization_images/chart-type-changed.png)

## Report Toolbar

Icons can be either enabled/disabled inside the report toolbar. This can be achieved by setting the properties under `e-toolbarIconSettings` option to false. The value is true by default.

{% highlight javascript %}

<div ng-controller="PivotClientCtrl">
    <div id="PivotClient1" ej-pivotclient e-toolbarIconSettings="toolbarIconSettings" />
</div>
<script>
    angular.module('PivotClientApp', ['ejangular']).controller('PivotClientCtrl', function ($scope) {
            //..
            //Disable toolbar icon in PivotClient.
            $scope.toolbarIconSettings = {
                enableAddReport: false,
                enableNewReport: false,
                enableRemoveReport: false
            };
    });
</script>

{% endhighlight %}

![](Layout-Customization_images/toolbarIconSettings1.png)

The following screenshot shows after disabling the toolbar icons.

![](Layout-Customization_images/toolbarIconSettings2.png)