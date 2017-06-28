---
layout: post
title: Functionalities in the DropDownList widget
description: Functionalities in the DropDownList widget
platform: AngularJS
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, Selection, Grouping, Sorting
---
# Functionalities

## Selection

By default only one item can be selected from the popup list. For multiple selection, you have to enable [checkboxes](Checkbox). The selected item consist of active class (“e-active”) to differentiate it from other items.

The following API’s, select the items in the DropDownList via text or value or indices.

<table>
    <tr>
        <th>
            Properties
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            {{'[value](http://help.syncfusion.com/api/js/ejdropdownlist#members:value)'| markdownify }} 
            <br/>
        </td>
        <td>
            To select an item initially, you can pass the item’s value via value property.
            <br/>
            Multiple items can select via value property, the given values should be separated by delimiter character.
        </td>
    </tr>
    <tr>
        <td>
            {{'[text](http://help.syncfusion.com/api/js/ejdropdownlist#members:text)'| markdownify }} 
            <br/>
        </td>
        <td>
            To select an item initially, you can pass the item’s text via text property.
            <br/>
            Multiple items can select via text property, the given values should be separated by delimiter character.
        </td>
    </tr>
    <tr>
        <td>
            {{'[selectedIndex](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectedindex)'| markdownify }} 
            <br/>
        </td>
        <td>
            Select a single item by passing an index value to the selectedIndex property.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
             {{'[selectedIndices](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectedindices)'| markdownify }}
            <br/>
        </td>
        <td>
            Select more than one items by passing index values to the selectedIndices property when multi selection enabled. 
            <br/>
        </td>
    </tr>
</table>

N> Index starts from 0 here.
N> To use “selectedIndices” property, you should enable with showCheckbox or multiSelectMode property.

The following methods, select the items in the DropDownList.

