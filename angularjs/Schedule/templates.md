---
title: Schedule - Template
description: Customize Scheduler with various available template options
platform: AngularJS
control: schedule
documentation: ug
keywords: appointment template, template, cell template, resource header 
---
# Template

Template is applicable to all the below specified elements of the Scheduler,

* Appointments
* Cells
* Resource header
* Date header
* Priority field
* TimeScale
* Date and time columns in Agenda view
* Tooltip

## Appointment Template

The template design that applies on for the Scheduler appointments. The field names that are mapped from the dataSource to the appropriate field properties within the [appointmentSettings](/api/js/ejschedule#members:appointmentsettings) can be accessed within the template.

Apart from the dataSource field names, the template can also access the current view of the Scheduler using the name **View** – which can contain either of the following values in lowercase. 

* day
* week
* workweek
* agenda
* month
* custom view

It is controlled by an API named `e-appointmenttemplateid` which accepts the id value of the template design block preceded by a symbol **#**.

Usually, the appointments are displayed with its **Subject** and **Start/End time** on the Scheduler. If suppose, the subject needs to be accompanied with location text, it can be done with the following code example.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource" e-appointmenttemplateid="#apptemplate">
        </ej-schedule>
    </div>
    <script id="apptemplate" type="text/x-jsrender">
        {{"{{"}}if View !== "agenda"{{}}}}
        <div style="height:100%; background-color:orange; margin-left: 5px;">
            <div style="margin-left: 2px;">{{"{{"}}:Subject{{}}}}</div>
            <div style="margin-left: 2px;">{{"{{"}}:Location{{}}}}</div>
        </div>
        {{"{{"}}else{{}}}}
        <div>{{"{{"}}:Subject{{}}}}, {{"{{"}}:Location{{}}}}</div>
        {{"{{"}}/if{{"}}"}}
    </script>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 1,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

## Cell Templates

The template design that applies on the Scheduler elements such as all-day cells, work cells and month cells which allows the customization to be done based on the date, view, resources and timescale. The cells can be customized to add images, colors, and other elements etc and can also access the current view of the Scheduler using the name **view**.

**All-day cells** - An API named `e-alldaycellstemplateid` can be used to customize the all-day cells, which accepts the id of the template design block preceded with a symbol **#**.

**Work cells and Month cells** - An API named `e-workcellstemplateid` can be used to customize the work cells in all the views, which accepts the id of the template design block preceded by a symbol **#**. 

The cells can be customized with the following code example.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource" e-alldaycellstemplateid="#alldayTemplate" e-workcellstemplateid="#workTemplate">
        </ej-schedule>
    </div>
    <!-- Template for All-day cells -->
    <script id="alldayTemplate" type="text/x-jsrender">
        <div class="e-icon e-scheduleallday" style="opacity:0.5"></div>
        <span style="opacity:0.5">AllDay</span>
    </script>
    <!-- Template for Workcells and Monthcells -->
    <script id="workTemplate" type="text/x-jsrender">
        {{"{{"}}if resource.classname == 'e-parentnode'{{}}}}
        {{"{{"}}:resource.text{{}}}}
        {{"{{"}}else{{}}}}
        {{"{{"}}if date.getDay() == 0 || date.getDay() == 6{{}}}}
        <div style="background-color:lightblue">Weekend</div>
        {{"{{"}}else{{}}}}
        {{"{{"}}if view == 'month' && resource.text == 'Party Hall-A' && date.getDay() == 5{{}}}}
        <div style="background-color:burlywood">Meeting</div>
        {{"{{"}}else resource.text != 'Party Hall-B' && date.getDate() == 15{{}}}}
        <div style="background-color:thistle">Holiday</div>
        {{"{{"}}else view != 'month' && resource.text == 'Party Hall-A' && date.getDay() == 5 && date.getHours() == 10{{}}}}
        <div style="background-color:burlywood">Meeting</div>
        {{"{{"}}else view == 'month' && resource.text == 'Party Hall-B' && date.getDay() == 5{{}}}}
        <div style="background-color:lightblue">Conf.</div>
        {{"{{"}}else resource.text == 'Party Hall-B' && date.getDate() == 16{{}}}}
        <div style="background-color:darkkhaki">Happyday</div>
        {{"{{"}}else view != 'month' && resource.text == 'Party Hall-B' && date.getDay() == 5 && date.getHours() == 12{{}}}}
        <div style="background-color:goldenrod">Conf.</div>
        {{"{{"}}else date.getDate() == 10 && date.getMonth() == 11{{}}}}
        <div style="background-color:palegreen">Day Spl</div>
        {{"{{"}}else date.getDate() == 25 && date.getMonth() == 11{{}}}}
        <div style="background-color:sandybrown">Christmas</div>
        {{"{{"}}/if{{}}}}
        {{"{{"}}/if{{}}}}
        {{"{{"}}/if{{}}}}
    </script>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 1,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

