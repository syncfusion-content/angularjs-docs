---
layout: post
title:  Ribbon-Application-Tab
description: application tab
documentation: ug
platform: Angular-1
keywords: application tab,ribbon application tab
---

# Application Tab

The Application Tab is used to represent a `Menu` that do some operations, such as File menu to create, open, and print documents. Application Tab classified by the following property:

*  menu
*  backstage


## Application Menu

The Application Menu is similar to traditional file menu options and Syncfusion `ejMenu` control is used internally to render this. To show Application Menu in Ribbon, set the type as `menu` and menuSettings to customize properties of `ejMenu`.

### _Create Using Template_

Set the UL element `id` to `e-applicationtab-menuitemid` property to create Application Menu and it will acts as template to render menu.

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
    <div id="Ribbon" ej-ribbon e-width="500px" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <e-tab e-id="home" e-text="Home"></e-tab>
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

![](Application-Tab_images/Application-Tab_img1.png)

## Backstage Page

The Backstage page is where documents and related data of those can be managed, such as Create, Save and other information.

The Backstage page has a feature to add custom Control in left side of the page which contains menu items and the right side contains corresponding user controls. 

To render the Ribbon with the Backstage page, refer to the following code snippet. 

{% highlight html %}
    
    <!DOCTYPE html>
    <html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="RibbonApp">
    <head>
    <title>Essential Studio for AngularJS: Ribbon</title>
    </head>
    <body ng-controller="RibbonCtrl">
    <div>
        <div id="newCon">
            <table>
                <tr>
                    <td>
                        <button id="btn1" class="e-bsnewbtnstyle">Blank WorkBook</button>
                    </td>
                </tr>
            </table>
        </div>
        <div id="accountCon">
            <div class="e-userDiv">
                <span>User Information</span>
                <div>
                    <div class="e-accuser e-newpageicon"></div>
                    <div class="e-userCon">
                        <div>user</div>
                        <div>xyz@syncfusion.com</div>
                    </div>
                </div>
            </div>
            <a href="#">Sign out</a>
        </div>
        <div id="defaultRibbon" ej-ribbon e-width="50%" e-applicationtab="backstage" e-expandpinsettings-tooltip="Collapse the Ribbon" e-collapsepinsettings-tooltip="Pin the Ribbon" e-create="createControl">
            <div e-tabs>
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
                    </div>
                </div>
            </div>
        </div>
    </div>
    <style type="text/css">
        .e-blank {
            background-image: url("../content/ejthemes/common-images/ribbon/blank.png");
        }

        .e-infopageicon {
            background-repeat: no-repeat;
            height: 150px;
            width: 198px;
        }

        .e-newpageicon {
            background-repeat: no-repeat;
            height: 42px;
            width: 42px;
        }

        .e-bspagestyle {
            line-height: 0;
            font-size: 30px;
        }

        .e-ribbon .e-ribbonbackstagepage .e-bsnewbtnstyle {
            color: #212121;
            background: #fdfdfd;
            margin: 20px;
        }
    </style>
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
                $scope.backstage = {
                    type: ej.Ribbon.ApplicationTabType.Backstage,
                    backstageSettings: {
                        text: "FILE", height: 350, width: 1000, headerWidth: 120, pages: [
                         { id: "new", text: "New", contentID: "newCon", itemType: ej.Ribbon.ItemType.Tab },
                        { id: "close", text: "Close", enableSeparator: true, itemType: ej.Ribbon.ItemType.Button },
                        { id: "account", text: "Office Account", contentID: "accountCon" }
                        ]
                    }
                }
            });
        $("#btn1").ejButton({
            size: "large",
            height: 200,
            width: 205,
            contentType: "textandimage",
            imagePosition: "imagetop",
            prefixIcon: "e-blank e-infopageicon"
        });
    </script>
    </body>
    </html>
    
{% endhighlight %}

![](Application-Tab_images/Application-Tab_img2.png)

N> Height & width of backstage can be set using `height` and `width`, if these are not set, Ribbon’s height & width will be considered.