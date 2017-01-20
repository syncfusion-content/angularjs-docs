---
layout: post
title: State-Persistence
description: State Persistence
platform: js
control: TreeView
documentation: ug
---

# State Persistence

TreeView state can be persisted by using [enablePersistence](http://help.syncfusion.com/api/js/ejtreeview#members:enablepersistence). In which entire modal has been persisted excluding data source in order to maintain performance. 

The model values of below are maintained through Id basis of tree node.

* **selected**
* **checked**
* **expanded/collapsed state**

N>  "Ul-li" template option, state has been persisted by index.

TreeView stores its model in local storage / cookies of browser before page refreshes and reinitialized with their stored model after refresh.

{% highlight html %}

<div id="treeViewdrag" e-treeview e-fields-datasource="localData" e-fields-id="id" e-fields-parentid="parent" e-fields-text="text" e-enablepersistence="true" />

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


{% endhighlight %}

