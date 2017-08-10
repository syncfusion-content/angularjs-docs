---
layout: post
title: Timescale-Modes
description: timescale modes
platform: AngularJS
control: Gantt
documentation: ug
---

# Timescale customization

Gantt contains built-in support to switch over various schedule modes. You can achieve this by defining a schedule header type for the Gantt.

## Schedule Header Types

Gantt contains the following built-in schedule header types

* Hour – Minute
* Day – Hour
* Week – Day
* Month – Week
* Year – Month

The following code example illustrates you on how to change the schedule mode.

### Week schedule mode

In the Week schedule mode, the upper part of the schedule header displays the weeks, whereas the bottom half of the header displays the days. Refer the following code example.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-scheduleheadersettings="scheduleHeaderSettings" 
      >
   </div>
  <script>
    var  scheduleHeaderSettings= {
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Week,
        weekHeaderFormat: "MMM dd , yyyy",
        dayHeaderFormat: "ddd",
    },
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.scheduleHeaderSettings = "scheduleHeaderSettings";
        });
</script>
</body>

{% endhighlight %}

The following screenshot illustrates the Week Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img1.png)

### Month schedule mode

In the Week schedule mode, the upper part of the schedule header displays the Months whereas the bottom header of the schedule displays its corresponding Weeks. Refer the following code example.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-scheduleheadersettings="scheduleHeaderSettings" 
      >
   </div>
  <script>
    var  scheduleHeaderSettings= {
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Month,
        monthHeaderFormat: "MMM yyyy",
        weekHeaderFormat: "M/dd",
    },
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.scheduleHeaderSettings = "scheduleHeaderSettings";
        });
</script>
</body>

{% endhighlight %}

The following screenshot illustrates the Month Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img2.png)

### Year schedule mode

In the Week schedule mode, the upper schedule header displays the Years, whereas the bottom header displays its corresponding Months. Refer the following code example.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-scheduleheadersettings="scheduleHeaderSettings" 
      >
   </div>
  <script>
    var  scheduleHeaderSettings= {
         scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Year,
         yearHeaderFormat: "yyyy",
         monthHeaderFormat: "MMM",
    },
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.scheduleHeaderSettings = "scheduleHeaderSettings";
        });
</script>
</body>
{% endhighlight %}

The following screen shot shows the Year Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img3.png)

### Day schedule mode

In the Week schedule mode, the upper part of the header displays the Days, whereas the bottom schedule header displays its corresponding Hours. Refer the following code example.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-scheduleheadersettings="scheduleHeaderSettings" 
      >
   </div>
  <script>
    var  scheduleHeaderSettings= {
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Day,
        dayHeaderFormat: " dd,MM,yy ",
        hourHeaderFormat: "HH",
    },
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.scheduleHeaderSettings = "scheduleHeaderSettings";
        });
</script>
</body>

{% endhighlight %}

The following screenshot illustrates the Day Schedule in Gantt control.

![](Timescale-Modes_images/Timescale-Modes_img4.png)

### Hour schedule mode

An Hour-Minute Schedule Mode tracks the tasks in minutes scale. In this mode, upper schedule header displays hour scale and the lower schedule header displays its corresponding Minutes. The minute split-up in the lower schedule header can be defined by using the [minutesPerInterval](/api/js/ejgantt#members:scheduleheadersettings-minutesperinterval) enumeration property. The enumeration values of the [minutesPerInterval](/api/js/ejgantt#members:scheduleheadersettings-minutesperinterval) are,

* Auto 
* oneMinute
* fiveMinutes
* fifteenMinutes
* thirtyMinutes

The value `auto`, automatically calculates the interval depending upon the `e-schedulestartdate` and `e-scheduleenddate`, whereas the other enumeration values splits up accordingly.

The Hour Schedule Mode supports both the `minute` and `hour` duration units.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
       e-dateformat= "M/d/yyyy hh:mm:ss tt"
       e-durationunit= ej.Gantt.DurationUnit.Minute,
       e-scheduleheadersettings="scheduleHeaderSettings" 
      >
   </div>
  <script>
    var  scheduleHeaderSettings= {
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Day,
        dayHeaderFormat: " dd,MM,yy ",
        hourHeaderFormat: "HH",
    },
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.scheduleHeaderSettings = "scheduleHeaderSettings";
        });
</script>
</body>
{% endhighlight %}

![](Timescale-Modes_images/Timescale-Modes_img5.png)

## Rounding off timescale (schedule) start date

You can able to round off the schedule start date in a project by using the "e-timescalestartdatemode" property. It is possible to set the following values to the property,

* auto
* month
* week
* year

The value `auto`, automatically calculates the schedule header depending on the datasource values, whereas the other enumeration values rounds off the schedule header accordingly. For Instance, in year schedule if you set "e-timescalestartdatemode" as `month` then the schedule header will start from the immediate month of the schedule instead of starting from beginning of the year.

{% highlight javascript %}

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
      //...
      e-scheduleheadersettings="scheduleHeaderSettings" 
      >
   </div>
  <script>
    var scheduleHeaderSettings= {
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Year,
        timescaleStartDateMode: ej.Gantt.TimescaleRoundMode.Month,
    },
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.scheduleHeaderSettings = "scheduleHeaderSettings";
        });
</script>
</body>

{% endhighlight %}

![](Timescale-Modes_images/Timescale-Modes_img6.png)
