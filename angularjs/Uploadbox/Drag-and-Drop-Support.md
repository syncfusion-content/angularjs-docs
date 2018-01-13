---
layout: post
title: Drag-and-Drop-Support
description: drag and drop support
platform: AngularJS
control: Uploadbox
documentation: ug
---

# Drag and Drop Support

The **Uploadbox** control provides the drag and drop support. You can simply drag-and-drop files, directly from the computer and can be dropped into the droppable area. A list of files can be dragged and dropped when you enable the [multipleFilesSelection](https://help.syncfusion.com/api/js/ejuploadbox#members:multiplefilesselection).

The following screenshot displays the drag and drop support.

![](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img1.png) 

## Enable drag and drop 

You can enable or disable drag and drop by using the [allowDragAndDrop](https://help.syncfusion.com/api/js/ejuploadbox#members:allowdraganddrop) property. By default, the **allowDragAndDrop** property is set as **false** in the **Uploadbox** control. You can enable drag and drop by setting the [allowDragAndDrop](https://help.syncfusion.com/api/js/ejuploadbox#members:allowdraganddrop) property as **true**. When you want to drag and drop multiple files, you can enable multiple file selection by setting **multipleFilesSelection** as **true** in the **Uploadbox** control.

The following steps explain how to enable the drag and drop in the **Uploadbox** control.

In the HTML page, add a **&lt;div&gt;** element to enable the drag and drop in Uploadbox control.

{% highlight html %}

<div class="frame">
    <div class="control">
        <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-multiplefilesselection="true" e-allowdraganddrop="true"></div>
    </div>
</div>

{% endhighlight %}


{% highlight js %}

    angular.module('UploadboxApp', ['ejangular'])
    .controller('UploadboxCtrl', function ($scope) {
        $scope.save = "saveFiles.ashx";
        $scope.remove= "removeFiles.ashx";
    });

{% endhighlight %}

In CSS, configure the custom styles for drag and drop.

{% highlight css %}

<style>
    .frame {
        width: 500px;
        height: 100px;
        margin-top: 10%;
    }

    .control {
        width: 100%;
        height: 100%;
    }
</style>


{% endhighlight %}

The following screenshot displays the output for the above code.

![](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img2.png) 

## Drag Area text

You can change the drag area text by using the **dragAreaText** property.  By default, the **dragAreaText** (string) property is **Drop files or click to upload** in the Uploadbox control.

In the **HTML** page, add a **&lt;div&gt;** element to enable the drag and drop in the **Uploadbox** control.

{% highlight html %}


<div class="frame">
    <div class="control">
        <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-multiplefilesselection="true" e-allowdraganddrop="true" e-dropareatext="drop files here"></div>
    </div>
</div>


{% endhighlight %}

{% highlight js %}

    angular.module('UploadboxApp', ['ejangular'])
        .controller('UploadboxCtrl', function ($scope) {
            $scope.save = "saveFiles.ashx";
            $scope.remove= "removeFiles.ashx";
    });

{% endhighlight %}

In CSS, configure the custom styles for drag and drop.

{% highlight css %}


<style>
    .frame {
        width: 500px;
        height: 100px;
        margin-top: 10%;
    }

    .control {
        width: 100%;
        height: 100%;
    }
</style>


{% endhighlight %}

 The following screenshot displays the output for the above code.

![](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img3.png) 

## Adjust Drop area size

The **Uploadbox** control provides the ability to change or adjust the drop area size. The [dropAreaHeight](https://help.syncfusion.com/api/js/ejuploadbox#members:dropareaheight) and [dropAreaWidth](https://help.syncfusion.com/api/js/ejuploadbox#members:dropareawidth) properties in the **Uploadbox** control allows you to set the maximum height and maximum width for the drop area. The value set to this property is **string** or **number** type.

The following steps explain you on how to adjust the Drop Area Size.

In the **HTML** page, add a **&lt;div&gt;** element to enable the drag and drop in **Uploadbox** control.

{% highlight html %}

<div class="control">
    <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-multiplefilesselection="true" e-allowdraganddrop="true" e-dropareaheight="300px" e-dropareawidth="600px"></div>
</div>

{% endhighlight %}

{% highlight js %}

  angular.module('UploadboxApp', ['ejangular'])
        .controller('UploadboxCtrl', function ($scope) {
            $scope.save = "saveFiles.ashx";
            $scope.remove= "removeFiles.ashx";
   });

{% endhighlight %}

The following screenshot displays the output for the above code.

![](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img4.png) 

## Drop area with Browse button behavior

You can click anywhere in the droppable area to browse and upload the files. The droppable area behaves like a browse button.

### Droppable area behavior

Enable the **allowDragAndDrop** property to achieve this feature. Next, set the [showBrowseButton](https://help.syncfusion.com/api/js/ejuploadbox#members:showbrowsebutton) as **false** in Uploadbox Control.

The following steps explain the droppable area containing the browse button behavior.

In the **HTML** page, add a **&lt;div&gt;** element to enable drag and drop in the **Uploadbox** control.

{% highlight html %}

<div class="frame">
    <div class="control">
        <div id="Uploadbox" ej-uploadbox e-saveurl="save" e-removeurl="remove" e-multiplefilesselection="true" e-allowdraganddrop="true" e-showbrowsebutton="false"></div>
    </div>
</div>


{% endhighlight %}

{% highlight js %}

    angular.module('UploadboxApp', ['ejangular'])
        .controller('UploadboxCtrl', function ($scope) {
            $scope.save = "saveFiles.ashx";
            $scope.remove= "removeFiles.ashx";
    });

{% endhighlight %}

In CSS, configure the custom styles for drag and drop.

{% highlight css %}

<style>
    .frame {
        width: 500px;
        height: 100px;
        margin-top: 10%;
    }

    .control {
        width: 100%;
        height: 100%;
    }
</style>

{% endhighlight %}

The following screenshot displays the output for the above code.

![](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img5.png)