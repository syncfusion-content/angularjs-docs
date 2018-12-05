---
layout: post
title: Validation | DataRangePicker | AngularJS | Syncfusion
description: Validation
platform: AngularJS
control: DataRangePicker
documentation: ug
---
# Validation

AngularJS form validation allows to monitor the state of the html element and add functionalities depending upon the states of the html element. It also allows us to define different classes for different states of the element, here we discuss about adding different classes and functionalities depending upon the states of the DateRangePicker element.

The states of the element may be pristine, touched, Untouched, dirty etc., which defines the actual states of the element.
 
The input element CSS properties can be varied depending upon the states of the input elements
as mentioned below.

{% highlight html %}

<style>   
     .e-daterangewidget.e-input.ng-touched.ng-pristine, input.ng-touched.ng-pristine {
            background-color: lightgray;
        }

        .e-daterangewidget.e-input.ng-touched.ng-dirty, input.ng-touched.ng-dirty {
            background-color: lightsteelblue;
        }

        .e-daterangewidget.e-input.ng-untouched, input.ng-untouched  {
            background-color: lightyellow;
        }

        .e-daterangewidget.e-input.ng-untouched.ng-dirty {
                background-color: lightcyan;
            }
</style>

{% endhighlight %}

In the above CSS classes, the normal input elements have been initialized using the input keyword but the DataRangePicker component, CSS classes are initialized by using “.e-daterangewidget.e-input”. 

AngularJS provides classes and properties on the form and its inputs so that you can style each state accordingly.

**ng-valid**    - whether an item is currently valid based on the rules you placed.
**ng-invalid**  - whether an item is currently invalid based on the rules you placed.
**ng-pristine** - The form/input has not been used yet.
**ng-dirty**    – The form/input has been used.
**ng-touched**  – The input has been blurred.

{% highlight html %}

        <div align="center" class="div" ng-controller="dateRangeCtrl" >
                <h1><b> Trip Planner </b></h1>
                <ng-form name="myForm">
                    <div>
                        <table>
                            <tr>
                                <td>Name :</td>
                                <td colspan="2"><input type="text" class="e-textbox" id="name" ng-model="val" /></td>
                            </tr>
                            <tr></tr>
                            <tr></tr>
                            <tr>
                                <td>Trip Way:</td>


                                <td>
                                    <input type="radio" ej-radiobutton id="radio1" name="trip" value="one way" /><label for="radio1">One Way</label>
                                </td>
                                <td colspan="2">
                                    <input type="radio" ej-radiobutton id="radio2" name="trip" value="two way" /><label for="radio2">Two Way</label>
                                </td>
                            </tr>
                            <tr></tr>
                            <tr></tr>
                            <tr>
                                <td>Date Range:</td>
                                <td colspan="2">
                                    <input type="text" id="daterange" e-value="daterange" name="daterange" ej-daterangepicker e-width="100%" required ng-required="req_Date" />

                                </td>
                            </tr>
                            <tr></tr>
                            <tr></tr>
                            <tr>
                                <td></td>
                                <td colspan="2" align="center">
                                    <button id="submit" ej-button e-showroundedcorner="true" type="submit" e-size="large" e-text="Submit" e-click="submitForm"></button>
                                </td>
                            </tr>
                        </table>
                    </div>
                </ng-form>
        </div>

{% endhighlight %}

{% highlight javascript %}

        <script>
            angular.module('syncApp', ['ejangular'])
            .controller('dateRangeCtrl', function ($scope) {
                $scope.val = "Name";
                $scope.submitForm = function () {
                    if ($scope.myForm.$valid) {
                        alert('Form Submitted');
                    }
                    else alert('Something Wrong with form');
                };
                    $scope.daterange = "";
                    $scope.req_Date = true;
            });
        </script>

{% endhighlight %}

Run the above code with mentioned CSS files to get the below mentioned outputs.

**Untouched**

![Validation with Untouched](validation_images/untouched.png)

**Untouched and dirty**

This class is applied when the DateRangePicker value has been changed using the calendar icon without touching the input element of the DateRangePicker.

![Validation without Touch and Dirty](validation_images/untouched-dirty.png)

**Touched and pristine**

![Validation with Touch and Pristine](validation_images/touched-pristine.png)

**Touched and Dirty**

![Validation with Touch and Dirty](validation_images/touched-dirty.png)

**Valid**

Here valid and invalid properties are used based on the form validation by using ng-required attribute to the daterangepicker component.

![Validation with Valid Values](validation_images/valid.png)

**Invalid**

Here the value of the daterangepicker is not hence invalid message is shown.

![Validation with Invalid Values](validation_images/invalid.png)

