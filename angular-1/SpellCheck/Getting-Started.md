---
title: Getting started with SpellCheck component	
description: Rendering a basic SpellCheck
platform: Angular-1
control: spellcheck
documentation: ug
keywords: ejSpellCheck, spellcheck, spellcheck widget, js spellcheck, getting started, initialization, service reference
---
# Getting Started 

The AngularJS directives are usually included within the ej.widget.angular.min.js file and all these directives are usually packed together in a common module known as ejangular. For basic details on how to configure Syncfusion widgets in AngularJS framework, refer [here](https://help.syncfusion.com/js/angularjs).

To get start with the SpellCheck control in AngularJS framework, the following list of external dependencies are mandatory,

[jQuery](http://jquery.com/) - 1.7.1 and later versions

[Angular](https://angularjs.org/)

The external AngularJS script file angular.min.js can also be accessed from the following installed location -

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\external

An another mandatory script is `ej.widget.angular.min.js`, which can be accessed from the specified location - 

* **(installed location)**\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\common

<table>
<tr>
<th>
File<br/><br/></th><th>
Description/Usage<br/><br/></th></tr>
<tr>
<td>
ej.core.min.js<br/><br/></td><td>
Must be referred always first before using all the JS controls.<br/><br/></td></tr>
<tr>
<td>
ej.data.min.js<br/><br/></td><td>
Used to handle data operation and should be used while binding data to JS controls.<br/><br/></td></tr>
<tr>
<td>
ej.spellcheck.min.js<br/><br/></td><td>
SpellCheck core script file.<br/><br/></td></tr>
<tr>
<td>
ej.scroller.js<br/><br/>ej.button.js<br/><br/>ej.dialog.js<br/><br/>ej.menu.js<br/><br/>ej.listbox.js<br/><br/>ej.draggable.js<br/><br/>ej.globalize.js<br/><br/></td><td>
These files are referred for proper working of the sub-controls used within SpellCheck.<br/><br/></td></tr>
</table>

N> SpellCheck uses one or more sub-controls, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the SpellChecker, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

## Script/CSS Reference

Create a new HTML file and include the below initial code.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta charset="utf-8" />
        <title> </title>
    </head>
    <body>
    </body>
</html>

{% endhighlight %}

Refer the CSS file from the specific theme folder to your HTML file within the head section. Refer the built-in available themes from [here](/js/theming-in-essential-javascript-components).

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - SpellCheck</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
</head>

{% endhighlight %}

Add links to the [CDN](/js/cdn) Script files with other required external dependencies.

{% highlight html %}

<head>
    <meta charset="utf-8" />
    <title>Getting Started - SpellCheck</title>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>    
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js" type="text/javascript"></script>
</head>

{% endhighlight %}

N> Uncompressed version of library files are also available which is used for development or debugging purpose and can be generated from the custom script [here](http://csg.syncfusion.com).


## Control Initialization

The ng-app directive explains the root element (<html> or <body> tags) of the application. You will assign a name to the ng-app directive, then you must create a module with that name. In this module, you have to define your directives, services,filters and configurations.

A controller is defined using ng-controller directive. Each controller accepts an object $scope which we pass as a parameter. This object is used to bind the controller with view.

Properties can be bind to ejSpellCheck component using the prefix e- and particular property name.

Add div element to create SpellCheck.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum,Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
    </div>
</div>

{% endhighlight %}

## Service Reference

Assign the service method (CheckWords) path reference to the property `dictionaryUrl`, which is mandatory to check the spelling of the word.

The CheckWords method will perform the splitting of target sentence into separate words and check each word is that an erroneous or not. If the word is erroneous fetching the possible suggestions for it and returns those details as a result.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum,Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
    </div>
</div>

{% endhighlight %}

Add the following script to create the pass the dictionary settings values.

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
});

{% endhighlight %}

## Spell Checking

To spell check the content of the target element, you need to add one button and calling any one of the SpellCheck method `showInDialog` or `validate` by clicking the button to highlight the error words.

The following code example depicts that checking the spelling of the target element through the "validate" method.

{% highlight html %}

<div ng-controller="spellcheckCtrl">
    <div id="SpellCheck" contenteditable="true" ej-spellcheck e-dictionarysettings="dictionarySettings">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum,Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
    </div>
    <button id="CheckSpell" ej-button e-text="Spell Check" e-click="checkErrors"></button>
</div>

{% endhighlight %}

Add the following script to create the pass the dictionary settings values.

{% highlight javascript %}

syncApp.controller('spellcheckCtrl', function ($scope) {
    $scope.dictionarySettings = {
		dictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/CheckWords",
        customDictionaryUrl: "http://js.syncfusion.com/ejServices/api/SpellCheck/AddToDictionary"
	};
    $scope.checkErrors = function (e) {
        var spellObj = $("#SpellCheck").data("ejSpellCheck");
        spellObj.showInDialog();
    }
});

{% endhighlight %}