---
layout: post
title: Data-binding
description: data binding
platform: AngularJS
control: Rating
documentation: ug
keywords: ejrating, rating, angularjs rating 
---

# Data-binding

In data binding concept of Rating control, need to set the value property using two way binding that is you need to assign the rating value using scope variable.

The following example depicts the way to bind data to the **Rating** control.

Add the following code to render Rating with data binding.

{% highlight html %}

<body ng-controller="RatingCtrl">
    <table>
        <th>
            <div id="control">
                <input id="apiRating" type="text" class="rating" ej-rating e-value="ratingValue">
            </div>
        </th>
        <th>
            <div id="binding">
                <input type="text" class="input ejinputtext" name="rating" value="" ng-model="ratingValue" />
            </div>
        </th>
    </table>
</body>

{% endhighlight %}

{% highlight javascript %}

    angular.module('ratingApp', ['ejangular'])
    .controller('RatingCtrl', function ($scope) {
        $scope.ratingValue = 3;
    });

{% endhighlight %}

{% highlight css %}

    <style type="text/css" class="cssStyles">
        #binding {
            margin-left: 150px;
        }
        .control {
            margin-top: 10px;
        }
        .input {
            height: 27px;
            text-indent: 10px;
            width: 81%;
        }
    </style>

{% endhighlight %}

The following screenshot displays the output of **Rating** with **data binding** support.

![](Data-binding_images/Data-binding_img1.png)