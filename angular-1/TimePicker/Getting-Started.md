---
layout: post
title: Getting-Started
description: getting started
platform: angularjs
control: TimePicker
documentation: ug
---

# Getting Started

This section explains briefly about how to create a **TimePicker** in your application with **AngularJS.** The **Essential JavaScript** **TimePicker** provides support to display a **TimePicker** in your web page and allows you to pick a time from the given **TimePicker**. Here, you can learn how to customize two dates and **TimePickers** in a real-time hotel table booking application. 

The following screenshot illustrates the functionality of a **TimePicker** with a time range of morning to evening. You can select a time to book a table, from a period of 9.00 AM to 6.00 PM for the current day. This avoids selecting a time prior to the morning.

![](/js/TimePicker/Getting-Started_images/Getting-Started_img1.png) 


## Create a TimePicker 

**Essential JavaScript TimePicker** widget renders built-in features such as keyboard navigation, other time navigation with animations and flexible APIs. You can easily create the **TimePicker** widget by using simple input textbox element as follows.

Create an **HTML** file and add the following template to the **HTML** file.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" ng-app="TimeCtrl">
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8" />
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="TimePickerCtrl">
    <!-- add time picker element here -->
</body>
</html>

{% endhighlight %}

N> jQuery.easing external dependency has been removed from version 14.3.0.49 onwards. Kindly include this jQuery.easing dependency for versions lesser than 14.3.0.49 in order to support animation effects.

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Properties can be bind to ejTimePicker control using the prefix e- and particular property name as shown as below

Add input element to render a **TimePicker**.

{% highlight html %}

<table>
    <tr>
        <td class="tdclass">Select date</td>
        <td class="tdclass">Select time</td>
        <td class="tdclass">Select party size</td>
    </tr>
    <tr>
        <td class="tdclass">
            <span class="innerdp">
                <input id="datepick" type="text" ej-DatePicker/>
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <input id="time" type="text" ej-TimePicker  />
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <select name="party_size">
                    <option name="party_size" value="default">select people</option>
                    <option name="party_size" value="5">5 people</option>
                    <option name="party_size" value="10">10 people</option>
                    <option name="party_size" value="15">15 people</option>
                    <option name="party_size" value="20">20 people</option>
                </select>
            </span>
        </td>
    </tr>
    <tr>
        <td class="tdclass">
            <button class="book">Book</button>
        </td>
    </tr>
</table>

{% endhighlight %}


Add the below code in angular module of script section.

{% highlight javascript %}

   <script type="text/javascript">
        angular.module('TimeCtrl', ['ejangular'])
               .controller('TimePickerCtrl', function ($scope) {
               });
    </script>

{% endhighlight %}



Add the following styles to show **Time Picker** control.



{% highlight css %}

<style type="text/css" class="cssStyles">
    .tdclass {
        width: 200px;
        font-weight: bold;
    }

    .innerdp {
        display: inline-block;
    }
</style>

{% endhighlight %}


The following screenshot displays a **TimePicker** control.

![](/js/TimePicker/Getting-Started_images/Getting-Started_img2.png) 


## Set the Min and Max Values

In a real-time hotel table booking scenario, the booking is open only for a limited time and limited number of days. You have to select a time and date from the given range. This is achieved by using the properties **minTime** and **maxTime**, **minDate** and **maxDate**. By this way, only times ranging between **minTime** and **maxTime**, **minDate** and **maxDate** are enabled in the **TimePicker**.

{% highlight html %}

<table>
    <tr>
        <td class="tdclass">Select date</td>
        <td class="tdclass">Select time</td>
        <td class="tdclass">Select party size</td>
    </tr>
    <tr>
        <td class="tdclass">
            <span class="innerdp">
                <input id="datepick" type="text" ej-DatePicker e-value="value" e-minDate="mindate" e-maxDate="maxdate" />
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <input id="time" type="text" ej-TimePicker e-minTime="mintime" e-maxTime="maxtime" />
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <select name="party_size">
                    <option name="party_size" value="default">select people</option>
                    <option name="party_size" value="5">5 people</option>
                    <option name="party_size" value="10">10 people</option>
                    <option name="party_size" value="15">15 people</option>
                    <option name="party_size" value="20">20 people</option>
                </select>
            </span>
        </td>
    </tr>
</table>

{% endhighlight %}


