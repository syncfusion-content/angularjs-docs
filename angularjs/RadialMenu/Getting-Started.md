---
layout: post
title: Syncfusion Radial Menu Getting-Started
description: getting started
platform: AngularJS
control: RadialMenu
documentation: ug
---

# Getting Started

This section helps to understand the getting started of the RadialMenu component for AngularJS.

![Getting Started](Getting_Started_images/getting-started_img1.png)

## Adding dependencies



The following steps guide you to add a **RadialMenu** component.

1. Create an **HTML** file and add required scripts and CSS files for rendering Essential JavaScript component as given in the [Getting Started](https://help.syncfusion.com/js/angularjs).

2. In addition to it for AngularJS implementation, refer the “angular.min.js” and “ej.widgets.angular.min.js” files.

{% highlight html %}

    <html ng-app="radialmenuApp">
    <head>
    <title>Simple RadialMenu</title>
    <!-- Add Scripts and CSS for rendering Essential JS components --> 

        <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
        <script src="[http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    </head>
    <body ng-controller="RadialMenuCtrl">
            <!-- Add RadialMenu component Here -->
            <div id="radialSliderMenu" ej-radialmenu> <div>
    </body>
    </html>

{% endhighlight %}

## Component initialization

        1. Initialize the ng-app and ng-controller for the application. For adding RadialMenu component, you have to use **ej-radialmenu** directive to corresponding element.

        2. Now initialize the control using angular module in script section



{% highlight javascript %}

    angular.module(radialmenuApp, ['ejangular']) .controller('RadialMenuCtrl', function ($scope){});

{% endhighlight %}

## Configuring properties



Declare the RadialMenu properties with prefix “e- “, refer the following code,

{% highlight html %}

    <div id="radialSliderMenu" ej-radialmenu e-imageClass="imageclass" e-backImageClass="backimageclass" e-targetElementId="targetId" style="display:none;">

    </div>

{% endhighlight %}


Note: All the Syncfusion widget’s properties are defined using e- prefix followed by the property name. You can find the complete API list from the [API reference](https://help.syncfusion.com/js/api/ejradialmenu)

## Image and text configuration



You can set the images for each item by giving the image URL with the [`data-ej-imageurl`] attribute in the inner list element and text with **data-ej-text** attribute. Refer to the following code example. 



{% highlight html %}

    <div id="radialSliderMenu" ej-radialmenu e-imageClass="imageclass" e-backImageClass="backimageclass" e-targetElementId="targetId" style="display:none;">

        <ul>
        <li data-ej-imageurl="content/images/RadialMenu/font.png" data-ej-text="Bold"></li>

        <li data-ej-imageurl="content/images/RadialMenu/f1.png" data-ej-text="Italic"></li>
        <li data-ej-imageurl="content/images/RadialMenu/redo.png" data-ej-text="Redo" 
    data-ej-enabled="false"></li>
        <li data-ej-imageurl="content/images/RadialMenu/undo.png" data-ej-text="Undo" 
    data-ej-enabled="false"></li>
    </ul>        
        </div>

{% endhighlight %}



Refer to the following code example to add target content to the **RadialMenu**.

{% highlight html %}

    <div id="radialtarget4" class="content-container-fluid">
            <div class="row">
                    <div class="cols-sample-area">
                            <textarea id="rteSample4"  ej-rte e-rows="10" e-cols="70" e-minWidth="10px" e-change="rteChange" e-select="radialShow" e-showToolbar="false" e-showContextMenu="false">
                            <p>Model-view-controller (MVC) is a software architecture pattern which separates the representation of information from the user's interaction with it.
                            The model consists of application data, business rules, logic, and functions. A view can be any output representation of data, such as a chart or a diagram.
                            Multiple views of the same data are possible, such as a bar chart for management and a tabular view for accountants.
                            The controller mediates input, converting it to commands for the model or view.The central ideas behind MVC are code reusabil7ity and in addition to dividing the application into three kinds of components, the MVC design defines the interactions between them.</p>

                            <p>A controller can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). It can also send commands to the model to update the model's state (e.g., editing a document).</p>

                            <p>A model notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.</p>

                            <p>A view requests from the model the information that it needs to generate an output representation to the user.</p>

                            </textarea>
                        </div>
                    </div>
        </div>

{% endhighlight %}


Add the following styles in your code.



{% highlight css %}

        #radialSliderMenu{
                display:table;       
                margin:auto;
            }    
        #radialtarget4{
                margin-left: 200px;
                width: 900px;
                height: 400px;
            }
        .e-radialmenu .imageclass {
                    background-image: url(content/images/RadialMenu/settings.png);
                }

        .e-radialmenu .backimageclass {
                background-image: url(content/images/RadialMenu/Back_button.png);
            }

