---
layout: post
title: Getting-Started
description: getting started
platform: Angular-1
control: TreeView
documentation: ug
---

# Getting Started

## Include Script and CSS

To get start with TreeView, create a new HTML file and add the required dependent CSS file as well as script files.

## CSS file

* [ej.web.all.min.css](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css# "") – includes all widgets styles (To know more about theme refer [Theming in Essential JavaScript Component](http://help.syncfusion.com/js/theming-in-essential-javascript-components# "") 

## External script files

* [jQuery 1.7.1](http://jquery.com/#) and later versions.

## Internal Script files

<table>
<tr>
<td>
<b>File</b><br/><br/></td><td>
<b>Description/Usage</b><br/><br/></td></tr>
<tr>
<td>
angular.min.js<br/><br/></td><td>
Common angular source file<br/><br/></td></tr>
<tr>
<td>
ej.core.min.js<br/><br/><br/></td><td>
Must be referred always before using all the JS controls.<br/><br/><br/></td></tr>
<tr>
<td>
ej.data.min.js<br/><br/><br/></td><td>
Used to handle data operation and should be used while binding data to JS controls.<br/><br/><br/></td></tr>
<tr>
<td>
ej.treeview.min.js<br/><br/><br/></td><td>
The TreeView main file<br/><br/><br/></td></tr>
<tr>
<td>
ej.widget.angular.min.js<br/><br/></td><td>
Essential Studio Angular source file<br/><br/></td></tr>
<tr>
<td>
ej.checkbox.min.js<br/><br/><br/></td><td>
Should be referred when using check box functionalities in TreeView.  <br/><br/><br/></td></tr>
<tr>
<td>
ej.draggable.min.js<br/><br/><br/></td><td>
Should be referred when using drag option in TreeView.<br/><br/><br/></td></tr>
<tr>
<td>
ej.waitingpopup.min.js<br/><br/><br/></td><td>
Should be referred when using load on demand in TreeView.<br/><br/><br/></td></tr>
</table>

## Initialize the Treeview

A simple HTML file with required CSS and script reference added to create TreeView control.


{% highlight html %}
<!doctype html>
<html lang="en" ng-app="TreeCtrl">
<head>
    <title>Essential Studio for JavaScript : Angular JS Support for TreeView </title>
    <!-- Style sheet for default theme (flat azure) -->
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <!--Scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script type="text/javascript" src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js "></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
    <!--Add custom scripts here -->
</head>
<body>
    <!--Add the Treeview elements here-->
</body>
</html>

{% endhighlight %}


## TreeView using Data Binding

You can bind local data or remote data source to create a TreeView as shown below code example.

{% highlight html %}
<div id="treeView" e-showCheckbox="true" ej-treeview e-fields-datasource="dataList" e-fields-id="id" e-fields-parentid="pid" e-fields-text="name" e-fields-haschild="hasChild" e-fields-expanded="expanded" />
{% endhighlight %}

{% highlight html %}              
var  phones = [
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
					
angular.module('treeApp', ['ejangular'])
.controller('TreeCtrl', function ($scope) {
   $scope.dataList = phones;               
     });       
 {% endhighlight %}
 
## Initialize the TreeView with remote DataSource

{% highlight html %} 
<div id="treeView" ej-treeview e-fields-datasource="dataList" e-fields-query="query" e-fields-id="CategoryID" e-fields-text="CategoryName" e-fields-child="child" />                        
{% endhighlight %}


{% highlight html %} 
var dataManager = ej.DataManager({
url: "//js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/"
});
// Query creation
var query = ej.Query().from("Categories").select("CategoryID,CategoryName").take(3);
         
			
					
angular.module('treeApp', ['ejangular']).controller('TreeCtrl', function ($scope) {
	$scope.dataList = dataManager;    
        $scope.query = query;
        $scope.child = { dataSource: dataManager, tableName: "Products", id: "ProductID", parentId: "CategoryID", text: "ProductName"
        };
});
{% endhighlight %}

## Two-way Binding

TreeView data source supports two-way (bidirectional) binding modes when we specifying **e-deepwatch** as **true** in TreeView control. It allows to synchronize the changes of the TreeView and data source.

When enable **e-deepwatch** support, if do any interaction (like drag and drop, edit, add, remove, selection, check, expand any node) in TreeView then mapped data source will be updated automatically. And also if do any changes in data source then TreeView will be updated automatically.

{% highlight html %}

<body ng-app="TreeCtrl" ng-controller="TreeViewCtrl">
    <!--create the TreeView wrapper-->
    <div id="twoway" e-deepwatch="true" ej-treeview e-fields="fields" e-fields-datasource="data" e-allowediting="true" e-allowmultiselection="true" e-allowdraganddrop="true" e-showcheckbox="true"></div>
    {{data}}
    <br />
    <button type="button" id="btn1" ng-click="addNode()">Add node via scope</button>
    <button type="button" id="btn2" ng-click="addScope()">Add node via TreeView</button>
    <button type="button" id="btn3" ng-click="removeNode()">Remove node via scope</button>
    <button type="button" id="btn4" ng-click="removeScope()">Remove node via TreeView</button>
</body>

{% endhighlight %}

{% highlight js %}

var localData = [
    { id: 1, name: "Item 1", hasChild: true, expanded: true },
    { id: 2, pid: 1, name: "Item 1.1", selected: true },
    { id: 3, pid: 1, name: "Item 1.2" },
    { id: 4, name: "Item 2" },
    { id: 5, name: "Item 3" },
];
angular.module('TreeCtrl', ['ejangular']).controller('TreeViewCtrl', function ($scope) {
    $scope.data = localData;
    $scope.fields = {
        id: "id",
        parentId: "pid",
        text: "name",
        hasChild: "hasChild",
        expanded: "expanded",
        selected: "selected"
    };
    var i = 4;
    $scope.addScope = function () {
        var treeobj = $("#twoway").data("ejTreeView");
        treeobj.addNode({ id: i, name: "New Item " + i });
        i++;
    };
    $scope.addNode = function () {
        $scope.data.push({ id: i, name: "New Item " + i });
        i++;
    };
    $scope.removeScope = function () {
        var treeobj = $("#twoway").data("ejTreeView");
        treeobj.removeNode(); //removed the selected node in TreeView
    };
    $scope.removeNode = function () {
        $scope.data.pop(); // removed last item in data source
    };
});
	
{% endhighlight %}

For more details about two-way binding in TreeView, refer the sample [here](http://jsplayground.syncfusion.com/Sync_w22vpvds).
