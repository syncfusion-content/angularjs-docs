---
layout: post
title:  Group
description: group
documentation: ug
platform: AngularJS
keywords: group,ribbon group
---

# Group

`Group` is a collection of logical content groups that are combined under related Tab. Each group can be defined using content groups or custom content.

## Adding Tab Groups

Group items can be added to Tabs by specifying `text` and corresponding `content` to be displayed. The content of group can be specified as either with `content`collection, `contentID` or `customContent`.

### Adding Content

Add content to Group item which is based on `type` of content specified. The available types are `button`, `splitButton`, `toggleButton`,`gallery`, and `dropDownList`.

Groups and defaults settings can be added with the `content`.

#### _Defaults_

The `height`, `width`, `type`, `isBig` property to the controls in the `group` can be specified commonly.
The `height` & `width` applicable to button, split button, dropdown list ,Toggle button controls and `isBig` applicable to only button controls ( button, split , toggle)

#### _Adding Content Groups_

Controls such as button, split button, dropdown list, toggle button, gallery in the subgroup of the Ribbon tab can be rendered. All of these can be customized using its corresponding settings property such as `buttonSettings`, `dropdownSettings`, etc.

Custom controls or items (such as table, div etc.) can be added when the `type` set as `custom`. `defaults` control settings of group can be specified for an `individual group` instead of specifying them to groups collection commonly.

`Tooltip` and `Custom Tooltip` can be specified for each group controls.

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
                    <div e-group e-text="Font" e-aligntype="columns">
                        <div e-content>
                            <div e-content e-defaults-isbig="false" e-defaults-type="togglebutton" e-defaults-width="75" e-defaults-height="30">
                                <div e-groups>
                                    <div e-group e-id="cut" e-type="togglebutton" e-togglebuttonsettings-defaulttext="Cut Over" e-togglebuttonsettings-activetext="Cut Over"></div>
                                    <div e-group e-id="copy" e-type="togglebutton" e-togglebuttonsettings-defaulttext="Copy" e-togglebuttonsettings-activetext="Copy Over"></div>
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

![](Group_images/Group_img1.png)

#### _Enable Separator_ 

Separates the control from the next control in the group when group `alignType` is `row`. Set “true” to `enableSeparator`.

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
                    <div e-group e-text="New" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
                                <div e-groups>
                                    <div e-group e-id="new" e-text="New" e-enableseparator="true" e-buttonsettings-width="100">
                                    </div>
                                    <div e-group e-id="font" e-text="Font" e-tooltip="Font" e-buttonsettings-width="100">
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

![](Group_images/Group_img2.png)

### Adding Custom Content 

Set group `type` as `custom` to add custom items such as div, table and custom controls. With type as custom, content can be added in two ways as specified below.

*	HTML contents can be directly added into the groups as string content using `customContent` property
*	Custom template id can be specified to render those specific custom template using `contentID` property

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
    <button id="btn">Using Content ID</button>
    <button id='customContent'>Using Custom Content</button>
    <div id="Ribbon" ej-ribbon e-width="50%" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="New" e-aligntype="columns">
                        <div e-content>
                            <div e-content e-defaults-isbig="false" e-defaults-width="120" e-defaults-height="30">
                                <div e-groups>
                                    <div e-group e-id="new" e-text="New" e-type="custom" e-contentid="customContent">
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div e-group e-text="Data" e-aligntype="columns">
                        <div e-content>
                            <div e-content e-defaults-isbig="false" e-defaults-width="90" e-defaults-height="30">
                                <div e-groups>
                                    <div e-group e-id="data" e-text="Data" e-type="custom" e-contentid="btn"></div>
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

![](Group_images/Group_img3.png)

## Group Expander

Set `enableGroupExpander` as true to show Group Expander for each group in Tab. These expanders can be customized using `groupExpand` event, such as to show popup dialog.

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
    <button id="btn">Home button</button>
    <div id="Ribbon" ej-ribbon e-width="50%" e-applicationtab-type="menu" e-applicationtab-menuitemid="ribbonmenu">
        <e-tabs>
            <div e-tab e-id="home" e-text="HOME">
                <div e-groups>
                    <div e-group e-text="New" e-enableGroupExpander="true" e-aligntype="rows">
                        <div e-content>
                            <div e-content e-defaults-isbig="false" e-defaults-width="120" e-defaults-height="30">
                                <div e-groups>
                                    <div e-group e-id="new" e-text="New" e-enablegroupexpander="true" e-type="custom" e-contentid="btn">
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

![](Group_images/Group_img4.png)

