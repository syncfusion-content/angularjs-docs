---
layout: post
title: getting started
description: getting started
platform: AngularJS
control: Signature
documentation: ug
---

## Getting Started

The Essential Angular Signature simplifies creation of a signature capture in a browser, allowing a user to draw a signature either using mouse or touch.

This section explains briefly about how to create a **Signature** component in your application with AngularJS by the following step-by-step instructions. The following screenshot demonstrates the functionality of Signature component.

![https://help.syncfusion.com/js/signature/Getting_Started_images/gettingstarted_img1.png](Getting_Started_images\gettingstarted_img1.png)

### Create Signature 

Create a new HTML file and include the below code:

{% highlight html %}


<!DOCTYPE HTML>
    <html lang="en" ng-app="syncApp">
    <head>
        <title>Essential Studio for JavaScript : Angular JS Support for Signature </title>
        <!-- Style sheet for default theme (flat azure) -->
        <link href="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <!--Scripts-->
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script>
        <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
        <script type="text/javascript" src="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/web/ej.web.all.min.js "></script>
        <script src="http://cdn.syncfusion.com/**{{**site.releaseversion**}}**/js/common/ej.widget.angular.min.js"></script>
        <!--Add custom scripts here -->
    </head>
    <body ng-controller="SignatureCtrl">
        <!--Add necessary HTML elements-->
    </body>
    </body>
</html>


{% endhighlight %}


The ng-app directive explains the root element (&lt;html&gt; or &lt;body&gt; tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you have to define your directives, services, filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter. This object is used to bind the controller with view.

Properties can be bind to ejSignature component using the prefix **e-** and particular property name.

Add div element to create Signature.

{% highlight html %}

  <div ng-controller="signatureCtrl">
                    <div id="signature" ej-signature e-height="height"></div>     
    </div>

{% endhighlight %}

Add the following script to create the signature.

{% highlight js %}

   syncApp.controller('signatureCtrl', function ($scope) {
            $scope.height = 400,
                   });

{% endhighlight %}

The following screenshot is the output for the above code.

![https://help.syncfusion.com/js/signature/Getting_Started_images/createsignaturecontrol_img1.png](Getting_Started_images\gettingstarted_img2.png)


### Adjusting Signature Size

You can customize the width and height of the Signature by **e-width** and **e-height** properties. These properties completely depend on signature canvas. The width and height are adjusted within the signature canvas.

The following code example is used to render the Signature component with customized width and height.

Add the following HTML to render signature.

{% highlight html %}

  <div ng-controller="signatureCtrl">
                    <div id="signature" ej-signature e-height="height" e-width="width" e-isresponsive="true" ></div>     
    </div>

{% endhighlight %}

Add the following script to render signature with customized width and height.

{% highlight js %}

syncApp.controller('signatureCtrl', function ($scope) {
             $scope.height = 300,
             $scope.width = 200,             

        });

{% endhighlight %}

The following screenshot illustrates signature with customized width and height.

![https://help.syncfusion.com/js/signature/Getting_Started_images/adjustingsignaturesize_img1.png](Getting_Started_images\gettingstarted_img3.png)
