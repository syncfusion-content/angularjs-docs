---
layout: post
title: Qualitative-Range
description: qualitative range
platform: AngularJS
control: BulletGraph	
documentation: ug
---

# Qualitative Range

**Qualitative Range** represents the quality of a specific range in quantitative scale like good, bad and satisfactory. Color for each qualitative range is customized using **rangeStroke** property. The **rangeEnd** property specifies the ending point of the qualitative range. Minimum value of quantitative scale is considered as the starting point of first qualitative range and previous end points are considered as starting point for other qualitative ranges.

{% highlight html %}

<html xmlns="http://www.w3.org/1999/xhtml" lang="en" ng-app="BulletGraphApp">
    <head>
        <title>Essential Studio for AngularJS: BulletGraph</title>
        <!--CSS and Script file References -->
    </head>
    <body ng-controller="BulletGraphCtrl">
        <div id="bulletframe">
                 <ej-bulletgraph e-qualitativerangesize="80"  e-height="200" e-quantativescalesettings-location-x="50" 
                 e-quantativescalesettings-location-y="20"  e-quantativescalesettings-minimum="0" 
                 e-quantativescalesettings-maximum="100" e-quantativescalesettings-interval="10"
                 e-quantativescalesettings-featureMeasures="featureMeasures">
                 <e-qualitativeranges>
                 <e-qualitativerange e-rangeend="35" e-rangestroke="darkred" e-rangeopacity="0.5"></e-qualitativerange>
                 <e-qualitativerange e-rangeend="50" e-rangestroke="red" e-rangeopacity="1"></e-qualitativerange>
                 <e-qualitativerange e-rangeend="75" e-rangestroke="blue" e-rangeopacity="0.7"></e-qualitativerange>
                 <e-qualitativerange e-rangeend="90" e-rangestroke="lightblue" e-rangeopacity="1"></e-qualitativerange>
                 <e-qualitativerange e-rangeend="100" e-rangestroke="green" e-rangeopacity="1"></e-qualitativerange>
                 </e-qualitativeranges>
                 </ej-bulletgraph>
        </div>
        <script type="text/javascript">
           angular.module('BulletGraphApp', ['ejangular'])
             .controller('BulletGraphCtrl', function ($scope) {
                 $scope.featureMeasures=[
                            { value: 55, comparativeMeasureValue: 75, category: "Year 1" },
                            { value: 65, comparativeMeasureValue: 70, category: "Year 2" },
                            { value: 80, comparativeMeasureValue: 65, category: "Year 3" }
                        ];
                 });
     </script>
    </body>
</html>



{% endhighlight %}



The following screenshot displays **Bullet Graph** with different qualitative ranges in different colors. In this image, range 0 to 35 represents bad performance, 35 to 50 represents average performance, 50 to 75 represents that the performance is above average, 75 to 90 represents good performance and above 90 represents excellent performance.

![](Qualitative-Range_images/Qualitative-Range_img1.png) 

