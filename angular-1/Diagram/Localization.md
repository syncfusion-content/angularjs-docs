---
layout: post
title: Globalize and Localize the Diagram control
description: How to globalize and localize the Diagram control?
platform: Angular-1
control: Diagram
documentation: ug
---

# Localization

* Localization is the process of providing controls in different cultures to help you set your own culture easily. Diagram provides localization support for Context Menu items.
* The Diagram model’s `locale` property is used to define the culture code. 

The following code illustrates how to provide localization support for Context Menu items.

{% highlight html %}

 <div ng-controller="diagramCtrl">
    <div>
        <ej-diagram id="DiagramContent" e-width="100%" e-height="700px" e-nodes="nodes" e-locale="locale">
        </ej-diagram>
    </div>
</div>

   {% endhighlight %}

   {% highlight javascript %}

// Defines the context menu items with spanish language
ej.datavisualization.Diagram.Locale["es-ES"] = {
    cut: "Corte",
    copy: "Copia",
    paste: "Pasta",
    undo: "Deshacer",
    redo: "Rehacer",
    selectAll: "Seleccionar todo",
    grouping: "Agrupación",
    group: "Grupo",
    ungroup: "Desagrupar",
    order: "Fin",
    bringToFront: "Traer a delante",
    moveForward: "Movimiento adelante",
    sendToBack: "Enviar a espalda",
    sendBackward: "Enviar hacia atrás"
};

var nodes = [{
    name: "rectangle1",
    offsetY: 100,
    labels: [{
        "text": "Rectangle1"
    }]
}];

//Initializes the Diagram.
syncApp.controller('diagramCtrl', function($scope) {
    $scope.nodes = nodes;
    $scope.locale = "es-ES";
    $scope.localeText = ["es-ES"];
});

{% endhighlight %}

![](/angular-1/Diagram/Localization_images/Localization_img1.png)

N> You have to define the textual descriptions of the context menu items for your custom cultures.