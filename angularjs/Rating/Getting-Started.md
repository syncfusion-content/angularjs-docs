---
layout: post
title: Getting-Started
description: getting started
platform: Angular-1
control: Rating
documentation: ug
keywords: ejrating, rating, angularjs rating 
---

# Getting Started

This section explains briefly about how to create a **Rating** control in your application with **JavaScript**. **Essential JavaScript** **Rating** helps to select the number of stars that represent Rating. Here, you can learn how to create **Rating** control in a real-time movie download application and also learn how to rate the application.

The following screenshot illustrates the functionality of a Rating widget with a Rating range of 0 to 5. 

![](/js/Rating/Getting-Started_images/Getting-Started_img1.png) 

##Create a Rating Widget in AngularJS

**Essential JavaScript Rating** widget is provided with built-in features such as precision, orientation and flexible API’s. You can create the **Rating** widget by using input textbox element as follows:

 Essential JS includes angular directives for all controls in the ej.widget.angular.min.js script file. All the Essential JS directives have been encapsulated into a single module called angular.min.js. To render our ej controls in angular, you need to refer the **“angular.min.js”** and **“ej.widget.angular.min.js”** in your application.
 
 Create an HTML file and add the following template to the HTML file.

{% highlight html %}

<!doctype html>
<html lang="en" ng-app="ratingApp">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for Rating </title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script> 
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body ng-controller="RatingCtrl">
<!--Add necessary HTML elements-->

</body>
</html>



{% endhighlight %}

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you will have to define your directives, services, filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter.  This object is used to bind the controller with view.   

Properties can be bind to ejRating control using the prefix e- and particular property name.

 Add movies list in the table to render Rating control. Here, you can add corresponding images in the images folder and give the accurate image path.

{% highlight html %}

<div class="content-container-fluid">
        <div class="row">
            <div class="cols-sample-area">
                <div style="width: 500px">
                    <div id="moviesTab" ej-tab>
                        <ul>
                            <li><a href="#steelman">Man of Steel</a></li>
                            <li><a href="#woldwar">World War Z</a></li>
                            <li><a href="#unive">Monsters University</a></li>
                        </ul>
                        <div id="steelman">
                            <div>
                                <table>
                                    <tr>
                                        <td class="movies-img" valign="top">
                                            <img src="rating/mos.png" alt="mos" />
                                        </td>
                                        <td valign="top">
                                            <div>
                                                <span class="movie-header">Man of Steel</span><br />
                                                Rating :
                                                        <br />
                                                <input id="mosRating" type="text" ej-rating class="rating" e-value="2" />
                                                <span>Movie Info:</span>
                                                <p>
                                                    A young boy learns that he has extraordinary powers and is not of this Earth.
                                                </p>
                                            </div>
                                        </td>
                                    </tr>
                                </table>
                            </div>
                        </div>
                        <div id="woldwar">
                            <table>
                                <tr>
                                    <td class="movies-img" valign="top">
                                        <img src="rating/wwz.png" alt="mos" />
                                    </td>
                                    <td valign="top">
                                        <div>
                                            <span class="movie-header">World War Z</span><br />
                                            Rating :
                                                    <br />
                                            <input id="wwzRating" type="text" ej-rating e-value="4" class="rating" />
                                            <span>Movie Info:</span>
                                            <p>
                                                The story revolves around United Nations employee Gerry Lane (Pitt).
                                            </p>
                                        </div>
                                    </td>
                                </tr>
                            </table>
                        </div>
                        <div id="unive">
                            <table>
                                <tr>
                                    <td class="movies-img" valign="top">
                                        <img src="rating/mu.png" alt="mos" />
                                    </td>
                                    <td valign="top">
                                        <div>
                                            <span class="movie-header">Monsters University</span><br />
                                            Rating :
                                                    <br />
                                            <input id="univRating" type="text" ej-rating e-value="4" class="rating" />
                                            <span>Movie Info:</span>
                                            <p>
                                                Mike Wazowski and James P. Sullivan are an inseparable pair, but that wasn't always the case. 
                                            </p>
                                        </div>
                                    </td>
                                </tr>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>


{% endhighlight %}


To render the ejRating using angular directive, we need to inject the ej angular directive with modules shown as below,
 Initialize Rating in script.

{% highlight js %}

    <script>
        angular.module('ratingApp', ['ejangular'])
         .controller('RatingCtrl', function ($scope) {
         });
    </script>
    
{% endhighlight %}


 Apply the following styles to show the Rating widget in the horizontal order.

{% highlight css %}

<style type="text/css" class="cssStyles">
    .movies-img {
        width: 125px;
    }
    
    .movie-header {
        font-size: 20px;
        font-weight: 600;
    }
</style>


{% endhighlight %}



 The following screenshot displays a Rating widget.

![](/js/Rating/Getting-Started_images/Getting-Started_img2.png) 

##Set the Min and Max Value

In a real-time scenario, you can extend the range by using the properties **minValue** and **maxValue** in the **Rating** widget. 

{% highlight html %}

<body>
<div class="content-container-fluid">
        <div class="row">
            <div class="cols-sample-area">
                <div class="frame">
                    <table>
                        <tr>
                            <td valign="top">Rate:
                            </td>
                            <td>
                                <input id="fullRating" type="text" class="rating" ej-rating e-minvalue="2" e-maxvalue="10" e-value="4"/> 
                            </td>
                            </tr>
                    </table>
                </div>
            </div>
        </div>
    </div>
      <script>
        angular.module('ratingApp', ['ejangular'])
         .controller('RatingCtrl', function ($scope) {
         });
    </script>
</body>


{% endhighlight %}

The above code example displays the following output.

![](/js/Rating/Getting-Started_images/Getting-Started_img3.png)

##Set Precision

In a real-time movie **Rating** scenario, you can set precision in between two whole numbers, such as 2.5 or 3.7 and it is done using the property **precision** by changing the value to **ej.Rating.Precision.Half** or **ej.Rating.Precision.Exact.**

{% highlight html %}

<body>
<div class="content-container-fluid">
        <div class="row">
            <div class="cols-sample-area">
                <div class="frame">
                    <table>
                        <tr>
                            <td valign="top">Full Precision :
                            </td>
                            <td>
                                <input id="fullRating" type="text" class="rating" ej-rating e-value="4" />
                            </td>
                        </tr>
                        <tr>
                            <td valign="top">Half Precision :
                            </td>
                            <td>
                                <input id="halfRating" type="text" class="rating"  ej-rating e-precision="Half"  e-value="3.5" />
                            </td>
                        </tr>
                        <tr>
                            <td valign="top">Exact Precision :
                            </td>
                            <td>
                                <input id="exactRating" type="text" class="rating" ej-rating e-value="3.7" e-precision="Exact" />
                            </td>
                        </tr>
                    </table>
                </div>
            </div>
        </div>
    </div>
    <script>
        angular.module('ratingApp', ['ejangular'])
         .controller('RatingCtrl', function ($scope) {
         });
    </script>
</body>


{% endhighlight %}


The above code example displays the following output.

![](/js/Rating/Getting-Started_images/Getting-Started_img4.jpeg)

You can also add additional functionalities such as orientation, event tracer and API’s to the **Rating**. 

