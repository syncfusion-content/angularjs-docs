---
layout: post
title: Getting started with Tooltip widget for Syncfusion Essential JS
description: How to create the Tooltip
platform: JS
control: Tooltip
documentation: ug
keywords : ejTooltip, Tooltip, js Tooltip, Tooltip widget
---
# Getting started

## Preparing HTML document

The Tooltip control has the following list of external JavaScript dependencies. 

* [jQuery](http://jquery.com/) 1.7.1 and later versions

* [jQuery.easing](http://gsgd.co.uk/sandbox/jquery/easing/) - to support animation effects in the components

Refer to the internal dependencies in the following table.

<table>
<tr>
<th>
File                                </th><th>
Description/Usage</th></tr>
<tr>
<td>
ej.core.min.js</td><td>
It is referred always before using all the JS controls.</td></tr>
<tr>
<td>
ej.tooltip.min.js</td><td>
The Tooltip's main file.</td></tr>
</table>

To get started, you can use the `ej.web.all.min.js` file that encapsulates all the `ej` controls and frameworks in one single file. So the complete boilerplate code is

{% highlight html %}

    <!DOCTYPE html>
    <html ng-app="ToolApp">
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
     <body ng-controller="ToolCtrl">
    <!-- add necessary HTML elements here -->
    </body>
    </html>

{% endhighlight %}


N> In production, we highly recommend you to use our [custom script generator](http://helpjs.syncfusion.com/js/include-only-the-needed-widgets)  to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [GZip compression](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en) in your server.

For themes, you can use the `ej.web.all.min.css` CDN link from the code example given. To add the themes in your application, please refer to [this link](http://help.syncfusion.com/js/theming-in-essential-javascript-components).

## Create a Tooltip

The Tooltip can be created from any HTML element with the HTML `id` attribute and pre-defined options set to it. To create the Tooltip  refer to the following code example.

{% highlight html %}
 
    <div class="img" id="sample">
      <div class="ctrl col-md-4" id="leftImg" ej-tooltip e-width="300px" e-height="60" e-position="position" e-content="content" >
        <img class="ctrImg" src="http://js.syncfusion.com/demos/web/images/tooltip/template-05.png" />
        <div class="desc">Delphi Succinctly</div>
     </div>
    </div>

    // Creates the Tooltip

{% endhighlight %}

{% highlight javascript %}

       <script>

         angular.module('ToolApp', ['ejangular']).controller('ToolCtrl', function ($scope) {
             $scope.content="Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms";
	         $scope.position = {
                 stem: {
                       horizontal: "left",
                       vertical: "center"
                   },
                   target: {
                       horizontal: "right",
                       vertical: "center",
                   },
				   }
            	});
    
       </script>
 
{% endhighlight %}

Apply the following style sheet

{% highlight css %}

    <style>

         div.img {
        border: 1px solid #ccc;
        width: 159px;
        height: 213px;
        left: 35%;
        position: relative;
        top: 20%;
           }	
         img {
        width: 159px;
        height: 179px;
           }
       div.desc {
        padding: 5px;
        text-align: center;
          }
	
     </style>
    
{% endhighlight %}

![](Getting-Started_images/Getting-Started_img1.jpeg)

## Setting Dimensions

Tooltip dimensions can be set using [width](http://help.syncfusion.com/js/api/ejtooltip#members:width) and [height](http://help.syncfusion.com/js/api/ejtooltip#members:height) API.

{% highlight html %}
 
       <div id="control" >
             TypeScript lets you write <a id="test" ej-tooltip e-content="content1" e-width="width" e-height="height"><u> JavaScript </u> </a>the way you really want to
       </div> 
       // Creates the Tooltip

{% endhighlight %}

{% highlight javascript %}
      
      <script>
         angular.module('ToolApp', ['ejangular']).controller('ToolCtrl', function ($scope) {
	           $scope.content="JavaScript is the programming language of HTML and the Web.";
	           $scope.width="100px";
	           $scope.height="100px";
			   });
	
      </script>
    
{% endhighlight %}

## Tooltip Appearance 

You can configure the appearance of the Tooltip with the title, close button and call out as your application requires.

{% highlight html %}
 
      <div class="img" id="sample">
          <div class="ctrl col-md-4" id="leftImg" ej-tooltip e-width="300px" e-height="100" e-title="Delphi Succintly" e-position="position" e-content="content" e-closeMode="sticky" e-isBalloon="false">
              <img class="ctrImg" src="http://js.syncfusion.com/demos/web/images/tooltip/template-05.png" />
              <div class="desc">Delphi Succinctly</div>
           </div>
      </div>

    // Creates the Tooltip

{% endhighlight %}

Apply the following styles to show the Tooltip.

{% highlight css%}

     <style>
        div.img {
        border: 1px solid #ccc;
        float: left;
        box-sizing: border-box;
        height: 200px;
        width: 146px;
         }
       img{
        width: 100%;
        height: 166px;
       }
      div.desc {
        padding: 6px;
        text-align: center;
        }

</style>
    
{% endhighlight %}

![](Getting-Started_images/Getting-Started_img2.jpeg)

