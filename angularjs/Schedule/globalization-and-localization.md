---
title: Globalization and Localization
description: Globalizing and localizing Scheduler
platform: Angular-1
control: schedule
documentation: ug
keywords: globalize, localize, localization, globalization 
---
# Globalization and Localization

## Globalization

The Scheduler control is built with default **globalization** support as it format the dates according to the user’s locale automatically and processes it internally without any need for manual conversions. This kind of default handling of Scheduler dates is achieved through the built-in **ej.globalize** library which globalize the date, day and month names accordingly. 

## Localization

Scheduler also comes with default localization support which allows it to customize the display of text within the Scheduler in a user-specific culture and locale. The Schedule control can be localized in specific culture using the common API [locale](/api/js/ejschedule#members:locale) along with the collection of localized words defined for that culture using the ej.Schedule.Locale [**culture-code**].

N> By default, the Schedule control is localized in **en-US** culture.

To localize Scheduler into any particular culture, it is necessary to refer the culture-specific script files in your application after the reference of **ej.web.all.min.js** file, which are available under the following location.                   

_<**Installed location**>\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n_

The following code example shows how to localize the Schedule control in **fr-FR** culture.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentdate="setDate" e-locale="fr-FR" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">  
            ej.Schedule.Locale["fr-FR"] = {
                ReminderWindowTitle: "fenêtre Rappel",
                CreateAppointmentTitle: "Créer un rendez",
                RecurrenceEditTitle: "Modifier Répéter rendez-vous",
                RecurrenceEditMessage: "Comment voulez-vous changer le rendez-vous dans la série?",
                RecurrenceEditOnly: "Seulement cette nomination",
                RecurrenceEditSeries: "La série entière",
                PreviousAppointment: "Nomination précédente",
                NextAppointment: "Prochain rendez-vous",
                AppointmentSubject: "Assujettir",
                StartTime: "Heure de départ",
                EndTime: "Heure de fin",
                AllDay: "Toute la journée",
                StartTimeZone: "Démarrez TimeZone",
                EndTimeZone: "End Time Zone",
                Today: "Aujourd'hui",
                Recurrence: "Répéter",
                Done: "Terminé",
                Cancel: "Annuler",
                Ok: "D'accord",
                Repeat: "Répéter",
                RepeatBy: "Répéter par",
                RepeatEvery: "Répéter chaque",
                RepeatOn: "Répéter l'opération sur",
                StartsOn: "Démarre sur",
                Ends: "Prend fin",
                Summary: "Résumé",
                Daily: "Tous les jours",
                Weekly: "Hebdomadaire",
                Monthly: "Mensuel",
                Yearly: "Annuel",
                Every: "Chaque",
                EveryWeekDay: "Tous les jours de la semaine",
                Never: "Jamais",
                After: "Après",
                Occurrence: "Occurrences",
                On: "Sur",
                Edit: "modifier",
                RecurrenceDay: "Journées",
                RecurrenceWeek: "Semaines",
                RecurrenceMonth: "Mois",
                RecurrenceYear: "Années",
                The: "le",
                OfEvery: "de toute",
                First: "Premier",
                Second: "Seconde",
                Third: "Troisième",
                Fourth: "Quatrième",
                Last: "Dernier",
                WeekDay: "Jour de la semaine",
                WeekEndDay: "Jour de weekend",
                Subject: "Assujettir",
                Categorize: "Catégories",
                DueIn: "Dû en",
                DismissAll: "Rejeter la totalité",
                Dismiss: "Rejeter",
                OpenItem: "Élément ouvert",
                Snooze: "Roupillon",
                Day: "journées",
                Week: "Semaine",
                WorkWeek: "Semaine de travail",
                Month: "Mois",
                AddEvent: "Ajouter un évènement",
                CustomView: "Vue personnalisée",
                Agenda: "Ordre du jour",
                Detailed: "Modifier Rendez-vous",
                EventBeginsin: "Nomination commence dans",
                Editevent: "Modifier Rendez-vous",
                Editseries: "Modifier la série",
                Times: "fois",
                Until: "jusqu'à",
                Eventwas: "Rendez-vous était",
                Hours: "hrs",
                Minutes: "mins",
                Overdue: "Nomination Overdue",
                Days: "journées)",
                Event: "un événement",
                Select: "sélectionner",
                Previous: "précédent",
                Next: "Prochain",
                Close: "Fermer",
                Delete: "Effacer",
                Date: "date",
                Showin: "Montre",
                Gotodate: "Aller à la date",
                Resources: "RESSOURCES",
                RecurrenceDeleteTitle: "Supprimer Répéter rendez-vous",
                Location: "Emplacement",
                Priority: "Priorité",
                RecurrenceAlert: "Alerte",
                NoTitle: "Pas de titre",
                OverFlowAppCount: "plus de nominations",
                AppointmentIndicator: "Cliquez pour plus de rendez-vous",
                WrongPattern: "Le modèle de récurrence est pas valide",
                CreateError: "La durée de la nomination doit être plus courte que la fréquence elle se produit. Raccourcir la durée, ou modifier le modèle de récurrence dans la boîte de dialogue Récurrence de rendez.",
                DragResizeError: "Vous ne pouvez pas reporter une occurrence du rendez-vous périodique si elle saute sur une occurrence ultérieure du même rendez-vous.",
                StartEndError: "L'heure de fin doit être supérieure à l'heure de début",
                MouseOverDeleteTitle: "Supprimer Nomination",
                DeleteConfirmation: "Êtes-vous sûr de vouloir supprimer ce rendez-vous?",
                Time: "Temps",
                EmptyResultText: "Pas de suggestions",
                BlockIntervalAlertTitle: "Alerte",
                BlockIntervalError: "L'intervalle de temps choisi a été bloqué et est indisponible pour la sélection."
            };
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 100,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30),
                Location: "CHINA"
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

