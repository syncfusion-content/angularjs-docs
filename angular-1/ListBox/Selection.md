---
layout: post
title: Selection
description: Selection
platform: Angular-1
control: ListBox
documentation: ug
---

# Selection

The ListBox component allows to highlight the selected item in the List items. It allows multiple selection also. 

## Selection with two-way binding

By default, the ListBox component allows to select the single list item. Also, Listbox component supports the two-way binding feature. When a component model attribute is bound to a scope variable, it can reflect the changes both ways.

Please use the below code the bind the ListBox in two-way support.

{% tabs %}
{% highlight html %}

    <div id="control">
        <ul id="bookSelect" ej-listbox e-datasource="dataList" e-value="value"></ul>
    </div>
    <div id="binding" style="padding-top:10px;">
        <input type="text" id="dropValue" class="input ejinputtext" ng-model="value" />
    </div>

{% endhighlight %}

{% highlight javascript %}

       $scope.dataList = [
                          { empid: "cr1", text: "Dodge Avenger" },
                          { empid: "cr2", text: "Chrysler 200" },
                          { empid: "cr3", text: "Ford Focus" },
                          { empid: "cr4", text: "Ford Taurus", },
                          { empid: "cr5", text: "Dazzler", },
                          { empid: "cr6", text: "Chevy Spark", },
                          { empid: "cr7", text: "Chevy Volt", },
                          { empid: "cr8", text: "Honda Fit", },
                          { empid: "cr9", text: "Honda Crosstour", },
                          { empid: "cr10", text: "Acura RL", },
                          { empid: "cr11", text: "Hyundai Elantra", },
                          { empid: "cr12", text: "Mazda3", }
             ];
       $scope.value = "Ford Taurus";     

{% endhighlight %}
{% endtabs %}

![](Selection_Images\Selection_img1.png)

## Multiple selection

To enable the multiple selection by using “allowMultiSelection” property. You can select the multiple list items using <kbd>“Ctrl”</kbd> and <kbd>“Shift”</kbd> keys.

{% seealso %} [Keyboard Interaction](http://help.syncfusion.com/angular-1/listbox/keyboard-interaction). {% endseealso %}

{% highlight html %}

          <ul id="selectgroup" ej-listbox e-datasource="dataList" e-selectedindex="selectedindex" e-allowmultiselection="true"></ul>
          
{% endhighlight %}

![](Selection_Images\Selection_img2.png)

## Checkbox

To enable the checkbox in the ListBox component by using "showCheckbox" property. The ListBox component allows the selection of list items through checkbox.

The specified list items can be checked on initialization of the ListBox component by using “checkedIndices” property. 

{% seealso %} [checkedIndices](http://helpjs.syncfusion.com/js/api/ejlistbox#members:checkedindices). {% endseealso %}

{% highlight html %}

    <ul id="selectgroup" ej-listbox e-datasource="dataList" e-showcheckbox="true" e-checkedindices="checkedindices"></ul>

{% endhighlight %}

{% highlight javascript %}

   $scope.dataList = [
                          { empid: "cr1", text: "Dodge Avenger" },
                          { empid: "cr2", text: "Chrysler 200" },
                          { empid: "cr3", text: "Ford Focus" },
                          { empid: "cr4", text: "Ford Taurus" },
                          { empid: "cr5", text: "Dazzler" },
                          { empid: "cr6", text: "Chevy Spark" },
                          { empid: "cr7", text: "Chevy Volt" },
                          { empid: "cr8", text: "Honda Fit" },
                          { empid: "cr9", text: "Honda Crosstour" },
                          { empid: "cr10", text: "Acura RL" },
                          { empid: "cr11", text: "Hyundai Elantra" },
                          { empid: "cr12", text: "Mazda3" }
             ];
  $scope.checkedindices = [2, 5];

{% endhighlight %}

![](Selection_Images\Selection_img3.png)