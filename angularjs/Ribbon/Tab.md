---
layout: post
title:  Tab
description: tab 
documentation: ug
platform: AngularJS
keywords: ribbon tab
---

# Tab

Tab is a collection of control `groups` which enables you to organize related commands into single view.  Tabs can be added to Ribbon using `tabs` property. `id` & `text` properties are used to set unique ID and header text to Tab. 

{% highlight html %}
    
    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RibbonApp">
    <head>
    <title>Essential Studio for AngularJS: Ribbon</title>
    </head>
    <body ng-controller="RibbonCtrl">
    <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
            <ul>
                <li><a>New</a></li>
                <li><a>Open</a></li>
                <li><a>Save</a></li>
                <li><a>Save As</a></li>
                <li><a>Print</a></li>
            </ul>
        </li>
    </ul>
    <div id="sendReceive">
        Send/Receive All Folders
    </div>
    <div id="Ribbon" ej-ribbon e-width="50%" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="Save" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="save" e-text="Save" e-buttonsettings-contenttype="imageonly" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-new" e-buttonsettings-click="executeAction">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="Print" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="print" e-text="Print" e-buttonsettings-contenttype="imageonly" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-new" e-buttonsettings-click="executeAction">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
            <div e-tab e-id="sendrec" e-text="Send/Receive">
                <div e-groups>
                    <div e-group e-text="Send/Receive" e-type="custom" e-contentid="sendReceive"></div>
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
    </html>
    
{% endhighlight %}

![](Tab_images/Tab_img1.png)

