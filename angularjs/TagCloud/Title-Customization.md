---
layout: post
title: Title-Customization
description: title customization
platform: AngularJS
control: TagCloud
documentation: ug
keywords: ejtagcloud, tagcloud, angularjs tagcloud
---

# Title Customization

## Show title

The **TagCloud** items are displayed with a Title element by default. To hide the title, you can use [showTitle](https://help.syncfusion.com/api/js/ejtagcloud#members:showtitle) property that is true by default.

### How to disable title in TagCloud

Refer to the below code to disable the title in tagcloud.

{% highlight html %}

 <div id="techweblist" ej-tagcloud e-datasource="dataList" e-showtitle="false"></div>

{% endhighlight %}

The following screenshot illustrates a **TagCloud** control when you disable title,

![](Title-Customization_images/Title-Customization_img1.png) 


## Title text

**TagCloud** widget allows you to set a custom title text by using the [titleText](https://help.syncfusion.com/api/js/ejtagcloud#members:titletext) property. By default titleText property is set to string value "Title".

### Defining title text for TagCloud

The following steps explains you on how to configure **titleText** for a **TagCloud**.

Refer to the below code to define the title in tagcloud.

{% highlight html %}

 <div id="techweblist" ej-tagcloud e-datasource="dataList" e-showtitle="true" e-titletext="title"></div>

{% endhighlight %}

{% highlight javascript %}

angular.module('tagCloudApp', ['ejangular'])
.controller('TagCloudCtrl', function ($scope) {
    $scope.title = "Tech Sites";
});

{% endhighlight %}

The following screenshot illustrates the **TagCloud** control with customized title text.

![](Title-Customization_images/Title-Customization_img2.png)


## Title image

**TagCloud** widget provides **titleImage** to set an image for the title. You can set the desired image **URL** to [titleImage](https://help.syncfusion.com/api/js/ejtagcloud#members:titleimage) property.

### Defining title text for TagCloud

The following steps explains you to configure **titleImage** for a **TagCloud**.

Refer to the below code to configure the title image in tagcloud.

{% highlight html %}

<div id="techweblist" ej-tagcloud e-datasource="dataList" e-titleimage="image" e-titletext="title"></div>

{% endhighlight %}

{% highlight javascript %}

var list = [
{ text: "Google", url: "http://www.google.co.in", frequency: 12 },
    { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
    { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
    { text: "Bxslider", url: "http://bxslider.com/examples", frequency: 2 },
    { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
    { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }
];
angular.module('tagCloudApp', ['ejangular'])
.controller('TagCloudCtrl', function ($scope) {
    $scope.title = "Tech Sites";
    $scope.dataList = list;
    $scope.image = "http://js.syncfusion.com/demos/web/images/waitingpopup/js_logo.png";
});

{% endhighlight %}

Using CSS class you can resize the image content as follows.

{% highlight css %}

<style type="text/css">

.e-title-img {
    height:35px;
    width:35px;
}

</style>

{% endhighlight %}

The following screenshot illustrates the **TagCloud** control with customized title image.

![](Title-Customization_images/Title-Customization_img3.png)