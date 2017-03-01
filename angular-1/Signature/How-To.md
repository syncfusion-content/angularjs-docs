---
layout: post
title: How To
description: How To
platform: Angular-1
control: Signature
documentation: ug
---

##How To?

### Save signature image with user defined format

By default, the downloaded image form the signature canvas will be in **png** format. We can define our own format to download the image with e-**saveimageformat** property. And we can also save the image along with the background by using the **e-savewithbackground** property.

The following code example is used to download drawn image on the Signature control.

{% highlight html %}

    <div ng-controller="signatureCtrl">

<div id="apisignature" ej-signature e-height="400px" e-isresponsive="true" e-backgroundimage="http://js.syncfusion.com/demos/web/content/images/signature/water.png" e-savewithbackground="true"></div>

    </div>
  <a id="download">
        <input id="signsave" class="e-btn" type="button" value="Save" ej-button e-width="50px" e-size="normal" e-showroundedcorner="true" e-click="onsave" />
    </a>



{% endhighlight %}



Add the following script to define the download format for the canvas.

{% highlight js %}

syncApp.controller('signatureCtrl', function ($scope) {
            $scope.onsave = function (args) {
                var clientPng = document.getElementById('download');
                if (clientPng.addEventListener)
                    clientPng.addEventListener('click', downloadClient, false);
                else
                    clientPng.attachEvent('onclick', downloadClient, false);

                function downloadClient(e) {
                    var sign = $("#apisignature").ejSignature("instance");
                    sign.option("saveImageFormat", "jpg")
                    this.download = "Signature." + sign.model.saveImageFormat + "";
                    var div = $("#apisignature");
                    var canvas = div["children"]()[0];
                    this.href = canvas.toDataURL("image/" + sign.model.saveImageFormat + "");
                }
            }
        });
{% endhighlight %}


The following screenshot illustrates the Signature with saving (downloading) the drawn image.

![https://help.syncfusion.com/js/signature/How_To_images/savesignatureimagewithuserdefinedformat_img1.png](How_To_images\savesignatureimagewithuserdefinedformat_img1.png)

### Make signature as responsive

When the signature component is resized or even the window is resized the strokes drawn in the signature will be disappeared. To make the strokes visible even after resizing the window, we must set the e-**isresponsive** property as true.

The following code example is used to render the Signature component with responsive support.

{% highlight html %}


<div ng-controller="signatureCtrl">
        <div id="signature" ej-signature e-height="height" e-width="width" e-isresponsive="true" ></div>     
    </div>


{% endhighlight %}


The following screenshot illustrates the Signature with responsiveness.

Before Responsiveness:

![https://help.syncfusion.com/js/signature/How_To_images/makesignatureasresponsive_img1.png](How_To_images\makesignatureasresponsive_img1.png)

After giving the Responsiveness:

![https://help.syncfusion.com/js/signature/How_To_images/makesignatureasresponsive_img2.png](How_To_images\makesignatureasresponsive_img2.png)



