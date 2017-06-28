---
layout: post
title: Drill-Operation
description: drill operation
platform: AngularJS
control: pivotchart
documentation: ug
keywords: ejpivotchart, pivotchart, pivotchart widget, js pivotchart 
---

# Drill Operation

This is a basic feature of PivotChart through which the amount of information can be limited, for a better view. It allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the Context Menu present in the PivotChart.
 
Drill up, also called roll up, navigates from more detailed data to less detailed data, by climbing up a concept hierarchy for a dimension.
 
Drill down, also called roll down, is the reverse of drill up. It navigates from less detailed data to more detailed data, by climbing down a concept hierarchy for a dimension.

![](Drill-Operation_images/Drill_img1.png)

![](Drill-Operation_images/Drill_img2.png)

DrillSuccess event is triggered when you right-click on the PivotChart and select any option available from the Context Menu to perform drill up or drill down operation.

{% highlight html %}

<body>
    <div ng-controller="PivotChartCtrl">
        <div id="PivotChart1" ej-pivotchart e-drillSuccess="drillSuccess"/>
    </div>
    <script>
        angular.module('PivotChartApp', ['ejangular']).controller('PivotChartCtrl', function ($scope) {
            ///..
            $scope.drillSuccess = function(args){
                alert("Drill Success");
            };
        });
    </script>
</body>

$(function()
{
    $("#PivotChart1").ejPivotChart(
    {
        ....
        drillSuccess: "drillSuccess"
    });
});

function drillSuccess(args)
{
    alert("Drill Success");
}

{% endhighlight %}



