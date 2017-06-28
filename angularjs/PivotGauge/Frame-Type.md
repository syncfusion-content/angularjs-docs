---
layout: post
title: Frame-Type
description: frame type 
platform: Angular-1
control: PivotGauge
documentation: ug
keywords: ejPivotGauge, PivotGauge, PivotGauge widget, js PivotGauge 
---

# Frame Type

## Full Circle

Full Circle frame lets the PivotGauge display in circular shape. Frame type can be set using the [`frameType`](/api/js/ejcirculargauge#members:frame) property.  By default, the frame type is "fullCircle".

{% highlight javascript %}

<div ng-controller="PivotGaugeCtrl">
    <div id="PivotGauge1" ej-pivotgauge e-frame="frame" />
</div>
<script>
    angular.module('PivotGaugeApp', ['ejangular']).controller('PivotGaugeCtrl', function ($scope) {
        //..
        $scope.frame = {
            frame: { frameType: "fullCircle" }
        };
    });
</script>

{% endhighlight %}

![](Frame-Type_images/FullCircle.png) 

## Half Circle

Half Circle frame lets the PivotGauge to display in semi-circular shape. For this, frame type needs to be set as "halfCircle" within the [`frameType`](/api/js/ejcirculargauge#members:frame) property and need to set `startAngle` and `sweepAngle` for the PivotGauge in the  [`scales`](/api/js/ejcirculargauge#members:scales) property.

{% highlight javascript %}

<div ng-controller="PivotGaugeCtrl">
    <div id="PivotGauge1" ej-pivotgauge e-scales="scales" e-frame="frame" />
</div>
<script>
    var scale= [{
        //..
        startAngle: 180, sweepAngle: 180
        //..
    }];
    angular.module('PivotGaugeApp', ['ejangular']).controller('PivotGaugeCtrl', function ($scope) {
        //..
        $scope.frame = {
               frameType: 'halfcircle',
               halfCircleFrameStartAngle: 180, halfCircleFrameEndAngle: 360
        };
        $scope.scales = scale;
    });
</script>

{% endhighlight %}

![](Frame-Type_images/HalfCircle.png) 

