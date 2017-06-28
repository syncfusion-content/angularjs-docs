---
layout: post
title: item-customization
description: item customization
platform: Angular-1
control: Radial Menu
documentation: ug
---

# Item Customization

You can customize individual Radial Menu items by using the items properties.

## Adding image and text to RadialMenu Items

The **e-imageUrl** property specifies the URL of the image for the items. **e-text** attribute is used to specify the item text. 

Refer to the following code example.

Define e-imageUrl and e-text values in HTML page.


{% highlight html %}

    <ej-radialmenu id="defaultradialmenu" e-targetelementid="radialtarget1" e-radius="radius">
    <e-items>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/copy.png" e-text="Copy"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/paste.png" e-text="Paste"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/redo.png" e-text="Redo"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/undo.png" e-text="Undo"></e-item>
    </e-items>
    </ej-radialmenu>

{% endhighlight %}


The following screenshot illustrates the output.

![](item-customization_images\item-customization_img1.png)

## Adding events to Radial Menu items

You can specify the click event to corresponding image/text of Radial Menu items for performing some specific action. You need to handle the e-click event in script manually for each item click.

Declare **e-click** event values in HTML page.


{% highlight html %}


    <ej-radialmenu id="defaultradialmenu" e-targetelementid="radialtarget1">
    <e-items>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/copy.png" e-text="Copy" e-click="copy"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/Font_letter.png" e-text="Font"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/list.png" e-text="List">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/list.png" e-text="List"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/l5.png" e-text="List"></e-item>
            </e-items>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/font.png" e-text="Bold" e-click="bold">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/f1.png" e-text="Italic" e-click="italic"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/font.png" e-text="Bold" e-click="bold"></e-item>
            </e-items>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/paste.png" e-text="Paste" e-click="paste"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/undo.png" e-text="Undo" e-click="undo" e-enabled="false">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/ undo.png" e-text="Undo" e-enabled="false"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/redo.png" e-text="Redo" e-enabled="false"></e-item>
            </e-items>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/align.png" e-text="Alignment">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/a1.png" e-text="Left"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/a2.png" e-text="Right"></e-item>
            </e-items>
        </e-item>
    </e-items>
    </ej-radialmenu>

    
{% endhighlight %}

Define the click functions and radialmenu show function in angular module section.
    
{% highlight javascript %}

    angular.module(radialmenuApp, ['ejangular'])
        var rteObj, rteEle = $("#rteSample1"), radialEle = $('#defaultradialmenu'), action = 0, forRedo = 0;
    });
    $scope.radialShow = function (e) {
        var target = $("#radialtarget1"), radialRadius = 150, radialDiameter = 2 * radialRadius,
            // To get Iframe positions
            iframeY = e.event.clientY, iframeX = e.event.clientX,
            // To set Radial Menu position within target
            x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
            y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
            radialEle.ejRadialMenu("setPosition",x,y);
		    radialEle.focus();
            rteObj = rteEle.data("ejRTE");
    }
    $scope.copy = function (e) {
        rteObj.executeCommand("copy");
    }
    $scope.italic = function (e) {
        rteObj.executeCommand("italic");
    }
    $scope.bold = function (e) {
        rteObj.executeCommand("bold");
    } 

{% endhighlight %}


The following screenshot illustrates the output.

![](item-customization_images\item-customization_img2.png)


## Badge Customization in Radial Menu Items

You can specify set badges for the items by using badge settings in the radial menu. You can set value for the badge and enable badge with a default value.

The **e-badge-enabled** property to enable or disable badges. **e-badge-value** attribute is to set the badge value.

Declare badge properties in HTML Page.


{% highlight html %}

    <ej-radialmenu id="defaultradialmenu" e-targetelementid="radialtarget1">
    <e-items>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/copy.png" e-text="Copy" e-enabled="true" e-badge-enabled="true" e-badge-value="3"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/paste.png" e-text="Paste"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/redo.png" e-text="Redo"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/undo.png" e-text="Undo"></e-item>
    </e-items>
    </ej-radialmenu>


{% endhighlight %}


The following screenshot illustrates the output.

![](item-customization_images\item-customization_img3.png)

## Slider Customization in Radial Menu Items

You can customize the Radial Menu with slider settings. The **e-type** property specifies the type of radial menu item, where you can set the type for RadialMenu item.

You can customize the Radial Menu slider settings by using the **e-ticks**, **e-strokeWidth** and **e-labelSpace** properties. The **e-sliderSettings-ticks** property specifies the slider ticks for radial menu item. **e-sliderSettings-strokeWidth** attribute is used to specify the slider’s stroke width value. **e-sliderSettings-labelSpace** attribute is used to specify the value of slider label space.

Refer to the following code example.


{% highlight html %}

    <ej-radialmenu id="defaultradialmenu" e-targetelementid="radialtarget1">
    <e-items>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/copy.png" e-text="Copy" e-click="copy"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/fontsize.png" e-text="Font" e-click="font" e-badge-value="2" e-badge-enabled="true" e-type="slider" e-slidersettings-ticks="ticksValue" e-slidersettings-strokewidth="1"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/font.png" e-text="Bold" e-click="bold">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/f1.png" e-text="Italic" e-click="italic"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/font.png" e-text="Bold" e-click="bold"></e-item>
            </e-items>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/list.png" e-text="List" e-click="unorderedList">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/list.png" e-text="List" e-click="unorderedList"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/l5.png" e-text="List" e-click="orderedList"></e-item>
            </e-items>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/paste.png" e-text="Paste" e-click="paste"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/undo.png" e-text="Undo" e-click="undo" e-enabled="false">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/undo.png" e-text="Undo" e-click="undo" e-enabled="false"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/redo.png" e-text="Redo" e-click="redo" e-enabled="false"></e-item>
            </e-items>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/align.png" e-text="Alignment" e-click="center">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/a1.png" e-text="Left" e-click="left"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/a2.png" e-text="Right" e-click="right"></e-item>
            </e-items>
        </e-item>
    </e-items>
    </ej-radialmenu>

{% endhighlight %}

Define slider ticks values in angular module section.
    
{% highlight javascript %}

    angular.module(radialmenuApp, ['ejangular'])
                .controller('RadialMenuCtrl', function ($scope,$compile) {
        $scope.ticksValue = [0, 2, 4, 6, 8, 10, 12, 14]
    });

{% endhighlight %}

The following screenshot illustrates the output.

![](item-customization_images\item-customization_img4.png)

















