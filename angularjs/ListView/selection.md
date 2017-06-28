---
layout: post
title: selection
description: selection
platform: Angular-1
control: ListView
documentation: ug
---

## Selection

### MultiSelection



**ListView** has a checklist feature that is used to select multiple list items at the same time in the **ListView**. For this, set **e-enablecheckmark** property to **“True”**.

Refer the following code examples.

{% highlight html %}


    <div ej-listview id="anglistview" e-width="width" e-enablecheckmark="checkmark">
                    <ul>
                        <li data-ej-text="Artwork"></li>
                        <li data-ej-text="Abstract"></li>
                        <li data-ej-text="2 Acrylic Mediums"></li>
                        <li data-ej-text="Creative Acrylic"></li>
                        <li data-ej-text="Modern Painting"></li>
                        <li data-ej-text="Canvas Art"></li>
                        <li data-ej-text="Black white"></li>
                        <li data-ej-text="Children"></li>
                        <li data-ej-text="Preschool Crafts"></li>
                        <li data-ej-text="School-age Crafts"></li>
                    </ul>
                </div>


{% endhighlight %}



Add the following script in your code.

{% highlight js %}


syncApp.controller('ListViewCtrl', function ($scope) {
    $scope.width = 400; 
    $scope.checkmark = true;

});


{% endhighlight %}



Run the codes to get the following output

![https://help.syncfusion.com/js/ListView/Selection_images/multiselection_img1.png](selection_images\multiselection_img1.png)

### PreventSelection

When selecting a specific list item, it is highlighted with an active color. **e-preventselection** property is used to prevent this behavior by setting it to **“True”**.

**NOTE**

When the click or select action is completed, the highlight is undone automatically even when the property is set to “False”.

Refer the following code examples.

{% highlight html %}


<div ej-listview id="anglistview" e-width="width" e-preventselection="selection">
                    <ul>
                        <li data-ej-text="Artwork"></li>
                        <li data-ej-text="Abstract"></li>
                        <li data-ej-text="2 Acrylic Mediums"></li>
                        <li data-ej-text="Creative Acrylic"></li>
                        <li data-ej-text="Modern Painting"></li>
                        <li data-ej-text="Canvas Art"></li>
                        <li data-ej-text="Black white"></li>
                        <li data-ej-text="Children"></li>
                        <li data-ej-text="Preschool Crafts"></li>
                        <li data-ej-text="School-age Crafts"></li>
                    </ul>
                </div>


{% endhighlight %}



Add the following script in your code.

{% highlight js %}


syncApp.controller('ListViewCtrl', function ($scope, $rootScope) {
    $scope.width = 400; 
    $scope.selection = true;

});


{% endhighlight %}



### PersistSelection

The **e-persistSelection** property is used to highlight the selected item in the **ListView** component even after touch end happens. By default, the active state is removed once the touch end happens.

Refer the following code examples.

{% highlight html %}

<div ej-listview id="anglistview" e-width="width" e-persistselection="selection">
                    <ul>
                        <li data-ej-text="Artwork"></li>
                        <li data-ej-text="Abstract"></li>
                        <li data-ej-text="2 Acrylic Mediums"></li>
                        <li data-ej-text="Creative Acrylic"></li>
                        <li data-ej-text="Modern Painting"></li>
                        <li data-ej-text="Canvas Art"></li>
                        <li data-ej-text="Black white"></li>
                        <li data-ej-text="Children"></li>
                        <li data-ej-text="Preschool Crafts"></li>
                        <li data-ej-text="School-age Crafts"></li>
                    </ul>
                </div>


{% endhighlight %}



Add the following script in your code.

{% highlight js %}


syncApp.controller('ListViewCtrl', function ($scope, $rootScope) {
    $scope.width = 400; 
    $scope.selection = true;

});


{% endhighlight %}



Run the codes to get the following output

![https://help.syncfusion.com/js/ListView/Selection_images/persistselection_img1.png](selection_images\persistselection_img1.png)



