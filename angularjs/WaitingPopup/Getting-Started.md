---
layout: post
title: Getting-Started | WaitingPopup | JavaScript | Syncfusion
description: getting started
platform: AngularJS
control: WaitingPopup
documentation: ug
keywords: ejwaitingpopup, waitingpopup, angularjs waitingpopup 
---

# Getting Started

This section explains briefly about how to create a **WaitingPopup** in your application with **JavaScript**.
**Essential JavaScript WaitingPopup** provides support to display a **WaitingPopup** within your webpage. From the following guidelines, you can learn how to create a **WaitingPopup** in a real-time login page authentication scenario. 

The following screenshot illustrates the functionality of a **WaitingPopup** with login page scenario.

![](/js/WaitingPopup/Getting-Started_images/Getting-Started_img1.png) 

You can give the Username and Password in the **login page**. When you click the **Login** button, you get the **WaitingPopup**. After loading, the alert box pops up with the message “Signed in successfully”.

## Create Username and Password

Essential JS includes angular directives for all controls in the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called angular.min.js. To render our ej controls in angular, you need to refer the **“angular.min.js”** and **“ej.widget.angular.min.js”** in your application.

**Essential JavaScript WaitingPopup** widget basically renders built-in features like blocking the other actions until the page is loaded. You can easily create the **WaitingPopup** widget by using simple **&lt;div&gt;** element as follows.

 Create an HTML file and add the following template to the HTML file.

{% highlight html %}


<!doctype html>
<html lang="en" ng-app="WaitingPopupApp">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for WaitingPopup </title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script> 
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="WaitingPopupCtrl">
 <!--Add necessary HTML elements-->
</html>

{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.


A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter.  This object is used to bind the controller with view.   


Properties can be bind to ejWaitingPopup control using the prefix e- and particular property name.

 Add **&lt;div&gt;** element to render a **WaitingPopup**.



{% highlight html %}


<div id="targetElement">
        <table class="loginTable">
            <tr>
                <td>Username</td>
                <td>
                    <input type="text" /></td>
            </tr>
            <tr>
                <td>Password</td>
                <td>
                    <input type="password" /></td>
            </tr>
            <tr>
                <td></td>
                <td>
                    <button id="button51" ej-button e-click="success">login</button></td>
            </tr>
        </table>
        <div id="popup" ej-waitingpopup></div>
    </div>

{% endhighlight %}



 Apply the following styles to show the **WaitingPopup**.



{% highlight css %}


<style type="text/css" class="cssStyles">
   #targetElement {
       width: 500px;
       height: 200px;
       margin: 50px;
       border: 1px solid #dbdcdb;
   }
   .loginTable {
       margin: 60px auto;
   }
   #popup_WaitingPopup .e-image {
       display: block;
       height: 70px;
   }
</style>


{% endhighlight %}


The following screenshot displays a **User** **login**.


![](/js/WaitingPopup/Getting-Started_images/Getting-Started_img2.png) 

## Add WaitingPopup Widget

To render the ejWaitingPopup using angular directive, we need to inject the ej angular directive with modules.

 In a real-time login page scenario, when you click the Login button, the WaitingPopup is displayed. 

{% highlight js %}

    <script>
        angular.module('WaitingPopupApp', ['ejangular'])
         .controller('WaitingPopupCtrl', function ($scope) {
             $scope.success = function (e) {
                var obj = $("#popup").data("ejWaitingPopup");
                obj.setModel({showOnInit: true,target: "#targetElement"});
				$timeout(function () {
				var obj = $("#popup").data("ejWaitingPopup");
				alert("Signed in successfully");
				obj.hide();
				}, 400);
             }
         });
    </script>


{% endhighlight %}


 The following screenshot shows the output of the above code example.

![](/js/WaitingPopup/Getting-Started_images/Getting-Started_img3.png) 

