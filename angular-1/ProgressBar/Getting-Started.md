---
layout: post
title: Getting-Started | ProgressBar | JavaScript | Syncfusion
description: getting started
platform: Angular-1
control: ProgressBar
documentation: ug
keywords: ejprogressbar, progressbar, js progressbar
---

# Getting Started

This section briefly describes how to create a **ProgressBar** control using **Javascript** and learn its features.
**Essential JavaScript** **ProgressBar** displays a **ProgressBar** within a webpage that allows you to show the progress of an event. Here, you can learn how to customize the progress and color of the **ProgressBar** in a real-time application to indicate the strength of the password, where the progress changes with respect to the change in length of the password. This helps you to validate the password is typed. 

The following screenshot shows the **ProgressBar.**

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img1.png) 

## Create a ProgressBar

Essential JS includes angular directives for all controls in the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called angular.min.js. To render our ej controls in angular, you need to refer the **“angular.min.js”** and **“ej.widget.angular.min.js”** in your application.

**Essential JavaScript ProgressBar** widget is created using a simple **&lt;div&gt;** element. This element provides built-in features that allow you to change the progress, size and text of the control.

You can create the **ProgressBar** widget by using a simple input **&lt;div&gt;** element as follows:

 Create an **HTML** file and add the following template to the **HTML** file to create your ProgressBar. It also includes the necessary scripts and styles.

{% highlight html %}

<!doctype html>
<html lang="en" ng-app="progressbarApp">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for ProgressBar </title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script> 
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="ProgressBarCtrl">
  <!--Initialize the ProgressBar -->
</body>
</html>

{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter.  This object is used to bind the controller with view.   

Properties can be bind to ejProgrssBar control using the prefix e- and particular property name.

 Add **&lt;input&gt;** element inside the **&lt;body&gt;** tag of your file to create a **ProgressBar.**



{% highlight html %}

         <div class="frame">
            <div class="wrap_up">
               <!--Initializing password field*-->
               <label for="startButton">Password</label>
               <input type="password" id="password" style="border-radius:0px"/>
            </div>
            <div class="control">
               <!--initializing ProgressBar control-->
               <div id="progressBar" ej-progressbar e-height="20" e-width="200" e-value="30"></div>
            </div>
         </div>

{% endhighlight %}


To render the ejProgrssBar using angular directive, we need to inject the ej angular directive with modules.

It also includes a Password field and through that the progress of the **ProgressBar** can be controlled

Initialize **ProgressBar** in script.

{% highlight js %}
 <script>
        angular.module('progressbarApp', ['ejangular'])
         .controller('ProgressBarCtrl', function ($scope) {
         });
        $(function () {
            progresObj = $("#progressBar").data("ejProgressBar");
            progresObj.option("text", "weak");
            $(".e-progress").css({ "background-color": "#DE0909", "border-radius": "10px" });
            $(".e-progressbar").css({ "border-radius": "10px", "border": "1px solid black" });
        });
    </script>

{% endhighlight %}

Here, you can initialize the properties of the **ProgressBar** such as height, value, width, text that is applied to the control by default.

The following screenshot displays a **ProgressBar** control.

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img2.png) 

Include the following code within the **&lt;head&gt;** tag to change the page layout.

{% highlight css %}

<style type="text/css" class="cssStyles">
   /*applying styles */
   .frame {
       border: 1px solid #BBBCBB;
       border-radius: 10px 10px 10px 10px;
       padding: 50px 60px;
       margin-top: 40px;
       width: 400px;
       margin-left: 400px;
   }
   .control {
       margin-bottom: 5px;
       margin-left: 230px;
   }
   .wrap_up {
       margin-left: 105px;
       font-size: 18px;
   }
   #progressBar {
       margin-top: 10px;
   }
</style>

{% endhighlight %}

## Progress Control using Length of the Password Field

In real-time scenario, the progress of **ProgressBar** is changed according to the length of text in the password field by binding the change in the properties of control and checking the length of the password field.

Add the following code example inside the **&lt;script&gt;** tag of your **HTML** file.

{% highlight js %}

     <script>
        angular.module('progressbarApp', ['ejangular'])
         .controller('ProgressBarCtrl', function ($scope) {
         });
        $(function () {
            $(".e-progress").css({ "background-color": "#DE0909", "border-radius": "10px" });
            $(".e-progressbar").css({ "border-radius": "10px", "border": "1px solid black" });
        });
        var progresObj, buttonObj, k = 10, timer = window.clearInterval(timer), i = 0, obj;
            $(document).keypress(function () {    //To capture the keypress inside the document           
                progresObj = $("#progressBar").data("ejProgressBar");
                i = $("#password").val().length;
                if (i < 5)
                    weak();
                else if (i == 5 || i < 7)
                    Strong();
                else if (i ==7 ||i>7) {
                    var pwd = $("#password").val();
                    very_strong();
                }
            });
            function Strong() {     //Change the width and text of the progress ... called when the length is greater than 5
                progresObj.option("text", "strong");
                progresObj.option("percentage", k + 50);
                $(".e-progress").css("background-color", "#0055FF");
            }
            function very_strong() {     //Change the width and text of the progress ... called when the length is greater than 7
                progresObj.option("text", "Very strong");
                progresObj.option("percentage", k + 90);
                $(".e-progress").css("background-color", "Green");
            }
            function weak() {     //Change the width and text of the progress... called when the length is less than 5
                progresObj.option("text", "Weak");
                progresObj.option("percentage", k + 20);
                $(".e-progress").css("background-color", "#DE0909");
            }
    </script>

{% endhighlight %}

You can calculate length of the password and call the appropriate function that changes the percentage property of **ProgressBar**.

* The **weak()** function changes the text inside the ProgressBar to **Weak** and percentage to 30, that is invoked when the length of the text is less than 5.
* The **strong()** function changes the text inside the ProgressBar to **Strong** and percentage to 60, that is invoked when the length of the text exceeds 5.
* The **very_strong()** function changes the text inside the ProgressBar to Very **Strong** and percentage to 100, that is invoked when the length of the text exceeds 7 and the text contains a symbol in it.

You can change themes or appearance of the ProgressBar as required.

The final output is displayed as follows.

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img3.png) 

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img4.png) 

![](/js/ProgressBar/Getting-Started_images/Getting-Started_img5.png) 

You can also bind an event at the start and finish of a ProgressBar by using the start, complete and change properties of the ProgressBar.

