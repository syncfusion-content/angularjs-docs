---
layout: post
title: Automatic Layout in AngularJS Diagram Control | Syncfusion
description: Learn here about automatic layout in Syncfusion Essential AngularJS Diagram Control, its elements, and more.
platform: AngularJS
control: Diagram
documentation: ug
---

# Automatic Layout in AngularJS Diagram

Diagram provides support to auto-arrange the nodes in the Diagram area that is referred as **Layout**. It includes the following layout modes.

* Hierarchical Layout
* Organization Chart
* Radial Tree

## Hierarchical Layout

The Hierarchical Tree Layout arranges nodes in a tree-like structure, where the nodes in the hierarchical layout may have multiple parents. There is no need to specify the layout root.
To arrange the nodes in hierarchical structure, you need to specify the layout `type` as hierarchical tree. The following example shows how to arrange the nodes in a hierarchical structure.


{% highlight javascript %}
 
<div ng-controller="diagramCtrl">
    <ej-diagram id="diagram" e-height="450px" e-layout-type="layout.type" e-layout-orientation="layout.orientation" e-layout-horizontalspacing="layout.horizontalSpacing" e-layout-verticalspacing="layout.verticalSpacing"
	 e-layout-marginx="layout.marginX" e-layout-marginy="layout.marginY" e-nodetemplate="nodeTemplate" e-datasourcesettings-datasource="dataSourceSettings.dataSource" e-datasourcesettings-parent="dataSourceSettings.parent"
	  e-datasourcesettings-id="dataSourceSettings.id" e-datasourcesettings-root="dataSourceSettings.root" e-defaultsettings-node="defaultSettings.node" e-defaultsettings-connector="defaultSettings.connector">
    </ej-diagram>
</div>

{% endhighlight %}

			{% highlight javascript %}

//Initializes data source
var data = [{
        Name: "Steve-Ceo"
    },
    {
        Name: "Kevin-Manager",
        ReportingPerson: "Steve-Ceo"
    },
    {
        Name: "Peter-Manager",
        ReportingPerson: "Steve-Ceo"
    },
    {
        Name: "John- Manager",
        ReportingPerson: "Peter-Manager"
    },
    {
        Name: "Mary-CSE ",
        ReportingPerson: "Peter-Manager"
    },
    {
        Name: "Jim-CSE ",
        ReportingPerson: "Kevin-Manager"
    },
    {
        Name: "Martin-CSE",
        ReportingPerson: "Kevin-Manager"
    }
];


//Binds custom JSON with node
function nodeTemplate(diagram, node) {
    node.labels[0].text = node.Name;
}

syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        type: "hierarchicaltree",
        orientation: "toptobottom",
        horizontalSpacing: 25,
        verticalSpacing: 35,
        marginX: 3,
        marginY: 3
    };
    $scope.defaultSettings = {
        node: {
            fillColor: "#88C65C",
            width: 100,
            height: 40,
            labels: [{
                name: "label1",
                fontColor: "white",
                fontSize: 12,
            }]
        },
        connector: {
            lineColor: "#000000",
            constraints: ej.datavisualization.Diagram.ConnectorConstraints.None,
            segments: [{
                type: "orthogonal"
            }]
        }
    };
    $scope.nodeTemplate = "nodeTemplate";
    $scope.dataSourceSettings = {
        id: "Name",
        parent: "ReportingPerson",
        dataSource: data
    };
});

{% endhighlight %}

![AngularJS Diagram Radial Tree Layout](Automatic-Layout_images/Automatic-Layout_img1.png)

N> You can ignore a particular Node from layout arrangement by setting its **excludeFromLayout** property as true.

## Radial Tree Layout

The Radial Tree layout arranges nodes on a virtual concentric circles around a root node. Sub-trees formed by the branching of child nodes are located radially around the child nodes. This arrangement results in an ever-expanding concentric arrangement with radial proximity to the root node indicating the node level in the hierarchy. When no root node is set, the algorithm automatically considers one of the Diagram nodes as the root node.

To arrange nodes in a radial tree structure, you need to set the `layout.type` as `radialtree`. The following code illustrates how to arrange the nodes in a radial tree structure.

{% highlight javascript %}

