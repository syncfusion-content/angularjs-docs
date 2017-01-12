---
layout: post
title: Controls-Support
description: controls support
documentation: ug
platform: Angular-1
keywords: controls support,ribbon controls support
---

# Controls Support

Button, Split Button, DropdownList, Toggle button, Gallery and Custom controls can be added to each groups. You can set `type` property in group to define the controls. Default `type` is `button`. 

## Built in Controls

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

    <div id="Ribbon" ej-ribbon e-width="50%" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="New" e-enablegroupexpander="true" e-aligntype="rows">
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
                                    <div e-group e-id="paste" e-text="Paste" e-customtooltip-prefixicon="e-pastetip" e-splitbuttonsettings-contenttype="imageonly" e-splitbuttonsettings-prefixicon="e-icon e-ribbon e-ribbonpaste" e-splitbuttonsettings-targetid="pasteSplit" e-splitbuttonsettings-buttonmode="dropdown" e-splitbuttonsettings-arrowposition="bottom" e-splitbuttonsettings-click="executeAction">
                                    </div>
                                </div>
                            </div>

                        </div>
                    </div>
                    <div e-group e-text="Font" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="dropdownlist" e-defaults-height="28">
                                <div e-groups>
                                    <div e-group e-id="fontfamily" e-dropdownsettings-datasource="fontlist" e-dropdownsettings-text="Segoe UI" e-dropdownsettings-select="executeAction" e-dropdownsettings-width="150">
                                    </div>
                                    <div e-group e-id="fontsize" e-dropdownsettings-datasource="fontsize" e-dropdownsettings-text="1pt" e-dropdownsettings-select="executeAction" e-dropdownsettings-width="65">
                                    </div>
                                </div>
                            </div>
                            <div e-content e-defaults-isbig="false">
                                <div e-groups>
                                    <div e-group e-id="bold" e-text="bold" e-type="togglebutton" e-togglebuttonsettings-contenttype="imageonly" e-togglebuttonsettings-defaulttext="Bold" e-togglebuttonsettings-activetext="Bold" e-togglebuttonsettings-defaultprefixicon="e-icon e-ribbon bold" e-togglebuttonsettings-activeprefixicon="e-ribbon e-icon bold" e-togglebuttonsettings-click="executeAction"></div>
                                    <div e-group e-id="italic" e-type="togglebutton" e-togglebuttonsettings-contenttype="imageonly" e-togglebuttonsettings-defaulttext="Italic" e-togglebuttonsettings-activetext="Italic" e-togglebuttonsettings-defaultprefixicon="e-icon e-ribbon e-ribbonitalic" e-togglebuttonsettings-activeprefixicon="e-ribbon e-icon e-ribbonitalic" e-togglebuttonsettings-click="executeAction"></div>

                                </div>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </e-tabs>
    </div>
    <script>
        var fontfamily = ["Segoe UI", "Arial", "Times New Roman", "Tahoma", "Helvetica"],
          fontsize = ["1pt", "2pt", "3pt", "4pt", "5pt"],
          action1 = ["New", "Clear"],
          action2 = ["Bold", "Italic", "Underline", "strikethrough", "superscript", "subscript", "JustifyLeft", "JustifyCenter", "JustifyRight", "JustifyFull", "Undo", "Redo"];
        angular.module('RibbonApp', ['ejangular'])

            .controller('RibbonCtrl', function ($scope) {
                $scope.fontlist = fontfamily;
                $scope.fontsize = fontsize;
                $scope.action1 = action1;
                $scope.action2 = action2;
            });
    </script>
    </body>
   
{% endhighlight %}

![](Controls-Support_images/Controls-Support_img1.png)

## Custom

You can set `type` as `custom` to render custom controls and Custom element id has to be specified as `contentID`.You can change the element defined in the custom template to appropriate Syncfusion control in the event of Ribbon `create`.

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
                    <div e-group e-text="Font" e-enablegroupexpander="true" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="new" e-text="New" e-buttonsettings-contenttype="imageonly" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-new" e-buttonsettings-click="executeAction">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="Operators" e-aligntype="columns">
                        <div e-content>
                            <div e-content e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-type="custom" e-contentid="design"></div>
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
            .controller('RibbonCtrl', ['$scope', '$timeout', function ($scope, $timeout) {
                $scope.colorValue = "#9999ff";
                $scope.$apply();
            }]);
    </script>
    </body>

{% endhighlight %}

![](Controls-Support_images/Controls-Support_img2.png)