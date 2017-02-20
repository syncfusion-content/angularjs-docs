---
title: Schedule - Views
description: View options available in Scheduler
platform: Angular-1
control: schedule
documentation: ug
keywords: day, week, workweek, month, timeline, horizontal, custom  
---
# Views

The number of days and its associated appointments are usually grouped together in Scheduler to organize different views. The available view options in Scheduler are as follows,

* Day
* Week
* Workweek
* Month
* Custom View
* Agenda
* Timeline View

Usually these view options are displayed as a toolbar in the date-header section of the Schedule control. The items within the views toolbar can be added/removed based on the value passed to the `e-views` property. 

By default, the Schedule control’s active view is **Week** view. Also, it is possible to change the active view of the Scheduler by setting `e-currentview` option with the required view name as depicted below.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-views="views" e-currentview="workweek">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.views = ["Day", "WorkWeek"];
        });
    </script>
</body>
</html>

{% endhighlight %}

N> The **e-currentview** property accepts both the `string` and `ej.Schedule.CurrentView` enum value.

## Day 

It represents a single day Scheduler view (single date display) with all its related appointments.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentview" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            // Set the Active view
            $scope.currentview = ej.Schedule.CurrentView.Day;
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

## Week

It’s a view displaying a count of 7 days (from Sunday to Saturday) with all its related appointments. The first day of the week can be changed using the `e-firstdayofweek` API which accepts either the `integer` (Sunday=0, Monday=1, Tuesday=2, etc) or `string` (“Sunday”, “Monday”, etc) or `ej.Schedule.DayOfWeek` enum type value. The default value of this **e-firstdayofweek** depends on the current culture (language) used in the Scheduler.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentview" e-currentdate="setDate" e-firstdayofweek="firstDayOfWeek" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            // Set the Active view
            $scope.currentview = ej.Schedule.CurrentView.Week;
            // Configure the week start day(First day of week)
            $scope.firstDayOfWeek = ej.Schedule.DayOfWeek.Monday,
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

## Work Week 

Work week view displays the working days of the week (count of 5 days) and its associated appointments. It is also possible to customize the days to be displayed in the work week view using `e-workweek` API which accepts the string array such as ["Monday", "Tuesday", "Wednesday", "Thursday" and "Friday"]. By default, it renders from Monday to Friday (5 days).

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentview" e-currentdate="setDate" e-workweek="workweek" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            // Set the Active view
            $scope.currentview = ej.Schedule.CurrentView.Workweek;
            // Configure the week start day(First day of week)
            $scope.workweek = ["Monday", "Tuesday", "Thursday", "Friday", "Saturday"];
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

## Month

Month view displays the entire days of a particular month and all its related appointments. An alternative way to navigate to a particular date in a day view directly from Month view, clicking on the appropriate month cell date header will do so. If the week date range column is clicked, it will navigate to the corresponding week view.

The next and previous month date cells in the Month view can be shown/hidden on the Scheduler using `e-shownextprevmonth` property by setting it to *false*.

For example – To set the Month view as current view in Scheduler and to hide the other month days in it, refer the below code example.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentview" e-currentdate="setDate" e-shownextprevmonth="false" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            // Set the Active view
            $scope.currentview = ej.Schedule.CurrentView.Month;
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

N> An appointment directly created in Month view will be considered as an all-day appointment.

## Custom

The Scheduler can be displayed with the user-specified date ranges, such as 4 days or any specific date ranges instead of default view options, by making use of the `e-renderdates` property. This property includes two sub properties namely **start** and **end**, which accepts the date object or date value in string format to specify the date range. 

To display the custom view option in the toolbar-like view options in the scheduler header area, add the `CustomView` value to the views property array collection as shown below. 

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-views="views" e-currentview="currentview" e-currentdate="setDate" e-renderdates="renderDates" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            // We can add the "CustomView" in views collection
            $scope.views = ["Day", "Week", "WorkWeek", "Month", "CustomView"];
            // Configure the custom date
            $scope.renderDates = {
                // Render start date 
                start: new Date(2015, 11, 6),
                // Render end date 
                end: new Date(2015, 11, 9)
            };
            // Set the Active view
            $scope.currentview = ej.Schedule.CurrentView.CustomView;
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

When the date difference between the provided start and end date is greater than 7, then the month-like view will get displayed in Vertical Scheduler mode - whereas with the date difference less than 7 days displays the Scheduler with exact count of the specified days.

N> When the `e-currentdate` property of Scheduler is set with a date, that lies beyond the specified custom date range - then the Scheduler navigates to the current date with the mentioned date differences.  

## Agenda

This View option lists out the appointments in a grid-like view for the next 7 days by default from the current date. The count of the number of appointments to be listed in this view can be customized using the `e-agendaviewsettings-daysinagenda`.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentview" e-agendaviewsettings-daysinagenda="daysCount" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            //Set the Active view
            $scope.currentview = ej.Schedule.CurrentView.Agenda;
            //Next 5 days Appointments lists out from current date
            $scope.daysCount = 5;
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

N> In Agenda view, the templates can be applied for the date and time columns which can be referred [here](/angular-1/schedule/templates). Also, the template passed through the `e-appointmenttemplateid` will gets applied to the event column in Agenda view.

## Restriction on View Navigation

It is possible to restrict the users to display only the specific list of views in the Schedule header section and also not to navigate to other views that are not listed. 

**For example**, if the views property is set only with `Month` view – then the Schedule header section displays only the Month option in the view toolbar and also other additional available actions like navigating to day/week view on clicking the month header dates and week date-range is stopped.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-views="views" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.views = ["Month"];
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

N> Even though Week view is the active view in Scheduler by default, if it is not listed in the views collection – then the first listed option in the views collection will be taken as current view of the Scheduler.

## Timeline View

Timeline view displays the day, time and its associated events horizontally arranged from left to right. By default, Scheduler renders in vertical mode and it can be changed to the timeline mode using `e-orientation` property which accepts both the `string` and `ej.Schedule.Orientation` enum value.

All the applicable features in Vertical mode works similar with Timeline mode (Horizontal) and only the visualization of the layout changes based on the orientation.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-orientation="orientation" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            //set the timeline (horizontal) view
            $scope.orientation = ej.Schedule.Orientation.Horizontal;
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
