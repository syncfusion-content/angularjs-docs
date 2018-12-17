---
layout: post
title: Syncfusion Splitter Apperance and Styling
description: Apperance and Styling
platform: AngularJS
control: Splitter
documentation: ug
---

# Appearance and Styling

## Html Attributes

You can add styles to Splitter component by using **e-htmlAttributes** option. The following steps explain the implementation of **htmlAttributes** option in the Splitter component.

In the **HTML** page set the corresponding **&lt;div&gt;** elements for outer and inner splitter component.


{% highlight html %}

        <div id="splitter" ej-splitter e-properties="proper" e-orientation="orientation" e-height="280" e-width="600" e-htmlAttributes="htmlAttributes">
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Tools </h3>
                    Essential Tools is an collection of user interface components used to create interactive JavaScript applications.
                </div>
            </div>
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">Grid </h3>
                    Essential JavaScript Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.
                </div>
            </div>
        </div>

{% endhighlight %}

Define **“e-htmlAttributes”** true in angular module in script section.

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
            .controller('SplitterCtrl', function ($scope) {
                $scope.orientation = ej.Orientation.Vertical;
                $scope.proper = [{}, {}];
                $scope.htmlAttributes = { class: "my-class", style: "border:1px solid red" };


{% endhighlight %}

The output for the above code as follows,

![Html Attributes](Appearance-and-Styling_images\Appearance-and-Styling_img1.png) 

## Enabling Responsiveness

The **e-isResponsive** option allows the Splitter component to adapt its rendering based on the parent container where it is actually placed. When this option is set to true, the Splitter component adjusts its height and width based on the outer container.

The following steps explain the implementation of Responsive option in the Splitter component.
In the **HTML** page set the corresponding **&lt;div&gt;** elements for outer and inner splitter component.

{% highlight html %}

    <div id="outersplitter" ej-splitter e-properties="proper" e-width="100%" e-height="280" e-isresponsive="responsive1" e-orientation="orientation">
            <div>
                <div style="padding: 0px 15px;">
                    <h3 class="h3">JavaScript </h3>
                </div>
            </div>
            <div id="innersplitter" ej-splitter e-isresponsive="responsive2">
                <div>
                    <div style="padding: 0px 15px;">
                        <h3 class="h3">Tools </h3>
                        Essential Tools is an collection of user interface components used to create interactive
                        JavaScript applications.
                    </div>
                </div>
                <div>
                    <div style="padding: 0px 15px;">
                        <h3 class="h3">Grid </h3>
                        Essential JavaScript Grid offers full featured a Grid control with extensive support for
                        Grouping and the display of hierarchical data.
                    </div>
                </div>
            </div>
    </div>

{% endhighlight %}

Define **“e-isResponsive”** true in angular module in script section.

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
            .controller('SplitterCtrl', function ($scope) {
                $scope.proper = [{ paneSize: 60 }];
                $scope.orientation = ej.Orientation.Vertical;
                $scope.responsive1 = true;
                $scope.responsive2 = true;
    })

{% endhighlight %}

## Animation Support

**Splitter** provides you animation support when you expand or collapse the pane. The animation speed can be modified by using the **e-animationSpeed** property that has values in milliseconds.

### Enabling Animation with Animation Speed

The following steps explain the implementation of **e-enableAnimation** option in the Splitter component.

In the **HTML** page set the corresponding **&lt;div&gt;** element for rendering Splitter component.

{% highlight html %}

    <div id="splitter" ej-splitter e-width="600" e-height="280" e-enableanimation="animation" e-animationspeed="speed" e-properties="proper">
        <div>
            <div style="padding: 0px 15px;">
                <h3 class="h3">Tools </h3>
                Essential Tools is an collection of user interface components used to create interactive
                ASP.NET MVC applications.
            </div>
        </div>
        <div>
            <div style="padding: 0px 15px;">
                <h3 class="h3">Grid </h3>
                Essential MVC Grid offers full featured a Grid control with extensive support for
                Grouping and the display of hierarchical data.
            </div>
        </div>
    </div>

{% endhighlight %}

Define **“e-animationSpeed”** and **“e-enableAnimation”** properties in angular module in script section.

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
            .controller('SplitterCtrl', function ($scope) {
                $scope.proper = [{}, { collapsible: true }];
                $scope.speed = 300;
                $scope.animation = true;
    })

{% endhighlight %}

The output for **Splitter** when **e-enableAnimation** is “True”. Expanding or collapsing the outer pane in the Splitter produces the animation effect with the animation speed.

![Enabling Responsiveness](Appearance-and-Styling_images\Appearance-and-Styling_img2.png) 

## Dimensions configuration

   You can adjust the splitter size by height, width, maxSize, minSize and paneSize properties.

### Height
   The height of Splitter can be modified by using the **e-height** property. The default value for e-height property is null in Splitter. You can set the e-height property by pixel or percentage values.

### Width

   The width of Splitter can be modified by using the **e-width** property. The default value for e-width property is null in Splitter. You can set the e-width property by pixel or percentage values.

### MaxSize

   Defines the maximum resizable size of the pane when you resize the Splitter component. The default value of **e-maxSize** is null in Splitter. You can set the e-maxSize property by pixel values.

### MinSize

   Defines the minimum resizable size of the pane when you resize the Splitter component. The default value of **e-minSize** is 10px in Splitter. You can set the e-minSize property by pixel values.
### PaneSize

   Defines the pane size in the Splitter component. The default value of **e-paneSize** is 0px in Splitter. You can set the e-paneSize property in pixels or percentage values.

### Resizable

   Defines whether the pane in the Splitter is resizable or not. Setting the **e-resizable** property as “False” disables the resize option to the pane. The default value of e-resizable property is true in Splitter.

   The following steps explain the implementation of Splitter properties.
    
   In the **HTML** page set the **&lt;div&gt;** element for rendering Splitter component.
    
   {% highlight html %}
   
    <div id="splitter" ej-splitter e-width="600" e-height="280" e-properties="proper">
        <div>
            <div style="padding: 0px 15px;">
                <h3 class="h3">Tools </h3>
                Essential Tools is an collection of user interface components used to create interactive ASP.NET MVC applications.
            </div>
        </div>
        <div>
            <div style="padding: 0px 15px;">
                <h3 class="h3">Grid </h3>
                Essential MVC Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.
            </div>
        </div>
    </div>
   
   {% endhighlight %}
   
   Define **“e-Resizable”** property set as true in angular module in script section.
   
   {% highlight javascript %}
   
    angular.module('syncApp', ['ejangular'])
            .controller('SplitterCtrl', function ($scope) {
                $scope.proper = [{}, { collapsible: true, minSize: 100, maxSize: 800, paneSize: 300, resizable: true }];
    })

   {% endhighlight %}
   
## Theme

**Splitter** component style and appearance can be controlled based on CSS classes. To apply styles to the Splitter component, refer 2 files namely: **ej.widgets.core.min.css** and **ej.theme.min.css**. If the file ej.web.all.min.css is referred, then it is not necessary to include the files **ej.widgets.core.min.css** and **ej.theme.min.css** in your project, as **ej.web.all.min.css** is the combination of these two.
By default, there are 13 themes support available for Splitter component namely

* flat-azure
* flat-azure-dark
* flat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* bootstrap-theme
* high-contrast-01
* high-contrast-02
* material
* office-365

### Customize using CSS class
The CSS properties can be customized by using **e-cssClass** in the Splitter component. The following steps explain the implementation of e-cssClass option in the Splitter component.
In the **HTML** page set the corresponding **&lt;div&gt;** element for rendering Splitter component.

{% highlight html %}

    <div id="splitter" ej-splitter e-width="600" e-height="280" e-cssClass="cssClass">
        <div>
            <div style="padding: 0px 15px;">
                <h3 class="h3">Tools </h3>
                Essential Tools is an collection of user interface components used to create interactive
                ASP.NET MVC applications.
            </div>
        </div>
        <div>
            <div style="padding: 0px 15px;">
                <h3 class="h3">Grid </h3>
                Essential MVC Grid offers full featured a Grid control with extensive support for
                Grouping and the display of hierarchical data.
            </div>
        </div>
    </div>

{% endhighlight %}

Define **“e-cssClass”** in angular module in script section.

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
            .controller('SplitterCtrl', function ($scope) {
                $scope.cssClass = "customCSS";
    })

{% endhighlight %}

Customize the **CSS** class by setting CSS properties.

{% highlight css %}

    .customCSS {
        border-color: #661e19;
    }

    /*Customize Splitbar*/
    .customCSS .e-splitbar {
        background-color: #f9c89f;
    }

    /*Customize Splitter pane*/
    .customCSS .e-pane {
        color: #b21010;
        background-color: #f6e492;
    }     

{% endhighlight %}

The output for Splitter after customizing the CSS class.

![Customize using CSS class](Appearance-and-Styling_images\Appearance-and-Styling_img3.png) 





