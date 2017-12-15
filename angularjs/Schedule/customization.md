---
title: Schedule - Customization	
description: Customization of working hours, date, and appointment window
platform: AngularJS
control: schedule
documentation: ug
keywords: customization, work hours, appointment window, display hours, Query cell info
---
# Customization

The Scheduler can be customized in various aspects like - 

* Setting different Start/end hour limits
* Highlighting the working hours 
* Setting different [date format](/angularjs/schedule/globalization-and-localization#date-format)
* Specifying minimum and maximum date ranges 
* Customize the entire appointment window with the user required fields
* Setting different time Slot duration
* Complete Scheduler customization using queryCellInfo event
* Setting different [first day of week](/angularjs/schedule/globalization-and-localization#first-day-of-week)

## Hour Customization

It includes customization of displaying Scheduler with specific Start/End hours and also defining the working hour time range which is differentiated as business hours.

### Schedule Display Hours

It denotes the start and end hour time limits to be displayed on the Scheduler. To set this time limit, two properties namely `e-starthour` and `e-endhour` can be used. 

* **startHour** - The hour from which the Scheduler time display actually starts.
* **endHour** - The hour on which the Scheduler time display should end.

The following code example renders the scheduler from 7.00 AM to 6.00 PM.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->>
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-starthour="7" e-endhour="18" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 100,
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

### Working Hours

Working hours indicates the work hour limit within the Scheduler, which is highlighted visually with white colored work cells. To enable the highlighting of work hours on the Scheduler, set the **highlight** option available within the workHours property to **true**. By default, it is set to true. `e-workhours` is a object property which contains the below specified options,

* **highlight** – enables/disables the highlighting of work hours.
* **start** - sets the start time of the working/business hour in a day. 
* **end** - sets the end time limit of the working/business hour in a day. 


{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-workhours-highlight="true" e-workhours-start="8" e-workhours-end="16" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 100,
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

N> By default, work hour **start** is set to **9** and **end** is set to **18**. Also, the Scheduler cells automatically scrolls up or down based on the starting work hour, to make the user to view that particular time initially.

## Hide Weekend days

The Scheduler can be customized to display only the working days, thus hiding the weekend days from it. The working days render based on the values given in the `e-workweek` property. The days that are not mentioned in the `e-workweek` collection is considered to be the weekend days and it can be hidden from the Scheduler by setting `false` to the `e-showweekend` property.

The following code example renders the Scheduler by hiding the weekend days.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-showweekend="false" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 100,
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

## TimeScale

The `e-timescale` allows the user to set the required time slot duration for the work cells that displays on the Scheduler. It provides option to customize both the major and minor slots using template option. It includes the below properties such as,

* `enable` - It accepts true or false value, denoting whether to show or hide the time slots. Its default value is `true`.
* `majorSlot` – Specifies the major time slot duration.
* `minorSlotCount` – Specifies the value, based on which the minor time slots are divided into appropriate count.
* [TimeScale templates](/angularjs/schedule/templates#timescale-templates) - 2 template options available for customizing timeScales namely `minorSlotTemplateId` and `majorSlotTemplateId`. 

The majorSlot and minorSlot can be set on the Scheduler with the following code example.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-timescale-enable="true" e-timescale-majorslot="60" e-timescale-minorslotcount="6" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 100,
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

## Date Customization

The date in the Scheduler can be customized by setting specific minimum and maximum date ranges and also defining various date formats to it.

### Current Date

The Current date indicates the date with which the Scheduler loads initially and based on which the appropriate date range displays in the week/workweek/month/agenda views. To set the current date to the Scheduler – use the following code example,

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 100,
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

N> By default, the System current date will be taken as Scheduler’s current date.

### MinDate and MaxDate

Providing the `e-mindate` and `e-maxdate` property with some date values, allows the Scheduler to set the minimum and maximum date range. The Scheduler date that lies beyond these minimum and maximum date range will be in a disabled state, so that the date navigation is blocked beyond these specified date range. Also, the appointments that lies beyond these date ranges will not be displayed on the Scheduler.  

The following code example shows how to set the minDate and maxDate properties of the Scheduler.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-mindate="minDate" e-maxdate="maxDate" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 100,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
            $scope.minDate = new Date(2017, 1, 4);
            $scope.maxDate = new Date(2017, 1, 10);
        });
    </script>
</body>
</html>

{% endhighlight %}

N> The **maxDate** value provided should always be greater than that of **minDate** value.

## Appointment Window Customization

It is possible to use the custom appointment window option to design it with the user-required extra fields apart from the other default available fields. To make use of the customized appointment window, it is necessary to use the `e-appointmentwindowopen` event within which the display of default appointment window is prevented.

The following code example lets you create the custom appointment window (using recurrence editor feature) with a single extra field for defining the appointment type.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentwindowopen="onAppointmentWindowOpen" e-appointmentsettings-datasource="appointments"
            e-appointmentsettings-id="Id"
            e-appointmentsettings-subject="Subject"
            e-appointmentsettings-starttime="StartTime"
            e-appointmentsettings-endtime="EndTime"
            e-appointmentsettings-description="Description"
            e-appointmentsettings-allday="AllDay"
            e-appointmentsettings-recurrence="Recurrence"
            e-appointmentsettings-recurrencerule="RecurrenceRule">
        </ej-schedule>
        <div id="customWindow" ej-dialog e-width="600" e-height="auto" e-position-x="200" e-position-y="100" e-showoninit="false" e-enablemodal="true" e-title="Appointment Window" e-enableresize="false" e-allowkeyboardnavigation="false" e-close="clearFields" style="display: none">
            <div id="appWindow">
                <form id="custom">
                    <table width="100%" cellpadding="5">
                        <tbody>
                            <tr style="display: none">
                                <td>
                                    Id:
                                </td>
                                <td colspan="2">
                                    <input id="customId" type="text" name="Id" />
                                </td>
                            </tr>
                            <tr>
                                <td>
                                    Subject:
                                </td>
                                <td colspan="2">
                                    <input id="subject" type="text" value="" name="Subject" ng-focus="temp()" style="width: 100%" />
                                </td>
                            </tr>
                            <tr>
                                <td>
                                    Description:
                                </td>
                                <td colspan="2">
                                    <textarea id="customdescription" name="Description" rows="3" cols="50" style="width: 100%; resize: vertical"></textarea>
                                </td>
                            </tr>
                            <tr>
                                <td>
                                    StartTime:
                                </td>
                                <td>
                                    <input id="StartTime" type="text" value="" ej-datetimepicker e-width="150px" />
                                </td>
                            </tr>
                            <tr>
                                <td>
                                    EndTime:
                                </td>
                                <td>
                                    <input id="EndTime" type="text" value="" ej-datetimepicker e-width="150px" />
                                </td>
                            </tr>
                            <tr>
                                <td>Appointment Type:</td>
                                <td>
                                    <input type="text" id="AppointmentType" ej-dropdownlist e-datasource="appTypes" e-fields-text="text" e-fields-id="id" e-fields-value="text" />
                                </td>
                            </tr>
                            <tr>
                                <td colspan="3">
                                    <div class="customcheck">AllDay:</div>
                                    <div class="customcheck">
                                        <input id="allday" type="checkbox" name="AllDay" ej-checkbox e-change="alldayCheck" />
                                    </div>
                                    <div class="customcheck">Recurrence:</div>
                                    <div>
                                        <input id="recurrence" type="checkbox" name="Recurrence" ej-checkbox e-change="recurCheck" />
                                    </div>
                                </td>
                            </tr>
                            <tr id="summarytr" style="display: none;">
                                <td colspan="3">
                                    <div class="recsummary">Summary:</div>
                                    <div>
                                        <label id="recsummary" name="Summary"></label>
                                    </div>
                                </td>
                            </tr>
                            <tr id="edittr" style="display: none;">
                                <td colspan="3">
                                    <div><a id="recedit" ng-click="recurrenceRule()">Edit</a></div>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </form>
                <div>
                    <button type="submit" id="btncancel" ej-button e-click="cancel" e-width="85px" style="float: right; margin-right: 20px; margin-bottom: 10px;">Cancel</button>
                    <button type="submit" id="btnsubmit" ej-button e-click="save" e-width="85px" style="float: right; margin-right: 20px; margin-bottom: 10px;">Submit</button>
                </div>
            </div>
            <div id="recWindow" style="display: none">
                <div id="recurrenceEditor" ej-recurrenceeditor e-frequencies="recFrequencies" e-selectedrecurrencetype="0"></div>
                <br />
                <div>
                    <button type="submit" id="reccancel" ej-button e-click="onRecurrenceClick" style="float: right; margin-right: 20px; margin-bottom: 10px;">Cancel</button>
                    <button type="submit" id="recsubmit" ej-button e-click="onRecurrenceClick" style="float: right; margin-right: 20px; margin-bottom: 10px;">Submit</button>
                </div>
            </div>
        </div>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.recFrequencies = ["daily", "weekly", "monthly", "yearly", "everyweekday"];
            // DataSource values for the appointment type field
            $scope.appTypes = [{
                text: "Tentative",
                id: 1
            }, {
                text: "Busy",
                id: 3
            }, {
                text: "Free",
                id: 5
            }, {
                text: "Out Of Office",
                id: 7
            }];
            $scope.appointments = [{
                Id: 1,
                Subject: "Talk with Nature",
                StartTime: new Date(2017, 1, 7, 6, 0),
                EndTime: new Date(2017, 1, 7, 7, 30)
            }];
            $scope.setDate = new Date(2017, 1, 7);
            //this function executes before the default appointment window is opened
            $scope.onAppointmentWindowOpen = function (args) {
                args.cancel = true; // prevents the display of default appointment window
                var schObj = angular.element("#Schedule1").data("ejSchedule");
                // When double clicked on the Scheduler cells, fills the StartTime and EndTime fields appropriately
                angular.element("#StartTime").ejDateTimePicker({ value: args.startTime });
                angular.element("#EndTime").ejDateTimePicker({ value: args.endTime });
                angular.element("#AppointmentType").ejDropDownList("clearText");
                angular.element("#recWindow").css("display", "none");
                angular.element("#appWindow").css("display", "");
                if (!ej.isNullOrUndefined(args.target)) {
                    // When double clicked on the Scheduler cells, if the target is allday or month cells � only then enable check mark on the allday checkbox
                    if ($(args.target.currentTarget).hasClass("e-alldaycells") || (args.startTime.getHours() == 0 && args.endTime.getHours() == 23))
                        angular.element("#allday").prop("checked", true);
                    else
                        args.model.currentView == "month" ? angular.element("#allday").prop("checked", true) : angular.element("#allday").prop("checked", false);
                        // If the target is allday or month cells � disable the StartTime and EndTime fields
                        angular.element("#StartTime,#EndTime").ejDateTimePicker({
                            enabled: ($(args.target.currentTarget).hasClass("e-alldaycells") || (args.startTime.getHours() == 0 && args.endTime.getHours() == 23) || $(args.target.currentTarget).hasClass("e-monthcells") || args.model.currentView == "month") ? false : true            });
                }
                // If double clicked on the appointments, fill the custom appointment window fields with appropriate values.
                if (!ej.isNullOrUndefined(args.appointment)) {
                    angular.element("#customId").val(args.appointment.Id);
                    angular.element("#subject").val(args.appointment.Subject);
                    angular.element("#customdescription").val(args.appointment.Description);
                    angular.element("#StartTime").ejDateTimePicker({ value: new Date(args.appointment.StartTime) });
                    angular.element("#EndTime").ejDateTimePicker({ value: new Date(args.appointment.EndTime) });
                    // Fills the Appointment type dropdown with its value
                    var value = args.appointment.AppointmentType;
                    angular.element("#AppointmentType").ejDropDownList({
                        text: value, value: value
                    });
                    angular.element("#allday").prop("checked", args.appointment.AllDay);
                    angular.element("#recurrence").ejCheckBox({ checked: args.appointment.Recurrence });
                    if (args.appointment.Recurrence) {
                        angular.element("#edittr").css("display", "");
                        angular.element("#recsummary").html(args.appointment.RecurrenceRule);
                        angular.element("#summarytr").css("display", "");
                        recObj = angular.element("#recurrenceEditor").ejRecurrenceEditor('instance');
                        recObj._recRule = args.appointment.RecurrenceRule; // app recurrence rule is stored in Recurrence editor object
                        recObj.recurrenceRuleSplit(args.appointment.RecurrenceRule, args.appointment.recurrenceExDate); //splitting the recurrence rule
                        recObj.showRecurrenceSummary(args.appointment.Id); // updating the recurrence rule in Recurrence editor
                    }
                }
                angular.element("#customWindow").ejDialog("open");
            }
            //this function executes when submit button of custom appointment window is clicked
            $scope.save = function () {
                // checks if the subject value is not left blank before saving it.
                if (angular.element.trim(angular.element("#subject").val()) == "") {
                    angular.element("#subject").addClass("error");
                    return false;
                }
                var obj = {}, temp = {}, rType;
                var formelement = angular.element("#customWindow").find("#custom").get(0);
                // looping through the custom form elements to get each value and form a JSON object
                for (var index = 0; index < formelement.length; index++) {
                    var columnName = formelement[index].name, $element = angular.element(formelement[index]);
                    if (columnName != undefined) {
                        if (columnName == "")
                            columnName = formelement[index].id.replace(this._id, "");
                            if (columnName != "" && obj[columnName] == null) {
                                var value = formelement[index].value;
                            if (columnName == "Id" && value != "")
                                value = parseInt(value);
                            if ($element.hasClass("e-datetimepicker")) {
                                columnName = $element.attr("id");
                                value = new Date(value);
                            }
                            if (formelement[index].type == "checkbox")
                                value = formelement[index].checked;
                            obj[columnName] = value;
                        }
                    }
                }
                obj["RecurrenceRule"] = (obj.Recurrence) ? recurRule : null;
                var appTypeObj = angular.element("#AppointmentType").data("ejDropDownList");
                obj["AppointmentType"] = appTypeObj.getSelectedValue();
                angular.element("#customWindow").ejDialog("close");
                var object = angular.element("#Schedule1").data("ejSchedule");
                object.saveAppointment(obj);
                clearFields();
            }
            // This function executes when the submit/cancel button in the recurrence editor window is pressed.
            $scope.onRecurrenceClick = function (args) {
                if (angular.element(args.e.currentTarget).attr("id") == "recsubmit") {
                    recObj = angular.element("#recurrenceEditor").ejRecurrenceEditor('instance');
                    recObj.closeRecurPublic();
                    recurRule = recObj._recRule;
                    angular.element("#recsummary").html(recurRule);
                }
                else
                    if ((angular.element(args.e.currentTarget).attr("id") == "reccancel")) {
                        if (angular.element("#recsummary").html() == "") {
                            angular.element("#edittr").css("display", "none");
                            angular.element("#recurrence").ejCheckBox({ checked: false });
                        }
                    else
                        angular.element("#recurrence").ejCheckBox({ checked: true });
                }
                angular.element("#recWindow").css("display", "none");
                angular.element("#appWindow").css("display", "");
                if (angular.element("#recsummary").html() != "")
                    angular.element("#summarytr").css("display", "");
            }

            // This function executes when the recurrence checkbox is checked in the custom appointment window
            $scope.recurCheck = function (args) {
                if (args.isInteraction) {
                    if (angular.element("#recurrence").get(0).checked == true) {  // Displays the recurrence field, when recurrence checkbox is checked.
                        angular.element("#recWindow").css("display", "");
                        angular.element("#appWindow").css("display", "none");
                        angular.element("#edittr").css("display", "");
                    }
                    else {
                        angular.element("#recWindow").css("display", "none");
                        angular.element("#edittr").css("display", "none");
                        angular.element("#recsummary").html("");
                        angular.element("#summarytr").css("display", "none");
                    }
                }
            }

            // This function executes when the All-day checkbox is checked in the custom appointment window
            $scope.alldayCheck = function () {
                // Disables and sets the specific hours to the StartTime and EndTime fields, when the all-day checkbox is checked
                if (angular.element("#allday").prop("checked")) {
                    var a = angular.element("#StartTime").data("ejDateTimePicker").model.value;
                    a.setHours(0, 0, 0);
                    var b = angular.element("#EndTime").data("ejDateTimePicker").model.value;
                    b.setHours(23, 59, 0);
                    angular.element("#StartTime").ejDateTimePicker({
                        value: new Date(a),
                        enabled: false
                    });
                    angular.element("#EndTime").ejDateTimePicker({
                        value: new Date(b),
                        enabled: false
                    });
                }
                else {  
                    angular.element("#StartTime").ejDateTimePicker({
                        enabled: true
                    });
                    angular.element("#EndTime").ejDateTimePicker({
                        enabled: true
                    });
                }
            }

            // This function executes when the cancel button in the custom appointment window is pressed.
            $scope.cancel = function () {
                recObj = angular.element("#recurrenceEditor").ejRecurrenceEditor('instance');
                clearFields();
                angular.element("#customWindow").ejDialog("close");
            }
            // This function executes when the Edit anchor tag in the edit appointment window is clicked.
            function recurrenceRule() {
                angular.element("#recWindow").css("display", "");
                angular.element("#appWindow").css("display", "none");
            }
        });

        // Clears all the field values of the custom window after saving appointments
        function clearFields() {
            angular.element("#customId").val("");
            recObj = angular.element("#recurrenceEditor").ejRecurrenceEditor('instance');
            recObj.clearRecurrenceFields();
            angular.element("#subject").val("");
            angular.element("#customdescription").val("");
            angular.element("#recsummary").html("");
            angular.element("#summarytr").css("display", "none");
            angular.element("#recurrence").ejCheckBox({ checked: false });
            angular.element("#edittr").css("display", "none");
            angular.element("#StartTime,#EndTime").ejDateTimePicker({ enabled: true });
        }

        // This function executes when the subject text field is currently being focused
        function temp() {
            angular.element("#subject").removeClass("error");
        }
    });
    </script>