//Initializes data source
var data = [{
        Id: "parent",
        ImageUrl: "images/Clayton.png"
    },
    {
        Id: 1,
        ImageUrl: "images/image55.png",
        ReportingPerson: "parent"
    },
    {
        Id: 2,
        ImageUrl: "images/Robin.PNG",
        ReportingPerson: "parent"
    },
    {
        Id: 3,
        ImageUrl: "images/Robin.PNG",
        ReportingPerson: "parent"
    },
    {
        Id: 4,
        ImageUrl: "images/Paul.png",
        ReportingPerson: "parent"
    },
    {
        Id: 5,
        ImageUrl: "images/image53.png",
        ReportingPerson: "parent"
    },
    {
        Id: 6,
        ImageUrl: "images/Maria.png",
        ReportingPerson: "parent"
    },
    {
        Id: 7,
        ImageUrl: "images/Jenny.png",
        ReportingPerson: 3
    },
    {
        Id: 8,
        ImageUrl: "images/Thomas.PNG",
        ReportingPerson: "parent"
    },
    {
        Id: 9,
        ImageUrl: "images/Jenny.png",
        ReportingPerson: 2
    },
    {
        Id: 10,
        ImageUrl: "images/Thomas.png",
        ReportingPerson: 2
    },
    {
        Id: 11,
        ImageUrl: "images/Maria.PNG",
        ReportingPerson: 4
    },
    {
        Id: 12,
        ImageUrl: "images/Thomas.PNG",
        ReportingPerson: 1
    },
    {
        Id: 13,
        ImageUrl: "images/Clayton.png",
        ReportingPerson: 6
    },
    {
        Id: 14,
        ImageUrl: "images/Jenny.png",
        ReportingPerson: 3
    },
    {
        Id: 15,
        ImageUrl: "images/Thomas.png",
        ReportingPerson: 3
    },
    {
        Id: 16,
        ImageUrl: "images/John.png",
        ReportingPerson: 6
    },
    {
        Id: 17,
        ImageUrl: "images/Jenny.png",
        ReportingPerson: 4
    },
    {
        Id: 18,
        ImageUrl: "images/Robin.png",
        ReportingPerson: 4
    },
    {
        Id: 19,
        ImageUrl: "images/Clayton.png",
        ReportingPerson: 4
    },
    {
        Id: 20,
        ImageUrl: "images/image57.png",
        ReportingPerson: 12
    },
    {
        Id: 21,
        ImageUrl: "images/Robin.png",
        ReportingPerson: 5
    },
    {
        Id: 22,
        ImageUrl: "images/image51.png",
        ReportingPerson: 6
    },
    {
        Id: 23,
        ImageUrl: "images/image55.png",
        ReportingPerson: 19
    },
    {
        Id: 24,
        ImageUrl: "images/Thomas.png",
        ReportingPerson: 8
    },
    {
        Id: 25,
        ImageUrl: "images/image56.png",
        ReportingPerson: 8
    },
    {
        Id: 26,
        ImageUrl: "images/image55.png",
        ReportingPerson: 1
    },
    {
        Id: 27,
        ImageUrl: "images/image57.png",
        ReportingPerson: 13
    },
    {
        Id: 28,
        ImageUrl: "images/Robin.PNG",
        ReportingPerson: 12
    },
    {
        Id: 29,
        ImageUrl: "images/Thomas.PNG",
        ReportingPerson: 13
    },
    {
        Id: 30,
        ImageUrl: "images/image57.png",
        ReportingPerson: 19
    }
];

//Binds custom JSON with node
function nodeTemplate(diagram, node) {
    node.name = node.Id;
    node.source = node.ImageUrl;
}

syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        type: "radialtree",
        horizontalSpacing: 30,
        verticalSpacing: 30
    };
    $scope.defaultSettings = {
        node: {
            width: 50,
            height: 50,
            borderColor: "transparent",
            type: "image"
        }
    };
    $scope.nodeTemplate = "nodeTemplate";
    $scope.dataSourceSettings = {
        id: "Name",
        parent: "ReportingPerson",
        dataSource: data
    };
});

{% endhighlight %}

![AngularJS Diagram Organizational Chart](Automatic-Layout_images/Automatic-Layout_img2.png)

## Organizational Chart

An **organizational chart** is a Diagram that displays the structure of an organization and relationships. To create an organizational chart, `layout.type` should be set as `organizationalchart`.
The following code example illustrates how to create an organizational chart.

{% highlight javascript %}

