---
layout: post
title: Stacked-Header
description: stacked header
platform: AngularJS
control: TreeGrid
documentation: ug

---
# Stacked Headers

The stacked headers helps you to group the logical columns in TreeGrid. It can be shown by setting `e-showstackedheader` as `true` and by defining `e-stackedheaderrows`.

## Adding Stacked header columns

To stack columns in stacked header, you need to define `column` property in `e-stackedheaderrows.stackedHeaderColumns` with field names of visible columns.

{% highlight html %}
<body ng-controller="TreeGridCtrl">
               <div id="angulartreegrid" ej-treegrid 
                     //		   
                     e-columns="columns"                   
                     e-showstackedheader="true"                    
                     e-stackedheaderrows="stackedHeaderRows">
                </div>            
    <script>       
        var stackedHeaderRows = [{
            stackedHeaderColumns: [{
                    column: "ID,Name,category,units",
                    headerText: "Shipment details"
                },
                {
                    column: "unitPrice,price",
                    headerText: "Price details"
                }
            ]
        ]
        angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function ($scope) {           
            //
         $scope.columns = columns;    
         $scope.stackedHeaderRows = stackedHeaderRows;
        });
    </script>    
</body>
{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img1.png)

## Stacked header column customization

we can customize the stacked header cells with more options as described below.

### CSS Class

You can provide external CSS styles to the stacked header with the help of `cssClass` property in `e-stackedheaderrows.stackedHeaderColumns`.

{% highlight html %}
<body ng-controller="TreeGridCtrl">   
           <div id="angulartreegrid" ej-treegrid 
                     //		   
                     e-columns="columns"                   
                     e-showstackedheader="true"                    
                     e-stackedheaderrows="stackedHeaderRows">
                </div>            
    <script>       
        var stackedHeaderRows = [{
            stackedHeaderColumns: [{
                    column: "ID,Name,category,units",
                    headerText: "Shipment details",
		    cssClass: "stack"
                },
                {
                    column: "unitPrice,price",
                    headerText: "Price details"
                }
            ]
        ]
        angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function ($scope) {           
            //
         $scope.columns = columns;    
         $scope.stackedHeaderRows = stackedHeaderRows;
        });
    </script>
    <style>
         .stack {
            background-color: #ffb3b3; 
        }
    </style>
</body>
{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img2.png)

### Text Align

There is an option to align the stacked header text inside the header cell using `textAlign` property in `e-stackedheaderrows.stackedHeaderColumns` as follows.

{% highlight html %}
<body ng-controller="TreeGridCtrl">                  
           <div id="angulartreegrid" ej-treegrid 
                     //		   
                     e-columns="columns"                   
                     e-showstackedheader="true"                     
                     e-stackedheaderrows="stackedHeaderRows">
                </div>            
    <script>       
        var stackedHeaderRows = [{
            stackedHeaderColumns: [{
                    column: "ID,Name,category,units",
                    headerText: "Shipment details",
		    textAlign:ej.TextAlign.Left 
                },
                {
                    column: "unitPrice,price",
                    headerText: "Price details",
		    textAlign: ej.TextAlign.Right 
                }
            ]
        ]
        angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function ($scope) {           
            //
         $scope.columns = columns;    
         $scope.stackedHeaderRows = stackedHeaderRows;
        });
    </script>    
</body>
{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img4.png)

### Tooltip

We can have the customized tooltip for the stacked header text with the help of `tooltip` property in `e-stackedheaderrows.stackedHeaderColumns`. JsRender template script id can be assigned to this property to get tooltip.

{% highlight html %}
<body ng-controller="TreeGridCtrl">
    <script id="tooltip" type="text/x-jsrender">
    <div>Custom Tooltip</div>
    </script>               
           <div id="angulartreegrid" ej-treegrid 
                     //		   
                     e-columns="columns"                   
                     e-showstackedheader="true"
                     e-showgridcelltooltip="true"
                     e-stackedheaderrows="stackedHeaderRows">
                </div>            
    <script>       
        var stackedHeaderRows = [{
            stackedHeaderColumns: [{
                    column: "ID,Name,category,units",
                    headerText: "Shipment details",
		   
                },
                {
                    column: "unitPrice,price",
                    headerText: "Price details",
		    tooltip: "#tooltip" 
                }
            ]
        ]
        angular.module('listCtrl', ['ejangular'])
        .controller('TreeGridCtrl', function ($scope) {           
            //
         $scope.columns = columns;    
         $scope.stackedHeaderRows = stackedHeaderRows;
        });
    </script>   
</body>
{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img3.png)

N>
To enable stacked header tooltip we need to set `e-showgridcelltooltip` as `true`.

