---
layout: post
title: Behavior-Settings
description: behavior settings
platform: js
control: GroupButton
documentation: ug
---

# Behavior Settings

EJ AngularJS GroupButton has some default behavior settings which helps you to customize the component based on application needs.

## Different modes of button

EJ AngularJS GroupButton provides the two different types of modes called check box mode, radio button mode. We can achive this using this **e-groupButtonMode** API which can be set through scope varibale. Setting a checkbox mode, we can perform the multiple actions in a single group. In this case, you can toggle the all the buttons state and perform the actions, since it all will behave as individual button in a group of button. 

** Radio Button Mode :** we can perform the only single action with all related actions in a group of button.

** Checkbox Mode :** Here, multiple button can be selected, please check with the below use case for this mode.

**HtML View Section:**

{% highlight html %}

     <div id="groupButton" ej-groupbutton e-groupButtonMode="'checkbox'">
        <ul>
            <li>
                Save
            </li>
            <li>
                Open
            </li>
            <li>
                Delete
            </li>
        </ul>
     </div>

{% endhighlight %}

**Controller section:**

{% highlight js %}

    angular.module("myApp", ['ejangular']).controller("groupbutton", function ($scope) {

    })

{% endhighlight %}

![](Behavior-Settings_images/Behavior-Settings_img1.jpeg)


** Radio Button Mode:** Here, single button only can be selected, Please check with the below code example 

**HTML View Section:**

{% highlight html %}

     <div id="groupButton" ej-groupbutton>
        <ul>
            <li>
                Save
            </li>
            <li>
                Open
            </li>
            <li>
                Delete
            </li>
        </ul>
     </div>

{% endhighlight %}

**Controller Section:**

{% highlight js %}

     <script>
            $("#groupButton").ejGroupButton({
                groupButtonMode: "radiobutton",
                width: "215px"
            });
    </script>    

{% endhighlight %}

![](Behavior-Settings_images/Behavior-Settings_img2.jpeg)

## SelectedItemIndex

The state of the button can be changed by user interacting with the button. Also the selection state of the button can be achieved by using **e-selectedItemIndex** API which is used to select the button items in GroupButton based on index. 

This property will accept the array values and its value will be differ based on current mode of Button. If the Button mode is “Radio”, then the selected items can have single value within the array, since we can select a single button only in this mode. Whereas for the “checkbox” mode, the selectedItemIndex can have the multiple values within an array, since multiple button can be in active state in this mode.

** Setting a selectedItemIndex for checkbox mode **

**HTML View Section:**

{% highlight html %}

     <div id="groupButton" ej-groupbutton e-selectedItemIndex="index">
        <ul>
            <li>
                Save
            </li>
            <li>
                Open
            </li>
            <li>
                Delete
            </li>
        </ul>
     </div>

{% endhighlight %}

** Setting a selectedItemIndex for radio button mode**

**Controller Section:**

{% highlight js %}

     <script>
        angular.module("myApp", ['ejangular']).controller("datepicker", function ($scope) {
		$scope.index=[1];
		});
    </script>

{% endhighlight %}

![](Behavior-Settings_images/Behavior-Settings_img3.jpeg)
