---
layout: post
title: Getting-Started
description: getting started
platform: AngularJS
control: TagCloud
documentation: ug
keywords: ejtagcloud, tagcloud, angularjs tagcloud
---

# Getting Started

This section explains briefly about how to create a **TagCloud** in your application with **JavaScript**. The **TagCloud** can be easily configured to the div element in which the tags are placed. The following screenshot illustrates the functionality of a **TagCloud** widget with a list of the topmost search engines. 

![](Getting-Started_images/Getting-Started1.jpg)

## Create TagCloud widget in AngularJS

 Create an **HTML** file and add the following template to the **HTML** file.

{% highlight html %}

    <!DOCTYPE html>
    <html ng-app="TagApp">
    <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8" />
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-2.1.4.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
    </head>
    <body ng-controller="TagCtrl">
    <!-- add necessary HTML elements here -->
    </body>
    </html>

{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you  have to define your directives, services, filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter.  This object is used to bind the controller with view.   

Properties can be bind to ejTagCloud control using the prefix e- and particular property name.



Add necessary **HTML** elements.

{% highlight html %}

    <div id="tag" ej-tagcloud e-datasource="dataList" e-titletext="Popular Sites"></div>

{% endhighlight %}

Add the following code example before **&lt;/body&gt;** tag to add list of items to the **TagCloud** and initialize the **TagCloud** widget.

{% highlight javascript %}

    <script>
	
	var list = [
              { text: "Google", url: "http://www.google.co.in", frequency: 20 },
              { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
              { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
              { text: "slider", url: "http://bxslider.com/examples", frequency: 2 },
              { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
              { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
              { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
              { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
              { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
              { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
              { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
              { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
              { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
              { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
              { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
              { text: "Valley", url: "http://valleywag.gawker.com/", frequency: 6 },
              { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
              { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }

              ];

	angular.module('TagApp', ['ejangular']).controller('TagCtrl', function ($scope) {
	
	$scope.dataList=list;
	
     });
	 
{% endhighlight %}

The following screenshot displays the output of the above code example.

![](Getting-Started_images/Getting-Started1.jpg) 

## Set Min and Max Font Size

In the above code example, the **frequency** properties are used to set the min and max font size to the **TagCloud** list item.

{% highlight javascript %}
   
    <script>
	
    	var list = [
              { text: "Google", url: "http://www.google.co.in", frequency: 20 },
              { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
              { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
              { text: "slider", url: "http://bxslider.com/examples", frequency: 2 },
              { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
              { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
              { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
              { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
              { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
              { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
              { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
              { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
              { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
              { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
              { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
              { text: "Valley", url: "http://valleywag.gawker.com/", frequency: 6 },
              { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
              { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }

              ];

	      angular.module('TagApp', ['ejangular']).controller('TagCtrl', function ($scope) {
	
	     $scope.dataList=list;
	
         });
	 
    </script>
{% endhighlight %}

In the above code, the min font size is 0 and max font size is 20.

## Set event to perform an operation

Here, you can set the **TagCloud** events such as create, mouseover, mouseout, click.

{% highlight html %}

    <div id="tag" ej-tagcloud e-datasource="dataList" e-titletext="Popular Sites" e-create="create" e-mouseover="mouseover" e-mouseout="mouseout" e-click="click"></div>

{% endhighlight %}

{% highlight javascript %}

    <script>
    
    	var list = [
              { text: "Google", url: "http://www.google.co.in", frequency: 12 },
              { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
              { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
              { text: "slider", url: "http://bxslider.com/examples", frequency: 2 },
              { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
              { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
              { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
              { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },
              { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },
              { text: "MSN", url: "http://www.msn.com/", frequency: 3 },
              { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },
              { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },
              { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },
              { text: "Menucool", url: "http://www.menucool.com", frequency: 3 },
              { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },
              { text: "Valley", url: "http://valleywag.gawker.com/", frequency: 6 },
              { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
              { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }

             ];

      	angular.module('TagApp', ['ejangular']).controller('TagCtrl', function ($scope) {
	
	      $scope.dataList=list;
	      $scope.create=function()
	        {
	          alert();
	        }
	     $scope.mouseover=function()
	         {
	          alert();
	        }
     	 $scope.mouseout=function()
          {
	          alert();
	        }
    	$scope.click=function()
          {
	          alert();
	        }
	});
    
    </script>

{% endhighlight %}

In the above code example, the **alert()** function is used  to show the events that happened.

