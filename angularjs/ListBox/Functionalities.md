---
layout: post
title: Functionalities in the Syncfusion ListBox component
description: Functionalities in the ListBox component
platform: AngularJS
control: ListBox
documentation: ug
---
# Behavior settings

## Drag and Drop

To move the list item from one Listbox component to another ListBox by using the drag and drop support through “allowDragAndDrop” property.

{% highlight html %}

    <div id="control">
        <ul id="selectskills" ej-listbox e-datasource="dataList" e-fields-text="text" e-height="220" e-width="180" e-allowdraganddrop="true"></ul>
    </div>
    <div id="control">
        <ul id="selected" ej-listbox e-height="220" e-width="180" e-allowdraganddrop="true"></ul>
    </div> 

{% endhighlight %}

{% highlight javascript %}

     $scope.dataList = [
             { skill: "ASP.NET" }, { skill: "ActionScript" }, { skill: "Basic" },
             { skill: "C++" }, { skill: "C#" }, { skill: "dBase" }, { skill: "Delphi" },
             { skill: "ESPOL" }, { skill: "F#" }, { skill: "FoxPro" }, { skill: "Java" },
             { skill: "J#" }, { skill: "Lisp" }, { skill: "Logo" }, { skill: "PHP" }
             ];
    $scope.text = "skill";

{% endhighlight %}


![Drag and Drop](Drag-And-Drop_Images\Drag-and-drop_img1.png)

![Drag and Drop Images](Drag-And-Drop_Images\Drag-and-drop_img2.png)

## Reordering

To reorder the list item within the ListBox component by using “allowDragAndDrop” property.

{% highlight html %}
  
     <div id="control">
        <ul id="selectskills" ej-listbox e-datasource="dataList" e-fields-text="text" e-height="220" e-width="180" e-allowdraganddrop="true"></ul>
    </div>	

{% endhighlight %}

{% highlight javascript %}

        $scope.dataList = [
             { skill: "ASP.NET" }, { skill: "ActionScript" }, { skill: "Basic" },
             { skill: "C++" }, { skill: "C#" }, { skill: "dBase" }, { skill: "Delphi" },
             { skill: "ESPOL" }, { skill: "F#" }, { skill: "FoxPro" }, { skill: "Java" },
             { skill: "J#" }, { skill: "Lisp" }, { skill: "Logo" }, { skill: "PHP" }
        ];

{% endhighlight %}

![Reordering](Drag-And-Drop_Images\Drag-and-drop_img3.png)

![Reordering Images](Drag-And-Drop_Images\Drag-and-drop_img4.png)

N> _The item reordering can be done dynamically without mouse interaction. For that we have provided two methods “[moveUp](http://help.syncfusion.com/js/api/ejlistbox#methods:moveup)” and “[moveDown](http://help.syncfusion.com/js/api/ejlistbox#methods:movedown)”._

## Incremental Search

The [Incremental search](https://en.wikipedia.org/wiki/Incremental_search) helps to finding the specific item in the ListBox. The user types any character in ListBox component for that matched list box item will be selected by enabling the [`enableIncrementalSearch`] property in the ListBox component. Incremental search can be case sensitive or case insensitive. To make case sensitive, you can use [caseSensitiveSearch](https://help.syncfusion.com/api/js/ejlistbox#members:casesensitivesearch) property. 

{% highlight html %}

      <div id="control">
        <ul id="selectfont" ej-listbox e-datasource="dataList" e-fields-value="value" e-fields-text="text" e-enableincrementalsearch ="true"></ul>
    </div> 

{% endhighlight %}

{% highlight javascript %}

      $scope.dataList = [
              { fonts: "Algerian" },
              { fonts: "ARIAL" }, { fonts: "Bimini" }, { fonts: "Courier" },
              { fonts: "Cursive" }, { fonts: "Fantasy" }, { fonts: "Georgia" }, { fonts: "Impact" },
              { fonts: "New York" }, { fonts: "Sans-Serif" }, { fonts: "Scripts" }, { fonts: "Times" },
              { fonts: "Times New Roman" }, { fonts: "Verdana" }, { fonts: "Western" }
             ];
             $scope.value = "fonts";
             $scope.text = "fonts";

{% endhighlight %}

![Incremental Search](Keyboard-interaction_Images\Keyboard-interaction_img1.png)

Press <kbd> tab </kbd> key to get ListBox focus and press <kbd>"C"</kbd> to get the following output.

![Incremental Search Images](Keyboard-interaction_Images\Keyboard-interaction_img2.png)





