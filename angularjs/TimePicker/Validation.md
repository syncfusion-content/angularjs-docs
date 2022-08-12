---
layout: post
title: Validation in AngularJS TimePicker Control | Syncfusion
description: Learn here all about validation support in Syncfusion AngularJS TimePicker control, its elements, and more.
platform: AngularJS
control: TimePicker
documentation: ug
---

# Validation in AngularJS TimePicker

**EJ AngularJS TimePicker** is a form control and can be used within **ng-form**. This will support with the **AngularJS validation** and update the AngularJS validation related built-in classes to element based on current state of the element.

State of the element can be **touched/dirty/valid**, based on this states corresponding classes will be add to control. These classes will be used to identify the state and picturing the components based on these using CSS in order to provide easily understandable validation status. To know more about **AngularJS Form Validation** and related classes please refer below

Just adding the **e-value** bounded component inside the ng-form, will work suitably with **AngularJS validation.**

**HTML View Section**

{% highlight html %}

    <ng-form name="timeForm" ng-submit="submitForm()">
        <h1>Meeting Scheduler</h1>
          <div>
            <table>
                <tr>
                    <td>Meeting Start Time:</td>
                    <td>
                        <input id="timepicker1" e-value="value" ej-timepicker name="starttime" e-mintime="mintime1" e-maxtime="maxtime1" required />
                    </td>
                    <td>
                        <p ng-show="timeForm.starttime.$invalid" >Start time is required.</p>
                    </td>
                </tr>
                <tr>
                    <td>Meeting End Time:</td>
                    <td>
                        <input id="timepicker2" e-value="value" ej-timepicker name="endtime" e-mintime="mintime2" e-maxtime="maxtime2" required />
                    </td>
                    <td>
                        <p ng-show="timeForm.endtime.$invalid">End time is required.</p>
                    </td>
                </tr>
            </table>
        </div>
       <button id="button" ej-button type="submit" e-text="Submit" e-size="mini" e-showRoundedCorner="true" e-click="submitForm" ng-disabled="timeForm.$invalid"></button>
    </ng-form>

{% endhighlight %}


Refer the below code for  uses the CSS to display validity of each form control.

**AngularJS**  provides classes and properties on the form and its inputs so that you can style each state accordingly. Those classes are **ng-valid**, **ng-invalid**, **ng-pristine**, **ng-dirty**, **ng-touched**, **ng-required**, **ng-show**, **ng-disabled**.

{% highlight css %}

      <style>
            .e-input.ng-invalid.ng-touched{
                background-color:orangered;
            }
            .e-input.ng-valid{
                background-color:lightgreen;
            }
            .e-input.ng-pristine{
                background-color:lightcyan;
            }
      </style>

{% endhighlight %}

**Controller Section**

Add the following code in your script section to validate the form with **TimePicker** control.

{% highlight javascript %}

            <script type="text/javascript">
                angular.module("TimeCtrl", ['ejangular']).controller("TimeCtrller", function ($scope) {
                    $scope.mintime1 = "10:00 AM",
                    $scope.maxtime1 = "05:00 PM",
                    $scope.mintime2 = "10:00 AM",
                    $scope.maxtime2 = "05:00 PM",
                    $scope.submitForm = function (isValid) {
                        if (isValid) {
                            alert("Submitted Successfully");
                        }
                    }
                  });
            </script> 

{% endhighlight %}

Run the above code to render the following output.


![AngularJS TimePicker validation](Validation_images/Validation_images1.png)


![AngularJS TimePicker provides classes and properties on the form and its inputs](Validation_images/Validation_images2.png)


![AngularJS TimePicker added script section to validate the form](Validation_images/Validation_images3.png)