## Date Header Template

The template design that applies on for the date header part of the Scheduler. An API named `e-dateheadertemplateid` can be used to customize the date header which accepts the id value of the template design block preceded by a symbol **#**. The template can also access the current view of the Scheduler in using the name **view**.

The Date header can be customized with the following code example.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource" e-dateheadertemplateid="#dateTemplate">
        </ej-schedule>
    </div>
    <!-- Template for Dateheader -->
    <script id="dateTemplate" type="text/x-jsrender">
        <div>{{"{{"}}:~dTemplate(date){{}}}}</div>
    </script>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 1,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
        function _dateFormat(date) {
            var dFormat = ej.format(new Date(date), "dd/MM");
            return dFormat;
        }
        $.views.helpers({ dTemplate: _dateFormat });
    </script>
</body>
</html>
    
{% endhighlight %}

## Resource Header Template

The template structure that applies on the resource headers of the Scheduler. By default, only the resource names will be displayed on the resource header bar. Also, the way of rendering resource headers on the Scheduler is comparatively different for both the vertical and horizontal scheduler views. 

The field names that are mapped from the dataSource to the appropriate field properties within the **resourceSettings** can be accessed within the resource header template.

### Resource Header Template in Vertical View

To customize the resource header with some additional images or other customizations in **vertical** **Scheduler** **View** – refer the below code example.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource" e-appointmentsettings-resourcefields="roomId" e-resourceheadertemplateid="#resTemplate" e-group="group">
            <e-resources>
                <e-resource e-field="roomId" e-title="Room" e-name="Rooms" e-resourcesettings="resourcedata"></e-resource>
            </e-resources>
        </ej-schedule>
    </div>
    <script id="resTemplate" type="text/x-jsrender">
        <div style="height:100%">
            <div style="width:15px;height:15px;margin-left:275px;margin-top:2px;float:left;background:{{"{{"}}:ResourceColor{{}}}};"></div><div style="float:left;margin-left:5px;">{{"{{"}}:ResourceText{{}}}}</div>
        </div>
    </script>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.group = {
                resources: ["Rooms"]
            }
            $scope.resourcedata = {
                dataSource: [{
                    ResourceText: "ROOM1",
                    id: 1,
                    ResourceColor: "orange"
                }, {
                    ResourceText: "ROOM2",
                    id: 2,
                    ResourceColor: "#56ca85"
                }],
                text: "ResourceText",
                id: "id",
                color: "ResourceColor"
            };
            $scope.dataSource = [{
                Id: 1,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30),
                roomId: 2
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

### Resource Header Template in Horizontal View

To perform the above specified same customization in **horizontal** **Scheduler** **view**, the template structure varies a little bit as depicted below.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-orientation="horizontal" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource" e-appointmentsettings-resourcefields="roomId" e-resourceheadertemplateid="#resTemplate" e-group="group">
            <e-resources>
                <e-resource e-field="roomId" e-title="Room" e-name="Rooms" e-resourcesettings="resourcedata"></e-resource>
            </e-resources>
        </ej-schedule>
    </div>
    <script id="resTemplate" type="text/x-jsrender">
        <div style="height:100%">
            <div style="width:15px;height:15px;margin-right:5px;margin-top:2px;float:left;background:{{"{{"}}:ResColor{{}}}};"></div><div>{{"{{"}}:ResText{{}}}}</div>
        </div>
    </script>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.group = {
                resources: ["Rooms"]
            }
            $scope.resourcedata = {
                dataSource: [{
                    ResText: "ROOM1",
                    id: 1,
                    ResColor: "orange"
                }, {
                    ResText: "ROOM2",
                    id: 2,
                    ResColor: "#56ca85"
                }],
                text: "ResText",
                id: "id",
                color: "ResColor"
            };
            $scope.dataSource = [{
                Id: 1,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30),
                roomId: 2
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

N> In horizontal Scheduler, the header template makes use of an additional field namely **classname** which holds either **e-parentnode** or **e-childnode** value. The field **classname** can be used in the application scenario to check for the parent or child header node. You can apply the different template customization accordingly based on it.

## TimeScale Templates

The TimeScale is also availed with template options to allow customization. It includes the following 2 properties for customization -

* `e-timescale-majorslottemplateid` - Accepts the id value of the template design block preceded by a symbol **#**, which gets applied for the major time slots.
* `e-timescale-minorslottemplateid` - Accepts the id value of the template design block preceded by a symbol **#**, which gets applied for the minor time slots.

The template customization for major and minor timeslots can be referred from the following code example.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource"
            e-timescale-enable="true" e-timescale-majorslot="60" e-timescale-majorslottemplateid="#majorTemplate" e-timescale-minorslotcount="6" e-timescale-minorslottemplateid="#minorTemplate">
        </ej-schedule>
    </div>
    <!-- Template for Majorslot -->
    <script id="majorTemplate" type="text/x-jsrender">
        <div>{{"{{"}}:~major(date){{}}}}</div>
    </script>
    <!-- Template for Minorslot -->
    <script id="minorTemplate" type="text/x-jsrender">
        <div>{{"{{"}}:~minor(date){{}}}}</div>
    </script>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 1,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
        function _majorFormat(date) {
            var dFormat = ej.format(new Date(date), "hh:mm");
            return dFormat;
        }
        function _minorFormat(date) {
            var dFormat = ej.format(new Date(date), "hh:mm");
            return dFormat;
        }
        $.views.helpers({
            major: _majorFormat,
            minor: _minorFormat
        });
    </script>
