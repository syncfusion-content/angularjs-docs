---
title: How-to
description: Custom Configuration with Schedule control
platform: AngularJS
control: schedule
documentation: ug
keywords: validation and customization of appointment window fields, Appointment filters 
---
# How To

## Validate the Custom Appointment Window Fields

The client-side validation of the fields present within the custom appointment window can be handled before submitting it, by adding appropriate validation classes to each field.

Refer the steps [here](/angular-1/schedule/customization#appointment-window-customization) and create a sample for Custom Appointment window, before proceeding with the following validations.

In the custom appointment window sample, create an additional CSS class **validation** as mentioned below to add it to the appropriate fields, if the validation of such fields fails.

{% highlight html %}

<style> 
    .validation {
        border-color: red;
    }
</style>

{% endhighlight %}

The sample contains the fields like Subject, Description, StartTime and EndTime which needs to be validated at client-side. To do so, add the required validation code within the script section as follows.

{% highlight html %}

<script type="text/javascript">

// To Validate the Subject field.
$("#subject").focusout(function() {
    if ($.trim($("#subject").val()) == "") {
        $("#subject").addClass("validation");
        return false;
    }
})

// To Validate the Description field.
$("#customdescription").focusout(function() {
    if ($.trim($("#customdescription").val()) == "") {
        $("#customdescription").addClass("validation");
        return false;
    }
})

// To Validate the Time duration of the appointments
$("#EndTime").focusout(function() {
    if (new Date($("#EndTime").val()).getDate() >= new Date($("#StartTime").val()).getDate()) {
        if (new Date($("#StartTime").val()).getTime() >= new Date($("#EndTime").val()).getTime())
            alert("EndTime value is lesser than the StartTime value");
    }
})

</script>

{% endhighlight %}

Now, after adding the above validations – whenever the fields within the custom appointment window are skipped without filling any information, it will be notified to the users appropriately.


## Display Scheduler with Appointments Filtered by Subject

It is possible to display the Scheduler with appointments, which is filtered based on the Subject. For example, if we keep a text box and start typing a character – the list of appointments whose subject matches the typed character alone will be shown on the Scheduler. The following code example depicts the way to achieve this.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <!--textbox for entering search character-->
        <input id='txtSearch' type='text' onkeyup='searchKeyUp()' />
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        // Appointment data to be bound to the Scheduler
        window.Default = [
            {
                Id: 101,
                Subject: "Bering Sea Gold",
                StartTime: new Date(2015, 11, 5, 10, 00),
                EndTime: new Date(2015, 11, 5, 11, 00),
                Description: "",
                AllDay: false,
                Recurrence: false,
                Categorize: "1,3"
            },
            {
                Id: 102,
                Subject: "Bering Sea Gold",
                StartTime: new Date(2015, 11, 2, 16, 00),
                EndTime: new Date(2015, 11, 2, 17, 30),
                Description: "",
                AllDay: false,
                Recurrence: false,
                Categorize: "2,5"
            },
            {
                Id: 104,
                Subject: "What Happened Next?",
                StartTime: new Date(2015, 11, 5, 12, 30),
                EndTime: new Date(2015, 11, 5, 15, 00),
                Description: "",
                AllDay: false,
                Recurrence: false,
                Categorize: "4,1"
            },
            {
                Id: 105,
                Subject: "Daily Planet",
                StartTime: new Date(2015, 11, 3, 01, 00),
                EndTime: new Date(2015, 11, 3, 02, 00),
                Description: "",
                AllDay: false,
                Recurrence: false,
                Categorize: "1,3,6"
            }, {
                Id: 107,
                Subject: "How It's Made",
                StartTime: new Date(2015, 11, 1, 06, 00),
                EndTime: new Date(2015, 11, 1, 07, 30),
                Description: "",
                AllDay: false,
                Recurrence: true,
                RecurrenceRule: "FREQ=WEEKLY;BYDAY=MO,TU;INTERVAL=1;COUNT=15",
                Categorize: "2,3,6"
            }, {
                Id: 108,
                Subject: "Deadest Catch",
                StartTime: new Date(2015, 11, 3, 16, 00),
                EndTime: new Date(2015, 11, 3, 17, 00),
                Description: "",
                AllDay: false,
                Recurrence: false,
                Categorize: "2,4,6,1"
            }, {
                Id: 109,
                Subject: "MayDay",
                StartTime: new Date(2015, 3, 30, 06, 30),
                EndTime: new Date(2015, 3, 30, 07, 30),
                Description: "",
                AllDay: false,
                Recurrence: false,
                Categorize: "5,3"
            }, {
                Id: 110,
                Subject: "Cash Cab",
                StartTime: new Date(2015, 3, 30, 15, 00),
                EndTime: new Date(2015, 3, 30, 16, 30),
                Description: "",
                AllDay: false,
                Recurrence: true,
                RecurrenceRule: "FREQ=DAILY;INTERVAL=1;COUNT=5",
                Categorize: "1,3"
            }
        ];
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.appointments = window.Default;
            $scope.setDate = new Date(2015, 11, 5);
        });
        // This function executes when a character is entered in the textbox
        function searchKeyUp() {
            var searchString = $("#txtSearch").val();
            var schObj = $("#Schedule1").data("ejSchedule");
            var result = schObj.searchAppointments(searchString);
            schObj.option("appointmentSettings", { dataSource: [] });
            if (!ej.isNullOrUndefined(result) && result.length != 0 && searchString != "")
                schObj.option("appointmentSettings", { dataSource: result });
            else
                schObj.option("appointmentSettings", { dataSource: window.Default });
        }
    </script>
