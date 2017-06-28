---
layout: post
title: Header-Customization
description: header customization
platform: AngularJS
control: Accordion 
documentation: ug
keywords: ejaccordion, accordion, angularjs accordion
---

# Header Customization

## Collapsible

**Accordion** widget allows you to set Collapsible state for an **Accordion** header by setting the collapsible property as true. It is used to expand and collapse accordion contents. By default [collapsible](https://help.syncfusion.com/api/js/ejaccordion#members:collapsible) property is set to **false**.

### Enable Collapsible settings

The following steps will explain to enable Collapsible state for **Accordion**.

In an HTML page, define a div element that is a container for Accordion widget and add the contents correspondingly.

{% highlight html %}
    
<div id="accordion" style="width: 500px" ej-accordion e-collapsible="true">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</div>

{% endhighlight %}

The following screenshot illustrates the Accordion control with collapsible headers.


![](Header-customization_images/Header-customization_img1.png) 

## Enable Header Expand

**Accordion** widget provides support to set the event, where the headers should expand and collapse. The default events are mouseout, mouseover, and click.

### Configure header expand event

Add the below code in order to set the mouseout event for accordion which will be triggered while expanding the header.

{% highlight html %}

  
<div id="accordion" style="width: 500px" ej-accordion e-events="mouseout">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</div>


{% endhighlight %}

Output for Accordion control that expands header on mouseout event is as follows.


![](Header-customization_images/Header-customization_img2.png) 

## Set Selected Header

### Single selection

Using [selectedItemIndex](https://help.syncfusion.com/api/js/ejaccordion#members:selecteditemindex) property you can modify the expanded panel when the control is rendered. By default **selectedItemIndex** is ‘0’ that always activate the first **Accordion** panel.

### Specify the selected item in Accordion panel

The following steps will explains the configurating selected item for **Accordion**.

In an HTML page, define a div element that is a container for Accordion widget and set the selectedItemIndex property as like the below code.

{% highlight html %}
  
<div id="accordion" style="width: 500px" e-selecteditemindex="1">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</div>

{% endhighlight %}

Output for Accordion control with the selected item by index is as follows.

![](Header-customization_images/Header-customization_img3.png) 

## Multiple Selection

In **Accordion** widget, you can select multiple panel items using [selectedItems](https://help.syncfusion.com/api/js/ejaccordion#members:selecteditems) property. It takes array of indices that needs to be selected on rendering the control. As you need to select multiple items, you can set [enableMultipleOpen](https://help.syncfusion.com/api/js/ejaccordion#members:enablemultipleopen) to **true**.

### Configure multiple selection in Accordion panel

The following steps explains to configure selected items for **Accordion**.

In an HTML page, define a &lt;div&gt; element that is a container for  Accordion widget and add the contents correspondingly

{% highlight html %}

  
<div id="accordion" style="width: 500px" ej-accordion e-enablemultipleopen="true" e-selecteditems="selecteditems">
    <h3>
        <a href="#">Orubase</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Orubase is the only mobile application development framework built especially for developing complex line-of-business mobile applications targeting iOS, Android, and Windows Phone platforms in the shortest possible timeframe.
    </div>
    <h3>
        <a href="#">WinRTXAML</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Essential Studio for WinRT contains all the controls you need to build line-of-business tablet applications including grid, chart, map, tree map, SSRS report viewer, rich-text editor, pdf viewer, gauges, barcode, editors, and much more. It also includes a unique set of controls for reading and writing Excel, Word, and PDF documents in Windows store apps.
    </div>
    <h3>
        <a href="#">Metro Studio</a>
    </h3>
    <div>
        <!-- add accordion contents here to load contents under this header -->
        Syncfusion Metro Studio is a collection of over 2500 Metro-style icon templates that can be easily customized to create thousands of unique Metro icons.
    </div>
</div>


{% endhighlight %}

{% highlight javascript %}

   angular.module('AccordionApp', ['ejangular'])
    .controller('AccordionCtrl', function ($scope) {
        $scope.selecteditems = [0, 2];
   });

{% endhighlight %}

Output for Accordion control with the multiple selected items is as follows.


![](Header-customization_images/Header-customization_img4.png)