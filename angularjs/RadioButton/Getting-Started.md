---
layout: post
title: Getting Started | Radio Button | AngularJs | Syncfusion
description: This section explains how to add radio button control to angularjs application and illustrates how to create the quiz application using angularjs radio button. 
platform: AngularJS
control: RadioButton
documentation: ug
---

# Getting Started

This section briefly describes you on how to create a QuizApp and RegistrationApp using Essential JavaScript RadioButton control and use the features available in it.**Essential JavaScript** **RadioButton** supports RTL, custom skins and events to display customized RadioButtons. In this example, you can learn how to use RadioButtons in a Quiz application. The following guidelines show you how to use the **RadioButton** to select the answers in the application and get the selected items. The following screenshot displays a sample Quiz application.


![AngularJs Radio Button](\Getting-Started_images/Getting-Started_img1.png) 

## Create a RadioButton in a Quiz Application

**Essential JavaScript RadioButton** is created by using a simple input textbox element as follows.

1. Create an HTML file and add required scripts and CSS files to render the Essential JavaScript component as given in the [Getting Started](https://help.syncfusion.com/js/control-initialization).
2. Essential JavaScript includes angular directives for all controls with the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called **ejangular**. To render our ej controls in angular, you need to refer the “angular.min.js” and “ej.widget.angular.min.js” in your application.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="RadioCtrl">
<head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8"  />
     <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css"rel="stylesheet"/>
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <!--Add custom scripts here -->
</head>
    <body style="background-color: #fcf7f7" ng-controller="RadioButtonCtrl">
        <!-- Add RadioButton element here --> 
    </body>
</html>

{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

Properties can be bind to ejRadioButton control using the prefix e- and particular property name as shown as below


 Add input element to render a **RadioButton**.

{% highlight html %}
    <div>
        1. What is the Expansion for MVC ? <br />
        <table>
            <tr>
                <td>
                    <input type="radio" name="small1" id="Radio1" ej-radiobutton e-size="size1" /><label for="Radio1">Model View Controller</label>
                </td>
                <td colspan="2">
                    <input type="radio" name="small1" id="Radio2" ej-radiobutton e-size="size2" /><label for="Radio2">Model Virtual Container</label>
                </td>
                <td colspan="2">
                    <input type="radio" name="small1" id="Radio3" ej-radiobutton e-size="size3" /><label for="Radio3">Model Visual Controller</label>
                </td>
            </tr>
        </table>
        <br /><br /><br />
        2.  What is the Expanson for USB ?<br />
        <table>
            <tr>
                <td>
                    <input type="radio" name="small2" id="Radio4" ej-radiobutton e-size="size4" /><label for="Radio4">Universal serialized Buffer</label>
                </td>
                <td>
                    <input type="radio" name="small2" id="Radio5" ej-radiobutton e-size="size5" /><label for="Radio5">Universal Serial Buffer</label>
                </td>
                <td>
                    <input type="radio" name="small2" id="Radio6" ej-radiobutton e-size="size6" /><label for="Radio6">Universal Serial Bus</label>
                </td>
            </tr>
        </table>
        <br /><br /><br />
        3.   What is the Expanson for HTML ?<br />
        <table>
            <tr>
                <td>
                    <input type="radio" name="small3" id="Radio7" ej-radiobutton e-size="size7" /><label for="Radio7">Hyper Text Makeup Language</label>
                </td>
                <td>
                    <input type="radio" name="small3" id="Radio8" ej-radiobutton e-size="size8" /><label for="Radio8">Hyper Text Markup Language</label>
                </td>
                <td>
                    <input type="radio" name="small3" id="Radio9" ej-radiobutton e-size="size9" /><label for="Radio9">Hyper Text Makeup Loader</label>
                </td>
            </tr>
        </table>
        <br /><br /><center>
            <button id="submitid" ej-button e-onclick="button">Submit</button>
        </center>
    </div>   
{% endhighlight %}

 Add the following angular module in script section.

{% highlight javascript %}
    <script>
        angular.module('RadioCtrl', ['ejangular'])
           .controller('RadioButtonCtrl', function ($scope) {
               $scope.size1 = "medium";
               $scope.size2 = "medium";
               $scope.size3 = "medium";
               $scope.size4 = "medium";
               $scope.size5 = "medium";
               $scope.size6 = "medium";
               $scope.size7 = "medium";
               $scope.size8 = "medium";
               $scope.size9 = "medium";
               $scope.button = function (e) {
                   var checkeditem = [];
                   $(".e-radiobtn:checked").each(function () {
                       checkeditem.push($(this).parent().siblings().html());
                   });
                   alert(checkeditem);
               }
           });
    </script>
    
{% endhighlight %}



 Add the following styles


{% highlight css %}
    <style>
        html, body {
            width: 71%;
            margin: 0;
        }

        .frame {
            width: 80%;
        }
    </style>
{% endhighlight %}


The following screenshot displays the output for the above code.

![AngularJs radio button in quiz application](\Getting-Started_images/Getting-Started_img2.png) 

