---
layout: post
title: Timescale-Modes
description: timescale modes
platform: AngularJS
control: Gantt
documentation: ug
---

# Timescale customization

The Gantt contains built-in support to switch over various schedule modes. You can achieve this by defining a schedule header type for the Gantt.

## Schedule header types

The Gantt contains the following built-in schedule header types:

* Hour – Minute
* Day – Hour
* Week – Day
* Month – Week
* Year – Month

The following code example illustrates how to change the schedule mode:

### Week schedule mode

In the week schedule mode, the upper part of the schedule header displays the weeks, whereas the bottom half of the header displays the days. Refer to the following code example:

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

The following screenshot illustrates week schedule in the Gantt control:

![](Timescale-Modes_images/Timescale-Modes_img1.png)

### Month schedule mode

In the week schedule mode, the upper part of the schedule header displays the months, whereas the bottom header of the schedule displays its corresponding weeks. Refer to the following code example:

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

The following screenshot illustrates month schedule in the Gantt control:

![](Timescale-Modes_images/Timescale-Modes_img2.png)

### Year schedule mode

In the week schedule mode, the upper schedule header displays the years, whereas the bottom header displays its corresponding months. Refer to the following code example:

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

The following screenshot shows year schedule in the Gantt control:

![](Timescale-Modes_images/Timescale-Modes_img3.png)

### Day schedule mode

In the week schedule mode, the upper part of the header displays the days, whereas the bottom schedule header displays its corresponding hours. Refer to the following code example:

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

The following screenshot illustrates day schedule in the Gantt control:

![](Timescale-Modes_images/Timescale-Modes_img4.png)

### Hour schedule mode

An hour-minute schedule mode tracks the tasks in minutes scale. In this mode, the upper schedule header displays hour scale and the lower schedule header displays its corresponding minutes. The minute split-up in the lower schedule header can be defined by using the [minutesPerInterval](/api/js/ejgantt#members:scheduleheadersettings-minutesperinterval) enumeration property. The enumeration values of the [minutesPerInterval](/api/js/ejgantt#members:scheduleheadersettings-minutesperinterval) are:

* Auto 
* oneMinute
* fiveMinutes
* fifteenMinutes
* thirtyMinutes

The value `auto`, automatically calculates the interval depending upon the `e-schedulestartdate` and `e-scheduleenddate`, whereas the other enumeration values splits up accordingly.

The hour schedule mode supports both the `minute` and `hour` duration units.

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

## Week start day customization

In Gantt, you can customize week start day by using the `e-scheduleheadersettings.weekStartDay` property.
By default, the weekStartDay will be assigned with 0 which specifies the start day of the week.

In week schedule mode, week starts with Sunday by default. But, you can customize the week start day by using the following code example:

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
		weekStartDay : 3
        },
    angular.module('listCtrl', ['ejangular'])
        .controller('GanttCtrl', function($scope) {
            //...
            $scope.scheduleHeaderSettings = "scheduleHeaderSettings";
        });
</script>
</body>
{% endhighlight %}

## Rounding off timescale (schedule) start date

You can round off the schedule start date in the project by using the `e-scheduleheadersettings.timescaleStartDateMode` property. You can set the following values to the property:

* auto
* month
* week
* year

The value `auto`, automatically calculates the schedule header depending on the data source values, whereas the other enumeration values rounds off the schedule header accordingly. For instance, in year schedule, if you set "e-timescalestartdatemode" as `month` then the schedule header will start from the immediate month of the schedule instead of starting from beginning of the year.

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

## Customize automatic timescale update action

In Gantt, schedule timeline will be automatically updated when the tasks are edited beyond the schedule start date and end date range. This can be enabled/disabled by using [`scheduleHeaderSettings.updateTimescaleView`](/api/angular/ejgantt#members:scheduleheadersettings-updatetimescaleview "scheduleHeaderSettings.updateTimescaleView") property.
The following code snippets shows how to prevent the automatic timescale update in Gantt.

{% highlight javascript %}

	<body ng-controller="GanttCtrl">
    <!--Add  Gantt control here-->    
    <div id="GanttContainer" ej-gantt
		//...
        e-scheduleheadersettings="scheduleHeaderSettings">
    </div>
    <script>
    var  scheduleHeaderSettings= {
        scheduleHeaderType: ej.Gantt.ScheduleHeaderType.Week,
		updateTimescaleView : false
    },
    angular.module('listCtrl', ['ejangular'])
    .controller('GanttCtrl', function($scope) {
        //...
        $scope.scheduleHeaderSettings = scheduleHeaderSettings;
    });
</script>
</body>
{% endhighlight %}

The following screenshot illustrates the behavior of `updateTimescaleView` property.

![](Timescale-Modes_images/Timescale-Modes_img7.png)
At Initial load
{:.caption}

![](Timescale-Modes_images/Timescale-Modes_img8.png)
`updateTimescaleView` property as `false`
{:.caption}

![](Timescale-Modes_images/Timescale-Modes_img9.png)
`updateTimescaleView` property as `true`
{:.caption}