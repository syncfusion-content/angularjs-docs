---
layout: post
title: Globalization Ribbon widget for Syncfusion Essential JS
description: How to use globalization 
platform: AngularJS
control: Ribbon
documentation: ug
---
# Globalization

## Right to Left - RTL

By default, Ribbon render its content and layout from left to right. To customize Ribbon direction, you can change direction from LTR to RTL by using `enableRTL` as true.

{% highlight html %}

     <body ng-controller="RibbonCtrl">
     <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
            <ul>
                <li><a>New</a></li>
                <li><a>Open</a></li>
                <li><a>Save</a></li>
            </ul>
        </li>
    </ul>
    <div id="Ribbon" ej-ribbon e-width="50%" e-applicationtab-type="menu" e-enablertl="true" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="New" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="new" e-text="New" e-buttonsettings-contenttype="imageonly" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-new" e-buttonsettings-click="executeAction">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="Clipboard" e-aligntype="columns">
                        <div e-content>
                            <div e-content e-defaults-type="splitbutton" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="paste" e-text="Paste" e-splitbuttonsettings-contenttype="imageonly" e-splitbuttonsettings-prefixicon="e-icon e-ribbon e-ribbonpaste" e-splitbuttonsettings-targetid="pasteSplit" e-splitbuttonsettings-buttonmode="dropdown" e-splitbuttonsettings-arrowposition="bottom" e-splitbuttonsettings-click="executeAction">
                                    </div>
                                </div>
                            </div>

                        </div>
                    </div>
                </div>
            </div>
        </e-tabs>
    </div>
    <script>
        angular.module('RibbonApp', ['ejangular'])
            .controller('RibbonCtrl', function ($scope) {

            });
    </script>

</body>

{% endhighlight %}

![](Globalizationandlocalization_images/Globalizationandlocalization._img1.png)


