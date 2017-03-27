---
layout: post
title: Levels
description: Learn how to customize various levels in SunburstChart
platform: Angular-1
control: SunburstChart
documentation: ug
---

## Levels

Sunburst chart is used to display hierarchical data. You can add more than one hierarchical data by using the `e-levels` property of Sunburst chart. Each level of the hierarchy is represented by circle.
The following code snippet illustrates 

{% highlight js %}
<div id="container" ej-sunburstchart  e-levels= "levels">
</div>
     

{% endhighlight %}

## GroupMemberPath

It is the string property that is used to map the group category value in the dataSource .
You can define the levels as shown in the below code example

{% highlight js %}

 <div id="container" ej-sunburstchart  e-levels= "levels">
 </div>
 <script>
 angular.module('SunburstChartApp', ['ejangular'])
 .controller('SunburstChartCtrl', function ($scope) {
 $scope.levels = [
 { groupMemberPath:"Level1"},
 {groupMemberPath:"Level2"},
 { groupMemberPath:"Level3"},
];
</script>

{% endhighlight %}

The following screenshot illustrates the Sunburst Chart with different levels

![](Levels_images/Levels_img1.png)