//Initializes data source
var data = [{
        Id: "parent",
        Role: "Project Management"
    },
    {
        Id: 1,
        Role: "R&D Team",
        Team: "parent"
    },
    {
        Id: 3,
        Role: "Philosophy",
        Team: "1"
    },
    {
        Id: 4,
        Role: "Organization",
        Team: "1"
    },
    {
        Id: 5,
        Role: "Technology",
        Team: "1"
    },
    {
        Id: 7,
        Role: "Funding",
        Team: "1"
    },
    {
        Id: 8,
        Role: "Resource Allocation",
        Team: "1"
    },
    {
        Id: 9,
        Role: "Targeting",
        Team: "1"
    },
    {
        Id: 11,
        Role: "Evaluation",
        Team: "1"
    },
    {
        Id: 156,
        Role: "HR Team",
        Team: "parent"
    },
    {
        Id: 13,
        Role: "Recruitment",
        Team: "156"
    },
    {
        Id: 113,
        Role: "Training",
        Team: "12"
    },
    {
        Id: 112,
        Role: "Employee Relation",
        Team: "156"
    },
    {
        Id: 14,
        Role: "Record Keeping",
        Team: "12"
    },
    {
        Id: 15,
        Role: "Compensations & Benefits",
        Team: "12"
    },
    {
        Id: 16,
        Role: "Compliances",
        Team: "12"
    },
    {
        Id: 17,
        Role: "Production & Sales Team",
        Team: "parent"
    },
    {
        Id: 119,
        Role: "Design",
        Team: "17"
    },
    {
        Id: 19,
        Role: "Operation",
        Team: "17"
    },
    {
        Id: 20,
        Role: "Support",
        Team: "17"
    },
    {
        Id: 21,
        Role: "Quality Assurance",
        Team: "17"
    },
    {
        Id: 23,
        Role: "Customer Interaction",
        Team: "17"
    },
    {
        Id: 24,
        Role: "Support and Maintenance",
        Team: "17"
    },
    {
        Id: 25,
        Role: "Task Coordination",
        Team: "17"
    }
];

//Binds JSON data with node
function nodeTemplate(diagram, node) {
    node.labels[0].text = node.Role;
}

//Initializes Diagram
syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        type: "organizationalchart"
    };
    $scope.defaultSettings = {
        //Sets the default properties of the node.
        node: {
            width: 100,
            height: 40,
            fillColor: "#546e20",
            labels: [{
                name: "label1",
                fontColor: "white"
            }]
        },

        //Sets the default properties of the connector.
        connector: {
            segments: [{
                "type": "orthogonal"
            }],
            targetDecorator: {
                shape: "none"
            }
        }
    };
    $scope.nodeTemplate = "nodeTemplate";
    $scope.dataSourceSettings = {
        id: "Id",
        parent: "Team",
        dataSource: data
    };
});

{% endhighlight %}

![AngularJS Diagram GetLayoutInfo](Automatic-Layout_images/Automatic-Layout_img3.png)

Organizational chart layout starts parsing from root and iterate through all its child elements. ‘getLayoutInfo’ method provides necessary information of a node’s children and the way to arrange (direction, orientation, offsets, etc.) them. You can customize the arrangements by overriding this function as explained.

### GetLayoutInfo

You can set Chart orientations, chart types, and offset to be left between parent and child nodes by overriding the method, diagram.model.layout.getLayoutInfo. The getLayoutInfo method is called to configure every subtree of the organizational chart. It takes the following arguments.

* `diagram`: Reference of diagram
* `node`: Parent node to that options are to be customized
* `options`: object to set the customizable properties

The following code example illustrates how to define the method getLayoutInfo.

{% highlight javascript %}

var chartOrientations = ej.datavisualization.Diagram.ChartOrientations;
var chartTypes = ej.datavisualization.Diagram.ChartTypes;

//Defines getLayoutInfo
function getLayoutInfo(diagram, node, options) {
    options.orientation = chartOrientations.Vertical;

    //Configures the sub tree of the node vertically at right-side.
    options.type = chartTypes.Right;
    options.offset = 10;
}

//Initializes Diagram
syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        type: "organizationalchart",
        getLayoutInfo: getLayoutInfo
    };
});

{% endhighlight %}

The following table illustrates the properties that "options" argument takes.

Property|Description|Default Value
---|---|---
options.children|Contains the list of child nodes. Children collection can be modified.|Array of child nodes
options.assistants|By default, the collection is empty. When any of the child nodes have to be set as "Assistant", you can remove from children collection and have to insert into assistants collection. |Empty array
options.orientation|Gets or sets the organizational chart orientation. |ChartOrientation.Vertical
options.type|Gets or sets the chart organizational chart type |For horizontal chart orientation:ChartType.Center For Vertical chart orientation:ChartType.Alternate
options.offset|Offset is the horizontal space to be left between parent and child nodes.|20 pixels.Applicable only for vertical chart orientations.
options.hasSubTree|Gets whether the node contains sub trees.|Boolean
options.level|Gets the depth of the node from layout root|Number
options.enableRouting|By default, Connections are routed based on the chart type and orientations.This property gets or sets whether default routing is to be enabled or disabled.|true
options.rows|Sets the number of rows on which the child nodes will be arranged. Applicable only for balanced type horizontal tree |Number

