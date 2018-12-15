---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: AngularJS
control: ListBox
documentation: ug
---

# Appearance and Styling

## Theme

**ListBox** control support rich appearance. This control consist of six flat themes and six gradient themes. To use these twelve themes, refer the themes files in HTML file. 

You need two style sheets to apply styles to **ListBox** control; one **ej.widgets.core.min.css** and one **ej.theme.min.css**. If you use **ej.web.all.min.css** then you don’t need to use **ej.widgets.core.min.css** and **ej.theme.min.css** because **ej.web.all.min.css** is a combination of these two.

The core style sheet applies styles related to positioning and size, but are not related to the color scheme and always require the control to look correct and function properly. The theme styles sheet applies theme-specific styles like colors and backgrounds.

The following list is of themes supported by **ListBox**:

* default-theme
* flat-azure-dark
* flat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* Material
* office-365
* Bootstrap
* High-Contrast-01
* High-contrast-02

Add the following code in your **HTML** page.

{% highlight html %}

<!DOCTYPE html>
<html lang="en" ng-app="listboxApp">
   <head>
      <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/gradient-lime/ej.web.all.min.css" rel="stylesheet" />
      <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.1.1.min.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
      <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script>
        <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
   </head>
 <body ng-controller="ListboxCtrl">
      <div id="control">
        <ul id="selectcustomer" ej-listbox e-datasource="dataList" e-fields-text="text"></ul>
    </div>
      <script>
         angular.module('listboxApp', ['ejangular'])
         .controller('ListboxCtrl', function ($scope, $document) {
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
           
         });
      </script>
   </body>
</html>

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)


## Css Class


**ListBox** control also allows you to customize its appearance using user-defined CSS and custom skin options such as colors and backgrounds. To apply custom themes you have a property called **cssClass**. **cssClass** property sets the root class for **ListBox** theme.

Using this **cssClass** you can override the existing styles under the theme style sheet. The theme style sheet applies theme-specific styles like colors and backgrounds. In the following example, the value of **cssClass** property is set as **customClass**. **customClass** is added as root class to **ListBox** control at the runtime. From this root class you can customize the **ListBox** control theme.

Add the following code in your **HTML** page to render the ListBox.

{% highlight html %}
   
<!DOCTYPE html>
<html lang="en" ng-app="listboxApp">
   <head>
      <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/gradient-lime/ej.web.all.min.css" rel="stylesheet" />
      <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.1.1.min.js"></script>
      <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
      <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script>
        <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
   </head>
 <body ng-controller="ListboxCtrl">
      <div id="control">
        <ul id="selectcustomer" ej-listbox e-datasource="dataList" e-fields-text="text" e-cssclass="customclass"></ul>
    </div>
      <script>
         angular.module('listboxApp', ['ejangular'])
         .controller('ListboxCtrl', function ($scope, $document) {
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
         });
      </script>
   </body>
</html>

{% endhighlight %}

In the following style sheet the existing theme style sheet file has been over-ridden using root class **customClass**. 

Add the following code in your style section.

{% highlight css %}

<style>
    .customclass .e-listbox .e-select {
        background: #FF1975;
    }
</style>

{% endhighlight %}


![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)

