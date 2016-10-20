---
layout: post
title: getting-started
description: getting started
platform: Angular-1-JS
control: navigation drawer
documentation: ug
---

# Getting Started

This section helps to get started of the Navigation Drawer component for AngularJS. 

## Adding dependencies

The following steps guide you to add a **Navigation Drawer** component.

  1. Create an **HTML** file and add required scripts and CSS files for rendering Essential JavaScript component as given in the [Getting Started](https://help.syncfusion.com/js/angularjs).

  2. In addition to it for AngularJS implementation, refer the “angular.min.js” and “ej.widgets.angular.min.js” files.

    {% highlight html %}

        <html ng-app="NavApp">
        <head>
        <title>Simple Navigation Drawer</title>
        <!-- Add Scripts and CSS for rendering Essential JS components --> 

            <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
            <script src="[http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
        </head>
        <body ng-controller="NavCtrl">
                <!-- Add Navigation Drawer component Here -->
            <div id="navpane" ej-navigationdrawer />
        </body>
        </html>

    {% endhighlight %}

## Component initialization

  1. Initialize the ng-app and ng-controller for the application. For adding Navigation Drawer component, you have to use **ej-navigationdrawer** directive to corresponding element.

  2. Now initialize the component using angular module in script section

    {% highlight javascript %}

        angular.module('NavApp', ['ejangular']).controller('NavCtrl', function ($scope) {});

    {% endhighlight %}


## Configuring properties

Declare the navigation drawer properties with prefix “e- “, refer the following code,

{% highlight html %}

    <div id="navpane" class="ang-navigationdrawer" ej-navigationdrawer
        e-type="overlay" e-enablelistview=true e-listviewsettings-width="220" e-listviewsettings-height="100%"
        e-listviewsettings-selecteditemindex=0 e-position="normal">
        <ul>
            <li data-ej-text="Home"></li>
            <li data-ej-text="People"></li>
            <li data-ej-text="Profile"></li>
        </ul>
    </div>

{% endhighlight %}

Create the target element as follows to display the list items by clicking target icon.

{% highlight html %}

    <div id="targetPane">
        <div class="e-lv">
            <div class="e-header">
                <div id="butdrawer" class="drawericon e-icon">
                </div>
            </div>
        </div>
    </div>

{% endhighlight %}


To set the target icon image and position it use the below mentioned styles .

{% highlight css %}

    <style>
      .drawericon {
            background-position: center center;
            background-repeat: no-repeat;
            height: 45px;
            width: 32px;
            background-size: 100% 100%;
            padding-right: 10px;
        }

        .drawericon:before {
            content: "\e76b";
            font-size: 24px;
            height: 26px;
            line-height: 24px;
        }

        #targetPane {
            height: 220px;
            position: relative;
            padding: 0px;
            overflow: hidden;
            margin: 0px;
        }
    </style>

{% endhighlight %}

![](Getting-Started_images\getting-started_img1.png)

You can open the list items by clicking on target element using the targetId property. 

{% highlight html %}

    <div id="navpane" class="ang-navigationdrawer" ej-navigationdrawer e-targetid="butdrawer" e-enablelistview=true e-listviewsettings-width="220" e-listviewsettings-height="100%"
            e-listviewsettings-selecteditemindex=0 e-position="normal">
        <ul>
            <li data-ej-text="Home"></li>
            <li data-ej-text="People"></li>
            <li data-ej-text="Profile"></li>
        </ul>
    </div>

{% endhighlight %}

![](Getting-Started_images\getting-started_img2.png)

You can set the images for list items of the Navigation Drawer by using the ImageClass property as follows.

{% highlight html %}

    <div id="navpane" class="ang-navigationdrawer" ej-navigationdrawer e-targetid="butdrawer"
            e-type="overlay" e-direction="left" e-enablelistview=true e-listviewsettings-width="220" e-listviewsettings-height="100%"
            e-listviewsettings-selecteditemindex=0 e-position="normal">
        <ul>
            <li data-ej-imageclass="icon-home" data-ej-text="Home"></li>
            <li data-ej-imageclass="icon-photos" data-ej-text="Photos"></li>
            <li data-ej-imageclass="icon-profile" data-ej-text="Profile"></li>
        </ul>
    </div>
    
{% endhighlight %}

You can set the images with the correct position by using the mentioned styles.

{% highlight css %}

    <style>
    
       #navpane [class*="icon-"] {
           width: 40px;
           height: 29px;
           background-image: url("http://js.syncfusion.com/ug/web/content/drawer/sprite.png");
       }

       .icon-home {
           background-position: 0 1px;
       }

       .icon-profile {
           background-position: 0px -532px;
       }

       .icon-photos {
           background-position: 0 -140px;
       }
            
    </style>

{% endhighlight %}

![](Getting-Started_images\getting-started_img3.png)

You can add desired page content while selecting the options in navigation drawer as follows.

{% highlight html %}

    <!-- Home Page Content-->

    <div id="Home">

        The Home screen allows you to choose the specific content type displayed.

    </div>

    <!-- Profile Page Content-->

    <div id="Profile" style="display: none">

        The Profile page content is displayed.

    </div>

    <!-- Photos Page Content-->

    <div id="Photos" style="display: none">

        The Photos page content is displayed.

    </div>

{% endhighlight %}

You can load the appropriate content for the navigation by using the mouseUp event handler of ListView component.

{% highlight html %}

    <div id="navpane" class="ang-navigationdrawer" ej-navigationdrawer e-targetid="butdrawer"
        e-type="overlay" e-direction="left" e-enablelistview=true e-listviewsettings-width="220" e-listviewsettings-height="100%"
        e-listviewsettings-selecteditemindex=0 e-listviewsettings-mouseup="headChange" e-position="normal">
        <ul>
            <li data-ej-imageclass="icon-home" data-ej-text="Home"></li>
            <li data-ej-imageclass="icon-photos" data-ej-text="Photos"></li>
            <li data-ej-imageclass="icon-profile" data-ej-text="Profile"></li>
        </ul>
    </div>

{% endhighlight %}


In the mouseUp handler,it's display the respective selected item’s content.


{% highlight javascript %}

    $scope.headChange = function (e) {
        $('#Home, #Profile, #Photos').hide(); //Hiding all other contents
        $('#' + e.text).show(); //Displaying the content based on the text of item selected
    }

{% endhighlight %}

Run the above code to render the following output. 

![](Getting-Started_images\getting-started_img4.png)

## Customize Direction

By using this property, you can change the list view open direction. The possible directions are Right, Left and the Left is default value.

{% highlight html %}

    <div id="navpane" class="ang-navigationdrawer" ej-navigationdrawer e-targetid="butdrawer"
        e-type="overlay" e-direction="right" e-enablelistview=true e-listviewsettings-width="220" e-listviewsettings-height="100%"
        e-listviewsettings-selecteditemindex=0 e-listviewsettings-mouseup="headChange" e-position="normal">
        <ul>
            <li data-ej-imageclass="icon-home" data-ej-text="Home"></li>
            <li data-ej-imageclass="icon-photos" data-ej-text="Photos"></li>
            <li data-ej-imageclass="icon-profile" data-ej-text="Profile"></li>
        </ul>
    </div>

{% endhighlight %}

![](Getting-Started_images\getting-started_img5.png)

N> All the Syncfusion component’s properties for AngularJS defined using e- prefix followed by the property name.You can find the complete API list from the [API reference](https://help.syncfusion.com/api/js/ejnavigationdrawer)
