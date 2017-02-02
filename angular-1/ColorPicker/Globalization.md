---
layout: post
title: Globalization | ColorPicker | AngularJS | Syncfusion
description: globalization
platform: AngularJS
control: ColorPicker
documentation: ug
---

# Globalization

**ColorPicker** has been provided with Built-in **localization** support, so that it will be able to adapt based on culture specific locale defined for it.
**ej.globalize** library is used to **globalize ColorPicker**. Globalize values will be automatically used when **e-locale** property is set with locale string value for example fr-FR.

More than 350 culture specific files are available to localize the colorpicker value. To know more about EJ globalize support, please refer the below link 

[](http://help.syncfusion.com/js/localization)

To translate our control content from default English to any of the culture, say **For example** - **German** language, then you need to refer the **ej.culture.de-DE.min.js** file in your application,
The **en-US locale** is currently being used as **default culture in ColorPicker**. You can set any other culture to **ColorPicker** by using **e-Locale** property. Below code example shows German cultured ColorPicker.

Refer the below German culture file in head section of HTML page after the reference of **ej.web.all.min.js** file.

**HTML View Section**

{% highlight html %}

     <input id="colorpicker" ej-colorpicker e-value="value" e-locale="locale" />

{% endhighlight %}

**Controller Section**

{% highlight javacsript %}

    <script>
        angular.module("ColorPickCtrl", ['ejangular']).controller("ColorPickCtrller", function ($scope) {
            $scope.value = "#278787",
            $scope.locale="de-DE",
        
            ej.ColorPicker.Locale["de-DE"] = {
                buttonText: {
                    apply: "Übernehmen",
                    cancel: "Stornieren",
                    swatches: "Farbfelder"
                },
                tooltipText: {
                    switcher: "Switcher",
                    addbutton: "Farbe hinzufügen",
                    basic: "Basic",
                    monochrome: "Einfarbig",
                    flatcolors: "Flache Farben",
                    seawolf: "See Wolf",
                    webcolors: "Webfarben",
                    sandy: "Sandig",
                    pinkshades: "Rosa Schatten",
                    misty: "misty",
                    citrus: "Zitrusfrucht",
                    vintage: "Jahrgang",
                    moonlight: "Mondlicht",
                    candycrush: "Candy Crush",
                    currentcolor: "Aktuelle Farbe",
                    selectedcolor: "Ausgewählte Farbe"
                }
            };
            });
    </script>

{% endhighlight %}

Run the above code to render the following output.

![](Globalization_images/Globalization_images1.png)
