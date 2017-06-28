---
layout: post
title: Position
description: position
platform: AngularJS
control: Tooltip
documentation: ug
keywords : ejtooltip, tooltip, angularjs tooltip
---

# Position

The position object defines various attributes of the Tooltip position, including the element it is positioned in relation to, and how the position is adjusted within the defined container.

Lets position the Tooltips (stems) left center corner at the right center of the target element.

{% highlight html %}
 
<div class="img" id="sample" ej-tooltip e-content="content" e-position-stem-horizontal="left" e-position-stem-vertical="center" e-position-target-horizontal="right" e-position-target-vertical="center">
    <a target="_blank" href="image/taj.png">
        <img src="http://js.syncfusion.com/demos/web/images/tooltip/template-05.png" alt="Delphi">
    </a>
    <div class="desc">Delphi Succinctly</div>
</div>

<script type="text/javascript">
        angular.module('TooltipApp', ['ejangular'])
        .controller('TooltipCtrl', function ($scope) {
            $scope.content = "Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms.";
        });
</script>
    
{% endhighlight %}

Apply the following styles to show the Tooltip.

{% highlight html %}

<style>
    div.img {
        border: 1px solid #ccc;
        float: left;
        box-sizing: border-box;
        height: 200px;
        width: 146px;
    }
    div.img img {
        width: 100%;
        height: 166px;
    }
    div.desc {
        padding: 6px;
        text-align: center;
    }
</style>
    
{% endhighlight %}

![](Position_images/position.png)

N> By default, the Tooltips "center bottom" corner is placed at the center top of the target element.

## Containment 

Determines the HTML element in which the Tooltip is appended to e.g. its containing element and the tooltip will be restricted to move only within the specified container element.

Let's append our Tooltip to a custom 'frame' container:

{% highlight html %}

<div class="frame">
    <div class="control">
        TypeScript lets you write <a id="test" ej-tooltip e-content="content" e-containment="containment"><u> JavaScript</u> </a>the way you really want to.
    </div>
</div>

<script>
angular.module('TooltipApp', ['ejangular'])
.controller('TooltipCtrl', function ($scope) {
    $scope.content="JavaScript is the programming language of HTML and the Web.";
    $scope.containment=".frame";
});
</script>
    
{% endhighlight %}

N> By default all Tooltips are appended to the document.body element.

## Associates 

 The Tooltip will be positioned in relation to target element. Can also be set to 'mouse' or the window, or an absolute x/y position on the page.
 
 Let's position the Tooltip in relation to the 'a' element inside the div element:
 
 {% highlight html %}

 <div class="frame">
    <div class="control">
        TypeScript lets you write <a id="test" ej-tooltip e-content="content"><u> JavaScript</u> </a>the way you really want to.
    </div>
</div>

<script>   
angular.module('TooltipApp', ['ejangular'])
.controller('TooltipCtrl', function ($scope) {
    $scope.content="JavaScript is the programming language of HTML and the Web.";
});
</script>
    
{% endhighlight %}
 
We can also position the Tooltip in relation to the mouse.
 
{% highlight html %}
 
<div class="frame">
    <div class="control">
        TypeScript lets you write <a id="test" ej-tooltip e-content="content" e-associate="associate"><u> JavaScript</u> </a>the way you really want to.
    </div>
</div>

<script>   
angular.module('TooltipApp', ['ejangular'])
.controller('TooltipCtrl', function ($scope) {
    $scope.content="JavaScript is the programming language of HTML and the Web.";
    $scope.associate="mousefollow";
});
</script>
    
{% endhighlight %}

Position the tooltip at the current mouse position, once enter to the target element as follows

{% highlight html %}
 
<div class="frame">
    <div class="control">
        TypeScript lets you write <a id="test" ej-tooltip e-content="content" e-associate="associate"><u> JavaScript</u> </a>the way you really want to.
    </div>
</div>

<script>   
angular.module('TooltipApp', ['ejangular'])
.controller('TooltipCtrl', function ($scope) {
    $scope.content="JavaScript is the programming language of HTML and the Web.";
    $scope.associate="mouseenter";
});
</script>
    
{% endhighlight %}


It also possible to place the tooltip relation to the window as follows

{% highlight html %}
 
<div class="frame">
    <div class="control">
        TypeScript lets you write <a id="test" ej-tooltip e-content="content" e-associate="associate" e-position-target-horizontal="right"  e-position-target-vertical="bottom"><u> JavaScript</u> </a>the way you really want to.
    </div>
</div>

<script>   
angular.module('TooltipApp', ['ejangular'])
.controller('TooltipCtrl', function ($scope) {
    $scope.content="JavaScript is the programming language of HTML and the Web.";
    $scope.associate="window";
});
</script>
    
{% endhighlight %}
    
And last but not least, absolute positioning via X,Y co-ordinates e.g. a Tooltip at 10px from left and top of the page:

{% highlight html %}

 <div class="frame">
    <div class="control">
        TypeScript lets you write <a id="test" ej-tooltip e-content="content" e-associate="associate" e-position-target-horizontal="10" e-position-target-vertical="10"><u> JavaScript</u> </a>the way you really want to.
    </div>
</div>

<script>   
angular.module('TooltipApp', ['ejangular'])
.controller('TooltipCtrl', function ($scope) {
    $scope.content="JavaScript is the programming language of HTML and the Web.";
    $scope.associate="axis";
});
</script>
    
{% endhighlight %}

## Collision 

When the positioned element overflows the window in some direction, move it to an alternative position. 

The following values determines the kind of positioning that takes place.

<table>
<tr>
<td>
Value<br/></td><td>
Description<br/></td></tr>
<tr>
<td>
Flip<br/></td><td>
Flips the element to the opposite side of the target if the collision detected.<br/></td></tr>
<tr>
<td>
Fit<br/></td><td>
Shift the element away from the edge of the window.<br/></td></tr>
<tr>
<td>
FlipFit(Default)<br/></td><td>
Ensure as much of the element is visible as possible to showcase.<br/></td></tr>
<tr>
<td>
None<br/></td><td>
Does not apply any collision detection.<br/></td></tr>
</table>

{% highlight html %}
 
<div class="frame">
    <div class="control">
        TypeScript lets you write <a id="test" ej-tooltip e-content="content" e-collision="collision"><u> JavaScript</u> </a>the way you really want to.
    </div>
</div>

<script>   
angular.module('TooltipApp', ['ejangular'])
.controller('TooltipCtrl', function ($scope) {
    $scope.content="JavaScript is the programming language of HTML and the Web.";
    $scope.collision="fit";
});
</script>
        
{% endhighlight %}