</body>
</html>

{% endhighlight %}

## Customize the Default Appointment Window

Apart from the custom appointment window, it is possible to customize the default appointment window by adding/removing the required number of fields into it. This can be achieved through the **create** event of the scheduler.

The following code example depicts the way to achieve the customization of default appointment window.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentwindowopen="onAppointmentOpen" e-appointmentsettings-datasource="appointments">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.appointments = [{
                Id: 100,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 0),
                EndTime: new Date(2017, 1, 7, 10, 30),
                Location: "CHINA",
                AppointmentType: "Tentative",
                Status: "90%"
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
        // This function executes before the appointment window gets opened.
        function onAppointmentOpen(args) {
            if (this._appointmentAddWindow.find(".customfields").length == 0) {
                var customDesign = "<tr class='customfields'><td class='e-textlabel'>Event Type</td><td><input class='apptype' style='width:140px;' type='text'/></td><td class='e-textlabel'>Event Status </td><td><input class='status' style='width:140px;' type='text'/></td></tr>";
                $("." + this._id + "parrow").after(customDesign);
            }
            if (!ej.isNullOrUndefined(args.appointment)) {
                // if double clicked on the appointments, retrieve the custom field values from the appointment object and fills it in the appropriate fields.
                this._appointmentAddWindow.find(".apptype").val(args.appointment.AppointmentType);
                this._appointmentAddWindow.find(".status").val(args.appointment.Status);
            } else {
                // if double clicked on the cells, clears the field values.               
                this._appointmentAddWindow.find(".apptype").val("");
                this._appointmentAddWindow.find(".status").val("");
            }
        }
    </script>
</body>
</html>

{% endhighlight %}

## Synchronize the Schedule with Outlook

Schedule appointments can be synchronized with Outlook and vice versa, by making use of the Microsoft Outlook 12/15 Object library. 

The following code example depicts the way to synchronize the Schedule with Outlook.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource"
            e-appointmentsettings-id="Id"
            e-appointmentsettings-subject="Subject"
            e-appointmentsettings-starttime="StartTime"
            e-appointmentsettings-endtime="EndTime"
            e-appointmentsettings-starttimezone="StartTimeZone"
            e-appointmentsettings-endtimezone="EndTimeZone"
            e-appointmentsettings-description="Description"
            e-appointmentsettings-allday="AllDay"
            e-appointmentsettings-recurrence="Recurrence"
            e-appointmentsettings-recurrencerule="RecurrenceRule">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        var dataManager = ej.DataManager({
            url: '@Url.Action("GetApp", "Home")',
            crudUrl: '@Url.Action("Batch","Home")',
            crossDomain: true
        });
        dataManager.adaptor = new ej.UrlAdaptor();
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = dataManager;
            $scope.setDate = new Date(2015, 5, 15);
        });
    </script>
</body>
</html>

{% endhighlight %}

Schedule control is not directly compatible with the Outlook calendar object, as it returns the COM object. Therefore, in order to bind the schedule control with those data retrieved from outlook, then it is necessary to convert the COM object into the schedule acceptable object format. To do so add the following code example in your code behind. 
 