The following table illustrates the different chart orientations and chart types.

| Orientation | Type | Description | Example |
|---|---|---|---|
| Horizontal | Left | Arranges the child nodes horizontally at the left side of parent. | ![Horizontal Left](Automatic-Layout_images/Automatic-Layout_img4.png) |
| | Right | Arranges the child nodes horizontally at the right side of parent. | ![Horizontal Right](Automatic-Layout_images/Automatic-Layout_img5.png) |
| | Center | Arranges the children like standard tree layout orientation. | ![Horizontal Center](Automatic-Layout_images/Automatic-Layout_img6.png) |
| | Balanced | Arranges the leaf-level child nodes in multiple rows. | ![Horizontal Balanced](Automatic-Layout_images/Automatic-Layout_img16.png) |
| Vertical | Left | Vertically arranges the children at the left side of parent | ![Vertical Left](Automatic-Layout_images/Automatic-Layout_img7.png) |
| | Right | Vertically arranges the children at the right side of parent | ![Vertical Right](Automatic-Layout_images/Automatic-Layout_img8.png) |
| | Alternate | Vertically arranges the children at both left and right sides of parent | ![Horizontal Alternate](Automatic-Layout_images/Automatic-Layout_img9.png) |


The following code example illustrates how to set the vertical right arrangement to the leaf level trees.

{% highlight javascript %}

//Initializes data source
var data = [{
        Id: "parent",
        Role: "Board"
    },
    {
        Id: "1",
        Role: "General Manager",
        Manager: "parent"
    },
    {
        Id: "2",
        Role: "Human Resource Manager",
        Manager: "1"
    },
    {
        Id: "3",
        Role: "Trainers",
        Manager: "2"
    },
    {
        Id: "4",
        Role: "Recruiting Team",
        Manager: "2"
    },
    {
        Id: "5",
        Role: "Finance Asst. Manager",
        Manager: "2"
    },
    {
        Id: "6",
        Role: "Design Manager",
        Manager: "1"
    },
    {
        Id: "7",
        Role: "Design Supervisor",
        Manager: "6"
    },
    {
        Id: "8",
        Role: "Development Supervisor",
        Manager: "6"
    },
    {
        Id: "9",
        Role: "Drafting Supervisor",
        Manager: "6"
    },
    {
        Id: "10",
        Role: "Marketing Manager",
        Manager: "1"
    },
    {
        Id: "11",
        Role: "Oversea sales Manager",
        Manager: "10"
    },
    {
        Id: "12",
        Role: "Petroleum Manager",
        Manager: "10"
    },
    {
        Id: "13",
        Role: "Service Dept. Manager",
        Manager: "10"
    },
];

var chartOrientations = ej.datavisualization.Diagram.ChartOrientations;
var chartTypes = ej.datavisualization.Diagram.ChartTypes;

//Creates the node template
function nodeTemplate(diagram, node) {
    node.labels[0].text = node.Role;
}

function getLayoutInfo(diagram, node, options) {
    if (!options.hasSubTree) {
        options.type = chartTypes.Right;
        options.orientation = chartOrientations.Vertical;
    }
}

//Initializes Diagram
syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        type: "organizationalchart",
        getLayoutInfo: getLayoutInfo
    };
    $scope.defaultSettings = {
        //Sets the default properties of the node.
        node: {
            width: 100,
            height: 40,
            fillColor: "#3c418B",
            borderColor: "transparent",
            labels: [{
                fontColor: "white"
            }]
        },
        connector: {
            segments: [{
                "type": "orthogonal"
            }],
            targetDecorator: {
                shape: "none"
            }
        }
    };
    $scope.nodeTemplate = "nodeTemplate";
    $scope.dataSourceSettings = {
        id: "Id",
        parent: "Manager",
        dataSource: data
    };
});

{% endhighlight %}

![AngularJS Diagram Assistant](Automatic-Layout_images/Automatic-Layout_img10.png)

### Assistant

**Assistants** are child item that have a different relationship with the parent node. They are laid out in a dedicated part of the tree. You can specify a node as an assistant of its parent by adding it to `assistants` property of the argument "options".

