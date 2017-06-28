---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: Angular-1
control: TagCloud
documentation: ug
keywords: ejtagcloud, tagcloud, angularjs tagcloud
---

# Appearance and Styling

## Minimum and maximum Font size

The **TagCloud** content can be set to different font sizes from minimum to maximum based on its frequency values. By default, [minFontSize](https://help.syncfusion.com/api/js/ejtagcloud#members:minfontsize) is “10px” and [maxFontSize](https://help.syncfusion.com/api/js/ejtagcloud#members:maxfontsize) is “40px”, using these properties you can customize the minimum and maximum font sizes.

### Customizing font sizes of TagCloud

Refer to the following code to configure font sizes for a **TagCloud**.

{% highlight html %}

 <div id="techweblist" ej-tagcloud e-datasource="dataList" e-minfontsize="20px" e-maxfontsize="50px" e-titletext="Tech Sites"></div>

{% endhighlight %}

The following screenshot illustrates the **TagCloud** control with customized font sizes.

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png) 


## Tag format

You can set the **TagCloud** content display format using **format** property. By default format is set to cloud, that displays content in **TagCloud**. You can set the format as list to display the content in linear format.

### Defining Cloud and List format

Refer to the following code to configure format option for a **TagCloud**.

{% highlight html %}

<table>
<tr>
<td>
<span>Tag format cloud</span>
<div id="techwebcloud" ej-tagcloud e-datasource="dataList" e-format="list" e-titletext="Tech Sites List"></div>
</td>
<td>
<span>Tag format list</span>
<div id="techweblist" ej-tagcloud e-datasource="dataList" e-format="cloud" e-titletext="Tech Sites Cloud"></div>
</td>
</tr>
</table>

{% endhighlight %}

The following screenshot illustrates the **TagCloud** control with customized formats.

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png) 


## Theme

You can control the style and appearance of **TagCloud** based on CSS classes. To apply styles to the **TagCloud** control, you can refer two files, **ej.widgets.core.min.css** and **ej.theme.min.css**. When you refer **ej.widgets.all.min.css** file, it is not necessary to include the files **ej.widgets.core.min.css** and **ej.theme.min.css** in your project**,** as **ej.widgets.all.min.css** is the combination of these two. 

By default, there are 12 themes support available for **TagCloud** control namely,

* default-theme
* flat-azure-dark
* fat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark

## CssClass

You can use the CSS class to customize the **TagCloud** appearance. Any of the CSS properties can be used to modify look and feel of tag cloud based on the requirement. Define a **CSS** class as per requirement and assign the class name to [cssClass](https://help.syncfusion.com/api/js/ejtagcloud#members:cssclass) property.

### Configure TagCloud using CSS class

Refer to the following code to configure **CSS** class for **TagCloud**.

{% highlight html %}

<div id="techweblist" ej-tagcloud e-datasource="dataList" e-titletext="title" e-cssclass="CustomCss"></div>

{% endhighlight %}

{% highlight javascript %}

var list = [
{ text: "Google", url: "http://www.google.co.in", frequency: 12 },
    { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },
    { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },
    { text: "Bxslider", url: "http://bxslider.com/examples", frequency: 2 },
    { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },
    { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },
    { text: "Blogspot", url: "http://www.blogspot.com/", frequency: 8 },
    { text: "Valleywag", url: "http://valleywag.gawker.com/", frequency: 6 },
    { text: "WOWslider", url: "http://wowslider.com", frequency: 9 },
    { text: "W3schools", url: "http://www.w3schools.com/", frequency: 2 }
];
angular.module('tagCloudApp', ['ejangular'])
.controller('TagCloudCtrl', function ($scope) {
    $scope.dataList = list;
    $scope.title = "Tech Sites";
});
    
{% endhighlight %}

Define CSS class for customizing the **TagCloud** widget.

{% highlight css %}

<style type="text/css" class="cssStyles">
        /* Customize the TagCloud div element */
        .CustomCss
        {
            background-color: #DDC;
            width: 400px;
        }
        /* Customize the TagCloud header element */        
        .CustomCss .e-header.e-title {
            text-align: center;
            font-weight: bold;
        }
</style>


{% endhighlight %}

The following screenshot illustrates the **TagCloud** with customized CSS class,

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)