N> Refer the **ej.culture.fr-FR.min.js** file in your HTML application and also define the **locale** property for the Schedule control with the appropriate **culture-code** [**fr-FR**].

For further information on – how to refer the required culture scripts into your application, refer [here](/angular-1/localization).

### Localizing Specific Words

To customize or localize only some specific words in the default `ej.Schedule.Locale["en-US"]` collection, the words to be localized/customized can be defined in a separate variable and then extended to the original collection as depicted in the following code example.

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
        var customizationMessage = {
            // customize the appointment window title
            CreateAppointmentTitle: "Create Event",
            // customize the view options text in the Schedule header
            Day: "1 Day",
            Week: "7 Days",
            WorkWeek: "5 Days",
            Month: "Month"
        };
        // Extend only the required changes to the original locale collection
        $.extend(ej.Schedule.Locale["en-US"], customizationMessage);
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

## Time Zone

The Scheduler makes use of the System time zone by default. If it needs to follow some other user-specific time zone, then the API `e-timezone` can be used. Also, the Scheduler can be set to observe the Daylight Saving Time (DST) with its **e-isdst** property which is set to **false** by default. 

When `e-isdst` property is set to **true**, the Scheduler internally processes the time difference values (for the Start and end time of the appointments) related to the Scheduler time zone that observes daylight savings time. 

The following code example shows the way to set the specific time zone value with the daylight savings time observed in the Scheduler.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-timezone="UTC +05:30" e-isdst="true" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
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

### Setting different TimeZone for Scheduler Appointments

Apart from the default action of applying specific timezone to the entire Scheduler, it is also possible to set different time zone values for each appointments through the properties **startTimeZone** and **endTimeZone** which can be defined as separate fields within the appointment dataSource. When these properties are not explicitly defined for appointments, the appointments Start and End time will be processed based on the Scheduler time zone.

N> The **e-isdst** property closely relies on the appointment fields like `e-appointmentsettings-starttimezone` and `e-appointmentsettings-endtimezone`, for appropriate time difference calculations. If these two fields are not defined for appointments, then **e-isdst** depends on the System **timeZone** value.

