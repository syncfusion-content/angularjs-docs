---
title: Schedule - Responsiveness
description: Display Scheduler with responsiveness
platform: AngularJS
control: schedule
documentation: ug
keywords: responsive, responsiveness, auto size 
---
# Responsiveness

Scheduler is provided with default **responsive** support, so that it adjust or auto-resize it’s UI content based on the window or the container size on which it is placed. 

## Auto-Resizing Scheduler

By default, setting 100% width to the Scheduler makes it adaptable to the window or its parent container, as and when the browser is resized. This will not allow the scheduler to adapt height-wise.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            //Array of JSON data configure in dataSource
            $scope.appointments = [{
                Id: 1,
                Subject: "Music Class",
                StartTime: new Date(2017, 1, 7, 6, 0, 0),
                EndTime: new Date(2017, 1, 7, 7, 0, 0)
            }, {
                Id: 2,
                Subject: "School",
                StartTime: new Date(2017, 1, 7, 9, 0, 0),
                EndTime: new Date(2017, 1, 7, 14, 30, 0)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

To auto-resize the Scheduler height – set the **e-height** property of the Scheduler to **100%** and also set some specific height (either percentage or pixel values) to its parent container (or) to the HTML and body tag elements as shown below.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp" style="height: 100%">
<head>
    <!-- Dependency file references -->
</head>
<body style="height: 100%">
    <div ng-controller="ScheduleCtrl" style="height: 100%">
        <ej-schedule id="Schedule1" e-height="100%" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            //Array of JSON data configure in dataSource
            $scope.appointments = [{
                Id: 1,
                Subject: "Music Class",
                StartTime: new Date(2017, 1, 7, 6, 0, 0),
                EndTime: new Date(2017, 1, 7, 7, 0, 0)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

N> When the Scheduler width is set to have **less** **than** **600px**, then the View selection options will be displayed in a **navigation** **drawer**. 

Also, whenever the Scheduler resizes - the width of the work cells adjusts automatically (if no **e-cellwidth** property is specified with pixel values), but the height of the cells are kept to remain as same as 20px until **e-cellheight** property is set explicitly with some pixel values.

## Scheduler in Mobile/Tablets

The Scheduler layout adapts automatically in the mobile and tablet devices with the appropriate UI changes, as the `e-isresponsive` property is set to **true** by default. In case, if the user wants to display the normal scheduler in mobile devices without any adaptive enhancements, then the `isResponsive` property can be set to false.

Some of the default changes done for adaptive Scheduler to render in mobile devices are as follows,

* Animation effect introduced between view/date navigation.
* Cell Height increased
* The header date display changes (displayed next to the navigation icons).
* View options displayed in Navigation drawer
* Time cell width decreased
* Quick window display blocked on cell/appointment single click.
* Appointment resizing action blocked.
* Multiple cell selection blocked.
* Delete appointment option made available within the appointment window.
* Week header display in month view hidden.
* With Multiple resources - only one resource is viewable initially on the screen and to further look onto other resources, user need to swipe the screen.

N> To make the Scheduler control to react as responsive in mobile/tablet devices, it is necessary to refer the additional [ej.responsive.css](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/responsive-css/ej.responsive.css) file in the application.

The following code snippet depicts the Scheduler code with responsive set to true.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp" style="height: 100%">
<head>
    <title>My first HTML page</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <link href=" http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/responsive-css/ej.responsive.css" rel="stylesheet" />
    <!-- Other required SCRIPT REFERENCES -->
</head>
<body style="height: 100%">
    <div ng-controller="ScheduleCtrl" style="height: 100%">
        <ej-schedule id="Schedule1" e-height="100%" e-currentdate="setDate" e-isresponsive="true" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            //Array of JSON data configure in dataSource
            $scope.appointments = [{
                Id: 1,
                Subject: "Music Class",
                StartTime: new Date(2017, 1, 7, 6, 0, 0),
                EndTime: new Date(2017, 1, 7, 7, 0, 0)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

