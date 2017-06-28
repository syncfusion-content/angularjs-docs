---
layout: post
title: Getting-Started
description: getting started
platform: Angular-1
control: Splitter
documentation: ug
---

# Getting Started

**Splitter** component consists of movable split bar(s) that divides a container's display area into two or more resizable and collapsible panels. 

From the following guidelines, you can create a **Splitter**, add Tree view in the **Splitter** and set actions to view the image. It is used to split the document or image and Expand or Collapse in the **Splitter**. The following screenshot demonstrates the functionality of Splitter component.

![](Getting_Started_images\Getting_Started_img1.png) 

## Adding a dependency

The following steps guide you to add a **Splitter** component.

1. Create an **HTML** file and add required scripts and CSS files for rendering Essential JavaScript component as given in the [Getting Started](https://help.syncfusion.com/js/angularjs).

2. In addition to it for AngularJS implementation, refer the “angular.min.js” and “ej.widgets.angular.min.js” files.

    {% highlight html %}

    <html ng-app="splitterApp">
    <head>
    <title>Simple Splitter</title>
    <!-- Add Scripts and CSS for rendering Essential JS components --> 

        <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
        <script src="[http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    </head>
    <body ng-controller="SplitterCtrl">
            <!-- Add Splitter component Here -->
            <div id="outterSpliter" ej-splitter/>
    </body>
    </html>

{% endhighlight %}

## Component initialization

1. Initialize the ng-app and ng-controller for the application. For adding Splitter component, you have to use **ej-splitter** directive to corresponding element.

2. Now initialize the control using angular module in script section



{% highlight javascript %}


    angular.module(splitterApp, ['ejangular']).controller(SplitterCtrl, function ($scope) {});


{% endhighlight %}

## Configuring properties

Declare the splitter properties with prefix “e- “, refer the following code,

{% highlight html %}

    <div id="outterSpliter" class="ang-splitter" ej-splitter e-height ="100%" e-width="485" e-properties="proper"  e-enableautoresize="true"></div>


{% endhighlight %}


Note: All the Syncfusion widget’s properties are defined using e- prefix followed by the property name. You can find the complete API list from the [API reference](https://help.syncfusion.com/js/api/ejsplitter)

## Configure Splitter Panes


Add &lt;div&gt; element to create **Splitter**. Save the images in the corresponding location.

{% highlight html %}


    <div class="content-container-fluid">
            <div class="row">
                <div class="cols-sample-area" style="height:400px; margin:0 auto;">
                    <div id="outterSpliter" class="ang-splitter" ej-splitter e-height ="100%" e-width="485" e-properties="proper"
                        e-enableautoresize="true">
                        <div>					
                            <div class="cont">
                                <h3 class="h3">AngularJS</h3>                          
                            </div>
                        </div>
                        <div>
                            <div class="cont">
                                <div class="_content">
                                    Select any product from the tree to show the description.
                                </div>
                                <div class=" galaxy spe">
                                    <h3>Mobile</h3>
                                    <img src="galaxy.jpg" />
                                </div>
                                <div class=" harddisk spe">
                                    <h3>Harddisk</h3>
                                    <img src="harddisk.jpg" />
                                </div>
                                <div class="logo spe">
                                    <h3>Logo</h3>
                                    <img src="logo.jpg" />
                                </div>
                            </div>
                        </div>                                     
                    </div>
                </div>
            </div>
        </div>
    </div>



{% endhighlight %}



Add the following styles to show the **Splitter** control in horizontal order.

{% highlight css %}


        .cont{
                    padding: 20px;
                    min-width: 50px;
                }
        #outterSpliter{
                margin:0 auto;
                }
        .cont #treeView_Container {
                        margin-bottom: 0;
                        border: none;
                }

        .h3 {
                    font-size: 14px;
                    margin: 0;
                }

        .spe {
                    display: none;
                }



{% endhighlight %}

## Configure Tree View 



For adding Treeview component, you have to use **ej-treeview** directive to corresponding element.

Add the following code example in **HTML** file to configure Tree View.

{% highlight html %}


    <ul id="treeView" class="visibleHide" ej-treeview e-nodeSelect="treeClicked">
        <li> Mobile
                <ul>
                    <li id=" Galaxy " class="_child">Galaxy</li>
                </ul>
        </li>
        <li>Harddisk
                <ul>
                    <li id="Harddisk" class="_child">Segate  </li>
                </ul>
        </li>
        <li>Logo
                <ul>
                    <li id="Logo" class="_child">Amazon</li>
                </ul>
        </li>
    </ul>




{% endhighlight %}


## Set Actions



Add the following code example in the view page to set the action to view the image.

{% highlight javascript %}


    splitterApp.controller('SplitterCtrl', function ($scope) {
            $scope.proper = [{ paneSize: "50%" }, {}]
        })


    function treeClicked(sender, args) {
                    if (sender.currentElement.hasClass('_child')) {
                        var content = $('.' + sender.currentElement[0].id).html();
                        $('._content').html(content);
                    }
                }



{% endhighlight %}


The following screenshot is the output for the above code.

![](Getting_Started_images\Getting_Started_img2.png) 