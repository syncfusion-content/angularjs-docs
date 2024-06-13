---
layout: post
title: How To Section in AngularJS Signature | Syncfusion
description: Learn here all about how to section Syncfusion AngularJS Signature component, its elements and more.
platform: angularjs
control: Signature
documentation: ug
---

# How To Section in AngularJS Signature

## Save signature image with user defined format

By default, the downloaded image from the signature canvas will be in **png** format. We can define our own format to download the image with [`e-saveimageformat`] property. And we can also save the image along with the background by using the **e-savewithbackground** property.

The following code example is used to download drawn image on the Signature control.

{% highlight html %}

    <div ng-controller="signatureCtrl">

<div id="apiSignature" ej-signature e-height="400px" e-isresponsive="true" e-backgroundimage="http://js.syncfusion.com/demos/web/content/images/signature/water.png" e-savewithbackground="true"></div>

    </div>

<input id="signsave" class="e-btn" type="button" value="Save" ej-button e-width="50px" e-size="normal" e-showroundedcorner="true" e-click="onSave" />

{% endhighlight %}



Add the following script to define the download format for the canvas.

{% highlight js %}

syncApp.controller('signatureCtrl', function ($scope) {
            $scope.onSave = function (args) {
                 var signature = $("#apiSignature").ejSignature("instance");
                 signature.save("MySignature");
            }
        });
{% endhighlight %}


The following screenshot illustrates the Signature with saving (downloading) the drawn image.

![Save signature image with user defined format](How_To_images\savesignatureimagewithuserdefinedformat_img1.png)

### To clear the Signature

To clear the signature, you can simply use the **clear()** method. This method will clear all the drawn strokes in the signature canvas and leaves it empty.

{% highlight html %}

    <div ng-controller="signatureCtrl">

<div id="apiSignature" ej-signature e-height="400px" e-isresponsive="true"></div>

    </div>

<input id="signclear" class="e-btn" type="button" value="Clear" ej-button e-width="50px" e-size="normal" e-showroundedcorner="true" e-click="onClear" />

{% endhighlight %}

Add the following script to clear the Signature.

{% highlight js %}

syncApp.controller('signatureCtrl', function ($scope) {
            $scope.onClear = function (args) {
                 var signature = $("#apiSignature").ejSignature("instance");
                 signature.clear();
            }
        });
{% endhighlight %}



## Make signature as responsive

When the signature component is resized or even the window is resized the strokes drawn in the signature will be disappeared. To make the strokes visible even after resizing the window, we must set the **e-isresponsive** property as true.

The following code example is used to render the Signature component with responsive support.

{% highlight html %}


<div ng-controller="signatureCtrl">
        <div id="signature" ej-signature e-height="height" e-width="width" e-isresponsive="true" ></div>     
    </div>


{% endhighlight %}


The following screenshot illustrates the Signature with responsiveness.

Before Responsiveness:

![Before signature as responsive](How_To_images\makesignatureasresponsive_img1.png)

After giving the Responsiveness:

![After signature as responsive](How_To_images\makesignatureasresponsive_img2.png)



## To check whether any input to the signature control since render

We can detect whether not there has been any input to the signature control since render. To detect we can use the storeSnap public variable, which is an array that stores all the canvas inputs. At initial rendering this array is empty and we can use this variable to check for the drawn strokes.


{% highlight js %}

   <script type="text/javascript">
      var sign = $("#signature").ejSignature("instance");

            if (ej.isNullOrUndefined(sign.storeSnap)) {
               
                //Something

            }
    </script>   

{% endhighlight %}