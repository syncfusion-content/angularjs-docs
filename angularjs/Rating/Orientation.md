---
layout: post
title: Orientation
description: orientation
platform: AngularJS
control: Rating
documentation: ug
keywords: ejrating, rating, angularjs rating 
---

# Orientation

**Rating** provides support for **vertical** orientation. By default Rating renders with **horizontal** orientation. You can the change the orientation by the [orientation](https://help.syncfusion.com/api/js/ejrating#members:orientation) property.

The following code example is used to render the Rating control with **vertical** **orientation**.

 Add the following HTML to render Rating with customized orientation.

{% highlight html %}

<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">
    <table>
        <tr>
            <td valign="top">Rating:
               </td>
               <td>
                 <input id="rating" type="text" ej-rating e-orientation="orientation"/>
               </td>
           </tr>
      </table>
 </div>
    
 {% endhighlight %}

{% highlight javascript %}

// Add the following script to render Rating with customized orientation.
 angular.module('ratingApp', ['ejangular'])
   .controller('RatingCtrl', function ($scope) {
       $scope.orientation ="vertical";
 });

{% endhighlight %}

The following screenshot illustrates the **Rating** with **vertical orientation**.

![](Orientation_images/Orientation_img1.png)