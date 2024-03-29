---
layout: post
title: Tree Node in AngularJS TreeView Control | Syncfusion
description: Learn here all about Tree Node support in Syncfusion Essential AngularJS TreeView control, its elements, and more.
platform: AngularJS
control: TreeView
documentation: ug
---


# Tree Node in AngularJS TreeView

TreeView node is structured with expand/collapse arrow, checkbox, image and text as shown in below.

![Tree Node in AngularJS TreeView](Tree-Node_images/Tree-Node_img1.png)


Also TreeView node object holds the following properties.

<table>
<tr>
<th>
Properties</th><th>
Data Type</th><th>
Description</th></tr>
<tr>
<td>
checked <br/><br/></td><td>
Boolean<br/><br/></td><td>
Checked state of the node<br/><br/></td></tr>
<tr>
<td>
count<br/><br/></td><td>
Number<br/><br/></td><td>
Number of child<br/><br/></td></tr>
<tr>
<td>
expanded<br/><br/></td><td>
Boolean<br/><br/></td><td>
Expanded state of the node<br/><br/></td></tr>
<tr>
<td>
index<br/><br/></td><td>
Number<br/><br/></td><td>
Index of the node <br/><br/></td></tr>
<tr>
<td>
level<br/><br/></td><td>
Number<br/><br/></td><td>
Level of the node<br/><br/></td></tr>
<tr>
<td>
id<br/><br/></td><td>
String<br/><br/></td><td>
Node id<br/><br/></td></tr>
<tr>
<td>
parentId<br/><br/></td><td>
String<br/><br/></td><td>
Parent id of the node<br/><br/></td></tr>
<tr>
<td>
selected<br/><br/></td><td>
Boolean<br/><br/></td><td>
Selected state of the node<br/><br/></td></tr>
</table>


## Get/Set Node Value

TreeView provides a set of options to configure all its properties by setting and getting values at initialization or dynamically.