The following code snippet shows how to define isDST and the time zones for specific appointments.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-isdst="true" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.dataSource = [{
                Id: 100,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30),
                StartTimeZone: "UTC +02:00",
                EndTimeZone: "UTC +02:00"
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

### Customizing the TimeZone Collection

It is also possible to define or customize the default time zone collection of the Scheduler, by using the `e-timezonecollection` API as follows.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-timezonecollection-datasource="timeZoneDataSource" e-timezonecollection-text="text" e-timezonecollection-id="id" e-timezonecollection-value="value" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.timeZoneDataSource = [{
                text: "UTC -04:00",
                id: "10",
                value: "UTC -04:00"
            }, {
                text: "UTC -03:30",
                id: "11",
                value: "UTC -03:30"
            }, {
                text: "UTC -03:00",
                id: "12",
                value: "UTC -03:00"
            }, {
                text: "UTC -02:00",
                id: "13",
                value: "UTC -02:00"
            }, {
                text: "UTC -01:00",
                id: "14",
                value: "UTC -01:00"
            }, {
                text: "UTC +00:00",
                id: "15",
                value: "UTC +00:00"
            }, {
                text: "UTC +01:00",
                id: "16",
                value: "UTC +01:00"
            }, {
                text: "UTC +02:00",
                id: "17",
                value: "UTC +02:00"
            }, {
                text: "UTC +03:00",
                id: "18",
                value: "UTC +03:00"
            }, {
                text: "UTC +03:30",
                id: "19",
                value: "UTC +03:30"
            }, {
                text: "UTC +04:00",
                id: "20",
                value: "UTC +04:00"
            }, {
                text: "UTC +04:30",
                id: "21",
                value: "UTC +04:30"
            }, {
                text: "UTC +05:00",
                id: "22",
                value: "UTC +05:00"
            }];
            $scope.dataSource = [{
                Id: 100,
                Subject: "Wild Discovery",
                StartTime: new Date(2017, 1, 7, 9, 00),
                EndTime: new Date(2017, 1, 7, 10, 30),
                StartTimeZone: "UTC +02:00",
                EndTimeZone: "UTC +02:00"
            }];
            $scope.setDate = new Date(2017, 1, 7);
        });
    </script>
</body>
</html>

{% endhighlight %}

N> The values defined within the **e-timezonecollection-datasource** are usually the only options displayed within the start and end time zone dropdown fields of the appointment window.

## Time Mode

The time mode of the Scheduler can be either **12** or **24 hours** format which is based on the `e-locale` set to the Scheduler. Since the default locale value of the Scheduler is **en-US**, therefore the time mode will be set to **12 hours** format (by default) automatically based on the culture. 

The user can also set specific time mode for the Scheduler using `e-timemode` property which accepts either **String** or **enum** value. It accepts the following **enum** values,

* ej.Schedule.TimeMode.Hour12
* ej.Schedule.TimeMode.Hour24

The following code snippet shows the way to set specific **24 hour format** time mode for the Scheduler.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-timemode="timeMode" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            $scope.timeMode = ej.Schedule.TimeMode.Hour24;
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

N> If the **e-timemode** property is not set with specific value, then the value will be taken based on the locale assigned for the Scheduler.

## Date Format

Scheduler can be used with all valid date formats. The default date format used in Scheduler is “MM/dd/yyyy”. 

If the `e-dateformat` property is not specified particularly, then it will be taken based on the locale that is assigned to the Scheduler. The default locale applied on the Scheduler is “en-US”, which makes it to follow the “MM/dd/yyyy” pattern by default.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-dateformat="yyyy/MM/dd" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
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

## First Day of Week

The `e-firstdayofweek` property allows to set any of the week days as start of the week/workweek/month view in Scheduler. It accepts either the `integer` (Sunday=0, Monday=1, Tuesday=2, etc) or `string` (“Sunday”, “Monday”, etc) or `ej.Schedule.DayOfWeek` enum type value. The default value of this `e-firstdayofweek` depends on the current culture (language) assigned to the Scheduler.

To set different first day of week in Scheduler,

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="ScheduleApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="ScheduleCtrl">
        <ej-schedule id="Schedule1" e-width="100%" e-height="525px" e-currentview="currentView" e-firstdayofweek="dayOfWeek" e-currentdate="setDate" e-appointmentsettings-datasource="dataSource">
        </ej-schedule>
    </div>
    <script type="text/javascript">
        angular.module('ScheduleApp', ['ejangular']).controller('ScheduleCtrl', function ($scope) {
            // Set the Active view
            $scope.currentView = ej.Schedule.CurrentView.Week;
            // Configure the week start day(First day of week)
            $scope.dayOfWeek = ej.Schedule.DayOfWeek.Tuesday;
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

N> The sub-control datepicker which is used within Scheduler for start/end time fields in appointment window and for date navigation purposes will also follow the same first day of week. 
