---
layout: post
title:  Quick Access Toolbar
description: quick access toolbar
documentation: ug
platform: AngularJS
keywords: quick access toolbar,ribbon quick access toolbar
---

# Quick Access Toolbar

Quick Access Toolbar provides the shortcuts to the most commonly used commands by placing the controls at the Quick Access Toolbar section. It can be placed at the top or bottom of the Ribbon.

Set `showQAT` as true to enable Quick Access Toolbar in Ribbon. It supports the Button, Split Button, Toggle Button controls. The `quickAccessMode` is used to change the controls state in Quick Access Toolbar through options as `toolbar`,`menu` and `none`. Default value is `none` and QAT toolbar is created with specified controls added in Toolbar.

The `toolbar` option used to set controls visibility in Quick Access Toolbar.The `menu` option shows the controls in Quick Access Menu and does not show controls in Quick Access Toolbar.

Once the controls are visible in Toolbar , then controls state will be set as ticked in Quick Access Menu and vice versa.  

The client side event for Quick Access Toolbar menu click is `qatMenuItemClick` and it will be triggered with QAT menu item click.

`More Commands` command provides with Quick Access Menu. This can be customized using `qatMenuItemClick` event, such as to show popup dialog. 

{% highlight html %}

	 <body ng-controller="RibbonCtrl">
    <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
            <ul>
                <li><a>New</a></li>
            </ul>
        </li>
    </ul>
    <div id="Ribbon" ej-ribbon e-width="50%" e-applicationtab-type="menu" e-showqat="true" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="Splitbutton" e-aligntype="columns">
                        <div e-content>
                            <div e-content e-defaults-type="splitbutton" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="paste" e-text="Paste" e-quickaccessmode="toolbar" e-splitbuttonsettings-contenttype="imageonly" e-splitbuttonsettings-prefixicon="e-icon e-ribbon e-ribbonpaste" e-splitbuttonsettings-targetid="pasteSplit" e-splitbuttonsettings-buttonmode="dropdown" e-splitbuttonsettings-arrowposition="bottom" e-splitbuttonsettings-click="executeAction">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="Button" e-aligntype="rows">
                        <div e-content>

                            <div e-content e-defaults-isbig="false">
                                <div e-groups>
                                    <div e-group e-id="italic" e-type="togglebutton" e-togglebuttonsettings-contenttype="imageonly" e-togglebuttonsettings-defaulttext="Italic" e-togglebuttonsettings-activetext="Italic" e-togglebuttonsettings-defaultprefixicon="e-icon e-ribbon e-ribbonitalic" e-togglebuttonsettings-activeprefixicon="e-ribbon e-icon e-ribbonitalic" e-togglebuttonsettings-click="executeAction" e-quickaccessmode="toolbar"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="Togglebutton" e-aligntype="rows">
                        <div e-content>

                            <div e-content e-defaults-isbig="false">
                                <div e-groups>
                                    <div e-group e-id="bold" e-text="bold" e-type="togglebutton" e-togglebuttonsettings-contenttype="imageonly" e-togglebuttonsettings-defaulttext="Bold" e-togglebuttonsettings-activetext="Bold" e-togglebuttonsettings-defaultprefixicon="e-icon e-ribbon bold" e-togglebuttonsettings-activeprefixicon="e-ribbon e-icon bold" e-togglebuttonsettings-click="executeAction" e-quickaccessmode="toolbar"></div>
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

![](Quick-Access-Toolbar_images/Quick-Access-Toolbar_img1.png)
