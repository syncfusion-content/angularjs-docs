---
layout: post
title: Bullet-Graph-Caption
description: bullet graph caption
platform: angular 1.0
control: BulletGraph	
documentation: ug
---

# Bullet Graph Caption

**Bullet Graph** supports title and **subtitle** to convey what is represented in **Bullet Graph**. They are customized using **captionSettings** property.

## Title

**Title** is set to **Bullet Graph** using **text** property in **captionSettings**. Caption settings also include properties like location, font, and textAngle for customizing the caption of **Bullet Graph**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-quantitativescalesettings-location-x="100" e-quantitativescalesettings-location-y="200" e-quantitativescalesettings-minimum="0" 
                 e-quantitativescalesettings-maximum="5" e-quantitativescalesettings-interval="0.5" e-quantitativescalesettings-featuremeasures="featuremeasure"
                 e-height="700" e-width="600" e-captionsettings-text="Revenue YTD" e-captionsettings-textangle="0" e-captionsettings-location-x="10"
                 e-captionsettings-location-y="220" e-captionsettings-font-fontfamily="segoe ui"e-captionsettings-font-color="gray"
                 e-captionsettings-font-fontstyle="bold" e-captionsettings-font-size="14px" e-captionsettings-font-fontweight="regular"
                 e-captionsettings-font-opacity="1"></ej-bulletgraph>
        </div>
     <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                 $scope.featuremeasure=[{ value: 4, comparativeMeasureValue: 3.5, category: "" }];
                 });
     </script>
     </body>
    </html>


{% endhighlight %}

The following screenshot displays a **Bullet Graph** with customized caption using the above code.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img1.png)

## Subtitle

**Subtitle** is added to **Bullet Graph** using **text** property of **subtitle** in **captionSettings**. **Subtitle** also provides properties like location, textAngle and font to customize subtitle similar to caption.

{% highlight html %}


<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph   e-captionsettings-subtitle-text="Subtitle"
                e-captionsettings-subtitle-location-x="20" e-captionsettings-subtitle-location-y="225" e-captionsettings-subtitle-font-color="black"
                e-captionsettings-subtitle-font-fontfamily="segoe ui" e-captionsettings-subtitle-font-fontstyle="italic"
                e-captionsettings-subtitle-font-size="16px" e-captionsettings-subtitle-font-fontweight="regular"
                e-captionsettings-subtitle-font-opacity="1"></ej-bulletgraph>
        </div>
     <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                       });
     </script>
     </body>
    </html>


{% endhighlight %}



The following screenshot displays **Bullet Graph** with a subtitle

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img2.png)

## Indicator

You can add **Indicator** to bullet graph by enabling **visible** and setting **text** properties of **indicator** in **captionSettings**. Indicator is used to represent whether target is achieved or not with text and symbol by comparing current and target values in bullet graph. 

Indicator displays a symbol along with text which is different from caption and subtitle. Images like logos can be used in indicator instead of symbols. Indicator has properties such as **symbol**, **text**, **textSpacing**, **textAngle**, **location** and **font**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph   e-captionsettings-indicator-visible="true" e-captionsettings-indicator-textangle="0" e-indicator-text="+ $0.5 K"
                 e-captionsettings-indicator-textspacing ="5" e-captionsettings-indicator-location-x="15" e-captionsettings-indicator-location-y="240" e-captionsettings-indicator-font-color="green"
                 e-captionsettings-indicator-symbol-color="green" e-captionsettings-indicator-symbol-shape="triangle" e-captionsettings-indicator-imageUrl="column.png" e-captionsettings-indicator-symbol-size-width="10"
                 e-captionsettings-symbol-size-height="10" e-captionsettings-symbol-border-width="1" e-captionsettings-symbol-border-color="green" 
                e-captionsettings-indicator-font-fontfamily="segoe ui" e-captionsettings-indicator-font-fontstyle="normal"
                e-captionsettings-indicator-font-size="12px" e-captionsettings-indicator-font-fontweight="regular"
                e-captionsettings-indicator-font-opacity="1"></ej-bulletgraph>
        </div>
     <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                       });
     </script>
     </body>
    </html>


{% endhighlight %}



The following screenshot displays a bullet graph with indicator.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img3.png)

## Trim

