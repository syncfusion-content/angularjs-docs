---
layout: post
title: Getting started with DropDownList widget for Syncfusion Essential JS
description: To get start with DropDownList by adding references.
platform: Angular-1
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, Populating data
---

# Getting Started

The external script dependencies of the DropDownList widget are,

* [jQuery 1.7.1](http://jquery.com/) and later versions.
* [jQuery.easing](http://gsgd.co.uk/sandbox/jquery/easing/) - to support the animation effects.

And the internal script dependencies of the DropDownList widget are:

<table>
	<tr>
		<th>File </th>
		<th>Description / Usage </th>
	</tr>
	<tr>
		<td>ej.core.min.js</td>
		<td>Must be referred always before using all the JS controls.</td>
	</tr>
	<tr>
		<td>ej.data.min.js</td>
		<td>Used to handle data operation and should be used while binding data to JS controls.</td>
	</tr>
	<tr>
		<td>ej.dropdownlist.min.js</td>
		<td>The dropdownlist’s main file</td>
	</tr>
	<tr>
		<td>ej.checkbox.min.js</td>
		<td>Should be referred when using checkbox functionalities in DropDownList.</td>
	</tr>
	<tr>
		<td>ej.scroller.min.js</td>
		<td>Should be referred when using scrolling in DropDownList.</td>
	</tr>
	<tr>
		<td>ej.draggable.min.js</td>
		<td>Should be referred when using popup resize functionality in DropDownList.</td>
	</tr>
</table>

For getting started you can use the ‘ej.web.all.min.js’ file, which encapsulates all the 'ej' controls and frameworks in one single file.<br/> 

For themes, you can use the ‘ej.web.all.min.css’ CDN link from the snippet given. To add the themes in your application, please refer [this link](http://help.syncfusion.com/js/theming-in-essential-javascript-components#adding-specific-theme-to-your-application).


## Preparing HTML document

Create a new HTML file and add [CDN](http://help.syncfusion.com/js/cdn) links to the [JavaScript](http://help.syncfusion.com/js/dependencies) and [CSS](http://help.syncfusion.com/js/theming-in-essential-javascript-components) dependencies to your project.

{% highlight html %}

    <!DOCTYPE html>
    <html ng-app="dropdownlistApp">
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
     <body ng-controller="dropdownlistCtrl">
    <!-- add necessary HTML elements here -->
    </body>
    </html>
{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you  have to define your directives, services, filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter.  This object is used to bind the controller with view.   

Properties can be bind to ejDropDownList control using the prefix e- and particular property name.


 N>  In production, we highly recommend you to use our [custom script generator](http://help.syncfusion.com/js/include-only-the-needed-widgets#) to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [GZip compression](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en#text-compression-with-gzip) in your server. 

## Creating DropDownList in Angular JS

The DropDownList can be created from a HTML ‘select’ element with the HTML 'id' attribute and pre-defined options set to it. Use the below given code to create a DropDownList in Angular JS.

{% highlight html %}
	
	 <select id="dropdown1" ej-dropdownlist e-datasource="dataList" e-value="value" />
			
{% endhighlight %}
	
{% highlight javascript %}	
	
		var list = [
                    { empid: "cr1", text: "ListItem 1", value: "ListItem 1" },
                    { empid: "cr2", text: "ListItem 2", value: "ListItem 2" },
                    { empid: "cr3", text: "ListItem 3", value: "ListItem 3" },
                    { empid: "cr4", text: "ListItem 4", value: "ListItem 4" },
                    { empid: "cr5", text: "ListItem 5", value: "ListItem 5" },
                    
                    
              ];

           angular.module('dropdownlistApp', ['ejangular']).controller('dropdownlistCtrl', function ($scope) {
	             $scope.dataList = list;
				 
            });			
	
{% endhighlight %}

![](Getting-Started_images/Getting-Started_img1.jpeg)

## Populating data

The DropDownList can be bounded to both local array and remote data services using [ej.DataManager](http://help.syncfusion.com/js/datamanager/overview). You can use [DataManager](http://help.syncfusion.com/js/datamanager/overview) component to serve data from the data services based on the query provided. To bind data to DropDownList widget, the [dataSource](http://help.syncfusion.com/js/api/ejdropdownlist#members:datasource) property should be assigned with the instance of 'ej.DataManager'.
 
N> ODataAdaptor is the default adaptor for DataManager. On binding to other web services, proper [data adaptor](http://help.syncfusion.com/js/datamanager/data-adaptors) needs to be set on 'adaptor' option of DataManager. 
	
{% highlight html %}

	<select id="dropdown1" ej-dropdownlist e-datasource="dataList"  e-fields-text="text"/>
	
{% endhighlight %}
	
{% highlight javascript %}	
	
       <script>
			
              var  Customers = [
                 { id: "1", text: "ALFKI" }, { id: "2", text: "ANATR" }, { id: "3", text: "ANTON" },
                 { id: "4", text: "AROUT" }, { id: "5", text: "BERGS" }, { id: "6", text: "BLAUS" }
            ];
			var dataManager = ej.DataManager(Customers);
            angular.module('dropdownlistApp', ['ejangular']).controller('dropdownlistCtrl', function ($scope) {
	             $scope.dataList = dataManager;
				  });

       </script>
			
{% endhighlight %}
	
![](Getting-Started_images/Getting-Started_img2.jpeg)

## Setting Dimensions

DropDownList dimensions can be set using width and height API.
	
{% highlight html %}
	
	<select id="dropdown1" ej-dropdownlist e-datasource="dataList" e-value="value" e-width="width" e-height="height"  />
	
{% endhighlight %}
	
{% highlight javascript %}	
	
	    <script>
	
	     var list = [
                    { empid: "cr1", text: "ListItem 1", value: "ListItem 1" },
                    { empid: "cr2", text: "ListItem 2", value: "ListItem 2" },
                    { empid: "cr3", text: "ListItem 3", value: "ListItem 3" },
                    { empid: "cr4", text: "ListItem 4", value: "ListItem 4" },
                    { empid: "cr5", text: "ListItem 5", value: "ListItem 5" },
                    
                    
              ];
         angular.module('dropdownlistApp', ['ejangular']).controller('dropdownlistCtrl', function ($scope) {
	             $scope.dataList = list;
				 $scope.width="300px";
				 $scope.height="40px"
              });   
			  
	    </script>
	
{% endhighlight %}

**Setting dimensions to Popup list**

PopupWidth and popupHeight can be used to create a fixed size popup list.

{% highlight html %}

	<select id="dropdown1" ej-dropdownlist e-datasource="dataList" e-value="value" e-popupHeight="popupheight" e-popupWidth="popupwidth"/>

{% endhighlight %}
	
{% highlight javascript %}
	
	    <script>

		var list = [
                    { empid: "cr1", text: "ListItem 1", value: "ListItem 1" },
                    { empid: "cr2", text: "ListItem 2", value: "ListItem 2" },
                    { empid: "cr3", text: "ListItem 3", value: "ListItem 3" },
                    { empid: "cr4", text: "ListItem 4", value: "ListItem 4" },
                    { empid: "cr5", text: "ListItem 5", value: "ListItem 5" },
                    
                    
              ];
          angular.module('dropdownlistApp', ['ejangular']).controller('dropdownlistCtrl', function ($scope) {
	             $scope.dataList = list;
				 $scope.popupwidth="200px";
				 $scope.popupheight="100px"
                 });
        </script>
	
{% endhighlight %}
	
## Setting and Getting Value

You can select single or multiple values from DropDownList widget. To assign a value initially to the DropDownList, you can use [value](http://help.syncfusion.com/js/api/ejdropdownlist#members:value) property.

N> To select multiple items based on index, refer [here](functionalities#selection).

{% highlight html %}

	<select id="dropdown1" ej-dropdownlist e-datasource="dataList" e-value="value" e-change="change"/>

{% endhighlight %}
	
{% highlight javascript %}	
	
	<script>

		var list = [
                    { empid: "cr1", text: "ListItem 1", value: "ListItem 1" },
                    { empid: "cr2", text: "ListItem 2", value: "ListItem 2" },
                    { empid: "cr3", text: "ListItem 3", value: "ListItem 3" },
                    { empid: "cr4", text: "ListItem 4", value: "ListItem 4" },
                    { empid: "cr5", text: "ListItem 5", value: "ListItem 5" },
                    
                    
              ];
            angular.module('dropdownlistApp', ['ejangular']).controller('dropdownlistCtrl', function ($scope) {
	             $scope.dataList = list;
				 $scope.value="ListItem 1";
				 $scope.change=function()
				 {
				     var obj = $('#dropdown1').data("ejDropDownList");
                      console.log("Selected Item's Text - " + obj.option("text"));
				      console.log("selected Item's Value - " + obj.option("value"));    

				 }
				  });
 
 				   
     </script>

{% endhighlight %}

