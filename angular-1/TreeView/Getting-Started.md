---
layout: post
title: Getting-Started
description: getting started
platform: js
control: TreeView
documentation: ug
---

# Getting Started

## Include Script and CS

To get start with TreeView, create a new HTML file and add the required dependent CSS file as well as script files.

## CSS file

* [ej.web.all.min.css](http://cdn.syncfusion.com/14.3.0.49/js/web/flat-azure/ej.web.all.min.css# "") – includes all widgets styles (To know more about theme refer [Theming in Essential JavaScript Component](http://help.syncfusion.com/js/theming-in-essential-javascript-components# "") )

## External script files

* [jQuery 1.7.1](http://jquery.com/# "") and later versions.
* [jQuery.easing.js](http://gsgd.co.uk/sandbox/jquery/easing/# "") - to support the animation effects.

## Internal Script files

<table>
<tr>
<td>
**File******<br/><br/></td><td>
**Description****/****Usage******<br/><br/></td></tr>
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

<table>
<tr>
<td>
<!doctype html><br/><br/><html lang="en" ng-app="'treeApp'"><br/><br/><head><br/><br/><title>Essential Studio for JavaScript : Angular JS Support for TreeView </title><br/><br/><!-- Style sheet for default theme (flat azure) --><br/><br/><link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" /><br/><br/><!--Scripts--><br/><br/><script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.11.3.min.js" type="text/javascript"> </script><br/><br/><script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"></script><br/><br/><script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script><br/><br/><script type="text/javascript" src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js "></script><br/><br/><script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script><br/><br/><!--Add custom scripts here --><br/><br/></head><br/><br/><body><br/><br/><!--Add the MaskEdit elements here--><br/><br/></body><br/><br/></html><br/><br/></td></tr>
</table>
## TreeView using Data Binding

You can bind local data or remote data source to create a TreeView as shown below code example.

<table>
<tr>
<td>
<div id="treeView" e-showCheckbox="true" ej-treeview e-fields-datasource="dataList" e-fields-id="id" e-fields-parentid="pid" e-fields-text="name" e-fields-haschild="hasChild" e-fields-expanded="expanded" />                        <br/><br/></td></tr>
</table>
<table>
<tr>
<td>
var  phones = [<br/><br/>{ id: 1, name: "Fiction Book Lists", hasChild: true, expanded: true },<br/><br/>{ id: 2, pid: 1, name: "To Kill a Mockingbird " },<br/><br/>{ id: 3, pid: 1, name: "Pride and Prejudice " },<br/><br/>{ id: 4, pid: 1, name: "Harry Potter and the Sorcerer's Stone" },<br/><br/>{ id: 5, pid: 1, name: "The Hobbit " },<br/><br/>{ id: 6, name: "Mystery Book Lists", hasChild: true, expanded: true },<br/><br/>{ id: 7, pid: 6, name: "And Then There Were None " },<br/><br/>{ id: 8, pid: 6, name: "Angels & Demons" },<br/><br/>{ id: 9, pid: 6, name: "In Cold Blood " },<br/><br/>{ id: 10, pid: 6, name: "The Name of the Rose " },<br/><br/>{ id: 11, name: "Horror Novels", hasChild: true },<br/><br/>{ id: 12, pid: 11, name: "The Shining (The Shining, #1) " },<br/><br/>{ id: 13, pid: 11, name: "The Haunting of Hill House " },<br/><br/>{ id: 14, pid: 11, name: "The Silence of the Lambs (Hannibal Lecter, #2) " },<br/><br/>{ id: 15, name: "Novel Lists", hasChild: true },<br/><br/>{ id: 16, pid: 15, name: "Shadow Hills (Shadow Hills, #1) " },<br/><br/>{ id: 17, pid: 15, name: "After Forever Ends " },<br/><br/>{ id: 18, pid: 15, name: "Angel Star" },<br/><br/>{ id: 19, pid: 15, name: "Raised by Wolves" },<br/><br/>{ id: 20, pid: 15, name: "Falling From Grace" }];<br/><br/><br/><br/>angular.module('treeApp', ['ejangular'])<br/><br/>.controller('TreeCtrl', function ($scope) {<br/><br/>$scope.dataList = phones;               <br/><br/>});       <br/><br/></td></tr>
</table>
## Initialize the TreeView with remote DataSource

<table>
<tr>
<td>
<div id="treeView" ej-treeview e-fields-datasource="dataList" e-fields-query="query" e-fields-id="CategoryID" e-fields-text="CategoryName" e-fields-child="child" />                        <br/><br/></td></tr>
</table>
<table>
<tr>
<td>
var dataManager = ej.DataManager({<br/><br/>url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"<br/><br/>});<br/><br/>// Query creation<br/><br/>var query = ej.Query().from("Categories").select("CategoryID,CategoryName").take(3);<br/><br/><br/><br/><br/><br/><br/><br/>angular.module('treeApp', ['ejangular']).controller('TreeCtrl', function ($scope) {<br/><br/>$scope.dataList = dataManager;    <br/><br/>$scope.query = query;<br/><br/>$scope.child = { dataSource: dataManager, tableName: "Products", id: "ProductID", parentId: "CategoryID", text: "ProductName"<br/><br/>};<br/><br/>});<br/><br/></td></tr>
</table>
