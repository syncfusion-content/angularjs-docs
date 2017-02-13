---
layout: post
title: Image and File browser in RichTextEditor widget
description: Configuring and working with Image and File browser in RichTextEditor  
platform: Angular-1
control: RichTextEditor
documentation: ug
keywords: RichTextEditor, File browser, Image, Image Browser

---

# Image and File browser

The editor allows you to manage the images and files using **FileExplorer**. The FileExplorer enables you to insert images from online source as well as local computer where you want to insert the image in your content. The Image and file browser is the ability to upload pictures and link file to the editor. 

## Insert a Image from Online Source

If you want to insert an image from online source like Google, Ping, etc., you need to enable images tool on the editor’s toolbar. By default, the images tool is open a simple dialog which allows you to inserting an image from online source.

{% highlight html %}

<textarea id="texteditor" ej-rte e-toolslist="toolslist" e-tools="tools"></textarea>

<script type="text/javascript">

var fileService = "http://mvc.syncfusion.com/OdataServices/fileExplorer/fileoperation/doJSONAction";

angular.module('rteApp', ['ejangular'])
.controller('RTECtrl', function ($scope) {
$scope.toolslist = ["images"];
$scope.tools = {
    images: ["image"]
}         
});

</script>

{% endhighlight %}

![](ImageandFilebrowser_images/ImageandFilebrowser_img1.png)


## Insert a Image from Your Computer

Configure the imageBrowser and fileBrowser property to insert an image from your computer. You can specify the settings required by the FileExplorer for create, read, upload, and destroy the files and images from the explorer. 

{% highlight html %}

<textarea id="texteditor" ej-rte e-width="100%" e-minwidth="150px" e-height="250px" e-toolslist="toolList" e-tools="tools" e-imagebrowser="imageBrowser" e-filebrowser="fileBrowser"></textarea>

<script type="text/javascript">

var fileService = "http://js.syncfusion.com/demos/ejServices/api/FileExplorer/FileOperations";
angular.module('rteApp', ['ejangular'])
.controller('RTECtrl', function ($scope) {
    $scope.toolList = ["images"];
    $scope.tools = { images: ["image"] };
    $scope.imageBrowser = { filePath: "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/", ajaxAction: fileService, extensionAllow: "*.png, *.gif, *.jpg, *.jpeg, *.docx" };
    $scope.fileBrowser = { filePath: "http://js.syncfusion.com/demos/ejServices/Content/FileBrowser/", ajaxAction: fileService, extensionAllow: "*.txt, *.png, *.pdf,*.jpeg"};
});

</script>

{% endhighlight %}

![](ImageandFilebrowser_images/ImageandFilebrowser_img2.png)


N> FileExplorer component has been implemented and integrated with the editor in Volume 1, 2015 release. For more information about FileExplorer component, see [here](http://helpjs.syncfusion.com/js/fileexplorer/overview#).

## Image Properties

You can set or modify properties of an image using the image dialog. It allows you to add links to images, apply border and additional styles. The editor provides option to specify the alternate text for an image, if the image cannot be displayed.

![](ImageandFilebrowser_images/ImageandFilebrowser_img3.png)


## Resize an Image

You can able to resize an image either manually or set the width and height in the image dialog. 

### Resize Manually

You can resize an image by manually select an image, and drag a handle until the image is the desired size. 

![](ImageandFilebrowser_images/ImageandFilebrowser_img4.png)

N> Set the default height and width of the Images which was inserted into the RTE text area in “change” event of RTE - {{'[Link](http://jsplayground.syncfusion.com/Sync_rghpsadi)'| markdownify }}

### Set Width and Height

The editor provides you to set the width and height properties to change the size of an image (rather than forcing you to set in style attributes) using [showDimensions](http://help.syncfusion.com/api/js/ejrte#members:showdimensions) property. By default, the Constrain Proportion checkbox is selected to resize an image to an exact proportion. To apply the exact width and height that you specify into the Height and Width textboxes, uncheck the Constrain Proportions checkbox.

{% highlight html %}

<textarea id="texteditor" ej-rte e-toolslist="toolslist" e-tools="tools" e-showdimensions="true"></textarea>

<script type="text/javascript">

angular.module('rteApp', ['ejangular'])
.controller('RTECtrl', function ($scope) {
    $scope.toolslist = ["images"];
    $scope.tools = {
        images: ["image"]
    }
});

</script>
{% endhighlight %}

![](ImageandFilebrowser_images/ImageandFilebrowser_img5.png)

## Suppression of the Image Browser

The General and Advanced tabs in the RTE Image browser can be removed by setting its corresponding display CSS property to none.

{% highlight CSS %}

    <style type="text/css" class="cssStyles">
        div.e-rte-imageTab.e-tab.e-js.e-widget {
            display: none;
        }
    </style>
    
 {% endhighlight %}
 
 Can remove the Add `NewFolder` button by using [removeToolbarItem](https://help.syncfusion.com/api/js/ejrte#methods:removetoolbaritem) property of Image Browser in the RTE create event. 

{% highlight html %}

    <textarea id="texteditor" ej-rte e-toolslist="toolslist" e-tools="tools" e-imagebrowser="imageBrowser" e-filebrowser="fileBrowser" e-create="create"></textarea>

    <script>

        var fileService = "http://mvc.syncfusion.com/OdataServices/fileExplorer/fileoperation/doJSONAction";
        angular.module('rteApp', ['ejangular'])
        .controller('RTECtrl', function ($scope) {
            $scope.toolslist = ["images"];
            $scope.tools = {
                images: ["image"]
            };
            $scope.imageBrowser = { filePath: "http://mvc.syncfusion.com/OdataServices/FileBrowser/", ajaxAction: fileService, extensionAllow: "*.png, *.gif, *.jpg, *.jpeg, *.docx" };
            $scope.fileBrowser = { filePath: "http://mvc.syncfusion.com/OdataServices/FileBrowser/", ajaxAction: fileService, extensionAllow: "*.txt, *.png, *.pdf,*.jpeg" };
            $scope.create=function (args) {
                this._explorerObj.removeToolbarItem("NewFolder");
            }
        });

    </script>
    
 {% endhighlight %}
 
In RTE control, there is no direct support for the autoUpload option. But this can be achieved by enabling the autoUpload at create event of RTE.

{% highlight html %}

    <textarea id="texteditor" ej-rte e-toolslist="toolslist" e-tools="tools" e-imagebrowser="imageBrowser" e-filebrowser="fileBrowser" e-create="create"></textarea>

    <script>

        var fileService = "http://mvc.syncfusion.com/OdataServices/fileExplorer/fileoperation/doJSONAction";

        angular.module('rteApp', ['ejangular'])
        .controller('RTECtrl', function ($scope) {
            $scope.toolslist = ["images"];
            $scope.tools = {
                images: ["image"]
            };
            $scope.imageBrowser = { filePath: "http://mvc.syncfusion.com/OdataServices/FileBrowser/", ajaxAction: fileService, extensionAllow: "*.png, *.gif, *.jpg, *.jpeg, *.docx" };
            $scope.fileBrowser = { filePath: "http://mvc.syncfusion.com/OdataServices/FileBrowser/", ajaxAction: fileService, extensionAllow: "*.txt, *.png, *.pdf,*.jpeg" };
            $scope.create=function (args) {
                this._explorerObj._uploadtag.data("ejUploadbox").option("autoUpload", true);
            }            
        });

    </script>
    
 {% endhighlight %}