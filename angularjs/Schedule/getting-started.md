---
title: Getting started with Schedule component	
description: Rendering a basic Scheduler with local data
platform: AngularJS
control: schedule
documentation: ug
keywords: ejschedule, schedule, schedule widget, js schedule 
---

# Getting Started

The AngularJS directives are usually included within the `ej.widget.angular.min.js` file and all these directives are usually packed together in a common module known as `ejangular`. For basic details on how to configure Syncfusion widgets in AngularJS framework, refer [here](https://help.syncfusion.com/js/angularjs).

To get start with the Schedule control in AngularJS framework, the following list of external dependencies are mandatory, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates
* [AngularJS](https://angularjs.org/)

The external AngularJS script file `angular.min.js` can also be accessed from the following installed location - 

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\external

An another mandatory script is `ej.widget.angular.min.js`, which can be accessed from the specified location - 

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\common

The other required internal dependencies of Scheduler are tabulated below,

<table>
<tr>
<th>
File<br/><br/></th><th>
Description/Usage<br/><br/></th></tr>
<tr>
<td>
ej.core.min.js<br/><br/></td><td>
Must be referred always first before using all the JS controls.<br/><br/></td></tr>
<tr>
<td>
ej.data.min.js<br/><br/></td><td>
Used to handle data operation and should be used while binding data to JS controls.<br/><br/></td></tr>
<tr>
<td>
ej.globalize.min.js<br/><br/></td><td>
Must be referred to localize any of the JS control's text and content.<br/><br/></td></tr>
<tr>
<td>
ej.schedule.min.js<br/><br/></td><td>
Schedule core script file which includes schedule related scripts files such as <i>ej.schedule.render.js</i>, <i>ej.schedule.resources.js</i> and <i>ej.schedule.horizontal.js</i><br/><br/></td></tr>
<tr>
<td>
ej.scroller.js<br/><br/>ej.touch.js<br/><br/>ej.draggable.js<br/><br/>ej.navigationdrawerbase.js<br/><br/>ej.listviewbase.js<br/><br/>ej.listview.js<br/><br/>ej.recurrenceeditor.js<br/><br/>ej.dropdownlist.js<br/><br/>ej.radiobutton.js<br/><br/>ej.dialog.js<br/><br/>ej.button.js<br/><br/>ej.autocomplete.js<br/><br/>ej.datepicker.js<br/><br/>ej.timepicker.js<br/><br/>ej.checkbox.js<br/><br/>ej.editor.js<br/><br/>ej.menu.js<br/><br/>ej.navigationdrawer.js<br/><br/>ej.tooltip.js<br/><br/></td><td>
These files are referred for proper working of the sub-controls used within Scheduler.<br/><br/></td></tr>
</table>

N> Scheduler uses one or more sub-controls, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the Scheduler, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

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
    <title>Getting Started - Schedule</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
</head>

{% endhighlight %}

Add links to the [CDN](https://help.syncfusion.com/js/cdn) Script files with other required external dependencies.

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - Schedule</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jsrender.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
	<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
	<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
</head>

{% endhighlight %}

N> Uncompressed version of the script files are also available, which is used for development or debugging purpose and can be generated from the custom script [here](http://csg.syncfusion.com).

## Control Initialization

Create the Schedule control using `ej-schedule` directive and define all its other properties prefixed with `e-` as shown in the below code -

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">

<body>
	<div ng-controller="ScheduleCtrl">
		<ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentView" e-currentdate="setDate">
	    </ej-schedule>
	</div>
</body>

</html>

{% endhighlight %}

In the above code example, `currentView` and `setDate` are the scope variables defined, in order to enable the two-way binding. Therefore, refer the below code example to know how to enable the model binding.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head> <!-- Dependency file references --> </head>
<body>
	<div ng-controller="ScheduleCtrl">
		<ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentView" e-currentdate="setDate">
	    </ej-schedule>
	</div>
    <script>
	angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
		$scope.setDate = new Date(2016, 4, 5);
		$scope.currentView = "week";
	});
</script>
</body>

</html>

{% endhighlight %}

The Scheduler properties that supports **two-way binding** are as follows - 

<table>
	<tr>
	<th>Properties</th>
	<th>Usage</th>
	</tr>
	<tr>
	<td>currentView</td>
	<td>sets the specific view on the Scheduler</td>
	</tr>
	<tr>
	<td>currentDate</td>
	<td>sets the specific date on the Scheduler</td>
	</tr>
	<tr>
	<td>fields.dataSource</td>
	<td>Sets the Scheduler dataSource</td>
	</tr>
</table>	

## Binding Appointment Data

Set the Scheduler `dataSource` with a set of local JSON data by passing it through the scope variable `appointments` - 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head> <!-- Dependency file references --> </head>
<body>
	<div ng-controller="ScheduleCtrl">
		<ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentView" e-currentdate="setDate"
            e-appointmentsettings-datasource="appointments" 
			e-appointmentsettings-id="Id" 
			e-appointmentsettings-subject="Subject" 
			e-appointmentsettings-starttime="StartTime"
			e-appointmentsettings-endtime="EndTime" 
			e-appointmentsettings-description="Description" 
			e-appointmentsettings-allday="AllDay" 
			e-appointmentsettings-recurrence="Recurrence" 
			e-appointmentsettings-recurrencerule="RecurrenceRule">
	    </ej-schedule>
	</div>
<script>
    var dManager = [{ 
        Id: 1, 
        Subject: "Bering Sea Gold", 
        StartTime: new Date(2016, 4, 5, 5, 30), 
        EndTime: new Date(2016, 4, 5, 7, 30), 
        Description:"", 
        AllDay: false, 
        Recurrence: false
    }];
	angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
        $scope.appointments = dManager;
		$scope.setDate = new Date(2016, 4, 5);
		$scope.currentView = "week";
	});
</script>
</body>

</html>

{% endhighlight %}

N> Other than the local JSON data, Scheduler `dataSource` can also be set with remote data services which is accessed through the help of `ejDataManager` instances.

The Scheduler displays as shown in the below image - 

![](getting-started_images/schedule.png)

## Mapper Fields

It is mandatory to map the appointment fields with the appropriate column names from the dataSource. For example, if the local appointment data is defined with specific column names as below - 

{% highlight html %}

<script>
    var dManager = [{ 
        AppId: 1, 
        AppSubject: "Bering Sea Gold", 
        AppStartTime: new Date(2016, 4, 5, 5, 30), 
        AppEndTime: new Date(2016, 4, 5, 7, 30), 
        AppDescription:"", 
        AllDay: false, 
        Recurrence: false
    }];
</script>

{% endhighlight %}

Those above specified field names of appointment data must be mapped accurately with the Scheduler `appointmentsettings` fields as shown below - 

{% highlight html %}

	<div ng-controller="ScheduleCtrl">
		<ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentView" e-currentdate="setDate"
            e-appointmentsettings-datasource="appointments" 
			e-appointmentsettings-id="AppId" 
			e-appointmentsettings-subject="AppSubject" 
			e-appointmentsettings-starttime="AppStartTime"
			e-appointmentsettings-endtime="AppEndTime" 
			e-appointmentsettings-description="AppDescription" 
			e-appointmentsettings-allday="AllDay" 
			e-appointmentsettings-recurrence="Recurrence" 
			e-appointmentsettings-recurrencerule="RecurrenceRule">
	    </ej-schedule>
	</div>

{% endhighlight %}