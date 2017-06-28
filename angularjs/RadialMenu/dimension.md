---
layout: post
title: Dimension
description: Dimension
platform: AngularJS
control: Radial Menu
documentation: ug
---

# Dimension

You can customize **Radial Menu** dimension by using **e-radius** and **e-position** properties.

## Radius

You can customize the **Radial Menu** size by using the **e-radius** property. By default, the Radial Menu radius is set as 150px. Refer to the following code example.

{% highlight html %}

    <ej-radialmenu id="defaultradialmenu" e-targetelementid="radialtarget1" e-radius="radius">
    <e-items>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/font.png" e-text="Bold></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/f1.png" e-text="Italic"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/align.png" e-text="Align"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/sort.png" e-text="Sort"></e-item>
    </e-items>
    </ej-radialmenu>

{% endhighlight %}

Define **e-radius** value in angular module in script section.
    
{% highlight javascript %}

    angular.module(radialmenuApp, ['ejangular'])
    .controller('RadialMenuCtrl', function ($scope,$compile) {
    $scope.radius=200;
    });

{% endhighlight %}

The following screenshot illustrates the Radial Menu while clicking on the settings icon.

![](dimension-images\dimension_img1.png)

Selecting text in the page
{:.caption}



The following screenshot illustrates the **Radial Menu** while clicking on the settings icon.

![](dimension-images\dimension_img2.png)

## Position 

To display the **Radial Menu** in the web page in a specific area, we can use the **e-position** property. By default, the Radial Menu position is set as null.

Refer to the following code example.

In the HTML page set the **e-position** value to the RadialMenu component.

{% highlight html %}

    <ej-radialmenu id="defaultradialmenu" e-targetelementid="radialtarget1" e-radius="radius" e-position="position">
        <e-items>
            <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/copy.png" e-text="Copy"></e-item>
            <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/paste.png" e-text="Paste"></e-item>
            <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/redo.png" e-text="Redo"></e-item>
            <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/undo.png" e-text="Undo"></e-item>
        </e-items>
    </ej-radialmenu>

{% endhighlight %}

Define **e-position** value in angular module in script section.
    
{% highlight javascript %}

    angular.module(radialmenuApp, ['ejangular'])
             .controller('RadialMenuCtrl', function ($scope,$compile) {
          $scope.radius=200;
          $scope.position={x:10,y:10};
    });

{% endhighlight %}

The following screenshot illustrates the output while selecting the text in the page.

![](dimension-images\dimension_img4.png)






