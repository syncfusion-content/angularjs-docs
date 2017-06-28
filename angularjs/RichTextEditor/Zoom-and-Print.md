---
layout: post
title: Zoom and Print support in RichTextEditor widget
description: Zoom and Print support for RichTextEditor widget
platform: Angular-1
control: RichTextEditor
documentation: ug
keywords: RichTextEditor, Zoom, Print
---
# Zoom

The editor provides zoom tools which enlarges the view of an editor's object enabling you to see more detail. You can continuous zoomIn and zoomOut either using zoom tools or keyboard.

You can assign Increases and decreases of zooming range using [zoomStep](http://help.syncfusion.com/api/js/ejrte#members:zoomStep) property

{% highlight html %}

<textarea id="texteditor" ej-rte e-value="val" e-toolslist="toolsList" e-tools="tools" e-zoomstep="zoomStep"></textarea>

<script type="text/javascript">

angular.module('rteApp', ['ejangular'])
.controller('RTECtrl', function ($scope) {
$scope.val= "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
$scope.toolsList= ["view"];
$scope.tools={ view:["zoomIn","zoomOut"]};
$scope.zoomStep= 0.1;
});

</script>

{% endhighlight %}

![](ZoomandPrint_images/zoom.png)

# Print

The editor provides print tools which use to print the contents of the editor.

{% highlight html %}

    <textarea id="texteditor" ej-rte e-value="val" e-toolslist="toolsList" e-tools="tools"></textarea>

    <script type="text/javascript">

        angular.module('rteApp', ['ejangular'])
        .controller('RTECtrl', function ($scope) {
            $scope.val= "The RichTextEditor (RTE) control enables you to edit the contents with insert table and images," + " it also provides a toolbar that helps to apply rich text formats to the content entered in the TextArea.";
            $scope.toolsList= ["print"];
            $scope.tools = { print: ["print"] };
        });

    </script>
{% endhighlight %}

![](ZoomandPrint_images/print.png)