</body>
</html>

{% endhighlight %}

The styles to be applied for the controls within the custom appointment window are as follows.

{% highlight html %}

<style>
    .customcheck {
    float: left;
    margin-right: 10px;
    }
	
    .error {
    background-color: #FF8A8A;
    }
	
    #custom table td {
    padding:5px;
    }
</style>

{% endhighlight %}


## Scheduler Customization using queryCellInfo

It is possible to format and customize almost every child elements of scheduler such as work cells, header cells, time cells and so on using `e-querycellinfo` event.

The following code snippet shows how to customize the appointment and work cells based on the query cell info event.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-querycellinfo="checkInfo">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
        });
        $scope.checkInfo = function (args) {
            switch (args.requestType) {
                case "workcells":
                    args.element.css("background-color", "#ffe9cc");
                    break;
                case "monthcells":
                    args.element.css("background-color", "#faa41a");
                    args.element.css("border-color", "#faa41a");
                    break;
            }
        }
    </script>
</body>
</html>

{% endhighlight %}

The Scheduler elements are listed below which can be formatted through this event. The names are listed in the format with which it can be accessed or used within the requestType argument of the event.

<table class="params">
    <thead>
        <tr>
            <th>Request Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">appointment</td>
            <td class="description">Depicts the appointment element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">agendacells</td>
            <td class="description">Depicts the Agenda Cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">alldaycells</td>
            <td class="description">Depicts the AllDay cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">headercells</td>
            <td class="description">Depicts the header cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">resourceheadercells</td>
            <td class="description">Depicts the resource header cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">leftheadercells</td>
            <td class="description">Depicts the left empty space on header cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">leftindentcells</td>
            <td class="description">Depicts the left empty space on date cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">timecells</td>
            <td class="description">Depicts the left side time panel cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">headerdate</td>
            <td class="description">Depicts the header date cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">emptytd</td>
            <td class="description">Depicts the empty space above the vertical scroller within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">resourcegroupheader</td>
            <td class="description">Depicts the header group cell in horizontal orientation in the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">monthcells</td>
            <td class="description">Depicts the month cell element within the Scheduler.</td>
        </tr>
        <tr>
            <td class="name">workcells</td>
            <td class="description">Depicts the work cell element within the Scheduler.</td>
        </tr>
    </tbody>
</table>