The title, indicator and indicator text can be overlapped to the scale group. You can avoid the overlapped text by using the enableTrim property of the captionSettings. The default value of the enableTrim is true. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph   e-captionsettings-text="Bullet Graph Title" e-captionsettings-enableTrim="true"></ej-bulletgraph>
        </div>
     <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                       });
     </script>
     </body>
    </html>


{% endhighlight %}



The following screenshot displays the BulletGraph with Trim.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img4.png)

## Text Placement

All the caption group elements (caption, subtitle, and indicator) in the **Bullet Graph** support text positioning by using the property **textPosition** available in all caption group elements. The properties, **textAlignment** and **textAnchor** are used to customize text placement further.

**Text Position**

The property, textPosition, is used to position the text at the top, bottom, left, and right side of the quantitative scale. The default value of this property is float. By default, text can be placed at any desired location by using the location property.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph  e-value="5" e-comparativemeasurevalue="8" e-quantitativescalesettings-location-x="120" e-quantitativescalesettings-location-y="40"
                 e-height="150" e-width="650"   e-captionsettings-text="BulletGraph Title" e-captionsettings-textPosition="top"
                e-captionsettings-font-size="20px" e-captionsettings-font-fontweight="bold"></ej-bulletgraph>
        </div>
     <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                       });
     </script>
     </body>
    </html>

{% endhighlight %}

The following screenshot displays the Bullet Graph with the title positioned above.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img5.png)

### Text Alignment

Alignment of text at different positions with respect to scale can be customized by using the **textAlignment** property. Text can be aligned in the **near**, **center,** and **far** locations of the scale. Text alignment depends upon **textPosition** property and is not applicable when the value of the **textPosition** property is **float**. The default value of the **textAlignment** property is **near**.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph  e-value="5" e-comparativemeasurevalue="8" e-quantitativescalesettings-location-x="120" e-quantitativescalesettings-location-y="40"
                 e-height="150" e-width="650"   e-captionsettings-text="Revenue" e-captionsettings-textPosition="left" e-captionsettings-textAnchor="middle"
                 e-captionsettings-font-size="16px" e-captionsettings-font-fontweight="bold"  e-captionsettings-subtitle-text="$ in thousands" 
                 e-captionsettings-subtitle-textPosition="left" e-captionsettings-subtitle-textAlignment="center"
                 e-captionsettings-subtitle-font-size="12px" e-captionsettings-subtitle-font-fontweight="bold"></ej-bulletgraph>
        </div>
     <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                       });
     </script>
     </body>
    </html>



{% endhighlight %}



The following screenshot displays the Bullet Graph with the title and subtitle at different alignments.

![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img6.png)

### Text Anchor

Text elements aligned at the same position are anchored by using the textAnchor property. These can be anchored at the start, middle, and end. The default value of this property is start and applicable only when two or more text elements are aligned at the same position. 

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph  e-value="5" e-comparativemeasurevalue="8" e-quantitativescalesettings-location-x="120" e-quantitativescalesettings-location-y="40"
                 e-height="150" e-width="650"   e-captionsettings-text="Revenue" e-captionsettings-textPosition="left" e-captionsettings-textAnchor="middle" 
                 e-captionsettings-font-size="16px" e-captionsettings-font-fontweight="bold"  e-captionsettings-subtitle-text="$ in thousands" 
                 e-captionsettings-subtitle-textPosition="left" e-captionsettings-subtitle-textAlignment="center"
                 e-captionsettings-subtitle-font-size="12px" e-captionsettings-subtitle-font-fontweight="bold"></ej-bulletgraph>
        </div>
     <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                       });
     </script>
     </body>
    </html>



{% endhighlight %}



![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img7.png)

### Padding

The space required between text and quantitative scale is customized by using the padding property. The default value of this property is 5 and not applicable when the value of the textPosition property is float.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph  e-value="5" e-comparativemeasurevalue="8" e-quantitativescalesettings-location-x="120" e-quantitativescalesettings-location-y="40"
                 e-height="150" e-width="650"   e-captionsettings-text="Profit in %" e-captionsettings-textPosition="left" e-captionsettings-textAlignment="center" 
                 e-captionsettings-padding="10" e-captionsettings-font-size="16px" e-captionsettings-font-fontweight="bold"  ></ej-bulletgraph>
        </div>
     <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                       });
     </script>
     </body>
    </html>




{% endhighlight %}


![](Bullet-Graph-Caption_images/Bullet-Graph-Caption_img8.png)

