---
layout: post
title: Template Support.
description: Template Support
platform: js
control: Radial Menu
documentation: ug
---

## Template Support

 Template support for RadialMenu items will allow you to use any type of [\<svg\>](https://developer.mozilla.org/en-US/docs/Web/SVG/Element#SVG_elements) permittable tags inside our template. Here for example, using this template support you can use the SVG icons in Radial Menu instead of image tags. To use SVG icons in RadialMenu, you need to use [e-prependto](https://help.syncfusion.com/api/js/ejradialmenu#members:items-prependTo) property.

 ### Add SVG to item Icon

Using SVG icon will optimize the icons quality and to reduce space occupation by normal images and svg images are scalable and zoomable. Define the text element for SVG with x and y position and code for rendering the font icons. Assign the SVG element ID to e-prependto property.

Add the following code in the html page,

{% highlight html %}

    <div ng-controller="RadialMenuCtrl">
         <div id="contentDiv">
             <div id="radialtarget1" class="content-container-fluid">
                 <div class="row">
                     <div class="cols-sample-area">
                       <textarea ej-rte id="rteSample1" rows="10" cols="70" style="height: 440px" e-width="100%" e-minwidth="10px" e-change="rteChange" e-select="radialShow" e-showtoolbar="false" e-showcontextmenu="false">
                           <p>
                            Model–view–controller (MVC) is a software architecture pattern which separates the representation of information from the user's interaction with it.
                            The model consists of application data, business rules, logic, and functions. A view can be any output representation of data, such as a chart or a diagram.
                            Multiple views of the same data are possible, such as a bar chart for management and a tabular view for accountants.
                            The controller mediates input, converting it to commands for the model or view.The central ideas behind MVC are code reusability and in addition to dividing the application into three kinds of components, the MVC design defines the interactions between them.
                            </p>

                            <p>A controller can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). It can also send commands to the model to update the model's state (e.g., editing a document).</p>

                             <p>A model notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.</p>

                            <p>A view requests from the model the information that it needs to generate an output representation to the user.</p>
                         </textarea>
                         </div>
                    </div>
                 </div>

            <ej-radialmenu id="defaultradialmenu" e-targetelementid="radialtarget1">
               <e-items>
                <e-item e-prependto="#template1" e-text="Bold" e-click="bold"></e-item>
                <e-item e-prependto="#template2" e-text="Italic" e-click="italic"></e-item>
                <e-item e-prependto="#template3" e-text="Redo" e-click="redo" e-enabled="false"></e-item>
                <e-item e-prependto="#template4" e-text="Undo" e-click="undo" e-enabled="false"></e-item>
               </e-items>
            </ej-radialmenu>
             </div>

         <svg id="template1" style="display: none" xmlns="http://www.w3.org/2000/svg">
              <text x="210" y="100">&#xe636;</text>
         </svg>
         <svg id="template2" style="display: none" xmlns="http://www.w3.org/2000/svg">
             <text x="210" y="218">&#xe635;</text>
         </svg>
         <svg id="template3" style="display: none" xmlns="http://www.w3.org/2000/svg">
              <text x="90" y="215">&#xe606;</text>
         </svg>
         <svg id="template4" style="display: none" xmlns="http://www.w3.org/2000/svg">
              <text x="93" y="100">&#xe607;</text>
         </svg>
    </div>

{% endhighlight %}

Add following code in your script section,

{% highlight javascript %}

syncApp.controller('RadialMenuCtrl', function ($scope, $compile) {

    var rteObj, rteEle = $("#rteSample1"), radialEle = $('#defaultradialmenu'), action = 0, forRedo = 0;
	$("#radialtarget1").parent().css("position", "relative");
    $scope.success = function (args) {
        $compile(args.content)($scope);
    };


    $scope.radialShow = function (e) {
        var target = $("#radialtarget1"), radialRadius = 150, radialDiameter = 2 * radialRadius,
            // To get Iframe positions
            iframeY = e.event.clientY, iframeX = e.event.clientX,
            // To set Radial Menu position within target
            x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
            y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
            radialEle.ejRadialMenu("setPosition", x, y);
            radialEle.focus();
            rteObj = $("#rteSample1").data("ejRTE");
    }
    $scope.rteChange = function (e) {
        radialEle.ejRadialMenu("enableItem", "Undo");
    }
    $scope.bold = function (e) {
        rteObj.executeCommand("bold");
        data = rteObj._getSelectedHtmlString() ? true : false;
        if (data) action = 1;
        forRedo = action;
        radialEle.focus();
    }
    $scope.italic = function (e) {
        rteObj.executeCommand("italic");
        data = rteObj._getSelectedHtmlString() ? true : false;
        if (data) action = 1;
        forRedo = action;
        radialEle.focus();
    }
    $scope.undo = function (e) {
        rteObj.executeCommand("undo");
        action -= 1;
        if (action == 0)
            radialEle.ejRadialMenu("disableItem", "Undo");
        radialEle.ejRadialMenu("enableItem", "Redo");
        radialEle.focus();
    }
    $scope.redo = function (e) {
        rteObj.executeCommand("redo");
        action = 1;
        if (forRedo == action) radialEle.ejRadialMenu("disableItem", "Redo");
        radialEle.ejRadialMenu("enableItem", "Undo");
        radialEle.focus();
    }
})

{% endhighlight %}

Add following code in your style section,

{% highlight css %}

    <style>
    .e-radialmenu .imageclass {
        background-image: url(../content/images/RadialMenu/settings.png);
    }

    @font-face {
        font-family: 'ej-webfont';
        font-weight: normal;
        font-style: normal;
        font-size: 20px;
    }

    .e-radialmenu .e-abs.e-radialshow, .e-radialmenu .e-abs.e-scaleshow {
        /* use !important to prevent issues with browser extensions that change fonts */
        font-family: 'ej-webfont' !important;
        speak: none;
        font-size: 20px;
        font-style: normal;
        font-weight: normal;
        font-variant: normal;
        text-transform: none;
        line-height: 1;
        -webkit-font-smoothing: antialiased;
        /* Better Font Rendering =========== */
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
    }

    </style>

{% endhighlight %}

The following screenshot illustrates the output,

![](template-support\img1.png)

     N> This is the example sample for SVG icon support for Radial Menu.Like wise you can add any SVG element to it, but you need to customize and position the element individually.  