The following code example illustrates how to add assistants to layout.

{% highlight javascript %}

//Initializes data source
var data = [{
        Id: 1,
        Role: "General Manager"
    },
    {
        Id: 2,
        Role: "Assistant Manager",
        Team: 1
    },
    {
        Id: 3,
        Role: "Human Resource Manager",
        Team: 1
    },
    {
        Id: 4,
        Role: "Design Manager",
        Team: 1
    },
    {
        Id: 5,
        Role: "Operation Manager",
        Team: 1
    },
    {
        Id: 6,
        Role: "Marketing Manager",
        Team: 1
    }
];

//Creates the node template
function nodeTemplate(diagram, node) {
    node.labels[0].text = node.Role;
}

//Defines getLayoutInfo
function getLayoutInfo(diagram, node, options) {
    if (node.labels[0].text == "General Manager") {
        options.assistants.push(options.children[0]);
        options.children.splice(0, 1);
    }
    options.orientation = "horizontal";
    options.type = "center"
}

//Initializes Diagram
syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        type: "organizationalchart",
        getLayoutInfo: getLayoutInfo
    };
    $scope.defaultSettings = {
        //Sets the default properties of the node.
        node: {
            width: 100,
            height: 40,
            fillColor: "#546e20",
            labels: [{
                name: "label1",
                fontColor: "white"
            }]
        },
        connector: {
            segments: [{
                "type": "orthogonal"
            }],
            targetDecorator: {
                shape: "none"
            }
        }
    };
    $scope.nodeTemplate = "nodeTemplate";
    $scope.dataSourceSettings = {
        id: "Id",
        parent: "Team",
        dataSource: data
    };
});

{% endhighlight %}

![AngularJS Diagram Customize Layout](Automatic-Layout_images/Automatic-Layout_img11.png)

## Customize Layout

Orientation, spacings, and position of layout can be customized with a set of properties.

To explore layout properties, refer to [Layout Properties](/api/js/ejDiagram#members:layout "Layout Properties").

### Layout Bounds 

Diagram provides support to align the layout within any custom rectangular area. For more information about bounds, refer to [Layout Bounds] (/api/js/ejDiagram#members:layout-bounds "Layout Bounds")

### Layout Alignment

You can align the layout anywhere over the layout bounds/viewport using the `horizontalAlignment` and `verticalAlignment` properties of layout.

The following code illustrates how to align the layout at the top left of the layout bounds.

{% highlight javascript %}

var type = ej.datavisualization.Diagram.LayoutTypes;
var orientation = ej.datavisualization.Diagram.LayoutOrientations;

//Initializes Diagram
syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        //Sets the type of the layout
        type: type.HierarchicalTree,
        orientation: orientation.TopToBottom,
        horizontalSpacing: 25,
        verticalSpacing: 30,

        //Sets the layout bounds
        bounds: {
            x: 0,
            y: 0,
            width: 500,
            height: 500
        },

        //Sets the alignment of the layout
        horizontalALignment: ej.datavisualization.Diagram.HorizontalAlignment.Left,
        verticalAlignment: ej.datavisualization.Diagram.VerticalAlignment.Top,
    };
    $scope.defaultSettings = {
        //Sets the default properties of the node.
        //Sets the default properties of the connector.
    };
    //Initializes the node template.
    $scope.nodeTemplate = "nodeTemplate";
    //Configures data source for Diagram
    $scope.dataSourceSettings = {
        //Specifies the dataSource
    };
});

{% endhighlight %}

![AngularJS Diagram Layout Margin](Automatic-Layout_images/Automatic-Layout_img14.png)

### Layout Margin

Layout provides support to add some blank space between the layout bounds/viewport and the layout. The `margin` property of the layout allows you to set the blank space.

The following code illustrates how to set the layout margin.

{% highlight js %}

var type = ej.datavisualization.Diagram.LayoutTypes;
var orientation = ej.datavisualization.Diagram.LayoutOrientations;

//Initializes Diagram
syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        type: type.HierarchicalTree,
        orientation: orientation.TopToBottom,
        bounds: {
            x: 0,
            y: 0,
            width: 500,
            height: 500
        },
        horizontalSpacing: 25,
        verticalSpacing: 30,
        horizontalALignment: ej.datavisualization.Diagram.HorizontalAlignment.Left,
        verticalAlignment: ej.datavisualization.Diagram.VerticalAlignment.Top,

        //Sets the margin
        margin: {
            left: 10,
            right: 10,
            top: 10,
            bottom: 10
        }
    };
    $scope.defaultSettings = {
        //Sets the default properties of the node.
        //Sets the default properties of the connector.
    };
    //Initializes the node template.
    $scope.nodeTemplate = "nodeTemplate";
    //Configures data source for Diagram
    $scope.dataSourceSettings = {
        //Specifies the dataSource
    };
});

