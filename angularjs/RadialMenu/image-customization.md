---
layout: post
title: image-customization
description: image customization
platform: js
control: Radial Menu
documentation: ug
---

# Image Customization

You can customize the Radial Menu’s Center and Back images by using the **e-imageClass** and **e-backImageClass** properties. Every menu item can be added with image using **e-imageurl** property. By using this e-imageClass attribute, you can customize the Radial Menu center image.

Sub-Items are also supported in the Radial Menu. To navigate Sub-Items, click the arrows in the outer ring and it displays the corresponding sub-items group. Clicking the center button when a sub-items group is shown, displays the items on the previous level. Nested Radial Menu has the second level back button. In this case, you can use the **e-backImageClass** attribute to change your second level back button. BackImageClass is used to customize the nestedRadialmenu back image. 

Refer to the following code example.

You can add the page content with text-area by referring to this section.


{% highlight html %}

    <ej-radialmenu id="defaultradialmenu" e-targetelementid="radialtarget1" e-imageclass "imageclass" e-backimageclass "backimageclass">
    <e-items>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/copy.png" e-text="Copy"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/font.png" e-text="Bold">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/f1.png" e-text="Italic"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/f2.png" e-text="Bold"></e-item>
            </e-items>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/table.png" e-text="Table"></e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/list.png" e-text="List">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/l1.png" e-text="List"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/l2.png" e-text="List"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/l3.png" e-text="List"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/l4.png" e-text="List"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/l5.png" e-text="List"></e-item>
            </e-items>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/paste.png" e-text="Paste">
            <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/c1.png" e-text="Paste"></e-item>
            <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/c2.png" e-text="Paste"></e-item>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/sort.png" e-text="Sort">
            <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/s1.png" e-text="Sort"></e-item>
            <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/s2.png" e-text="Sort"></e-item>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/align.png" e-text="Alignment">
            <e-items>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/a1.png" e-text="Left"></e-item>
                <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/a2.png" e-text="Right"></e-item>
            </e-items>
        </e-item>
        <e-item e-imageurl="http://js.syncfusion.com/UG/web/Content/radial/draw.png" e-text="Draw"></e-item>
    </e-items>
    </ej-radialmenu>

    
{% endhighlight %}

Add the following styles in your code.
    
{% highlight css %}

    <style type="text/css" class="cssStyles">
    .e-radialmenu .imageclass {
        background-image: url(http://js.syncfusion.com/UG/web/Content/radial/main.png);
    }

    .e-radialmenu .backimageclass {
        background-image: url(http://js.syncfusion.com/UG/web/Content/radial/Back_button.png);
    }
    </style>

{% endhighlight %}


The following screenshot illustrates the output.

![](image-customization_images\image-customization_img1.png)

Radial Menu - Image Customization – Main menu
{:.caption}

When you click the arrow, it navigates to the child item as illustrated in the following screenshot.

![](image-customization_images\image-customization_img2.png)

Radial Menu- Image Customization – Child menu 
{:.caption}



