---
layout: post
title: Context-Menu
description: context menu
platform: Angular-1
control: Menu
documentation: ug
keywords: ejmenu, menu, angularjs menu
---

# Context Menu

A context menu is a type of menu in a graphical user interface (GUI) that appears when you perform right click operation. In this **Menu** control you can use a context menu by specifying the type of menu as **ContextMenu**. A context also provides support for nested level of menu items.

Before using the context menu, we need to set the target area for it. 

In the following example, a context menu for the division containing text is created. In this, when you perform right click operation, the following menu appears with open, edit, etc.

Add the following code in your **HTML** page.

{% highlight html %}

   <div>
        <div id="target" class="textarea">
            HTML is written in the form of HTML elements consisting of tags enclosed in angle
            brackets (like
            &lt;html&gt;
            ),within the web page content. HTML tags most commonly come in pairs like and ,although
            some tags, known as empty elements, are unpaired, for example
            &lt;img&gt;. The purpose of a web browser is to read HTML documents and compose them into
            visible or audible web pages. The browser does not display the HTML tags, but uses
            the tags to interpret the content of the page.
        </div>
        <ul id="contextMenu" ej-menu e-menutype="menuType" e-contextmenutarget="#target">
            <li><a>Open</a></li>
            <li><a>Edit</a></li>
            <li><a>Save</a></li>
            <li class="separator"></li>
            <li><a>Save as</a></li>
            <li><a>Print</a></li>
            <li><a>Properties</a></li>
        </ul>
    </div>

{% endhighlight %}

{% highlight javascript %}

angular.module('MenuApp', ['ejangular'])
.controller('MenuCtrl', function ($scope) {
    $scope.menuType = ej.MenuType.ContextMenu;
});

{% endhighlight %}

Add the following code in your style section.

{% highlight css %}

<style type="text/css">

    .textarea {
        border: 1px solid;
        padding: 10px;
        position: relative;
        text-align: justify;
        width: 463px;
        color: gray;
        margin: 0 auto;
    }

</style>

{% endhighlight %}

The following screen shot displays the output of the above code.

![](/js/Menu/Context-Menu_images/Context-Menu_img1.png) 


You can hide and show the context menu using the following methods.

## HideContextMenu

We can hide the context menu using [hide()](https://help.syncfusion.com/api/js/ejmenu#methods:hide) method. Add the following script code in the sample in order to hide the context menu.

{% highlight javascript %}

    //create an instance from an existing Menu.

        // only after control creation we can get menuObj otherwise it throws exception.
         //initialize the menu object
        var menuObj = $("#contextMenu").data("ejMenu");
        //To hide the context menu
        menuObj.hide();

    });

{% endhighlight %}

## ShowContextMenu

Shows the context menu control. Add the following script code in the sample in order to show the context menu.

{% highlight javascript %}

    //create an instance from an existing Menu.
        // only after control creation we can get menuObj otherwise it throws exception.
         //initialize the menu object
        var menuObj = $("#contextMenu").data("ejMenu");
        //To show the context menu
        menuObj.show();

{% endhighlight %}