<table>
    <tr>
        <th>
            Methods
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            {{'[selectItemByIndices](http://help.syncfusion.com/api/js/ejdropdownlist#methods:selectitembyindices)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to select the list of items in the DropDownList through the Index of the items.
        </td>
    </tr>
    <tr>
        <td>
            {{'[selectItemByText](http://help.syncfusion.com/api/js/ejdropdownlist#methods:selectItemByText)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to select an item in the DropDownList by using the given text value.
        </td>
    </tr>
    <tr>
        <td>
            {{'[selectItemByValue](http://help.syncfusion.com/api/js/ejdropdownlist#methods:selectitembyvalue)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to select an item in the DropDownList by using the given value.
            <br/>
        </td>
    </tr>
</table>

The following methods, used to retrieve the items from the DropDownList.

<table>
    <tr>
        <th>
            Methods
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            {{'[getListData](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getlistdata)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to retrieve the items that are bound with the DropDownList.
        </td>
    </tr>
    <tr>
        <td>
            {{'[getSelectedItem](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getselecteditem)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to get the selected items in the DropDownList.
        </td>
    </tr>
    <tr>
        <td>
            {{'[getSelectedValue](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getSelectedValue)'| markdownify }}
            <br/>
        </td>
        <td>
            This method is used to retrieve the items value that are selected in the DropDownList.
            <br/>
        </td>
    </tr>
</table>

I> When multiSelectMode is enabled in a DropDownList and selected items having same text but its value is different means, the items can be selected. Please refer the online [link](http://jsplayground.syncfusion.com/Sync_5fgywhmb)

### Using value or text

To select an item initially you can pass the item’s value via [value](http://help.syncfusion.com/api/js/ejdropdownlist#members:value) property or [selectItemByValue](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectitembyvalue) method. To achieve this DropDownList widget must be initiated with the associate value. 

{% highlight html %}

 <input type="text" id="dropdown1" ej-dropdownlist e-datasource="data" e-fields-text="text" e-fields-value="value" e-value="item3" />
     
{% endhighlight %}

{% highlight javascript %}
    
        var items = [{
            text: "ListItem 1",
            value: "item1"
        }, {
            text: "ListItem 2",
            value: "item2"
        }, {
            text: "ListItem 3",
            value: "item3"
        }, {
            text: "ListItem 4",
            value: "item4"
        }, {
            text: "ListItem 5",
            value: "item5"
        }];
        angular.module('dropdownlistApp', ['ejangular'])
        .controller('dropdownlistCtrl', function ($scope) {
            $scope.data = items;
        });

{% endhighlight %}

![](Functionalities_images/Functionalities_img1.png)

N> To retrieve the selected item’s LI elements and value you can use [getSelectedItem](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getselecteditem), [getSelectedValue](http://help.syncfusion.com/api/js/ejdropdownlist#methods:getselectedvalue) methods respectively.

{% highlight javascript %}
	
  //create an instance from an existing DropDownList.

        // only after control creation we can get dropdownObj otherwise it throws exception.

        var obj = $('#dropdown1').data("ejDropDownList");
        //the below given code will return the li element of the selected item
        console.log(obj.getSelectedItem());
        //the below given code will return the JSON object of the selected item
        console.log(JSON.parse(obj.getSelectedValue()));
    });
	
{% endhighlight %}

### Using indices

You can select a single or more than one item by passing index values to the properties [selectedIndex](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectedindex) or [selectedIndices](http://help.syncfusion.com/api/js/ejdropdownlist#members:selectedindices) respectively. Index starts from 0 here.

{% highlight html %}

     <input type="text" id="dropdown1" ej-dropdownlist e-datasource="data" e-fields-text="text" e-fields-value="value" e-selectedindex="1" />
     
{% endhighlight %}

{% highlight javascript %}
  
         var items = [{
            text: "ListItem 1",
            value: "item1"
        }, {
            text: "ListItem 2",
            value: "item2"
        }, {
            text: "ListItem 3",
            value: "item3"
        }, {
            text: "ListItem 4",
            value: "item4"
        }, {
            text: "ListItem 5",
            value: "item5"
        }];
        angular.module('dropdownlistApp', ['ejangular'])
        .controller('dropdownlistCtrl', function ($scope) {
            $scope.data = items;
        });

{% endhighlight %}

![](Functionalities_images/Functionalities_img2.png)

I> To use "selectedIndices" property, you should enable either showCheckbox or multiSelectMode property First.

{% highlight html %}

     <input type="text" id="dropdown1" ej-dropdownlist e-datasource="data" e-fields-text="text" e-fields-value="value" e-selectedindices="select" e-showcheckbox="true"/>
     
{% endhighlight %}

{% highlight javascript %}
	
        var items = [{
            text: "ListItem 1",
            value: "item1"
        }, {
            text: "ListItem 2",
            value: "item2"
        }, {
            text: "ListItem 3",
            value: "item3"
        }, {
            text: "ListItem 4",
            value: "item4"
        }, {
            text: "ListItem 5",
            value: "item5"
        }];
        angular.module('dropdownlistApp', ['ejangular'])
        .controller('dropdownlistCtrl', function ($scope) {
            $scope.data = items;
            $scope.select=[1,2];
        });

{% endhighlight %}

### Unselect items

Similarly, you can unselect a single or multiple items by using [unselectItemByValue](http://help.syncfusion.com/api/js/ejdropdownlist#methods:unselectitembyvalue) or [unselectItemByIndices](http://help.syncfusion.com/api/js/ejdropdownlist#methods:unselectitembyindices) or [unselectItemByText](http://help.syncfusion.com/api/js/ejdropdownlist#methods:unselectitembytext) methods. This will remove the selection state of the corresponding data item from the popup list and textbox. 

{% highlight html %}

    <input type="text" id="dropdown1" ej-dropdownlist e-datasource="data" e-fields-text="text" e-fields-value="value" e-selectedindices="select" e-showcheckbox="true" />
    
    <input type="button" value="Unselect" onclick="unselect()" />

     
{% endhighlight %}

{% highlight javascript %}

    var items = [{
            text: "ListItem 1",
            value: "item1"
        }, {
            text: "ListItem 2",
            value: "item2"
        }, {
            text: "ListItem 3",
            value: "item3"
        }, {
            text: "ListItem 4",
            value: "item4"
        }, {
            text: "ListItem 5",
            value: "item5"
        }];
        angular.module('dropdownlistApp', ['ejangular'])
        .controller('dropdownlistCtrl', function ($scope) {
            $scope.data = items;
            $scope.select = [1,2,3];
        });
        function unselect() {
            var obj = $('#dropdown1').data("ejDropDownList");
            obj.unselectItemByValue("item2");
            obj.unselectItemsByIndices(2);
            obj.unselectItemByText("ListItem 4");
        }

{% endhighlight %}

## Grouping

The DropDownList items can be categorized by using a specific field in the popup list. This is enabled by using [groupBy](http://help.syncfusion.com/api/js/ejdropdownlist#members:fields-groupby) field on data source binding. By default grouping is disabled in DropDownList.
The below given example explains the behavior of grouping with JSON array binding.

{% highlight html %}

    <input type="text" id="dropdown1" ej-dropdownlist e-width="150" e-datasource="data" e-fields-text="skill" e-fields-groupby="category" e-watermarktext="Select a vegetable" e-popupheight="300" />
     
{% endhighlight %}

{% highlight javascript %}

        var skillset = [{
            skill: "Cabbage",
            category: "Leafy and Salad"
        }, {
            skill: "Pea",
            category: "Leafy and Salad"
        }, {
            skill: "Spinach",
            category: "Leafy and Salad"
        }, {
            skill: "Wheatgrass",
            category: "Leafy and Salad"
        }, {
            skill: "Yarrow",
            category: "Leafy and Salad"
        }, {
            skill: "Chickpea",
            category: "Beans"
        }, {
            skill: "Green bean",
            category: "Beans"
        }, {
            skill: "Horse gram",
            category: "Beans"
        }, {
            skill: "Peanut",
            category: "Beans"
        }, {
            skill: "Pigeon pea",
            category: "Beans"
        }, {
            skill: "Garlic",
            category: "Bulb and Stem"
        }, {
            skill: "Garlic Chives",
            category: "Bulb and Stem"
        }, {
            skill: "Lotus root",
            category: "Bulb and Stem"
        }, {
            skill: "Nopal",
            category: "Bulb and Stem"
        }, {
            skill: "Onion",
            category: "Bulb and Stem"
        }, {
            skill: "Shallot",
            category: "Bulb and Stem"
        }, {
            skill: "Beetroot",
            category: "Root and Tuberous"
        }, {
            skill: "Carrot",
            category: "Root and Tuberous"
        }, {
            skill: "Ginger",
            category: "Root and Tuberous"
        }, {
            skill: "Potato",
            category: "Root and Tuberous"
        }, {
            skill: "Radish",
            category: "Root and Tuberous"
        }, {
            skill: "Turmeric",
            category: "Root and Tuberous"
        }];
        angular.module('dropdownlistApp', ['ejangular'])
        .controller('dropdownlistCtrl', function ($scope) {
            $scope.data = skillset;
        });

{% endhighlight %}

![](Functionalities_images/Functionalities_img3.png)

N> Grouping has restrictions in the following scenarios,<BR>
1.  It is not supported on using HTML "select" element with predefined set of options<BR>
2.  When using UL-LI elements you need to use “e-category” class in LI element to specify it as the grouping header. The following code will explain this behavior,<BR>
3.  The sorting behavior varies when grouping is enabled in the DropDownList, based on browser as we have used browser based stable sorting method when there is multiple level of sorting. <BR>
4.  To overcome this behavior on sorting order with browser, we suggest you to set ej.support.stableSort as false from the script when the page is loaded or in document ready function.
  
   {% highlight javascript %}
   
    <script type="text/javascript">
            $(document).ready(function () {
                ej.support.stableSort = false;            
            });
    </script>
    
   {% endhighlight %}

{% highlight html %}

            <input type="text" id="dropdown1" ej-dropdownlist e-targetid="dropdownitems"/>
                
{% endhighlight %}

![](Functionalities_images/Functionalities_img4.jpeg)

I> Virtual scrolling is not supported with Grouping.

## Sorting

Sorting is enabled to order to display the items alphabetically in either ascending or descending order. By default the items is displayed in the initialized order, use [enableSorting](http://help.syncfusion.com/api/js/ejdropdownlist#members:enablesorting) property to automatically sort strings based on text field value. You can assign either “ascending” or “descending” string values to the [sortOrder](http://help.syncfusion.com/api/js/ejdropdownlist#members:sortorder) property to sort out the list items. By default ascending order is followed when "sortOrder" property is not specified. 

{% highlight html %}

   <input type="text" id="dropdown1" ej-dropdownlist e-datasource="data" e-fields-text="text" e-fields-value="value" e-enablesorting="true" e-sortorder="ascending" />
                
{% endhighlight %}

{% highlight javascript %}

        var items = [{
            text: "ListItem 1",
            value: "item1"
        }, {
            text: "ListItem 5",
            value: "item5"
        }, {
            text: "ListItem 4",
            value: "item4"
        }, {
            text: "ListItem 2",
            value: "item2"
        }, {
            text: "ListItem 3",
            value: "item3"
        }, ];
        angular.module('dropdownlistApp', ['ejangular'])
        .controller('dropdownlistCtrl', function ($scope) {
            $scope.data = items;
        });
  
{% endhighlight %}

I> Virtual scrolling is not supported with Sorting.

## Cascading

This works for series of DropDownList in which items are filtered based on the previous DropDownList‘s selection. Cascading is performed based on the value field and this field should be bounded with a foreign key. To perform cascading, specify the child DropDownList’s id in [cascadeTo](http://help.syncfusion.com/api/js/ejdropdownlist#members:cascadeto) property and use delimiter (“,”) to specify more than one child DropDownList.

Configuring the data items for cascading to the series of DropDownList is demonstrated below

{% highlight html %}

     <div style="width: 400px;">
            <div style="float: left;">
                <span>Select Group</span>
                <input id="groupslist" type="text" ej-dropdownlist e-datasource="group" e-fields-text="text" e-fields-value="parentid" e-cascadeto='countrylist'/>
            </div>
            <div style="float: right;">
                <span>Select Country</span>
                <input id="countrylist" type="text" ej-dropdownlist e-datasource="countries" e-enabled="false" />
            </div>
     <div>
                
{% endhighlight %}

{% highlight javascript %}
 
        var groups = [{
            parentId: 'a',
            text: "Group A"
        }, {
            parentId: 'b',
            text: "Group B"
        }, {
            parentId: 'c',
            text: "Group C"
        }, {
            parentId: 'd',
            text: "Group D"
        }, {
            parentId: 'e',
            text: "Group E"
        }];
        //second dropdown
        var countries = [{
            value: 11,
            parentId: 'a',
            text: "Algeria"
        }, {
            value: 12,
            parentId: 'a',
            text: "Armenia"
        }, {
            value: 13,
            parentId: 'a',
            text: "Bangladesh"
        }, {
            value: 14,
            parentId: 'a',
            text: "Cuba"
        }, {
            value: 15,
            parentId: 'b',
            text: "Denmark"
        }, {
            value: 16,
            parentId: 'b',
            text: "Egypt"
        }, {
            value: 17,
            parentId: 'c',
            text: "Finland"
        }, {
            value: 18,
            parentId: 'c',
            text: "India"
        }, {
            value: 19,
            parentId: 'c',
            text: "Malaysia"
        }, {
            value: 20,
            parentId: 'd',
            text: "New Zealand"
        }, {
            value: 21,
            parentId: 'd',
            text: "Norway"
        }, {
            value: 22,
            parentId: 'd',
            text: "Poland"
        }, {
            value: 23,
            parentId: 'e',
            text: "Romania"
        }, {
            value: 24,
            parentId: 'e',
            text: "Singapore"
        }, {
            value: 25,
            parentId: 'e',
            text: "Thailand"
        }, {
            value: 26,
            parentId: 'e',
            text: "Ukraine"
        }];
        angular.module('dropdownlistApp', ['ejangular'])
        .controller('dropdownlistCtrl', function ($scope) {
            $scope.group = groups;
            $scope.country = countries;
        });

{% endhighlight %}

![](Functionalities_images/Functionalities_img5.png)

![](Functionalities_images/Functionalities_img6.jpeg)

### Binding the data source to the cascading DropDownList using cascade event

Bind the data source to the cascading DropDownList dynamically using [cascade](http://help.syncfusion.com/api/js/ejdropdownlist#events:cascade) event as demonstrated below,

{% highlight html %}

      <div style="width: 530px;">
        <div style="float: left;">
            <span>Select Group</span>
            <input id="groupslist" type="text" ej-dropdownlist e-datasource="group" e-fields-text="text" e-fields-value="parentId" e-cascadeto="countrylist,playerslist" e-cascade="onChange" />
        </div>
        <div style="float: left; padding-left: 50px;">
            <span>Select Country</span>
            <input id="countrylist" type="text" ej-dropdownlist e-enabled="false" />
        </div>
        <div style="float: right;">
            <span>Select Players</span>
            <input id="playerslist" type="text" ej-dropdownlist e-enabled="false"/>
        </div>
    </div>
                
{% endhighlight %}

{% highlight javascript %}
  
    var groups = [{
        parentId: 'a',
        text: "Group A"
    }, {
        parentId: 'b',
        text: "Group B"
    }];
    angular.module('dropdownlistApp', ['ejangular'])
    .controller('dropdownlistCtrl', function ($scope) {
        $scope.group = groups;
    });
    function onChange(args) {
        var countries = [{
            parentId: 'a',
            text: "Algeria"
        }, {
            parentId: 'a',
            text: "Armenia"
        }, {
            parentId: 'a',
            text: "Bangladesh"
        }, {
            parentId: 'a',
            text: "Cuba"
        }, {
            parentId: 'b',
            text: "Denmark"
        }, {
            parentId: 'b',
            text: "Egypt"
        }];

        var players = [{
            parentId: 'a',
            text: "Adams"
        }, {
            parentId: 'a',
            text: "Clarke"
        }, {
            parentId: 'b',
            text: "Brett"
        }, {
            parentId: 'b',
            text: "James"
        }];

        var obj2 = $('#countrylist').data("ejDropDownList");
        obj2.option({
            "dataSource": countries,
            "enabled": true
        });

        var obj3 = $('#playerslist').data("ejDropDownList");
        obj3.option({
            "dataSource": players,
            "enabled": true
        });
    }

{% endhighlight %}

![](Functionalities_images/Functionalities_img7.png)

## Search

Items are searched based on the keyed in values to the textbox. There are two types of searches,

* Incremental Search
* Filter Search

### Incremental Search

Selects the item in the popup list based on the keyed in value. If the time taken to type exceeds 1000 milliseconds then filtered items will be reset based on the current input value. By default this mode of search is enabled. Incremental search can be case sensitive or case insensitive. To make case sensitive, you can use [caseSensitiveSearch](http://help.syncfusion.com/api/js/ejdropdownlist#members:casesensitivesearch) property.

{% highlight html %}

    <input type="text" id="dropdown1" ej-dropdownlist e-datasource="data" e-fields-text="text" e-fields-value="value" e-enableincrementalsearch="true" e-casesensitivesearch="true" />
                
{% endhighlight %}

{% highlight javascript %}

    var items = [{
        text: "Adams",
        value: "emp1"
    }, {
        text: "James",
        value: "emp2"
    }, {
        text: "Maria",
        value: "emp3"
    }, {
        text: "Jessica",
        value: "emp4"
    }, {
        text: "jenneth",
        value: "emp5"
    }];
    angular.module('dropdownlistApp', ['ejangular'])
    .controller('dropdownlistCtrl', function ($scope) {
        $scope.data = items;
    });

{% endhighlight %}

![](Functionalities_images/Functionalities_img8.png)

### Filter search

You can quickly locate specific item within a large data source by filtering matches with a search box. A text box appears in the popup list for searching when [enableFilterSearch](http://help.syncfusion.com/api/js/ejdropdownlist#members:enablefiltersearch) property is enabled. By default, filtering returns the matched items list based on text in search textbox. 
You can configure the search filter by using [filterType](http://help.syncfusion.com/api/js/ejdropdownlist#members:filtertype) property. There is two types of filter options,

* Starts With 
* Contains

N> Items are filtered based on “contains” filter type by default.

{% highlight html %}

    <input type="text" id="dropdown1" ej-dropdownlist e-datasource="data" e-fields-text="text" e-fields-value="value" e-enablefiltersearch="true" e-filtertype="startsWith" />
                
{% endhighlight %}

{% highlight javascript %}

        var items = [{
            text: "Adams",
            value: "emp1"
        }, {
            text: "James",
            value: "emp2"
        }, {
            text: "Maria",
            value: "emp3"
        }, {
            text: "Jessica",
            value: "emp4"
        }, {
            text: "jenneth",
            value: "emp5"
        }];
        angular.module('dropdownlistApp', ['ejangular'])
        .controller('dropdownlistCtrl', function ($scope) {
            $scope.data = items;
        });

{% endhighlight %}

![](Functionalities_images/Functionalities_img9.png)