---
layout: post
title: Validation | DateTimePicker | AngularJS | Syncfusion
description: validation
platform: AngularJS
control: DateTimePicker
documentation: ug
---
## Validation

**AngularJS** form validation allows us to monitor the state of the html element and add functionalities depending upon the states of the html element. It also allows us to define different classes for different states of the element, here we discuss about adding different classes and functionalities depending upon the states of the e-datetimepicker element.

The states of the element may be pristine, touched, Untouched, dirty etc., which defines the actual states of the element.

The validation of the **DateTimePicker** in a form is explained below with Bio Data. Here, different *ng-classes* have been used to determine the different sate of the input element of the **DateTimePicker**, also *ng-required* has been used to set the input field of **DateTimePicker** in the form as required.

**HTML View Section**

{%highlight html%}

    <body ng-controller="ctrl">
        <div align="center" class="div">
            <h1><b> Hotel Room Booking </b></h1>
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
                            <td>Room Preference</td>
                            <td>
                                <input type="radio" ej-radiobutton id="radio1" name="trip" value="one way" /><label for="radio1">Single Room</label>
                            </td>
                            <td colspan="2">
                                <input type="radio" ej-radiobutton id="radio2" name="trip" value="two way" /><label for="radio2">Double Room</label>
                            </td>
                        </tr>
                        <tr></tr>
                        <tr></tr>
                        <tr>
                            <td>Check In Date and Time</td>
                            <td colspan="2">
                                <input type="text" id="dateTime" e-value="datetime" name="datetime" ej-datetimepicker e-width="100%" required ng-required="req_Date" />

                            </td>
                        </tr>
                        <tr>
                            <td>Check Out Date and Time</td>
                            <td colspan="2">
                                <input type="text" id="dateTime" e-value="datetime" name="datetime" ej-datetimepicker e-width="100%" required ng-required="req_Date" />

                            </td>
                        </tr>
                        <tr>
                            <td>Rent Payment Option:</td>
                            <td>
                        <select id="dropdown1" ej-dropdownlist e-datasource="dataList" e-value="value" />    </td>
                        </tr>
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


{%endhighlight%}

**Controller Section**

{%highlight JS%}

        <script>
                var list = [
                            { empid: "cr1", text: "Debit Card", value: "Debit Card" },
                            { empid: "cr2", text: "Credit Card", value: "Credit Card" },
                            { empid: "cr3", text: "Paypal", value: "Paypal" },
                            { empid: "cr4", text: "Cash", value: "Cash" },
                            
                            
                            
                    ];
                angular.module('DateRangeCtrl', ['ejangular'])
                .controller('ctrl', function ($scope) {
                    $scope.val = "Name";
                    $scope.submitForm = function () {
                        if ($scope.myForm.$valid) {
                            alert('Form Sumbitted');
                        }
                        else alert('Something Wrong with form');

                    };
                    $scope.daterange = "";
                    $scope.req_Date = true;
                    $scope.dataList = list;
                });
                
            </script>


{%endhighlight%}

![](validation_images/datetime8.png)
