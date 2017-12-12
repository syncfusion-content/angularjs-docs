---
title: Schedule - Context Menu	
description: Default and Custom context menu options for appointments and cells in Scheduler
platform: AngularJS
control: schedule
documentation: ug
keywords: context-menu
---
# Context Menu

Scheduler provides default context menu options for both appointments as well as work cells. It also allows to define additional custom context menu options.

The options that are available under `e-contextmenusettings` are as follows,

* **enable** - Enables/disables the context menu option in Scheduler.
* **menuItems** - Contains the sub-menu collections related to both the appointment and cells.

## Default Menu Options


The menu items contains two separate collection based on the appointment and cells. 

### Appointment

The appointment collection includes the following options. 

<table>
<tr>
<td>
Open Appointment (default)</td></tr>
<tr>
<td>
Delete Appointment (default)</td></tr>
<tr>
<td>
Print Appointment</td></tr>
<tr>
<td>
Categorize</td></tr>
</table>

### Cells

The default options available within the cell collection includes - 

<table>
<tr>
<td>
New Appointment</td></tr>
<tr>
<td>
New Recurring Appointment</td></tr>
<tr>
<td>
Today</td></tr>
<tr>
<td>
Go to date</td></tr>
<tr>
<td>
Settings (View, TimeMode, Work Hours) </td></tr>
</table>

The following code snippet shows how to enable the context menu settings in Scheduler and to make use of it with default available options. 

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments" e-contextmenusettings-enable="true">
        <e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="open" e-text="Open Appointment"></e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="delete" e-text="Delete Appointment"></e-contextmenusettings-menuitems-appointment>
        </e-contextmenusettings-menuitems-appointment>
        <e-contextmenusettings-menuitems-cells>
           <e-contextmenusettings-menuitems-cell e-id="new" e-text="Create New Appointment"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="recurrence" e-text="Create recurrence Appointment"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="today" e-text="Today"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="gotodate" e-text="Go to date"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="settings" e-text="Settings"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="view" e-text="View" e-parentid="settings"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="timemode" e-text="TimeMode" e-parentid="settings"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="view_Day" e-text="Day" e-parentid="view"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="view_Week" e-text="Week" e-parentid="view"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="view_Workweek" e-text="Workweek" e-parentid="view"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="view_Month" e-text="Month" e-parentid="view"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="timemode_Hour12" e-text="12 Hours" e-parentid="timemode"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="timemode_Hour24" e-text="24 Hours" e-parentid="timemode"></e-contextmenusettings-menuitems-cell>
           <e-contextmenusettings-menuitems-cell e-id="workhours" e-text="Work Hours" e-parentid="settings"></e-contextmenusettings-menuitems-cell>           
        </e-contextmenusettings-menuitems-cells>
        </ej-schedule>
    </div>
    <script>
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.appointments = [{
                Id: 1,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2017, 1, 7, 6, 9, 0),
                EndTime: new Date(2017, 1, 7, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

N> In agenda view, only the appointment menu items shows up in the context menu options. For default menu items, the id must be defined the same as mentioned in the above code example – as we have processed the menus based on this id within our source.

## Custom Menu Options

Apart from the default available options, it is also possible to add custom menu options to the context-menu of both the appointment and cell collection.

The following code example depicts how **to add the custom menu items** to the appointment and cell collection of the context menu settings.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments" e-contextmenusettings-enable="true">
        <e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="open" e-text="Open Appointment"></e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="delete" e-text="Delete Appointment"></e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="option1" e-text="User Option 1"></e-contextmenusettings-menuitems-appointment>
        </e-contextmenusettings-menuitems-appointment>
        <e-contextmenusettings-menuitems-cells>
           <e-contextmenusettings-menuitems-cell e-id="celloption1" e-text="Custom Option 1"></e-contextmenusettings-menuitems-cell>
        </e-contextmenusettings-menuitems-cells>
        </ej-schedule>
    </div>
    <script>
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.appointments = [{
                Id: 1,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2017, 1, 7, 6, 9, 0),
                EndTime: new Date(2017, 1, 7, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

N> The **id** given for the custom menu items **must be unique** in both the appointment and cell collection. 

## Handling Menu Actions

To define specific actions for a click made on the custom menu items, the client-side event `e-menuitemclick` can be used as depicted in the below code example.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments" e-contextmenusettings-enable="true" e-menuitemclick="appMenuClick">
        <e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="open" e-text="Open Appointment"></e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="delete" e-text="Delete Appointment"></e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="option1" e-text="User Option 1"></e-contextmenusettings-menuitems-appointment>
        </e-contextmenusettings-menuitems-appointment>
        </ej-schedule>
    </div>
    <script>
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.appointments = [{
                Id: 1,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2017, 1, 7, 6, 9, 0),
                EndTime: new Date(2017, 1, 7, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
            $scope.appMenuClick = function (args) {
                //args.events contains information of the clicked menu item.
                if (args.events.ID == "option1")
                    alert("Custom menu clicked");
            };
        });
    </script>
</body>
</html>

{% endhighlight %}


Also, it is possible to predict the target on which the right click is made, either on the cells or appointments with the use of the event `e-beforecontextmenuopen`. The below code example shows how to block the display of context menu, when right clicked on the cells by setting **args.cancel** as **true**.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments" e-contextmenusettings-enable="true" e-beforecontextmenuopen="onBeforeMenuOpen">
        <e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="open" e-text="Open Appointment"></e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="delete" e-text="Delete Appointment"></e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="option1" e-text="User Option 1"></e-contextmenusettings-menuitems-appointment>
        </e-contextmenusettings-menuitems-appointment>
        </ej-schedule>
    </div>
    <script>
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.appointments = [{
                Id: 1,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2017, 1, 7, 6, 9, 0),
                EndTime: new Date(2017, 1, 7, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
            $scope.onBeforeMenuOpen = function (args) {
                //args.events.target – target information to depict either cell/appointment
                if (angular.element(args.events.target).hasClass("e-workcells") || angular.element(args.events.target).hasClass("e-monthcells"))
                    args.cancel = true;
            };
        });
    </script>
</body>
</html>


{% endhighlight %}

## Adding Categorize Option

To include the default categorize option within the context menu, it is necessary to enable the `e-categorizesettings` property as shown in the below code example.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments" e-contextmenusettings-enable="true" e-categorizesettings-enable="true">
        <e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="open" e-text="Open Appointment"></e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="delete" e-text="Delete Appointment"></e-contextmenusettings-menuitems-appointment>
           <e-contextmenusettings-menuitems-appointment e-id="categorize" e-text="Categorize"></e-contextmenusettings-menuitems-appointment>
        </e-contextmenusettings-menuitems-appointment>
        </ej-schedule>
    </div>
    <script>
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.appointments = [{
                Id: 1,
                Subject: "Research on Sky Miracles",
                StartTime: new Date(2017, 1, 7, 6, 9, 0),
                EndTime: new Date(2017, 1, 7, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>


{% endhighlight %}

N> The **categorize** option must be added only to the **appointment** collection, which displays on right clicking the appointments.