{% endhighlight %}

![AngularJS Diagram Layout Orientation](Automatic-Layout_images/Automatic-Layout_img15.png)

### Layout Orientation

Diagram provides support to customize the orientation of layout. You can set the desired orientation using `layout.orientation`. For more information about orientation, refer to [Layout Orientations](/api/js/global#layoutorientations "Layout Orientations")

The following code illustrates how to arrange the nodes in a "BottomToTop" orientation.

{% highlight javascript %}

var type = ej.datavisualization.Diagram.LayoutTypes;
var orientation = ej.datavisualization.Diagram.LayoutOrientations;

//Initializes Diagram
syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        //Sets the type of the layout
        type: type.HierarchicalTree,

        //Sets the orientation
        orientation: orientation.BottomToTop,

        //Sets the space to be horizontally left between nodes
        horizontalSpacing: 20,

        //Sets the space to be vertically left between nodes
        verticalSpacing: 20
    };
    $scope.defaultSettings = {
        //Sets the default properties of the node.
        //Sets the default properties of the connector.
    };
    //Initializes the node template.
    $scope.nodeTemplate = "nodeTemplate";
    //Configures data source for Diagram
    $scope.dataSourceSettings = {
        //Specifies the dataSource
    };
});

{% endhighlight %}

![AngularJS Diagram Fixed Node](Automatic-Layout_images/Automatic-Layout_img12.png)

### Fixed Node

Layout provides support to arrange the nodes with reference to the position of a fixed node and the fixed node has to be set to the `layout.fixedNode`.
This is helpful when you try to expand/collapse a node. It might be expected that the position of the double-clicked node should not be changed.

{% highlight javascript %}

//Initializes data source
var data = [{
    name: "parent",
    Role: "General Manager",
    offsetX: 250,
    offsetY: 50
}, {
    name: "1",
    Role: "Human Resource Manager",
    Manager: "parent"
}, {
    name: "2",
    Role: "Design Manager",
    Manager: "parent",
}, {
    name: "3",
    Role: "Marketing Manager",
    Manager: "parent",
}];

//Creates the node template
function nodeTemplate(diagram, node) {
    node.labels[0].text = node.Role;
}

//Defines getLayoutInfo
function getLayoutInfo(diagram, node, options) {
    options.orientation = "horizontal";
    options.type = "center"
}

//Initializes Diagram
syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        type: "organizationalchart",
        fixedNode: "parent",
        getLayoutInfo: getLayoutInfo
    };
    $scope.defaultSettings = {
        //Sets the default properties of the node.
        //Sets the default properties of the connector.
    };
    //Initializes the node template.
    $scope.nodeTemplate = "nodeTemplate";
    //Configures data source for Diagram
    $scope.dataSourceSettings = {
        //Specifies the dataSource
    };
});

{% endhighlight %}

![AngularJS Diagram Expand and collapse](Automatic-Layout_images/Automatic-Layout_img13.png)

### Expand and collapse

Diagram allows to expand/collapse the sub trees of a layout. `node.isExpanded` allows you to expand/collapse its children. The following code example shows how to expand/collapse the children of a node.

{% highlight javascript %}

//Initializes Diagram
syncApp.controller('diagramCtrl', function($scope) {
    //Uses layout to auto-arrange nodes on the Diagram page
    $scope.layout = {
        type: "organizationalchart",
        fixedNode: "node1"
    };
    //Defines double click event
    $scope.doubleClick = onDoubleClick
});

function onDoubleClick(args) {
    var diagram = $("#diagram").ejDiagram("instance");
    var node = args.element;

    // Sets the double clicked node as fixed node
    $("#diagram").ejDiagram({
        layout: {
            fixedNode: node.name
        }
    });

    //Expands/collapses the children of node
    diagram.updateNode(node.name, {
        isExpanded: !node.isExpanded
    });
}

{% endhighlight %}

In above example, while expanding/collapsing a node, it is set as fixed node in order to prevent it from repositioning.

### Refresh layout

Diagram allows to refresh the layout at runtime. To refresh the layout, refer to [Refresh layout](/api/js/ejDiagram#methods:layout "Refresh layout").