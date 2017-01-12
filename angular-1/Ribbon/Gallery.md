---
layout: post
title: Gallery
description: gallery
documentation: ug
platform: Angular-1
keywords: gallery,ribbon gallery
---

# Gallery

Galleries are used to display items that can be arranged in a grid-type layout. Items in the gallery can be customized as `button`/`menu` to display images, text, or both images and text. You can set `type` of group as `gallery`.

## Gallery Items

`Gallery items` are collection of the items to be included in the main gallery. You can set `text` and `toolTip` to gallery item which can also be customized with `buttonSettings`.
 
Number of `columns` to display in gallery for each row should be specified and the Number of columns in Expanded State `(expandedColumns)` can be customized, if not set, `columns` count will be set as default. 

N> The `itemHeight`and `itemWidth` for gallery item can be set, if not set default values will be used.

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
                    <div e-group e-text="Gallery" e-aligntype="rows">
                        <div e-content>
                            <div e-content>
                                <div e-groups>
                                    <div e-group e-id="Gallery" e-columns="2" e-itemheight="54" e-itemwidth="68" e-expandedcolumns="3" e-type="gallery">
                                        <div e-galleryitems>
                                            <div e-galleryitem e-text="GalleryContent1" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent1 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>
                                            <div e-galleryitem e-text="GalleryContent2" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent2 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>
                                            <div e-galleryitem e-text="GalleryContent3" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent3 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>
                                            <div e-galleryitem e-text="GalleryContent4" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent4 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>

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


![](Gallery_images/Gallery_img1.png)

Ribbon Gallery.
{:.caption}


![](Gallery_images/Gallery_img2.png)

Gallery at Expanded State
{:.caption}

## Custom Gallery Items

`Custom gallery items` are the additional items to be displayed at gallery expanded state. You can set `customItemType` as `button` or `menu`, Default is `button`.

You can also set `text`and `toolTip`to custom gallery item which can also be customized with `buttonSettings`/`menuSettings`based on the `customItemType` specified.

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
    <ul id="extramenu">
        <li>
            <a>New Quick Step</a>
            <ul>
                <li><a>Flag and Move</a></li>
            </ul>
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
                                    <div e-group e-id="Gallery" e-columns="2" e-itemheight="54" e-itemwidth="73" e-expandedcolumns="3" e-type="gallery">
                                        <div e-galleryitems>
                                            <div e-galleryitem e-text="GalleryContent1" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent1 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>
                                            <div e-galleryitem e-text="GalleryContent2" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent2 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>
                                            <div e-galleryitem e-text="GalleryContent3" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent3 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>
                                            <div e-galleryitem e-text="GalleryContent4" e-buttonsettings-contenttype="imageonly" e-buttonsettings-prefixicon="e-icon e-gallerycontent4 e-gbtnimg" e-buttonsettings-cssclass="e-gbtnposition"></div>

                                        </div>
                                        <div e-customgalleryitems>

                                            <div e-customgalleryitem e-customitemtype="menu" e-menuid="extramenu" e-menusettings-openonclick="false"></div>
                                            <div e-customgalleryitem e-text="Clear Formatting" e-tooltip="Clear Formatting" e-customitemtype="button" e-buttonsettings-cssclass="e-extrabtnstyle"></div>

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

![](Gallery_images/Gallery_img3.png)