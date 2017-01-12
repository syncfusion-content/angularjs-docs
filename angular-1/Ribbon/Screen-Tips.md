---
layout: post
title:  Screen Tips
description: screen tips
documentation: ug
platform: Angular-1
keywords: screen tips,ribbon screen tips
---

# Screen Tips

ScreenTip/Tooltip is used to reduce the controls related Help that are needed to the end user to do control related actions.

## HTML Tooltip

Standard `html tooltip` can be set using `tooltip` property of each group item.

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

                    <div e-group e-text="Clipboard" e-enablegroupexpander="true" e-aligntype="rows">
                        <div e-content>

                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70" e-defaults-isbig="false">
                                <div e-groups>
                                    <div e-group e-id="cut" e-text="Cut" e-tooltip="Remove the selection and put it on clipboard" e-buttonsettings-contenttype="textandimage" e-buttonsettings-prefixicon="e-icon e-ribbon e-ribboncut" e-buttonsettings-click="executeAction">
                                    </div>
                                    <div e-group e-id="copy" e-text="Copy" e-tooltip="Put a copy of selection on clipboard" e-buttonsettings-contenttype="textandimage" e-buttonsettings-prefixicon="e-icon e-ribbon e-ribboncopy" e-buttonsettings-click="executeAction">
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

![](Screen-Tips_images/Screen-Tips_img1.png)

## Custom Tooltip

Custom Tooltip is used to set detailed help to the user about the controls. You can set `title`, `content` and `prefixIcon` class to customize the tooltip with icons.

### For Groups 

`Custom tooltip` for each group controls can be specified. Such as to the controls button, split button, dropdown list etc.

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

                    <div e-group e-text="Clipboard" e-enablegroupexpander="true" e-aligntype="rows">
                        <div e-content>

                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70" e-defaults-isbig="false">
                                <div e-groups>
                                    <div e-group e-id="paste" e-text="Paste" e-customtooltip-content="<h6>Paste the content.<br &#47;><br &#47;>Add content on the Clipboard to your document.<&#47;h6>" e-customtooltip-prefixicon="e-pastetip" e-buttonsettings-contenttype="textandimage">
                                    </div>
                                    <div e-group e-id="copy" e-text="Copy" e-tooltip="Put a copy of selection on clipboard" e-buttonsettings-contenttype="textandimage" e-buttonsettings-prefixicon="e-icon e-ribbon e-ribboncopy" e-buttonsettings-click="executeAction">
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
    <style type="text/css">
        .e-pastetip {
            background-image: url("../content/ejthemes/common-images/ribbon/paste.png");
            background-repeat: no-repeat;
            height: 64px;
            width: 64px;
        }
    </style>
    </body>

{% endhighlight %}

![](Screen-Tips_images/Screen-Tips_img2.png)

### For Gallery

`Custom tooltip` for each `gallery` and `custom gallery` items button control can be specified. 

N> Custom gallery item `menu` is not supported to Custom tooltip.

{% highlight html %}

     <body ng-controller="RibbonCtrl">
    <ul id="ribbonmenu">
        <li>
            <a>FILE</a>
        </li>
    </ul>
    <div id="Ribbon" ej-ribbon e-width="50%" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="Gallery" e-aligntype="rows">
                        <div e-content>
                            <div e-content>
                                <div e-groups>
                                    <div e-group e-id="Gallery" e-columns="2" e-itemheight="54" e-itemwidth="68" e-expandedcolumns="3" e-type="gallery">
                                        <div e-galleryitems>
                                            <div e-galleryitem e-text="GalleryContent1" e-customtooltip-title="Style 1" e-customtooltip-content="<i>Style 1 to customize the table<i>" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent1 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>
                                            <div e-galleryitem e-text="GalleryContent2" e-customtooltip-title="Style 2" e-customtooltip-content="<i>Style 2 to customize the table<i>" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent2 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>
                                            <div e-galleryitem e-text="GalleryContent3" e-customtooltip-title="Style 3" e-customtooltip-content="<i>Style 3 to customize the table<i>" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent3 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>
                                            <div e-galleryitem e-text="GalleryContent4" e-customtooltip-title="Style 4" e-customtooltip-content="<i>Style 4 to customize the table<i>" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent4 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>

                                        </div>

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

    <style type="text/css">
        .e-gallerycontent1 {
            background-position: 0 -105px;
        }

        .e-gallerycontent2 {
            background-position: -69px -105px;
        }

        .e-gallerycontent3 {
            background-position: -136px -105px;
        }

        .e-gallerycontent4 {
            background-position: 0 -53px;
        }

        .e-gbtnposition {
            margin-top: 5px;
        }

        .e-gbtnimg {
            background-image: url("../content/ejthemes/common-images/ribbon/homegallery.png");
            background-repeat: no-repeat;
            height: 64px;
            width: 64px;
        }
    </style>
    </body>

{% endhighlight %}

![](Screen-Tips_images/Screen-Tips_img3.png)

### For Expand Pin

Specifies the `custom tooltip` for expand pin in the Ribbon. 

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
    <div id="Ribbon" ej-ribbon e-width="50%" e-expandpinsettings-customtooltip-title="Collapse the Ribbon" e-expandpinsettings-customtooltip-content="<h6>Click the icon to collapse the Ribbon.<&#47;h6>" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="New" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="new" e-text="New" e-customtooltip-title="New" e-customtooltip-content="<h6>New.<&#47;h6>" e-buttonsettings-contenttype="imageonly" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-new" e-buttonsettings-click="executeAction">
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

![](Screen-Tips_images/Screen-Tips_img4.png)

### For Collapse Pin

Specifies the `custom tooltip` for collapse pin in the Ribbon. 

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
    <div id="Ribbon" ej-ribbon e-width="50%" e-collapsepinsettings-customtooltip-title="Pin the Ribbon" e-collapsepinsettings-customtooltip-content="<h6>Keep it open while you work.<&#47;h6>" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="New" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="new" e-text="New" e-customtooltip-title="New" e-customtooltip-content="<h6>New.<&#47;h6>" e-buttonsettings-contenttype="imageonly" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-new" e-buttonsettings-click="executeAction">
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

![](Screen-Tips_images/Screen-Tips_img5.png)

### For GroupExpander

`Custom tooltip` for each group expander can be specified.

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
    <div id="Ribbon" ej-ribbon e-width="50%" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="New" e-enablegroupexpander="true" e-enablegroupexpander-customtooltip-title="Clipboard" e-enablegroupexpander-customtooltip-content="<h6>Show a popup for the Clipboard group.<&#47;h6>" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="new" e-text="New" e-buttonsettings-contenttype="imageonly" e-buttonsettings-imageposition="imagetop" e-buttonsettings-prefixicon="e-icon e-ribbon e-new" e-buttonsettings-click="executeAction">
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

![](Screen-Tips_images/Screen-Tips_img6.png)