To get the node data, you can use [getNode](https://help.syncfusion.com/api/js/ejtreeview#methods:getnode) method as shown in the below code example, in which on button click action the node value has retrieved.
Also you can get the text value of tree node by using [getText](https://help.syncfusion.com/api/js/ejtreeview#methods:gettext) method.

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
        { id: 14, pid: 11, name: "The Silence of the Lambs " },
        { id: 15, name: "Novel Lists", hasChild: true },
        { id: 16, pid: 15, name: "Shadow Hills (Shadow Hills, #1) " },
        { id: 17, pid: 15, name: "After Forever Ends " },
        { id: 18, pid: 15, name: "Angel Star" },
        { id: 19, pid: 15, name: "Raised by Wolves" },
        { id: 20, pid: 15, name: "Falling From Grace" }];

        angular.module('TreeCtrl', ['ejangular']).controller('TreeCtrl', function ($scope)       {
            $scope.dataList = phones;
        });
  //bind below onClick action to button to get node at button click or else in any action

        function onClick() {

            //create an instance from an existing TreeView.

            // only after control creation we can get treeObj otherwise it throws exception.

            treeObj = $("#treeView").ejTreeView('instance');

            //get node object using getNode method

            var node = treeObj.getNode("1");

        }
{% endhighlight %}

N>  Existing TreeView instance can be created by [jQuery.data()](http://api.jquery.com/jQuery.data/#) and you can control the API’s of TreeView behavior.

To edit the node text, you can use [updateText](http://help.syncfusion.com/api/js/ejtreeview#methods:updatetext) method as shown below code example. 

{% highlight js %}

        //create an instance from an existing TreeView.

        // only after control creation we can get treeObj otherwise it throws exception.

        treeObj = $("#treeView").ejTreeView('instance');

        //get node object using getNode method

        var node = treeObj.getNode("2");

        //sets text to existing node 

        treeObj.updateText(node.id, "updated Item");

{% endhighlight %}

## Get Parent Node

To get current parent node of a particular node, you can use the [getParent](http://help.syncfusion.com/api/js/ejtreeview#methods:getparent) method as shown in below code example 

{% highlight js %}


        //create an instance from an existing TreeView.

        // only after control creation we can get treeObj otherwise it throws exception.

        treeObj = $("#treeView").ejTreeView('instance');

        //get parent node using getParent method

        var node = treeObj.getParent("4");

{% endhighlight %}

## Get Node Index

To get node index you can use the [getNodeIndex](https://help.syncfusion.com/api/js/ejtreeview#methods:getnodeindex) as shown in below code example.
You can use [getNodeByIndex](https://help.syncfusion.com/api/js/ejtreeview#methods:getnodebyindex) method to get TreeView node by using index position

{% highlight js %}

        //create an instance from an existing TreeView.

        // only after control creation we can get treeObj otherwise it throws exception.

        treeObj = $("#treeView").ejTreeView('instance');

        //get node object using getNode method

        var node = treeObj.getNode("4");

        //gets the index of node 

        treeObj.getNodeIndex(node.id);

{% endhighlight %}

## Node Manipulations

You can perform following operation in tree nodes and the modified node values can be saved in database.

### Add or Remove nodes

To add/remove nodes programmatically, use [addNode](http://help.syncfusion.com/api/js/ejtreeview#methods:addnode) and [removeNode](http://help.syncfusion.com/api/js/ejtreeview#methods:removenode) methods of the TreeView.

{% highlight js %}

        //create an instance from an existing TreeView.

        // only after control creation we can get treeObj otherwise it throws exception.

        treeObj = $("#treeView").ejTreeView('instance');

        var newNode = { id: 11, text: "Item 2.1" };

        //to add tree node

        treeObj.addNode(newNode, "2");

        //to remove node

        treeObj.removeNode("4");

{% endhighlight %}

You can able to add a new node after or before specific TreeView node by using [insertAfter](http://help.syncfusion.com/api/js/ejtreeview#methods:insertafter) and [insertBefore](http://help.syncfusion.com/api/js/ejtreeview#methods:insertbefore) methods.

{% highlight js %}

        //create an instance from an existing TreeView.

        // only after control creation we can get treeObj otherwise it throws exception.

        treeObj = $("#treeView").ejTreeView('instance');

        var newNode = { id: 12, text: "Item 2.2" };



        //to add tree node after some element, which having id 2

        treeObj.insertAfter(newNode, "2");



        var newNode = { id: 13, text: "Item 2.3" };

        //to add tree node before some element, which having id 2

        treeObj.insertBefore(newNode, "2");

{% endhighlight %}

### Move node

You can also achieve cut and paste operation by using [moveNode](http://help.syncfusion.com/api/js/ejtreeview#methods:movenode) methods.

{% highlight js %}

        //create an instance from an existing TreeView.

        // only after control creation we can get treeObj otherwise it throws exception.

        treeObj = $("#treeView").ejTreeView('instance');



        //to move tree node which having id 5, to child of node which having id 2.   

        treeObj.moveNode("5", "2");

{% endhighlight %}

### Expand or Collapse node

Tree nodes can be expanded or collapsed by clicking the expand/collapse icon of the node or in code behind by using the following methods.

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
{{'[expandNode](http://help.syncfusion.com/api/js/ejtreeview#methods:expandnode)'| markdownify }} <br/><br/></td><td>
Expands the node with specified id<br/><br/></td></tr>
<tr>
<td>
{{'[collapseNode](http://help.syncfusion.com/api/js/ejtreeview#methods:collapsenode)'| markdownify }}<br/><br/></td><td>
Collapse the node with specified id <br/><br/></td></tr>
<tr>
<td>
{{'[expandAll](http://help.syncfusion.com/api/js/ejtreeview#methods:expandall)'| markdownify }}<br/><br/></td><td>
Expands all the node<br/><br/></td></tr>
<tr>
<td>
{{'[collapseAll](http://help.syncfusion.com/api/js/ejtreeview#methods:collapseall)'| markdownify }}<br/><br/></td><td>
Collapse all the node<br/><br/></td></tr>
</table>
Also you can get all the expanded nodes index in tree by using [getExpandedNodesIndex](http://help.syncfusion.com/api/js/ejtreeview#methods:getexpandednodesindex) method, which returns the array of expanded node indices. 

### Get updated node collection

You can get the updated node values after manipulating or editing the node of TreeView to save at server end using [getTreeData](http://help.syncfusion.com/api/js/ejtreeview#methods:gettreedata) method. It returns the JSON data represented as in tree with modified structure.

You can also get the updated data source for remote data binding after performing the operation like editing, selecting/unselecting, expanding/collapsing, checking/unchecking and removing node. You cannot get the updated data source when you perform operation like drag and drop, adding node for remote data binding.

TreeView does not support the two-way binding for remote data binding.

The updated data source also contains custom attributes if you return these from server.

{% highlight js %}

        //create an instance from an existing TreeView.

        // only after control creation we can get treeObj otherwise it throws exception.

        treeObj = $("#treeView").ejTreeView('instance');

        //to get TreeView data

        treeObj.getTreeData();

{% endhighlight %}

## Editing

You can directly edit the tree node’s text in-place by double-click on the tree node or select the tree node and press F2 key. The editing works only if the [allowEditing](https://help.syncfusion.com/api/js/ejtreeview#members:allowediting) property is true in TreeView control. When editing is completed by focus out or “enter” key press, the modified node’s text is saved automatically. The [nodeEdit](https://help.syncfusion.com/api/js/ejtreeview#events:nodeedit) event will be triggered whenever edited the TreeView node.
Also [beforeEdit](https://help.syncfusion.com/api/js/ejtreeview#events:beforeedit) event will be triggered before the TreeView node change into editing mode.

{% highlight html %}

// Initialize and bind the TreeView with allowEditing property

<div id="treeView" e-allowediting="true" ej-treeview e-fields-datasource="dataList" e-fields-id="id" e-fields-parentid="pid" e-fields-text="name" e-fields-haschild="hasChild" e-fields-expanded="expanded" />

{% endhighlight %}

## Selection

You can select a specific node by setting index value in [selectedNode](https://help.syncfusion.com/api/js/ejtreeview#members:selectednode) property or passing node’s id/element to [selectNode](https://help.syncfusion.com/api/js/ejtreeview#methods:selectnode) method.
To get the selected status of a given TreeView node you have to use [isSelected](https://help.syncfusion.com/api/js/ejtreeview#methods:isselected) method.  
The [nodeClick](https://help.syncfusion.com/api/js/ejtreeview#events:nodeclick) event will be triggered whenever TreeView node is clicked. The [beforeSelect](https://help.syncfusion.com/api/js/ejtreeview#events:beforeselect) event will be triggered before the TreeView node is selected. 
The [nodeSelect](https://help.syncfusion.com/api/js/ejtreeview#events:nodeselect)/[nodeUnselect](https://help.syncfusion.com/api/js/ejtreeview#events:nodeunselect) events will be triggered based on the TreeView node click operations. 

{% highlight html %}

// Initialize and bind the TreeView with allowEditing property

<div id="treeView" ej-treeview e-selectnode="2" e-fields-datasource="dataList" e-fields-id="id" e-fields-parentid="pid" e-fields-text="name" e-fields-haschild="hasChild" e-fields-expanded="expanded" />

{% endhighlight %}


{% highlight js %}

            treeObj = $("#treeView").ejTreeView('instance');

            treeObj.selectNode("4");

        });

{% endhighlight %}

## Ensure Visibility

To get the visibility status of the given TreeView node, you can use [isVisible](https://help.syncfusion.com/api/js/ejtreeview#methods:isvisible) method.
You can ensure the specified tree node is visible by using [ensureVisible](https://help.syncfusion.com/api/js/ejtreeview#methods:ensurevisible) method, which expands tree nodes and scrolls the TreeView control as necessary.
Also you can use [getVisibleNodes](https://help.syncfusion.com/api/js/ejtreeview#methods:getvisiblenodes) method to get currently visible nodes in TreeView.

{% highlight html %}

<div id="treeView" ej-treeview e-fields-datasource="localData" e-fields-id="id" e-fields-parentid="parent" e-fields-text="text"/>

{% endhighlight %} 

{% highlight js %}

        var localData = [

        { id: 1, text: "Item 1" },

        { id: 2, text: "Item 2" },

        { id: 3, text: "Item 3" },

        { id: 4, text: "Item 4" },

        { id: 5, parent: 1, text: "Item 1.1" },

        { id: 6, parent: 1, text: "Item 1.2" },

        { id: 7, parent: 1, text: "Item 1.3" },

        { id: 8, parent: 3, text: "Item 3.1" },

        { id: 9, parent: 3, text: "Item 3.2" },

        { id: 10, parent: 5, text: "Item 1.1.1" }

        ];

    
        function onClick() {

            //create an instance from an existing TreeView.

            // only after control creation we can get treeObj otherwise it throws exception.

            treeObj = $("#treeView").ejTreeView('instance');

            //to ensure the visibility of node

            treeObj.ensureVisible("10");

        }  

{% endhighlight %}
