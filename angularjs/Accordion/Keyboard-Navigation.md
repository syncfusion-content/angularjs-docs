---
layout: post
title: Keyboard-Navigation
description: keyboard navigation
platform: AngularJS
control: Accordion 
documentation: ug
keywords: ejaccordion, accordion, angularjs accordion
---

# Keyboard Navigation

You can use **Keyboard** shortcut keys as an alternative to the mouse in Accordion widget using [allowKeyboardNavigation](https://help.syncfusion.com/api/js/ejaccordion#members:enablepersistence) property. However, you will have to focus the control to enable the keyboard navigation. Accordion Widget allows you to perform all kind of actions using keyboard shortcuts.

List of Keyboard shortcut keys are shown below,

<table>
<tr>
<th>Shortcut Key</th><th>Description</th></tr>
<tr>
<td>
Access key + j	</td><td>
Focuses into the accordion control</td></tr>
<tr>
<td>
Up</td><td>
Moves to previous panel</td></tr>
<tr>
<td>
Down</td><td>
Moves to next panel</td></tr>
<tr>
<td>
Left</td><td>
Moves to previous panel</td></tr>
<tr>
<td>
Right</td><td>
Moves to next panel</td></tr>
<tr>
<td>
Home</td><td>
Moves to the first accordion panel</td></tr>
<tr>
<td>
End</td><td>
Moves to the last accordion panel</td></tr>
</table>

### Configure keyboard interaction

The following steps explains how to enable keyboard interaction for an **Accordion** widget.

In an HTML page, define a &lt;div&gt; element that is a container for Accordion widget and add the contents correspondingly.

{% highlight html %}

<div id="accordion" style="width: 500px" ej-accordion e-allowkeyboardnavigation="true">    
</div>

{% endhighlight %}

N> Need to set focus on Accordion component to access the keyboard shortcuts.