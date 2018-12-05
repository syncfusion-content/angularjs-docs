---
layout: post
title: Behaviour settings | DateTimePicker | AngularJS | Syncfusion
description: Behaviour settings for DateTimePicker
platform: AngularJS
control: DateTimePicker
documentation: ug
---

# Behavior Settings

In AngularJS, **DateTimePicker** Component has some default settings which helps you to perform more operation by built-in.

**HTML View Section**

{% highlight html %}

        <div class="control">
               <input type="text" id="dateTime1" ej-datetimepicker e-value="value"/>
          </div>

{% endhighlight %}

 **Controller Section**

{% highlight JS %}

    <script>
    angular.module('DateTimeCtrl', ['ejangular'])
            .controller('DateTimeController', function ($scope) {
                $scope.value =new Date();
                });
    </script>

{% endhighlight %}

## MinDateTime and MaxDateTime

**e-minDateTime** and **e-MaxDateTime** API’s of **DateTimePicker** component is used to set the maximum date value and minimum date value. 

In a real-time appointment scenario, the appointment is open only for a limited number of days. You should select a date and time within the given range. This can be achieved by using the properties **e-minDateTime** and **e-maxDateTime** that enables the specified date range in the **DateTimePicker**  control.

**HTML View Section**

{% highlight html %}

      <input type="text" id="dateTime1" ej-datetimepicker e-value="value" e-mindatetime="minDateTime" e-maxdatetime="maxDateTime"/>

{% endhighlight %}

 **Controller Section**

{% highlight JS %}

        <script>
        angular.module('DateTimeCtrl', ['ejangular'])
                .controller('DateTimeController', function ($scope) {
                    $scope.dateFormat = "yyyy/MM/dd";
                    $scope.value =new Date();
                    $scope.minDateTime = "1/8/2017 12:00 AM";
                    $scope.maxDateTime = "1/10/2017 12:00 PM";
                    
                });
        </script>

{% endhighlight %}

![MinDateTime and MaxDateTime](Behaviour_settings_images/datetime1.png)


## ShowOtherMonths

In **DateTimePicker** Component, **e-showOtherMonths** API allow showing days in adjacent months of DatePicker calendar inside the **DateTimePicker** popup which will help us to find the adjacent month dates while viewing current month calendar. If it is set as false, then other month days will be disabled in the calendar.

**HTML View Section**

{% highlight html %}

        <input type="text" id="dateTime1" ej-datetimepicker e-value="value"   e-showothermonths="false"/>

{% endhighlight  %}

 **Controller Section**

{% highlight JS %}

        <script>
        angular.module('DateTimeCtrl', ['ejangular'])
                .controller('DateTimeController', function ($scope) {
                    $scope.value =new Date();
                    
                    
                });
        </script>


{% endhighlight %}

![Show Other Months](Behaviour_settings_images/datetime2.png)

## DateTimeFormat

In AngularJS, **DateTimePicker** Component allows you to define the text representation of a date and time value to be displayed in the DateTimePicker control. By default, the date and time format will be set based on the culture but we can also manually configure date and time format by using **e-datetimeformat** property.

**HTML View Section**

{% highlight html %}

      <div class="control">
               <input type="text" id="dateTime1" ej-datetimepicker e-value="value"  e-datetimeformat="dateTimeFormat"/>
            </div>

{% endhighlight %}

 **Controller Section**

{% highlight JS %}

    <script>
    angular.module('DateTimeCtrl', ['ejangular'])
            .controller('DateTimeController', function ($scope) {
                $scope.dateTimeFormat = "d/M/yyyy tt h:mm";
                $scope.value =new Date();
        
            });
    </script>


{% endhighlight %}

![Date Time Format](Behaviour_settings_images/datetime3.png)

## Enable Persistence

In AngularJS, **e-enablePersistence** property is used to maintain the state of **DateTimePicker** Component in the browser’s local storage. When **e-enablePersistence** is set as true, it will save the model object value of DateTimePicker component in the browser’s local storage. So, the state of the **DateTimePicker** remains same even if refresh the web page.

{% highlight html %}

    <input type="text" id="dateTime1" ej-datetimepicker e-value="value"  e-enablepersistence="true" />

{% endhighlight %}

{% highlight JS %}

    <script>
    angular.module('DateTimeCtrl', ['ejangular'])
            .controller('DateTimeController', function ($scope) {
                $scope.value =new Date();
                $scope.width="180px";
                
            });
    </script>


{% endhighlight %}

![Enable Persistence](Behaviour_settings_images/datetime4.png)