---
layout: post
title: Grouping
description: Grouping
platform: AngularJS
control: ListBox
documentation: ug
---

# Grouping

The ListBox items can be categorize by using the following methods.

1. Using CSS class

2. Grouping with Local Data binding

## Using CSS class name

The header for each group can be defined using the “li” element”. 

{% tabs %}
{% highlight html %}

   <ul id="selectgroup" ej-listbox>
            <li class="e-ghead">A</li>
            <li>Albania</li>
            <li>Argentina</li>
            <li>Algeria</li>
            <li>Angola</li>
            <li>Afghanistan</li>
            <!--header-->
            <li class="e-ghead">B</li>
            <li>Brazil</li>
            <li>Bahrain</li>
            <li>Burma</li>
            <li>Barbados</li>
            <li>Botswana</li>
            <li>Belarus</li>
            <li>Bolivia</li>
   </ul>

{% endhighlight %}

{% endtabs %}

![](Grouping_Images\Grouping_img1.png)

## Grouping with Local Data binding

The ListBox items can be categorized by using a specific field. This is enabled by using groupBy field on data source binding. By default grouping is disabled in ListBox. The below given example explains the behavior of grouping with JSON array binding.

{% seealso %} [Data Binding](http://help.syncfusion.com/angular-1/listbox/databinding). {% endseealso %}

The grouping will be defined based on the “groupBy” API in fields object.

{% highlight html %}

   <ul id="selectgroup" ej-listbox e-datasource="dataList" e-fields-text="text" e-fields-groupby="groupby"></ul>
   
{% endhighlight %}

{% highlight javascript %}

  $scope.dataList = [
         { skill: "Bahrain", category: "B" }, { skill: "Brazil", category: "B" }, { skill: "Argentina", category: "A" },
         { skill: "Bangladesh", category: "B" }, { skill: "Burma", category: "B" }, { skill: "Afghanistan", category: "A" }, { skill: "Antigua and Barbuda", category: "A" },
         { skill: "Barbados", category: "B" }, { skill: "Botswana", category: "B" }, { skill: "Albania", category: "A" }, { skill: "Andorra", category: "A" },
         { skill: "Belarus", category: "B" }, { skill: "Bolivia", category: "B" }, { skill: "Algeria", category: "A" }, { skill: "Angola", category: "A" }
             ];
  $scope.text = "skill";
  $scope.groupby = "category";
   
{% endhighlight %}

![](Grouping_Images\Grouping_img2.png)