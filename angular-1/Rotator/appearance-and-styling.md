---
layout: post
title: appearance and styling
description: appearance and styling
platform: angular-1
control: rotator
documentation: ug
---

## Appearance and Styling

### Adjusting rotator item size

#### Slide width

This e-slidewidth property sets the width of a Rotator Item. The value set to this property is string or number.

#### Slide height

This e-slideheight property sets the height of a Rotator Item. The value set to this property is string or number.



{% highlight html %}
   <ul id="sliderContent" ej-rotator e-slidewidth="500px" e-slideheight="250px">
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/green.jpg" title="green" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snow.jpg" title="snow" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" title="wheat" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" title="tablet" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sea.jpg" title="sea" /></li>
    </ul>
{% endhighlight %}



{% highlight js %}
    <script>
        angular.module('rotatApp', ['ejangular']).controller('RotatCtrl', function ($scope) {
        });
    </script>
{% endhighlight %}



![](appearance and styling_images\slideheight_img1.png)

### Showing Play button

The e-showplaybutton  property enables play / pause button on Rotator. The default value is ‘false’. The value set to this property is Boolean.

{% highlight js %}

<ul id="sliderContent" ej-rotator e-datasource="dataList" e-showplaybutton="true" e-slidewidth="600px" e-slideheight="350px"/>

{% endhighlight %}



![](appearance and styling_images\showingplaybutton_img1.png)

### Showing Navigate button

The e-shownavigatebutton” property turns on or off the slide buttons (next and previous) in the Rotator Items. Slide buttons are used to navigate the Rotator Items. The default value is ‘false’. The value set to this property is Boolean.

{% highlight html %}

<ul id="sliderContent" ej-rotator e-datasource="dataList" e-shownavigatebutton="true" e-slidewidth="600px" e-slideheight="350px"/>

{% endhighlight %}



![](appearance and styling_images\showingnavigatebutton_img1.png)

### Image captions

When the Rotator Item is an image, you can specify a caption for the Rotator Item. The caption text for each Rotator Item is set by using the title attribute of the respective &lt;image&gt; tag. The caption cannot be displayed when multiple Rotator Items are present. The default value is ‘false’ and the property is e-showcaption. 

{% highlight html %}
                    	<ul id="sliderContent" ej-rotator e-datasource="dataList" e-showcaption="true" e-slidewidth="600px" e-slideheight="350px"/>
{% endhighlight %}



![](appearance and styling_images\imagecaptions_img1.png)


### Supported Themes

Rotator control’s style and appearance are controlled based on CSS classes. In order to apply styles to the Rotator component, you can refer 2 files namely, ej.widgets.core.min.css and ej.theme.min.css. When the file ej.widgets.all.min.css is referred, then it is not necessary to include the files ej.widgets.core.min.css and ej.theme.min.css in your project.

By default, there are 16 themes support available for Rotator control as follows,

•	flat-azure
•	flat-azure-dark
•	fat-lime
•	flat-lime-dark
•	flat-saffron
•	flat-saffron-dark
•	gradient-azure
•	gradient-azure-dark
•	gradient-lime
•	gradient-lime-dark
•	gradient-saffron
•	gradient-saffron-dark
•	high-contrast-01
•	high-contrast-02
•	material
•	office-365

### Customize using CSS Class

This property e-cssclass is used to set root class for Rotator control theme. The value set to this property is string type.

{% highlight html %}


<ul id="sliderContent" ej-rotator e-slidewidth="500px" e-slideheight="300px" e-cssclass="flat-lime" >
                             <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snow.jpg" title=" snow " /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/green.jpg" title="f" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" title="wheat" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" title="tablet" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sea.jpg" title="sea" /></li>                        </ul>


{% endhighlight %}

Add the following code in your CSS.

{% highlight css %}


<style>
    .flat-lime {
        background-color: yellowgreen;
    }
</style>


{% endhighlight %}



![](appearance and styling_images\CustomizeusingCSSClass_img1.png)



