---
layout: post
title: Add gridlines behind nodes and connectors to ease alignments
description: How to add gridlines behind nodes and connectors?
platform: Angular-1
control: Diagram
documentation: ug
---

# Gridlines

**Gridlines** are the pattern of lines drawn behind the Diagram elements. It provides a visual guidance while dragging or arranging the objects on the Diagram surface.

## Customize the gridlines visibility

The `snapSettings.snapConstraints` enables you to show/hide the gridlines. The following code example illustrates how to show or hide gridlines.

{% highlight html %}

<div ng-controller="diagramCtrl">
    <ej-diagram id="diagramCore" e-height="500px" e-width="700px" e-snapsettings="snapSettings">
    </ej-diagram>
</div>

 {% endhighlight %}

{% highlight javascript %}
 
//Shows both horizontal and vertical gridlines
var snapSettings = {
    snapConstraints: ej.datavisualization.Diagram.SnapConstraints.ShowLines
};

syncApp.controller('diagramCtrl', function($scope) {
    $scope.snapSettings = snapSettings
});

{% endhighlight %}

![](/angular-1/Diagram/Gridlines_images/Gridlines_img1.png)

To show only horizontal/vertical gridlines or to hide gridlines, refer to [Constraints](/angular-1/Diagram/Constraints#snapconstraints "Constraints")

## Appearance

You can customize the appearance of the gridlines by using a set of predefined properties. To explore those properties, refer to [Gridlines](/api/js/ejDiagram#snapsettings:horizontalgridlines "Gridlines")
The `horizontalGridLines` and `verticalGridLines` properties allow to customize the appearance of the gridlines. The following code example illustrates how to customize the appearance of gridlines.

{% highlight html %}

<div ng-controller="diagramCtrl">
    <ej-diagram id="diagramCore" e-height="500px" e-width="700px" e-snapsettings-horizontalGridLines="snapSettings.horizontalGridLines" 
	e-snapsettings-verticalGridLines="snapSettings.verticalGridLines" e-snapsettings-snapConstraints="snapSettings.snapConstraints">
    </ej-diagram>
</div>
 
 {% endhighlight %}

 {% highlight javascript %}

var snapSettings = {
    snapConstraints: ej.datavisualization.Diagram.SnapConstraints.ShowLines,
    // Customizes the line color and line style to the gridlines.
    horizontalGridLines: {
        lineColor: "blue",
        lineDashArray: "2 2"
    },
    verticalGridLines: {
        lineColor: "blue",
        lineDashArray: "2 2"
    }
};

syncApp.controller('diagramCtrl', function($scope) {
    $scope.snapSettings = snapSettings
});

{% endhighlight %}

![](/angular-1/Diagram/Gridlines_images/Gridlines_img4.png)

### Line Intervals

Thickness and the space between gridlines can be customized by using `linesInterval` property. In the linesInterval collections, values at the odd places are referred as the thickness of lines and the values at the even places are referred as the space between gridlines.

The following code example illustrates how to customize the thickness of lines and the line intervals.

{% highlight javascript %}

var snapSettings = {
    snapConstraints: ej.datavisualization.Diagram.SnapConstraints.ShowLines,
    horizontalGridLines: {
        // Defines the thickness and intervals for a pattern of lines
        linesInterval: [1.25, 14, 0.25, 15, 0.25, 15, 0.25, 15, 0.25, 15],
        lineColor: "blue",
        lineDashArray: "2 2"
    },
    verticalGridLines: {
        linesInterval: [1.25, 14, 0.25, 15, 0.25, 15, 0.25, 15, 0.25, 15],
        lineColor: "blue",
        lineDashArray: "2 2"
    }
};

syncApp.controller('diagramCtrl', function($scope) {
    $scope.snapSettings = snapSettings
});

{% endhighlight %}

![](/angular-1/Diagram/Gridlines_images/Gridlines_img2.png)

# Snapping

## Snap To Lines

This feature allows the Diagram objects to snap to the nearest intersection of gridlines while being dragged or resized. This feature enables easier alignment during layout or design.

Snapping to gridlines can be enabled/disabled with the `snapSettings.snapConstraints`. The following code example illustrates how to enable/disable the snapping to gridlines.

{% highlight javascript %}

//Enables snapping to both the horizontal and vertical lines.
snapSettings = {
    snapConstraints: ej.datavisualization.Diagram.SnapConstraints.SnapToLines
};

syncApp.controller('diagramCtrl', function($scope) {
    $scope.snapSettings = snapSettings
});

{% endhighlight %}

To enable/disable snapping to horizontal/vertical lines, refer to [Constraints] (/angular-1/Diagram/Constraints#SnapConstraints "Constraints")

## Customization of Snap Intervals

By default, the objects are snapped towards the nearest gridline. The gridline or position towards where the diagram object snaps can be customized with the property, `snapInterval`. The following code example illustrates how to customize the snap intervals.

{% highlight html %}

<div ng-controller="diagramCtrl">
    <ej-diagram id="diagramCore" e-height="500px" e-width="700px" e-snapsettings-horizontalGridLines="snapSettings.horizontalGridLines"
	 e-snapsettings-verticalGridLines="snapSettings.verticalGridLines" e-snapsettings-snapConstraints="snapSettings.snapConstraints">
    </ej-diagram>
</div>
{% endhighlight %}

 {% highlight javascript %}

       syncApp.controller('diagramCtrl', function($scope) {
        $scope.snapSettings = {
            horizontalGridLines: {
                //Defines a set of intervals where the object is snapped.
                //In this example, the object is snapped to every 10px.
                snapInterval: [10]
            },
            verticalGridLines: {
                //The object is snapped to every 10px.
                snapInterval: [10]
            },
            snapConstraints: ej.datavisualization.Diagram.SnapConstraints.All
        };
    });

{% endhighlight %}

## Snap To Objects

The snap-to-object provides visual cues to assist with aligning and spacing Diagram elements. A node can be snapped with its neighboring objects based on certain alignments. Such alignments are visually represented as smart guides.

The `enableSnapToObject` property allows you to enable/disable smart guides. The following code example illustrates how to enable/disable the smart guides.

{% highlight html %}

<div ng-controller="diagramCtrl">
    <ej-diagram id="diagramCore" e-height="500px" e-width="700px" e-snapsettings-enableSnapToObject="snapSettings.enableSnapToObject">
    </ej-diagram>
</div>

 {% endhighlight %}

 {% highlight javascript %}
 
    syncApp.controller('diagramCtrl', function($scope) {
     $scope.snapSettings = {
         enableSnapToObject: true,
     };
 });

{% endhighlight %}

![](/angular-1/Diagram/Gridlines_images/Gridlines_img4.png)