{% endhighlight %}

## Displaying RadialMenu

After initializing the RadialMenu control, you can set its target content by using scope variable in script as follows.

{% highlight javascript %}

        var rteObj, rteElement = $("#rteSample4"), radialElement = $('#radialSliderMenu'), action = 0, forRedo = 0;

    angular.module(radialmenuApp, ['ejangular'])
                    .controller('RadialMenuCtrl', function ($scope,$compile) {
            $scope.targetId = "radialtarget4";	
        });

        $(function(){
            rteObj = $("#rteSample4").data("ejRTE");

        });

{% endhighlight %}


You can display the **Radial Menu** by performing desired action on the target content while selecting the text inside the target. Therefore, call the **radialShow** method in the select action of the content. Refer to the following code example and add it to the script.

{% highlight javascript %}

        function radialShow(e) {

            var target = $("#radialtarget4"), radialRadius = 150, radialDiameter = 2 * radialRadius,
                        // To get Iframe positions
                        iframeY = target.offset().top + e.event.clientY, iframeX = target.offset().left + e.event.clientX,
                        // To set Radial Menu position within target
                        x = iframeX > target.width () - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
                        y = iframeY > target.height () - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
                    radialElement.ejRadialMenu("setPosition", x, y);
                    radialElement.css("display","block");
                    $('iframe').contents().find('body').blur();
        }

{% endhighlight %}

Run the above code and select any text inside the target. The settings icon is displayed. Click that icon to render the following output.

![Adding dependencies](Getting_Started_images\getting-started_img2.png)

## RadialMenu item functionalities

You can set the functionalities for each item and define click function by using **data-ej-click** attribute. Refer to the following code example. Define the click function for Radial Menu component items as follows.

{% highlight html %}

    <div id="radialSliderMenu" ej-radialmenu e-imageClass="imageclass" e-backImageClass="backimageclass" e-targetElementId="targetId" style="display:none;">

        <ul>
                <li data-ej-imageurl="content/images/RadialMenu/font.png" data-ej-text="Bold" 
    data-ej-click="bold"></li>

                <li data-ej-imageurl="content/images/RadialMenu/f1.png" data-ej-text="Italic" 
    data-ej-click="italic"></li>
                <li data-ej-imageurl="content/images/RadialMenu/redo.png" data-ej-text="Redo" 
    data-ej-click="redo" data-ej-enabled="false"></li>
                <li data-ej-imageurl="content/images/RadialMenu/undo.png" data-ej-text="Undo" 
    data-ej-click="undo" data-ej-enabled="false"></li>
    </ul>        
    </div>

{% endhighlight %}

Refer to the following code example to add click functions for RadialMenu items.

{% highlight javascript %}

       function bold(e) {
            rteObj.executeCommand("bold");
            data = rteObj._getSelectedHtmlString() ? true : false;
            if (data) action += 1;
            forRedo = action;
            radialElement.focus();
        }
        function italic(e) {
            rteObj.executeCommand("italic");
            data = rteObj._getSelectedHtmlString() ? true : false;
            if (data) action += 1;
            forRedo = action;
            radialElement.focus();
        }
        function undo(e) {
            rteObj.executeCommand("undo");
            action -= 1;
            if (action == 0)
                radialElement.ejRadialMenu("disableItem", "Undo");
            radialElement.ejRadialMenu("enableItem", "Redo");
            radialElement.focus();
        }
        function redo(e) {
            rteObj.executeCommand("redo");
            action += 1;
            if (forRedo == action) radialElement.ejRadialMenu("disableItem", "Redo");
            radialElement.ejRadialMenu("enableItem", "Undo");
            radialElement.focus();
        }

{% endhighlight %}

Run the above code and select any text inside the target. The settings icon is displayed. Click that icon to render the RadialMenu component. Click **bold** item in Radialmenu component, to render the following output.

![RadialMenu item functionalities](Getting_Started_images\Getting_Started_img3.png)







