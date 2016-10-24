---
layout: post
title: Getting-Started
description: getting started
platform: AngularJS
control: Scroller
documentation: ug
---

# Getting Started

This section explains briefly about how to create a **Scroller** in your application with **JavaScript**.

## Create your first Scroller in AngularJS

Essential JS includes angular directives for all controls in the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called angular.min.js. To render our ej controls in angular, you need to refer the **“angular.min.js”** and **“ej.widget.angular.min.js”** in your application.

**Essential JavaScript Scroller** control can be rendered based on the target panel height and width, and includes more customization options.


Create a HTML file and paste the following template to the HTML file to create the ejScroller.

{% highlight html %}

<!DOCTYPE html>
<!doctype html>
<html lang="en" ng-app="scrollerrApp">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for Tagcloud </title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="ScrollerCtrl">
               <div class="control">
                  <div id="scrollcontent" ej-scroller e-height="300" e-width="600">
                     <div>
                        <div class="sampleContent">
                           <h3 style="font-size: 20px;">MVC</h3>
                           <div>
                              <p>Model–view–controller (MVC) is a software architecture pattern which separates the
                                 representation of information from the user's interaction with it.
                                 The model consists of application data, business rules, logic, and functions. A view can be any
                                 output representation of data, such as a chart or a diagram. Multiple views of the same data 
                                 are possible, such as a bar chart for management and a tabular view for accountants. 
                                 The controller mediates input, converting it to commands for the model or view.The central 
                                 ideas behind MVC are code reusability and n addition to dividing the application into three 
                                 kinds of components, the MVC design defines the interactions between them.
                              </p>
                              <ul>
                                 <li>
                                    <b>A controller </b>can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). 
                                    It can also send commands to the model to update the model's state (e.g., editing a document).
                                 </li>
                                 <li>
                                    <b>A model</b> notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. 
                                    A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.
                                 </li>
                                 <li>
                                    <b>A view</b> requests from the model the information that it needs to generate an output representation to the user.
                                 </li>
                              </ul>
                           </div>
                        </div>
                     </div>
                  </div>
               </div>
</body>
</html>


{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter.  This object is used to bind the controller with view.   

Properties can be bind to ejScroller control using the prefix e- and particular property name.

To render the ejScroller using angular directive, we need to inject the ej angular directive with modules.

Initialize **ejScroller** in the target area in the script.

{% highlight js %}

   <script>
        angular.module('scrollerrApp', ['ejangular'])
         .controller('ScrollerCtrl', function ($scope) {
        });
  </script>


        
{% endhighlight %}



Configure the styles.

{% highlight css %}
    
<style type="text/css">
        .control {
            border: 1px solid #bbbcbb;
            width: 600px;
            margin: 0 auto;
            height: 300px;
        }
        .sampleContent {
            width: 700px;
            padding:15px;
        }
</style>

{% endhighlight %}



Scroller control is added to the application. 

![](/js/Scroller/Getting-Started_images/Getting-Started_img1.png)

