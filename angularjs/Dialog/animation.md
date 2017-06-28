---
layout: post
title: animation
description: animation
platform: AngularJS
control: Angular- Dialog
documentation: ug
---

## Animation

The Dialog component can be animated while opening and closing the dialog.

We can specify the effect and the duration for the animation. The two types of effects of Dialog are slide and fade. We can configure these settings separately for open and close dialog actions.



{% highlight html %}


<div id="dialog" ej-dialog e-title="Dialog" e-actionbuttons="Icons" e-animation-show="Effect" e-animation-show="Duration" e-animation-hide="Effects" e-animation-hide="Duration">
         <p>This is a simple dialog</p>
    </div>
    <script>
        angular.module('dialogApp', ['ejangular'])
         .controller('DialogCtrl', function ($scope) {
             $scope.Icons = ["close", "maximize", "minimize"]
             $scope.Effect="slide",
             $scope.Duration=500,
             $scope.Effects="fade"
             $scope.Duration= 500           
         });
    </script>


{% endhighlight %}



![Animation](animation_images\animation_img1.png)


### Loading Dialog content

By default, the content inside the Dialog element is simply the user given content. But also, we can render the Dialog’s component content through the following ways.

1. AJAX

2. Using iframe

3. iImage

This settings can be specified through **e-contenttype** property.


#### AJAX

We can load the content through AJAX by setting the **e-contenttype** property as ajax


{% highlight html %}
 <div id="dialog" ej-dialog e-title="Dialog" e-contenturl="dialogcontent.html" e-contenttype="ajax"/>;
{% endhighlight %}


The content of that dialogcontent.html file is below:

**&lt;div id="content"&gt;** This content is loaded via AJAX request. **&lt;/div&gt;**

![Load content](animation_images\ajax_img1.png)

We can handle the AJAX request’s success and failures through the events “e-ajaxsuccess” and “e-ajaxerror” events respectively. See also ajaxSuccess and ajaxError

The previous example is modified as below to handle the success and failure events.

{% highlight html %}
 <div id="dialog" ej-dialog e-title="Dialog" e-contenturl="dialogcontent.html" e-contenttype="ajax" e-ajaxsuccess="onSuccess" e-ajaxerror="onError"/>;
{% endhighlight %}






#### Iframe



We can also load the content in iframe by setting the **e-contenttype** property as iframe.





{% highlight html %}


  <div id="dialog" ej-dialog e-title="Dialog" e-contenturl="iframecontent.html" e-contenttype="iframe" ></div>


{% endhighlight %}



![](animation_images\iiframe_img1.png)


#### Image 

We can also load an image as the content by setting the **e-contenttype** property as image



&lt;div id="dialog" ej-dialog e-title="Dialog" e-contenturl=" http://js.syncfusion.com/demos/web/content/images/twitter.jpg" e-contenttype="image" &gt;&lt;/div&gt;



![](animation_images\iimage-_img1.png)



