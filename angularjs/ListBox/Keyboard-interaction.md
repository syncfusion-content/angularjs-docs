---
layout: post
title: Keyboard-interaction
description: Keyboard-interaction
platform: AngularJS
control: ListBox
documentation: ug
---

# Keyboard interaction

To use the Keyboard shortcut keys as an alternative for mouse actions to interact with the ListBox component. Refer to the following table for details of the short cut keys and its corresponding usage.

<table>
<tr>
<td>
<b>Shortcut Key</b></td><td>
<b>Single Selection</b></td><td>
<b>Multi Selection</b></td></tr>
<tr>
<td>
<kbd>Up</kbd></td><td>
Selects to previous item</td><td>
Selects to previous item and clear all existing selection</td></tr>
<tr>
<td>
<kbd>Down</kbd></td><td>
Selects to next item</td><td>
Selects to next item and clear all existing selection</td></tr>
<tr>
<td>
<kbd>Left</kbd></td><td>
Selects to previous item</td><td>
Selects to previous item and clear all existing selection</td></tr>
<tr>
<td>
<kbd>Right</kbd></td><td>
Selects to next item</td><td>
Selects to next item and clear all existing selection</td></tr>
<tr>
<td>
<kbd>Home</kbd></td><td>
Selects to first list item</td><td>
Selects to first item and clear all existing selection</td></tr>
<tr>
<td>
<kbd>End</kbd></td><td>
Selects to last list item</td><td>
Selects to last item and clear all existing selection</td></tr>
<tr>
<td>
<kbd>Page Up</kbd></td><td>
Selects the item in list item (i.e.,) scrolls up to next set of items</td><td>
Selects the item in list item (i.e.,) scrolls up to next set of items and clear all existing selection</td></tr>
<tr>
<td>
<kbd>Page Down</kbd></td><td>
Selects the item in list item (i.e.,) scrolls down to next set of items</td><td>
Selects the item in list item (i.e.,) scrolls down to next set of items and clear all existing selection</td></tr>
<tr>
<td>
<kbd>Shift + up</kbd></td><td>
Selects the previous item in list item</td><td>
Selects the immediate preceding item from current selected item</td></tr>
<tr>
<td>
<kbd>Shift + Down</kbd></td><td>
Selects the next item in list item</td><td>
Selects the immediate successive item from current selected item</td></tr>
<tr>
<td>
<kbd>Shift + Home</kbd></td><td>
Selects the first list item</td><td>
Selects all items between focused item to first item</td></tr>
<tr>
<td>
<kbd>Shift + End</kbd></td><td>
Selects the last list item</td><td>
Selects all items between focused item to last item</td></tr>
<tr>
<td>
<kbd>Shift + Page Up</kbd></td><td>
Selects the first list item</td><td>
Selects all item between focused item to previous set of list items</td></tr>
<tr>
<td>
<kbd>Shift + Page Down</kbd></td><td>
Selects the last list item</td><td>
Selects all item between focused item to next set of list items</td></tr>
<tr>
<td>
<kbd>Ctrl + Up</kbd></td><td>
Selects the item in list item (i.e.,) scrolls up to previous set of items</td><td>
Selects the item in list item (i.e.,) scrolls up to previous set of items and clear all existing selection</td></tr>
<tr>
<td>
<kbd>Ctrl + Down</kbd></td><td>
Selects the item in list item (i.e.,) scrolls down to next set of items</td><td>
Selects the item in list item (i.e.,) scrolls down to next set of items clear all existing selection</td></tr>
</table>

N> Initial focus can be done by pressing tab key multiple times until it is focused.

{% highlight html %}

      <div id="control">
        <ul id="selectfont" ej-listbox e-datasource="dataList" e-fields-value="value" e-fields-text="text"></ul>
    </div> 

{% endhighlight %}

{% highlight javascript %}

      $scope.dataList = [
              { fonts: "Algerian" },
              { fonts: "ARIAL" }, { fonts: "Bimini" }, { fonts: "Courier" },
              { fonts: "Cursive" }, { fonts: "Fantasy" }, { fonts: "Georgia" }, { fonts: "Impact" },
              { fonts: "New york" }, { fonts: "Sans-Serif" }, { fonts: "Scripts" }, { fonts: "Times" },
              { fonts: "Times New Roman" }, { fonts: "Verdana" }, { fonts: "Western" }, { fonts: "Zapfellipt bt" }
             ];
             $scope.value = "fonts";
             $scope.text = "fonts";
             $document.bind("keydown", function (e) {
                 if (e.altKey && e.keyCode === 74) { // j- key code.
                     var target = $('#selectfont').data("ejListBox");
                     if (!ej.isNullOrUndefined(target)) {
                         target.selectItemByIndex(0);
                         $("#selectfont_container").focus();
                     }
                 }
             });

{% endhighlight %}

![](Keyboard-interaction_Images\Keyboard-interaction_img1.png)

**Note:**
 
 *Round robin method is used on navigating through the list items in listbox, so that navigation will continue when reaching the start/end of the list item.* 

