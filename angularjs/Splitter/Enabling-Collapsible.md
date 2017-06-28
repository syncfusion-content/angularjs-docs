---
layout: post
title: Enabling-Collapsible
description: enabling collapsible
platform: Angular-1
control: Splitter
documentation: ug
---

# Configure Collapsible and Expandable

The **Splitter** provides you the option to enable or disable the pane collapse functionality. You can click the icon in Split bar to collapse or expand the corresponding pane element in Splitter. Setting the **e-collapsible** property to **“false”** disables the pane collapse functionality in the Splitter component. 

## Enabling Collapsible

The following steps explain the implementation of the collapsible option in Splitter.

In the HTML page set the **&lt;div&gt;** element to render Splitter component.

{% highlight html %}

    <div id="splitter" ej-splitter e-properties="proper" e-height="280" e-width="600">
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

Define the **e-collapsible** property as “true” in angular module in script section.

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
            .controller('SplitterCtrl', function ($scope) {  
    $scope.proper = [{collapsible: true}];
    })

{% endhighlight %}

The output of the splitter when **collapsible** property is set to **true** as follows,

![](Enabling-Collapsible_images\Enabling-Collapsible_img1.png) 

The output for Splitter when **collapsible** is **“false”** as follows,

![](Enabling-Collapsible_images\Enabling-Collapsible_img2.png) 

## Disable Expandable

The following steps explain the implementation of **e-expandable** option in splitter.

In the **HTML** page set the **&lt;div&gt;** element to render Splitter component.

{% highlight html %}

    <div id="splitter" ej-splitter e-properties="proper" e-height="280" e-width="600">
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
                Essential JavaScript Grid offers full featured a Grid control with extensive support for Grouping and the display of hierarchical data.
            </div>
        </div>
    </div>

{% endhighlight %}

Define the **e-expandable** property as **“false”** in angular module in script section.

{% highlight javascript %}

    angular.module('syncApp', ['ejangular'])
            .controller('SplitterCtrl', function ($scope) {  
                $scope.proper = [{ expandable: false }, { collapsible: false }];
    })

{% endhighlight %}

The output of the splitter when expandable property is set to false as follows,

![](Enabling-Collapsible_images\Enabling-Collapsible_img3.png)