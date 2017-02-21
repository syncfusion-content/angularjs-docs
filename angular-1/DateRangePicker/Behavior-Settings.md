---
layout: post
title: Behavior Settings 
description: Behavior Settings
platform: Angular-1
control: DataRangePicker
documentation: ug
---
# Introduction
**DateRangePicker** is integrated in Angular JS using Syncfusion widgets , which allows to use **daterangepicker** features such as One-way binding , Two-way binding , Form validation. Please refer the getting started page for general information regarding integrating Syncfusion widget’s.

# Behavior Settings

Behavior Settings in **DateRangePicker** refers to the default behavior of the **daterangepicker** component. It help us to perform more built in operations of the **daterangepicker** component like selecting range value of the **daterangepicker**, presetting the ranges as required, enabling timepicker along with date range picker 

## Select Date Range

### Value

**DateRangePicker** value can be selected by picking two date values from available two **DatePicker** calendars or you can bind it by using e-value property.

The value property can be bound to the **DateRangePicker** as used in the snippet below.

(Note: Value property of DateRangePicker is Two-Way Bindable.)

{% highlight html %}

<div ng-controller="dateRangeCtrl" >
     <input type="text" id="daterange" ej-daterangepicker e-value="value" e-width="300px" />
</div>

{% endhighlight %}

{% highlight javascript %}

<script>
     angular.module('syncApp', ['ejangular'])
        .controller('dateRangeCtrl', function ($scope) {
            $scope.value = "5/28/2016 - 5/28/2018";
              });
</script>

{% endhighlight %}

Run the above code to get the below output.

![](behavior-settings/value.png)

### StartDate and EndDate

Start Date and End Date properties allows to set the starting and ending date of DateRangePicker. Start Date and End Date of the date range can be pick from DatePicker calendars or we can use the e-StartDate and e-endDate properties to bind their values.

Start Date and End Date of range, can be bound by using e-startDate and e-endDate as used in the snippet below:

{% highlight html %}

<div ng-controller="dateRangeCtrl" >
   <input type="text" id="daterange" ej-daterangepicker e-startDate="startDate" e-endDate="endDate" e-width="300px" />    
</div>

{% endhighlight %}

{% highlight javascript %}

<script>
    angular.module('syncApp', ['ejangular'])
       .controller('dateRangeCtrl', function ($scope) {
           $scope.startDate = new Date("1/1/2017");
           $scope.endDate = new Date("1/31/2017");
           });
</script>

{% endhighlight %}

Run the above code to get the below output.

![](behavior-settings/start and end date.png) 

### Preset Ranges

We can make use of preset range for easy selection of a date range in the popup that is predefined in the code. The ranges are bounded with the e-ranges property, this will be processed and corresponding label will be added to popup in right side with given label name as given in the below snippet.

{% highlight html %}

<div ng-controller="dateRangeCtrl" >
        <input type="text" id="daterange" ej-daterangepicker e-ranges="ranges" e-width="300px" />
</div>

{% endhighlight %}

{% highlight javascript %}

<script >
     angular.module('syncApp', ['ejangular'])
     .controller('dateRangeCtrl', function ($scope) {
     $scope.ranges = [
                     { label: "Today", range: [new Date(), new Date()] },
                     { label: "Last 1 Week", range: [new Date(new Date().setDate(new Date().getDate() - 7)), new Date()] },
                     { label: "Last 1 Month", range: [new Date(new Date().setMonth(new Date().getMonth() - 1)), new Date()] },
                     { label: "Last 2 Month", range: [new Date(new Date().setMonth(new Date().getMonth() - 2)), new Date()] },
               ];
          });
</script>
    
{% endhighlight %}

Run the above code to get the below output.

![](behavior-settings/ranges.png) 

### Enable TimePicker 

Daterangepicker comes inbuilt with Timepicker control that lets you select the time range along with date range. Both start date and end date, have separate Time Pickers. Enabling the time picker can be bounded with the enableTimePicker property as shown in the below snippet.

{% highlight html %}

<div ng-controller="dateRangeCtrl" >
        <input type="text" id="daterange" ej-daterangepicker e-enableTimePicker="enable" e-width="300px" />
</div>

{% endhighlight %}

{% highlight javascript %}

<script>
        angular.module('syncApp', ['ejangular'])
           .controller('dateRangeCtrl', function ($scope) {
               $scope.enable = "true";
           });
</script>

{% endhighlight %}
 
Run the above code to get the below output.

![](behavior-settings/enable time.png) 