{% highlight javascript %}

   <script type="text/javascript">
        var curdate = new Date();// mentions the current date.
        var mintime = "9:00 AM"; // mentions the start time.
        var maxtime = "6:00 PM"; // mentions the start time.
        // the following code sets the date range to 30 days from the current date.
        var rangeDate = new Date(curdate.getFullYear(), curdate.getMonth(), curdate.getDate() + 30);
        angular.module('TimeCtrl', ['ejangular'])
            .controller('TimePickerCtrl', function ($scope) {
                $scope.value= curdate;
                $scope.mindate= curdate;
                $scope.maxdate= rangeDate;
                $scope.mintime= mintime;
                $scope.maxtime= maxtime;
        });
    </script>

{% endhighlight %}

The above code example displays the following output.

![](/js/TimePicker/Getting-Started_images/Getting-Started_img3.png) 


## Set Time Interval

You can select the **Time** in **TimePicker** with the interval of one hour. You need to set the property **interval** as 60.

The following code example shows how to set **Time interval**.

{% highlight html %}

<table>
    <tr>
        <td class="tdclass">Select date</td>
        <td class="tdclass">Select time</td>
        <td class="tdclass">Select party size</td>
    </tr>
    <tr>
        <td class="tdclass">
            <span class="innerdp">
                <input id="datepick" type="text" ej-DatePicker e-value="value" e-minDate="mindate" e-maxDate="maxdate" />
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <input id="time" type="text" ej-TimePicker e-minTime="mintime" e-maxTime="maxtime" e-interval="interval" e-value="timevalue"/>
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <select name="party_size">
                    <option name="party_size" value="default">select people</option>
                    <option name="party_size" value="5">5 people</option>
                    <option name="party_size" value="10">10 people</option>
                    <option name="party_size" value="15">15 people</option>
                    <option name="party_size" value="20">20 people</option>
                </select>
            </span>
        </td>
    </tr>
</table>

{% endhighlight %}


{% highlight javascript %}

<script type="text/javascript">
    var curdate = new Date();// mentions the current date.
    var mintime = "9:00 AM"; // mentions the start time.
    var curtime = "9:00 AM";// mentions the time value.
    var maxtime = "6:00 PM"; // mentions the start time.
    // the following code sets the date range to 30 days from the current date.
    var rangeDate = new Date(curdate.getFullYear(), curdate.getMonth(), curdate.getDate() + 30);
	angular.module('TimeCtrl', ['ejangular'])
		.controller('TimePickerCtrl', function ($scope) {
			$scope.value= curdate;
			$scope.mindate= curdate;
			$scope.maxdate= rangeDate;
            $scope.timevalue = curtime;
			$scope.mintime= mintime;
			$scope.maxtime= maxtime;
			$scope.interval = 60; // Specify time interval
	});
</script>

{% endhighlight %}

Execute the above code to achieve the desired result. You can select the date and time in **TimePicker** within the given range of one hour interval. This scenario is illustrated in the following screenshot.

![](/js/TimePicker/Getting-Started_images/Getting-Started_img4.png)


## Display the Acknowledgment Message

The **acknowledgment message** is displayed when you click the **Book** button.

The following code example shows how to display the **acknowledgment message**.

{% highlight html %}
<table>
    <tr>
        <td class="tdclass">Select date</td>
        <td class="tdclass">Select time</td>
        <td class="tdclass">Select party size</td>
    </tr>
    <tr>
        <td class="tdclass">
            <span class="innerdp">
                <input id="datepick" type="text" ej-DatePicker e-value="value" e-minDate="mindate" e-maxDate="maxdate" />
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <input id="time" type="text" ej-TimePicker e-minTime="mintime" e-maxTime="maxtime" e-interval="interval" e-value="timevalue"/>
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <select name="party_size">
                    <option name="party_size" value="default">select people</option>
                    <option name="party_size" value="5">5 people</option>
                    <option name="party_size" value="10">10 people</option>
                    <option name="party_size" value="15">15 people</option>
                    <option name="party_size" value="20">20 people</option>
                </select>
            </span>
        </td>
		<tr>
        <td class="tdclass">
            <button class="book" ej-button e-text="Book" e-click="onClick"></button>
        </td>
    </tr>
    </tr>
</table>
{% endhighlight %}

{% highlight javascript %}

