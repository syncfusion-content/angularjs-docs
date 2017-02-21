---
layout: post
title: Keyboard-Navigation
description: keyboard navigation
platform: Angular-1
control: Tab
documentation: ug
keywords: ejtab, tab, angularjs tab 
---

# Keyboard Navigation

**Tab** control provides supports **keyboard** interaction. Using this functionality you can interact with control using keyboard. This is achieved by enabling [allowKeyboardNavigation](https://help.syncfusion.com/api/js/ejtab#members:allowkeyboardnavigation) to **true**. By default this property value is set to ‘**true**’.

Following table illustrates the accessible key and their usage

<table>
<tr>
<th>
Keys</th><th>
Behavior</th></tr>
<tr>
<td>
Up</td><td>
Selected previous item.</td></tr>
<tr>
<td>
Right</td><td>
Selected previous item.</td></tr>
<tr>
<td>
Down</td><td>
Selected next item.</td></tr>
<tr>
<td>
Left</td><td>
Selected next item.</td></tr>
<tr>
<td>
Home</td><td>
Selected first item.</td></tr>
<tr>
<td>
End</td><td>
Selected last item.</td></tr>
</table>
The following code example is used to render the **Tab** element in **RTL** format. 

Add the following **HTML** to render **Tab** with **keyboard** navigation.

{% highlight html %}

N> Need to set focus on Tab component to access the keyboard shortcuts.