{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.Mvc;
using System.ComponentModel;
using System.Configuration;
using System.Data;
using System.Data.SqlClient;
using Microsoft.Office.Interop.Outlook; // required Microsoft DLL 
using System.Web.Script.Serialization;
using System.Web.UI;
using System.Web.UI.WebControls;
using ScheduleCRUDJS.Models;
using System.Collections;
namespace ScheduleCRUDJS.Controllers
{
    public class HomeController : Controller
    {
        ScheduleDataDataContext db = new ScheduleDataDataContext();

        public ActionResult Index()
        {
            return View();
        }

        [HttpPost]
        public JsonResult GetApp() // function to display the outlook appointments in Schedule initially
        {
            IEnumerable data = GetData(); 
            return Json(data, JsonRequestBehavior.AllowGet);
        }
        public List<MultipleResource> GetData() // function to return the outlook appointments
        {
            Microsoft.Office.Interop.Outlook.Application oApp = new Microsoft.Office.Interop.Outlook.Application();
            Microsoft.Office.Interop.Outlook.NameSpace mapiNamespace = oApp.GetNamespace("MAPI");
            Microsoft.Office.Interop.Outlook.MAPIFolder CalendarFolder = mapiNamespace.GetDefaultFolder(Microsoft.Office.Interop.Outlook.OlDefaultFolders.olFolderCalendar);
            Microsoft.Office.Interop.Outlook.Items outlookCalendarItems = CalendarFolder.Items;
            List<Microsoft.Office.Interop.Outlook.AppointmentItem> lst = new List<Microsoft.Office.Interop.Outlook.AppointmentItem>();

            foreach (Microsoft.Office.Interop.Outlook.AppointmentItem item in outlookCalendarItems)
            {
                lst.Add(item);
            }

            List<MultipleResource> newApp = new List<MultipleResource>();
            // converting COM object into IEnumerable object
            for (var i = 0; i < lst.Count; i++)
            {
                MultipleResource app = new MultipleResource();
                app.Id = i;
                app.Subject = lst[i].Subject;
                app.AllDay = lst[i].AllDayEvent;
                app.StartTime = Convert.ToDateTime(lst[i].Start.ToString());
                string endTime = lst[i].End.ToString();
                DateTime appEndDate = Convert.ToDateTime(endTime);
                if (endTime.Contains("12:00:00 AM") && app.AllDay == true)
                    app.EndTime = appEndDate.AddMinutes(-1);
                else
                    app.EndTime = appEndDate;
                app.Recurrence = false;
                app.RecurrenceRule = null;
                newApp.Add(app);
            }
            return newApp;
        }
        public JsonResult Batch(EditParams param)
        {
            if (param.action == "insert" || (param.action == "batch" && param.added != null))          // this block of code will execute while inserting the appointments
            {
                var value = param.action == "insert" ? param.value : param.added[0];
                int intMax = db.MultipleResources.ToList().Count > 0 ? db.MultipleResources.ToList().Max(p => p.Id) : 1;
                DateTime startTime = Convert.ToDateTime(value.StartTime);
                DateTime endTime = Convert.ToDateTime(value.EndTime);
                MultipleResource appoint = new MultipleResource()
                {
                    Id = intMax + 1,
                    StartTime = startTime,
                    EndTime = endTime,
                    StartTimeZone = value.StartTimeZone,
                    EndTimeZone = value.EndTimeZone,
                    Subject = value.Subject,
                    OwnerId = value.OwnerId,
                    AllDay = value.AllDay,
                    Recurrence = value.Recurrence,
                    RecurrenceRule = value.RecurrenceRule
                };
                db.MultipleResources.InsertOnSubmit(appoint);
                db.SubmitChanges();
                Microsoft.Office.Interop.Outlook.Application outlookApp = new Microsoft.Office.Interop.Outlook.Application();
                Microsoft.Office.Interop.Outlook.AppointmentItem newAppointment = null;
                newAppointment = (Microsoft.Office.Interop.Outlook.AppointmentItem)outlookApp.CreateItem(Microsoft.Office.Interop.Outlook.OlItemType.olAppointmentItem);
                newAppointment.Start = Convert.ToDateTime(value.StartTime).ToUniversalTime();
                newAppointment.End = Convert.ToDateTime(value.EndTime).ToUniversalTime();
                newAppointment.Subject = value.Subject.ToString();
                newAppointment.Save();
            }
            IEnumerable data = new ScheduleDataDataContext().MultipleResources.Take(200);
            return Json(data, JsonRequestBehavior.AllowGet);
        }
    }
}

{% endhighlight %}

N> In order to achieve the above scenario, need to refer the Microsoft assembly in your application (Microsoft Outlook 12/15 Object library [Microsoft.Office.Interop.Outlook] and refer it in the controller page as shown above).