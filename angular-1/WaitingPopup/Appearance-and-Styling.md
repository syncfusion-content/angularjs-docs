---
layout: post
title: Appearance-and-Styling
description: appearance and styling 
platform: Angular-1
control: WaitingPopup
documentation: ug
keywords: ejwaitingpopup, waitingpopup, angularjs waitingpopup 
---

# Appearance and Styling 

## Custom Text

**WaitingPopup** control provides support for Custom Text to mention any message inside the pop-up panel. You can specify a custom text through the [text](https://help.syncfusion.com/api/js/ejwaitingpopup#members:text) property that displays when the **WaitingPopup** is loading.

The following steps explains you the configuration of the custom text for **WaitingPopup** control.

 In the **HTML** page, add a **&lt;div&gt;** element to render **WaitingPopup** widget.

{% highlight html %}

<div class="control">
 <div id="waitingPopUp" ej-waitingpopup e-showoninit="true" e-text="Loading... Please wait..."></div>
</div>

{% endhighlight %}

Add the following styles to render **WaitingPopup** widget.

{% highlight css %}

<style type="text/css" class="cssStyles">
   #waitingPopUp {
       height: 320px;
       width: 600px;
   }
</style>

{% endhighlight %}

Execute the above code to render the following output.

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png) 

## Template

We can customize the appearance of **WaitingPopup** widget using [template](https://help.syncfusion.com/api/js/ejwaitingpopup#members:template) support which is used to include the **HTML** content instead of the default image.

The following steps explains that how to display a text and image using template for **WaitingPopup** control.

 In the **HTML** page, add a **&lt;div&gt;** element to configure **WaitingPopup** widget.


{% highlight html %}

<div class="control">
    <div id="waitingPopUp" ej-waitingpopup e-cssclass="customcss" e-showoninit="true" e-template="#content"></div>
</div>  

{% endhighlight %}

 Add customized template for **WaitingPopup** control using the following code example.

{% highlight html %}

<div id="content">
   <div class="block">
      <div class="logo"></div>
      <div class="txt">
         <p>Create cutting edge </p>
         <p><b>HTML5</b> web application </p>
         <p>with ease </p>
      </div>
   </div>
   <div class="loader"></div>
</div>

{% endhighlight %}

Initialize the **WaitingPopup** with custom template using the following code example.

{% highlight js %}

angular.module('WaitingPopupApp', ['ejangular'])
.controller('WaitingPopupCtrl', function ($scope) {
    $scope.template = "#content";
});

{% endhighlight %}

In **CSS**, you can configure the custom styles for **WaitingPopup**.


N> Images for this sample are available ‘installed sample location /images/waitingPopup’ and we need to define images in mentioned CSS. Henceforth the images will display.

{% highlight css %}

<style type="text/css" class="cssStyles">
   #waitingPopUp {
       height: 320px;
       width: 600px;
       margin: 0 auto;
   }
   .block {
    height: 76px;
   }
   .logo {
       background-image: url("../images/waitingPopup/js_logo.png");
       float: left;
       height: 100%;
       width: 77px;
       margin-right: 15px;
   }
   .txt {
       float: left;
       font-size: 17px;
       height: 100%;
       text-align: left;
   }
   .txt p {
       margin: 0;
   }
   .loader {
       background: url("../images/waitingPopup/load_light.gif") no-repeat scroll -5px 18px transparent;
       height: 40px;
       width: 100%;
   }
   #content {
       cursor: default;
       height: 112px;
       width: 275px;
   }
</style>

{% endhighlight %}

Execute the above code to render the following output.

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png) 

## CSS Class

You can use the **CSS** class to customize the **WaitingPopup** control appearance. Define a **CSS** class as per requirement and assign the class name to [cssClass](https://help.syncfusion.com/api/js/ejwaitingpopup#members:cssclass) property.

The following steps allows you to configure **CSS** class for an auto-complete textbox.

 In the **HTML** page, add a **&lt;div&gt;** element to configure **WaitingPopup** widget.

{% highlight html %}

<div class="control">
   <div id="waitingPopUp" ej-waitingpopup e-cssclass="customcss" e-showoninit="true" e-text="Loading.. Please wait..."></div>
</div>  

{% endhighlight %}

Define CSS class for customizing the WaitingPopup widget.

{% highlight css %}

<style type="text/css" class="cssStyles">
   /*Customize the panel property*/
   #waitingPopUp {
       height: 320px;
       width: 600px;
       margin: 0 auto;
   }
   /* Customize the WaitingPopup */
  .customcss{
    background-color: darkred;
    font-style: italic;
    font-weight: bolder;
    opacity: 0.5;		
    color: white;
  }
</style>

{% endhighlight %}


The following screenshot displays the output for the above code.

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png) 