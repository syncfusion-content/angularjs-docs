---
title: Getting started with RecurrenceEditor component and basic render.	 	
description: Rendering a basic Recurrence editor with properties and generate the recurrence rule for Recurrence editor.
platform: AngularJS
control: Recurrence Editor
documentation: ug
keywords: recurrence editor, recurrence widget, ejRecurrenceEditor, js recurrence editor
---
# Recurrence Editor

The **Recurrence Editor** includes the entire recurrence related information in a separate portable manner which can be either utilized as a separate widget or else can be embed within the appointment window of Scheduler to enable recurrence options within it. The recurrence rule can be easily generated based on the frequency selected. The customizations like changing the labels of the recurrence editor is also possible to achieve through its properties. The frequencies available are Never, Daily, Weekly, Monthly, Yearly and Every weekday.
 
## Getting Started

To render the Recurrence Editor control as a separate widget, the following list of external dependencies are needed, 

* [jQuery](http://jquery.com) - 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates

The other required internal dependencies are tabulated below,


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
ej.globalize.min.js<br/><br/></td><td>
Must be referred to localize any of the JS control's text and content.<br/><br/></td></tr>
<tr>
<td>
ej.recurrenceeditor.min.js<br/><br/></td><td>
Schedule core file<br/><br/></td></tr>
<tr>
<td>
ej.scroller.min.js<br/><br/>ej.datepicker.min.js<br/><br/>ej.checkbox.min.js<br/><br/>ej.editor.min.js<br/><br/>ej.dropdownlist.min.js<br/><br/>ej.radiobutton.min.js<br/><br/></td><td>
These files are referred for proper working of the sub-controls used within RecurrenceEditor.<br/><br/></td></tr>
</table>


N> Recurrence Editor uses one or more sub-controls, therefore refer the `ej.web.all.min.js` (which encapsulates all the `ej` controls and frameworks in a single file) in the application instead of referring all the above specified internal dependencies. 

To get the real appearance of the Recurrence Editor, the dependent CSS file `ej.web.all.min.css` (which includes styles of all the widgets) should also needs to be referred.

## Control Initialization 

Create the Recurrence editor control using `ej-recurrenceeditor` directive and define all its other properties prefixed with `e-` as shown in the below code -

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="RecurrenceeditorApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="RecurrenceeditorCtrl">
        <ej-recurrenceeditor id="RecEditor"></ej-recurrenceeditor>
    </div>
    <script type="text/javascript">
        angular.module('RecurrenceeditorApp', ['ejangular']).controller('RecurrenceeditorCtrl', function ($scope) {
        });
    </script>
</body>
</html>

{% endhighlight %}


## Generating Recurrence Rule

The Recurrence Editor can be used to generate the recurrence rule as a string, based on the repeat options selected.

The following code example depicts the way to generate the recurrence rule.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml" ng-app="RecurrenceeditorApp">
<head>
    <!-- Dependency file references -->
</head>
<body>
    <div ng-controller="RecurrenceeditorCtrl">
        <ej-recurrenceeditor id="RecurrenceEditor" e-selectedrecurrencetype="1"></ej-recurrenceeditor>
        <button id="donerecur1" ej-button w-width="150px" e-height="35px" e-showroundedcorner="true" onclick="closerecurrence()">Recurrence String</button>
    </div>
    <script type="text/javascript">
        angular.module('RecurrenceeditorApp', ['ejangular']).controller('RecurrenceeditorCtrl', function ($scope) {
        });
        function closerecurrence() {
            var obj = $("#RecurrenceEditor").data("ejRecurrenceEditor")
            alert(obj.getRecurrenceRule());
        }
    </script>
</body>
</html>

{% endhighlight %}