</body>
</html>

{% endhighlight %}

## Priority Settings Template

The template design which can be applied to the content of the priority field in the appointment window. By default, the appropriate icons are displayed for each priority options such as **None**, **High**, **Medium** and **Low**. 

When template is applied for the prioritySettings, these default icons will be replaced by the custom icons or styles defined newly. The following code example depicts the way to enable the priority settings and to define the new custom styles to replace the default icons in the Priority field.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments" e-appointmentsettings-priority="Priority"
             e-prioritysettings-enable="true" e-prioritysettings-datasource="priorityDatasource" e-prioritysettings-template="priorityTemplate">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.priorityTemplate = "<div class='${value}'></div>";
            $scope.priorityDatasource = [{
                text: "None",
                id: 1,
                value: "none"
            }, {
                text: "Critical",
                id: 2,
                value: "critical"
            }, {
                text: "Ultra Critical",
                id: 3,
                value: "ultracritical"
            }];
            $scope.appointments = [{
                Id: 1,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30),
                Priority: "critical"
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
    <style type="text/css">
        .critical,
        .ultracritical,
        .none {
            height: 13px;
            width: 13px;
            float: left;
            margin-right: 4px;
            background-repeat: no-repeat;
            background-size: 60px;
            padding: 1px;
            margin-top: 2px;
        }
        .critical {
            background-color: orange;
            background-position: -13px;
        }
        .ultracritical {
            background-color: #56ca85;
            background-position: -59px;
        }
    </style>
</body>
</html>

{% endhighlight %}

The custom style class names defined for the priority template should be same as that of the values defined for each priority option within the dataSource, so that it applies properly.

N> Additionally, the priority field within the `e-appointmentsettings` should be defined with appropriate dataSource field name. When an appointment is assigned with a priority value, the custom style/icon defined for that priority option will get applied over that appointment.

## Tooltip Template

The tooltip can be applied with the customized template design. Currently the tooltip support is provided only for the appointments and the default tooltip displays the Subject and duration on hovering across the appointments. 

By making use of template feature with tooltip, all the field names that are mapped from the dataSource to the appropriate field properties within the **appointmentSettings** can be accessed.

To define the template option for tooltip, the `e-tooltipsettings-enable` must be enabled first. The following code example depicts the way to add the tooltip template.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments" e-tooltipsettings-enable="true" e-tooltipsettings-templateid="#tooltipTemplate">
        </ej-schedule>
    </div>
    <script id="tooltipTemplate" type="text/x-jsrender">
        <div style="width:145px">
            <div style="padding-top:3px;">
                <div style="float:left; font:13px Segoe UI; font-weight:bold;">Subject&nbsp;&nbsp;:&nbsp;</div>
                <div style="padding-top:2px; font:12px Segoe UI SemiBold;">{{"{{"}}:Subject{{}}}}</div>
            </div>
            <div style="padding-top:3px">
                <div style="float:left; font:13px Segoe UI; font-weight:bold;">Location:&nbsp;</div>
                <div style="padding-top:2px; font:12px Segoe UI SemiBold;">{{"{{"}}:Location{{}}}}</div>
            </div>
        </div>
    </script>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.appointments = [{
                Id: 1,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30),
                Location: "India"
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

## Agenda View Templates

Agenda View provides two separate templates – one for date column and another for time column. These templates allows the customization of the content of both the date and time columns. Apart from this, the event column can also be customized through the existing API named `e-appointmenttemplateid`.

The following code snippet shows how to customize the content of the date, time and event column.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-currentview="agenda" e-appointmentsettings-datasource="appointments" e-appointmenttemplateid="#apptemplate" e-agendaviewsettings-datecolumntemplateid="#datetemplate" e-agendaviewsettings-timecolumntemplateid="#timetemplate">
        </ej-schedule>
    </div>
    <!--Template for date column-->
    <script id="datetemplate" type="text/x-jsrender">
        <div style="height:100%">
            <div>
                <div>{{"{{"}}:~dateDisplay(StartTime){{}}}}</div>
            </div>
        </div>
    </script>
    <!--Template for time column-->
    <script id="timetemplate" type="text/x-jsrender">
        <div style="height:100%">
            <div>
                <div>{{"{{"}}:~timeDisplay(StartTime){{}}}}</div>
            </div>
        </div>
    </script>
    <!--Template for appointment which applies for event column in agenda view.-->
    <script id="apptemplate" type="text/x-jsrender">
        {{"{{"}}if View !== "agenda"{{}}}}
        <div style="height:100%; background-color:orange; margin-left: 5px;">
            <div style="margin-left: 2px;">{{"{{"}}:Subject{{}}}}</div>
            <div style="margin-left: 2px;">{{"{{"}}:Location{{}}}}</div>
        </div>
        {{"{{"}}else{{}}}}
        <div>{{"{{"}}:Subject{{}}}}, {{"{{"}}:Location{{}}}}</div>
        {{"{{"}}/if{{}}}}
    </script>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.appointments = [{
                Id: 1,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30),
                Location: "India"
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
        function _getDate(date) {
            var dateCol = new Date(date);
            return dateCol.toDateString();
        }
        function _getTime(date) {
            var time = new Date(date);
            return time.toLocaleTimeString();
        }
        //Here, used the helper function to get the date and time value part from the StartTime.
        $.views.helpers({
            dateDisplay: _getDate,
            timeDisplay: _getTime
        });
    </script>
</body>
</html>

{% endhighlight %}
