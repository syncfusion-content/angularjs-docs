---
layout: post
title: Port in AngularJS Diagram Control | Syncfusion
description: Learn here all about port support in Syncfusion Essential AngularJS Diagram Control, its elements and more.
platform: AngularJS
control: Diagram
documentation: ug
---

# Port in AngularJS Diagram

Essential Diagram for JS provides support to define custom ports for making connections.

![AngularJS Diagram custom ports](Port_images/Port_img3.png)

When a connector is connected between two nodes, its end points are automatically docked to node's nearest boundary as shown in the following image. 

![AngularJS Diagram two nodes](Port_images/Port_img4.png)

Ports act as the connection points of node and allows to create connections with only those specific points as shown in the following image.

![AngularJS Diagram connection points of node](Port_images/Port_img5.png)

## Create Port

### Add ports when initializing nodes

To add a connection port, you need to define the port object and add it to node's `ports` collection. The `offset` property of port accepts an object of fractions and used to determine the position of ports. The following code illustrates how to add ports when initializing the node.

{% highlight html %}

<div ng-controller="diagramCtrl">
    <ej-diagram id="diagramCore" e-height="500px" e-width="700px" e-nodes="nodes">
    </ej-diagram>
</div>

{% endhighlight %} 

{% highlight javascript %}

var nodes = [{
    width: 100,
    height: 100,
    // Defines a collection of ports
    ports: [
        //Defines JSON to create port
        {
            //Sets the port name
            name: "port1",
            // Specifies the port offset – fraction value relative to node bounds
            offset: {
                x: 0,
                y: 0.5
            },
        }
    ]
}];

syncApp.controller('diagramCtrl', function($scope) {
    // Sets the nodes to Diagram model
    $scope.nodes = nodes;
});

{% endhighlight %} 

### Add ports at runtime

You can add ports at runtime by using the client side method `addPorts`. The following code illustrates how to add ports to node at runtime.

{% highlight javascript %}

// Defines a collection of ports that have to be added at runtime
var ports = [{
        name: "port1",
        // Specifies the port offset – fraction value relative
        to node bounds– determines the position of port on node
        offset: {
            x: 0,
            y: 0.5
        }
    },
    {
        name: "port2",
        offset: {
            x: 1,
            y: 0.5
        }
    },
    {
        name: "port3",
        offset: {
            x: 0.5,
            y: 0
        }
    },
    {
        name: "port4",
        offset: {
            x: 0.5,
            y: 1
        }
    }
];

// Gets the instance for the Diagram
var diagram = $("#diagram").ejDiagram("instance");
// Adds the ports to the node of name "node"
diagram.addPorts("node", ports)

{% endhighlight %}

![AngularJS Diagram node](Port_images/Port_img1.png)

To explore the set of properties for defining a port, refer to [Port Properties](/api/js/ejDiagram#members:nodes-ports "Port Properties")

### Update Port at runtime

The client side API `updatePort` is used to update the ports at run time. The following code example illustrates how to change the port properties.

{% highlight javascript %}

var diagram = $("#diagram").ejDiagram("instance");
var selectedObject = diagram.model.selectedItems.children[0];
var visibility = ej.datavisualization.Diagram.PortVisibility.Visible;
diagram.updatePort(selectedObject.name, selectedObject.ports[0], {
    fillColor: "red",
    visibility: visibility
});

{% endhighlight %}

## Connect with ports

Connector’s `sourcePort` and `targetPort` properties allow to create connections between some specific points of source/target nodes. 
For more information about creating connections with port, refer to [Connections with ports](/angularjs/Diagram/Connector#connections-with-ports "Connections with ports")

## Appearance 

You can change the shape of port by using its `shape` property. To explore the different types of port shapes, refer to [Port Shapes](/api/js/global#portshapes "Port Shapes").
The appearance of ports can be customized with a set of style specific properties. 

The following code illustrates how to change the appearance of port.

{% highlight javascript %}

var ports = [{
    // Specifies the port position
    offset: {
        x: 1,
        y: 0.5
    },
    //Defines the shape of port
    shape: ej.datavisualization.Diagram.PortShapes.Circle,
    //Specifies the port visibility
    visibility: true,
    //Customizes the appearance
    fillColor: "yellow",
    size: 12,
    borderColor: "black",
    borderWidth: 2
}];

var nodes = [{
    name: "node",
    width: 100,
    height: 100,
    offsetX: 100,
    offsetY: 100,
    ports: ports
}];
syncApp.controller('diagramCtrl', function($scope) {
    // Sets the nodes to Diagram model
    $scope.nodes = nodes;
});

{% endhighlight %}

![AngularJS Diagram Constraints](Port_images/Port_img2.png)

## Constraints

The `constraints` property allows to enable/disable certain behaviors of ports. For more information about port constraints, refer to [Port Constraints](/angularjs/diagram/constraints#portconstraints)