<script type="text/javascript">
    var curdate = new Date();// mentions the current date.
    var mintime = "9:00 AM"; // mentions the start time.
    var curtime = "9:00 AM";// mentions the time value.
    var maxtime = "6:00 PM"; // mentions the start time.
    // the following code sets the date range to 30 days from the current date.
    var rangeDate = new Date(curdate.getFullYear(), curdate.getMonth(), curdate.getDate() + 30);
	angular.module('TimeCtrl', ['ejangular'])
		.controller('TimePickerCtrl', function ($scope) {
			$scope.value= curdate;
			$scope.mindate= curdate;
			$scope.maxdate= rangeDate;
            $scope.timevalue = curtime;
			$scope.mintime= mintime;
			$scope.maxtime= maxtime;
			$scope.interval = 60; // Specify time interval
            $scope.onClick = function(e) {
                var a = $scope.value;
                var b = $scope.timevalue;
                var c = $('select').val();
                alert("You are booked the table with date " + a + " time " + b + " Party_size is " + c);
            }
	});
</script>

{% endhighlight %}

The following screenshot displays the **acknowledgment message**.

![](/js/TimePicker/Getting-Started_images/Getting-Started_img5.png) 



## Create Two TimePickers

You can select the **Start time** in the first **TimePicker** and then the **End time** in the second **TimePicker**. The validation process is done after the selection of **Start time** and the changes are reflected in the **End time** selection **TimePicker**. You can manipulate this process in the **Select** event of **Start Time** selection **TimePicker**. 

Add input element to render **Two TimePickers**.



{% highlight html %}

<table>
    <tr>
        <td class="tdclass">Select date</td>
        <td class="tdclass">Select start time</td>
        <td class="tdclass">Select end time</td>
        <td class="tdclass">Select party size</td>
    </tr>
    <tr>
        <td class="tdclass">
            <span class="innerdp">
                <input id="datepick" type="text" ej-DatePicker e-value="value" e-minDate="mindate" e-maxDate="maxdate" />
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <input id="time" type="text" ej-TimePicker e-minTime="mintime" e-maxTime="maxtime" e-interval="interval" e-select="selectTime"/>
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <input id="timeend" type="text" ej-TimePicker e-minTime="mintime1" e-maxTime="maxtime" e-interval="interval"/>
            </span>
        </td>
        <td class="tdclass">
            <span class="innerdp">
                <select name="party_size">
                    <option name="party_size" value="default">select people</option>
                    <option name="party_size" value="5">5 people</option>
                    <option name="party_size" value="10">10 people</option>
                    <option name="party_size" value="15">15 people</option>
                    <option name="party_size" value="20">20 people</option>
                </select>
            </span>
        </td>
    </tr>
    <tr>
    <td class="tdclass">
        <button class="book" ej-button e-text="Book" e-click="onClick"></button>
    </td>
    </tr>
<table>



{% endhighlight %}


Add the below codes in script section.

{% highlight javascript %}

<script type="text/javascript">
    var curdate = new Date();// mentions the current date.
    var mintime = "9:00 AM"; // mentions the start time.
    var maxtime = "6:00 PM"; // mentions the start time.
    var minTime1 = "9:00 AM"
    // the following code sets the date range to 30 days from the current date.
    var rangeDate = new Date(curdate.getFullYear(), curdate.getMonth(), curdate.getDate() + 30);
	angular.module('TimeCtrl', ['ejangular'])
		.controller('TimePickerCtrl', function ($scope) {
			$scope.value= curdate;
            $scope.mintime1 = minTime1;
			$scope.mindate= curdate;
			$scope.maxdate= rangeDate;
			$scope.mintime= mintime;
			$scope.maxtime= maxtime;
			$scope.interval= 60;
			$scope.selectTime= function selectedStartTime(sender) {
                $scope.mintime1 = sender.value;// setting minTime property dynamically.
            }
            $scope.onClick = function(e) {
                var a = $scope.value;
                var b = $scope.timevalue;
                var c = $('select').val();
                alert("You are booked the table with date " + a + " time " + b + " Party_size is " + c);
            }
	});	
</script>

{% endhighlight %}

Execute the above code to achieve the desired result. By selecting the **Start Time** in the first **TimePicker**, you can select the End Time within the given range. This restricts you from selecting false time. This scenario is illustrated in the following screenshot.

![](/js/TimePicker/Getting-Started_images/Getting-Started_img6.png) 

You can also add additional functionalities such as localization and time formats to the **TimePicker**. 

