---
layout: post
title:  Resize
description: resize
documentation: ug
platform: AngularJS
keywords: resize,ribbon resize,responsive
---

# Resize 

Ribbon control dynamically resizes to display possible number of controls in the optimal layout as the application window size changes.

As the window is narrowed, controls in the Ribbon will be combined as group button with dropdown arrow, in which controls can be expanded with dropdown arrow.

## Tablet Layout 

Set `isResponsive` as true to enable responsive layout in Ribbon.If client width is above  420px or control content exceeds the page then, the ribbon will render in Tablet mode.

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

    <div id="Ribbon" ej-ribbon e-width="40%" e-applicationtab-type="menu" e-isResponsive="true" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>

                    <div e-group e-text="Clipboard" e-aligntype="rows">
                        <div e-content>

                            <div e-content e-defaults-width="70" e-defaults-height="40">
                                <div e-groups>
                                    <div e-group e-id="cut" e-text="Cut">
                                    </div>
                                    <div e-group e-id="copy" e-text="Copy">
                                    </div>

                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="Font" e-aligntype="rows">
                        <div e-content>

                            <div e-content e-defaults-width="70" e-defaults-height="40">
                                <div e-groups>
                                    <div e-group e-id="bold" e-text="bold"></div>
                                    <div e-group e-id="italic" e-text="italic"></div>

                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="Alignment" e-aligntype="rows">
                        <div e-content>

                            <div e-content e-defaults-width="70" e-defaults-height="40">
                                <div e-groups>
                                    <div e-group e-id="left" e-text="Left"></div>

                                    <div e-group e-id="right" e-text="Right"></div>

                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="View" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="zoomin" e-text="Zoom In" e-width="58" e-buttonsettings-contenttype="textandimage" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-zoomin" e-buttonsettings-click="executeAction"></div>
                                    <div e-group e-id="zoomout" e-text="Zoom Out" e-width="70" e-buttonsettings-contenttype="textandimage" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-zoomout" e-buttonsettings-click="executeAction"></div>
                                    <div e-group e-id="fullscreen" e-text="Full Screen" e-width="73" e-buttonsettings-contenttype="textandimage" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-fullscreen" e-buttonsettings-click="executeAction"></div>
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

![](Resize_images/Resize_img1.png)

## Group Button Customization

Based on window size, detailed group is shrined into single button and you can expand group items with group button click.

For each group shirked for resizing, Custom Class will be added based on group text.For example, `e-action` whereas `action` is group text. Using this custom class, group button can be customized such as to set icons etc.

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
    <div id="Ribbon" ej-ribbon e-width="40%" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>

                    <div e-group e-text="Clipboard" e-enablegroupexpander="true" e-aligntype="columns">
                        <div e-content>
                            <div e-content e-defaults-type="splitbutton" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="paste" e-text="Paste" e-customtooltip-prefixicon="e-pastetip" e-splitbuttonsettings-contenttype="imageonly" e-splitbuttonsettings-prefixicon="e-icon e-ribbon e-ribbonpaste" e-splitbuttonsettings-targetid="pasteSplit" e-splitbuttonsettings-buttonmode="dropdown" e-splitbuttonsettings-arrowposition="bottom" e-splitbuttonsettings-click="executeAction">
                                    </div>
                                </div>
                            </div>
                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-isbig="false">
                                <div e-groups>
                                    <div e-group e-id="cut" e-text="Cut" e-buttonsettings-contenttype="textandimage" e-buttonsettings-prefixicon="e-icon e-ribbon e-ribboncut" e-buttonsettings-click="executeAction">
                                    </div>
                                    <div e-group e-id="copy" e-text="Copy" e-buttonsettings-contenttype="textandimage" e-buttonsettings-prefixicon="e-icon e-ribbon e-ribboncopy" e-buttonsettings-click="executeAction">
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

                        </div>
                    </div>
                    <div e-group e-text="New" e-enablegroupexpander="true">
                        <div e-content>
                            <div e-content e-defaults-type="splitbutton" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="new" e-text="New" e-buttonsettings-contenttype="imageonly" e-buttonsettings-imageposition="imagetop" e-buttonsettings-arrowposition="bottom" e-buttonsettings-prefixicon="e-icon e-ribbon e-new" e-buttonsettings-click="executeAction">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="Actions" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-width="40" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="undo" e-text="Undo" e-buttonsettings-contenttype="textandimage" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-undo" e-buttonsettings-click="executeAction"></div>
                                    <div e-group e-id="redo" e-text="Redo" e-buttonsettings-contenttype="textandimage" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-redo" e-buttonsettings-click="executeAction"></div>
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

![](Resize_images/Resize_img2.png)
