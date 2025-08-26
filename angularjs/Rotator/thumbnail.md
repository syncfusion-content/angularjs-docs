---
layout: post
title: preview thumbnail
description: preview thumbnail
platform: AngularJS
control: rotator
documentation: ug
---

# Thumbnail

This feature implements Thumbnail in Rotator control. You can view or access any of the Rotator items instantly. All the images are given as Thumb Element to use this feature.

The property e-showthumbnail turns on or off thumbnail support in the Rotator control. Thumbnail is used to navigate between slides. Thumbnail supports only single slide transition. You must specify the source for thumbnail elements through the e-thumbnailsourceid property. The default value is ‘false’. The value set to this property is boolean.

The property e-thumbnailsourceid specifies the source for thumbnail elements. The default value is null. The value set to this property is object.

You can refer the following code example of Thumbnail in Rotator.

{% highlight html %}



 <ul id="sliderContent" ej-rotator e-slidewidth="600px" e-slideheight="350px" e-showpager="true" e-showcaption="true" e-showthumbnail="thumbnail" e-thumbnailsourceid="thumbnailId" e-showplaybutton="true" e-isresponsive="true">
<li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/green.jpg" title="green" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snow.jpg" title="snow" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" title="wheat" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" title="tablet" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sea.jpg" title="sea" /></li>					</ul>

<ul id="thumbElement" style="display: none">
<li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/green.jpg" title="green" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/snow.jpg" title="snow" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/wheat.jpg" title="wheat" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/tablet.jpg" title="tablet" /></li>
        <li><img class="image" src="http://js.syncfusion.com/demos/web/content/images/rotator/sea.jpg" title="sea" /></li>					</ul>
</div>



{% endhighlight %}





![thumbnail in Rotator component.](thumbnail_images\previewthumbnail_img1.png)

