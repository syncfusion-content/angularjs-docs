---
layout: post
title: how-to
description: How to
platform: js
control: Angular- Dialog
documentation: ug
---
##How To?

### Create Multiple Dialogs

The Essential Angular Dialog can support multiple Dialog components in the same web page with different contents and different functionalities.

Initialize the Dialog components by adding the script section as below.

{% highlight html %}

<body ng-controller="DialogCtrl">
     <div id="dialog1" ej-dialog title="Dialog" e-position-X="PositonX" e-position-Y="PositonY" e-width="250">
        <p>
            This is a simple dialog
        </p>
    </div>
    <!--dialog 2-->
    <div id="dialog2" ej-dialog title="Window" e-position-X="PositonX1" e-position-Y="PositonY1" e-width="250">
        <p>
            This is a different dialog
        </p>
    </div>
    <!--dialog 3-->
    <div id="dialog3" ej-dialog title="PopUp" e-position-X="PositonX2" e-position-Y="PositonY2" e-width="250">
        <p>
            This is an another dialog
        </p>
    </div>
    <script>
        angular.module('dialogApp', ['ejangular'])
         .controller('DialogCtrl', function ($scope) {
             $scope.PositonX=20,
             $scope.PositonY=20,
             $scope.PositonX1=300,
             $scope.PositonY1=20,
             $scope.PositonX2=150,
             $scope.PositonY2=150
         });
    </script>
</body>
{% endhighlight %}



NOTE

If the position of the dialog is not set as above, all the three dialogs will be overlapped with each other.

![Create Multiple Dialogs](how-to_images\create-multiple-dialogs_img1.png)

### Create Nested Dialog

A Dialog component can be nested within another Dialog component.

Create a div element to render the child Dialog component and use it as a content of parent Dialog component.

{% highlight html %}


<body ng-controller="DialogCtrl">
    <button id="button1" ej-button e-click="openDialog">Open Dialog</button>
    <div id="dialog" ej-dialog e-title="Dialog" e-height="400" e-width="500" e-showoninit="false" e-actionbuttons="Icons">
        <!— button to open the nested dialog -->
        <button id="button2" ej-button e-click="openNestedDialog" class="ejButton">Open Nested Dialog</button>
        <!—nested dialog-->
        <div id="nesteddialog" ej-dialog e-height="200" e-width="300" e-title="Nested Dialog" e-showoninit="false" e-actionbuttons="Icons">
            This is a nested Dialog
        </div>
    </div>
     </body>


{% endhighlight %}



Initialize both the Dialog components by adding the script section as below.

{% highlight js %}


<script>
        angular.module('dialogApp', ['ejangular'])
         .controller('DialogCtrl', function ($scope) {
             $scope.openDialog = function (e) {
                 $("#dialog").ejDialog("open");
             }
             $scope.openNestedDialog = function (e) {
                 $("#nesteddialog").ejDialog("open");
             }
             $scope.Icons = ["close", "maximize", "minimize"]
         });
    </script>



{% endhighlight %}



![](how-to_images\create-nested-dialog_img1.png)

### Create Confirmation Dialog with Footer option.

We can use the **e-showfooter** property to render Alert type Dialog box with Footers in Dialog component.

Initialize the Dialog component using the below code.

{% highlight html %}
                <input type="button" id="Getopen" ej-button value="Click to open dialog"  e-click="onOpoen" />
                    <div id="basicDialog" ej-dialog e-title="Confirmation Dialog">Do you really leave the session?  </div>
{% endhighlight %}



Initialize Footer in Dialog components by adding the script section in JsRender as below.

{% highlight html %}


<script id="sample" type="text/x-jsrender">
    <div class="footerspan" style="float:right"> <button id='btn1'>Ok</button> <button id='btn2'>Cancel</button> </div>
    <div class="condition" style="float:left; margin-left:15px"> <input type="check" id="check1"></div>
</script>


{% endhighlight %}



Add the below script to render the Dialog component.

{% highlight js %}
    <script>
        angular.module('dialogApp', ['ejangular'])
             .controller('DialogCtrl', function ($scope) {
                 $scope.onOpoen = function (e) {
                     $("#basicDialog").ejDialog("open");
                 }
             });
    </script>

{% endhighlight %}



![Create Alert Dialog](how-to_images\create-confirmation-dialog-with-footer-option_img1.png)
