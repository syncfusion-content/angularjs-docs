---
layout: post
title:  Contextual-Tab-and-Tab-Set
description: contextual tab and tab set
documentation: ug
platform: AngularJS
keywords: contextual tab and tab set
---

# Contextual Tabs

`Contextual Tabs` are collection of Tabs that extended styling and can be shown based on some criteria. Contextual Tabs can be added like `tabs` including groups and content section. You can set `backgroundColor`and `borderColor` to highlight them as Tab set

{% highlight html %}

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
    <table id="design" class="e-designtablestyle">
        <tr>
            <td style="width:87px">
                <input type="checkbox" id="check1" /><label for="check1">Header Row</label>
            </td>
            <td>
                <input type="checkbox" id="Check2" checked="checked" /><label for="Check2">First Column</label>
            </td>
        </tr>
        <tr>
            <td>
                <input type="checkbox" id="check4" checked="checked" /><label for="check4">Total Row</label>
            </td>
            <td>
                <input type="checkbox" id="Check5" /><label for="Check5">Last Column</label>
            </td>
        </tr>
    </table>
    <div id="Ribbon" ej-ribbon e-width="50%" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                </div>
            </div>
        </e-tabs>
        <div e-contextualtabs>
            <div e-contextualtab e-backgroundcolor="#FCFBEB" e-bordercolor="#F2CC1C">
                <div e-tabs>
                    <div e-tab e-id="Design" e-text="DESIGN">
                        <div e-groups>

                        </div>
                    </div>
                </div>
            </div>
            <div e-contextualtab backgroundcolor="blue" bordercolor="lightblue">
                <div e-tabs>
                    <div e-tab e-id="tabset1" e-text="Tabset1">
                        <div e-groups>
                            <div e-group e-type="custom" e-contentid="design"></div>
                        </div>
                    </div>
                    <div e-tab e-id="tabset2" e-text="Tabset2">
                        <div e-groups>

                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <script>
        angular.module('RibbonApp', ['ejangular'])
            .controller('RibbonCtrl', function ($scope) {
            });
    </script>
    </body>
    
{% endhighlight %}


![](Contextual-Tab-and-Tab-Set_images/Contextual-Tab-and-Tab-Set_img1.png)

