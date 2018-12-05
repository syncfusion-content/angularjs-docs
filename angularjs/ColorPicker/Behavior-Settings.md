---
layout: post
title: Behavior Settings | ColorPicker | AngularJS | Syncfusion
description: behavior settings
platform: AngularJS
control: ColorPicker
documentation: ug
---

# Behavior Settings

## Set value

You can use **e-value** property to set default color for the **ColorPicker**. **ColorPicker** value API is two way binding enabled API that can be accessed using **“e-value attribute”**. This API value could be set either as a color object or a formatted string.

**HTML View Section**

{% highlight html %}

     <input id="colorpicker" ej-colorpicker e-value="value"/>

{% endhighlight %}


**Controller Section**

{% highlight javascript %}

        <script>
            angular.module("ColorPickCtrl", ['ejangular']).controller("ColorPickCtrller", function ($scope) {
                $scope.value = "#278787";
                        });
        </script>

{% endhighlight %}

Run the above code to render the following output.

![Set value](Behavior-Settings_images/Behavior-Settings_images1.png)

## showPreview

The **ColorPicker** control provides live preview support for current cursor selection color and selected color. **e-showPreview** property allows you to preview the selected color in the picker or from the palette.

**HTML View Section**

{% highlight html %}

     <input id="colorpicker" ej-colorpicker e-value="value" e-showPreview="false"/>

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

        <script>
            angular.module("ColorPickCtrl", ['ejangular']).controller("ColorPickCtrller", function ($scope) {
                $scope.value = "#278787";
                  });
        </script>

{% endhighlight %}

Run the above code to render the following output.

![Show Preview](Behavior-Settings_images/Behavior-Settings_images2.png)

## showRecentColors

The **ColorPicker** control allows you to store the color values in custom list by using **e-showRecentColors** property. The **ColorPicker** keeps up to 11 colors in a custom list. By clicking the add button, the selected color from picker or palette gets added in the recent color list.

**HTML View Section**

{% highlight html %}

     <input id="colorpicker" ej-colorpicker e-value="value" e-showRecentColors="true"/>

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

        <script>
            angular.module("ColorPickCtrl", ['ejangular']).controller("ColorPickCtrller", function ($scope) {
               $scope.value = "#278787";
                 });
        </script>

{% endhighlight %}

Run the above code to render the following output.

![Show Recent Colors](Behavior-Settings_images/Behavior-Settings_images3.png)

## enableOpacity

The **ColorPicker** control allows you to enable or disable the opacity slider. You can achieve this by using the **e-enableOpacity** property.

**HTML View Section**

{% highlight html %}

     <input id="colorpicker" ej-colorpicker e-value="value" e-enableOpacity="false"/>

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

        <script>
            angular.module("ColorPickCtrl", ['ejangular']).controller("ColorPickCtrller", function ($scope) {
                $scope.value = "#278787";
                    });
        </script>

{% endhighlight %}

Run the above code to render the following output.

![Enable Opacity](Behavior-Settings_images/Behavior-Settings_images4.png)

## columns

The palette model consists of color values in the rows and columns order. Palette only consists of predefined colors and allows you to select anyone color from it. The **e-columns** property allows you to modify the number of columns in palette model.

**HTML View Section**

{% highlight html %}

     <input id="colorpicker" ej-colorpicker e-value="value" e-columns="columns"/>

{% endhighlight %}

**Controller Section**

{% highlight javascript %}

        <script>
          angular.module("ColorPickCtrl", ['ejangular']).controller("ColorPickCtrller", function ($scope) {
            $scope.value = "#278787";
            $scope.columns = 8;
                 });
        </script>

{% endhighlight %}

Run the above code to render the following output.

![Columns](Behavior-Settings_images/Behavior-Settings_images5.png)