---
layout: post
title: Duration-units
description: duration units
platform: AngularJS
control: Gantt
documentation: ug
---

# Duration Units

In Gantt, the tasks’ duration value can be measured by the following duration units, 

* Day
* Hour
* Minute

Each task in the project can be defined with different duration units and the duration unit of a task can be defined by the following ways,

1. Using **e-durationunitmapping** property, to map the duration unit data source field.
2. Defining the duration unit value along with the duration field in the data source.

## Mapping the Duration Unit field


The below code snippet explains the mapping of duration unit data source field to the Gantt control using the **e-durationunitmapping** property.

{% highlight javascript %}

<script>
var data = [
//...
Duration: 5,
DurationUnit: ej.Gantt.DurationUnit.Day,
}];
</script>

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
   //...
    e-durationmapping= "Duration"
    e-durationunitmapping= "DurationUnit">
   </div>
</body>

{% endhighlight %}

N> 1. The default value of the **e-durationunit** property is “day”.

## Defining duration unit along with duration field

Duration units for the tasks can also be defined along with the duration values, the below code snippet explains the duration unit for a task along with duration value,

{% highlight javascript %}

<script>
var data = [
//...
Duration: "5days"
}];
</script>

<body ng-controller="GanttCtrl">
   <!--Add  Gantt control here-->    
   <div id="GanttContainer" ej-gantt
   //...
    e-durationmapping= "Duration"
    >
   </div>
</body>

{% endhighlight %}

The below sample explains the tasks’ duration unit in Gantt.

[Duration Unit](http://js.syncfusion.com/demos/web/#!/bootstrap/gantt/schedulingconcepts/durationunits)

The below screen shot shows different duration unit support in Gantt control.

![](Duration-units_images/Duration-units_img1.png)

N> 1. The edit type of the duration column in Gantt is string, to support editing the duration field along with duration units.

## Localizing the duration unit

We can localize the duration unit texts like below,

{% highlight javascript %}

<script>
ej.Gantt.Locale["en-US"] = {
    //...
    durationUnitTexts: {
        days: "days",
        hours: "hours",
        minutes: "minutes",
        day: "day",
        hour: "hour",
        minute: "minute"
    },
    durationUnitEditText: {
        minute: ["m", "min", "minute", "minutes"],
        hour: ["h", "hr", "hour", "hours"],
        day: ["d", "dy", "day", "days"]
    }
};
</script>

{% endhighlight %}

N> **durationUnitTexts** property is used to display the unit of duration in columns and taskbar tooltips.
N> **durationUnitEditText** property is used to save the edited duration unit value on editing action.
