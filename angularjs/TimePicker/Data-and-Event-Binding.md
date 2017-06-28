---
layout: post
title: Data and Event Binding| TimePicker | AngularJS | Syncfusion
description: data and event binding
platform: AngularJS
control: TimePicker
documentation: ug
---

# Data and Event Binding

## Data Binding

**Data binding** in **AngularJS** is the synchronization between the model and the view. **Data binding** is an approach where a value is taken from the data model and inserted into an HTML element. There is no way to update model from view.

**HTML View Section**

{% highlight html %}

     <input id="timepicker" ej-timepicker e-value="value" />
     <p>Time is {{value}}</p>

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

            <script type="text/javascript">
            angular.module("TimeCtrl", ['ejangular']).controller("TimeCtrller", function ($scope) {
                // Event Binding
                $scope.value="9:00 AM",
                }
                });
            </script>

{% endhighlight %}

Run the above code to render the following output.


![](Data-and-Event-Binding_images/Data and Event Binding_images2.png)


## Event Binding

Component events and captured and processed based on application needs. These events can be registered with scope to enhance the component functionality with **AngularJS**. Please refer the below code example,

**HTML View Section**

{% highlight html %}

     <input id="timepicker" ej-timepicker e-change="valuechanged"/>

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

        <script type="text/javascript">
        angular.module("TimeCtrl", ['ejangular']).controller("TimeCtrller", function ($scope) {
            // Event Binding
             $scope.valuechanged = function (e) {
                alert("Time is changed", +e.value);
            }
        });
    </script>

{% endhighlight %}

## Two-way Binding

In **AngularJS** framework, any changes to view proximately update to model, any changes in model directly updated with view rapidly.With **TimePicker** control, value API enabled with two way binding to achieve this delightful functionality. 

Please refer the below code example,

**HTML View Section**

{% highlight html %}

     <input id="timepicker1" ej-timepicker  e-value="value"/>
     <input id="timppicker2" ej-timepicker  e-value="value"/>

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

        <script type="text/javascript">
            angular.module("TimeCtrl", ['ejangular']).controller("TimeCtrller", function ($scope) { 
            //data Binding
            $scope.value="12:00 AM"
               })
        </script>

{% endhighlight %}

Run the above code to render the following output.


![](Data-and-Event-Binding_images/Data and Event Binding_images1.png)



