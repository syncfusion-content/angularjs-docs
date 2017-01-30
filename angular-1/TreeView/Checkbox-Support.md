---
layout: post
title: Checkboxes
description: checkboxes
platform: angular-1
control: TreeView
documentation: ug
---

# Checkboxes

TreeView consists of in-build checkbox option and it can be displayed to the left of the tree node by setting the [showCheckbox](http://help.syncfusion.com/api/js/ejtreeview#members:showcheckbox) property as true. It allows you to select more than one node at a time. 

## Indeterminate Checkboxes

TreeView supports tristate checkboxes in addition with standard two state checkboxes. By default TreeView has been enabled with tristate in checkboxes. You can enable 2-state checkboxes by using [autoCheckParentNode](http://help.syncfusion.com/api/js/ejtreeview#members:autocheckparentnode) as false.

{% highlight html %}

<div id="treeView" e-showcheckbox="true" e-autocheckparentnode="false" ej-treeview e-fields-datasource="dataList" e-fields-id="id" e-fields-parentid="pid" e-fields-text="name" e-fields-haschild="hasChild" e-fields-expanded="expanded" />

{% endhighlight %}

{% highlight js %}

       var phones = [
        { id: 1, name: "Fiction Book Lists", hasChild: true, expanded: true },
        { id: 2, pid: 1, name: "To Kill a Mockingbird " },
        { id: 3, pid: 1, name: "Pride and Prejudice " },
        { id: 4, pid: 1, name: "Harry Potter and the Sorcerer's Stone" },
        { id: 5, pid: 1, name: "The Hobbit " },
        { id: 6, name: "Mystery Book Lists", hasChild: true, expanded: true },
        { id: 7, pid: 6, name: "And Then There Were None " },
        { id: 8, pid: 6, name: "Angels & Demons" },
        { id: 9, pid: 6, name: "In Cold Blood " },
        { id: 10, pid: 6, name: "The Name of the Rose " },
        { id: 11, name: "Horror Novels", hasChild: true },
        { id: 12, pid: 11, name: "The Shining (The Shining, #1) " },
        { id: 13, pid: 11, name: "The Haunting of Hill House " },
        { id: 14, pid: 11, name: "The Silence of the Lambs (Hannibal Lecter, #2) " },
        { id: 15, name: "Novel Lists", hasChild: true },
        { id: 16, pid: 15, name: "Shadow Hills (Shadow Hills, #1) " },
        { id: 17, pid: 15, name: "After Forever Ends " },
        { id: 18, pid: 15, name: "Angel Star" },
        { id: 19, pid: 15, name: "Raised by Wolves" },
        { id: 20, pid: 15, name: "Falling From Grace" }];

        angular.module('TreeCtrl', ['ejangular']).controller('TreeCtrl', function ($scope) {
            $scope.dataList = phones;
        });

{% endhighlight %}

## Auto Checkable

By default checkbox state of child nodes depends up on parent node checkbox state and also parent node state gets updated based on child nodes state. You can turn off this option by setting [autoCheck](http://help.syncfusion.com/api/js/ejtreeview#members:autocheck) as false to make independent parent and child nodes checkboxes.

{% highlight html %}

<div id="treeView" e-showcheckbox="true" e-autocheck="false" ej-treeview e-fields-datasource="dataList" e-fields-id="id" e-fields-parentid="pid" e-fields-text="name" e-fields-haschild="hasChild" e-fields-expanded="expanded" />

{% endhighlight %}


## Check or Uncheck Node

Tree node can be checked or unchecked using [checkNode](http://help.syncfusion.com/api/js/ejtreeview#methods:checknode) and [uncheckNode](http://help.syncfusion.com/api/js/ejtreeview#methods:unchecknode) methods while [showCheckbox](http://help.syncfusion.com/api/js/ejtreeview#members:showcheckbox) property is enabled in TreeView. [nodeCheck](http://help.syncfusion.com/api/js/ejtreeview#events:nodecheck) and [nodeUncheck](http://help.syncfusion.com/api/js/ejtreeview#events:nodeuncheck) event occurs based on checkbox state.

{% highlight js %}

        //create an instance from an existing TreeView.

        // only after control creation we can get treeObj otherwise it throws exception.

        treeObj = $("#treeView").ejTreeView('instance');

        //to check node

        treeObj.checkNode("2");

        //to uncheck node

        treeObj.uncheckNode("2");

{% endhighlight %}


## Get Checked Nodes

To get checked nodes of TreeView, you can use [getCheckedNodes](http://help.syncfusion.com/api/js/ejtreeview#methods:getcheckednodes) method. It returns the collection of tree node.

{% highlight js %}

        function onClick() {

            //create an instance from an existing TreeView.

            // only after control creation we can get treeObj otherwise it throws exception.

            treeObj = $("#treeView").ejTreeView('instance');

            //to get checked nodes

            treeObj.getCheckedNodes();

        }

{% endhighlight %}

