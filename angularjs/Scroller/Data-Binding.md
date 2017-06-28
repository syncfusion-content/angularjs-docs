---
layout: post
title: Data-Binding
description: Data Binding 
platform: AngularJS
control: Scroller
documentation: ug
---

# Data Binding

## One-Way Binding

In Scroller, the one way binding of a property is achieved by using "e-" prefixed with a property name. Here, one-way binding is explained using the height and width properties. The height and the width properties of the scroller content being bound with e-height and e-width properties has been shown below.

{% highlight html %}

    <div ng-controller="ScrollerCtrl">
    <div class="control">
            <div id="scrollcontent" ej-scroller e-height="height" e-width="width">
                <div>
                    <div class="sampleContent">
                        <h3 style="font-size: 20px;">Syncfusion</h3>
                        <div>
                            <p>
                                We are a world leader in software components. With close to a decade of experience, we have thousands of satisfied customers world-wide who have used our products to ship award winning software. We have won numerous industry awards which honors the top innovators and leaders in the software development industry.
                                Since we provide building blocks that power applications, our work requires a level of understanding that is not required when working on applications. We are always looking for candidates with the right technical aptitude and the will to be masters in this programming trade we all love.
                            </p>
                            <h4 style="font-size: 20px;">What we do</h4>
                            <ul>
                                <li>
                                    We work to produce software building blocks that other developers use. As software has become more and more complex to produce it is commonly the case that more and more companies rely on software building blocks to produce complex software.
                                </li><br />
                                <li>
                                    We work at a much lower level than typical application development. We write the plumbing that powers application development for thousands of developers worldwide. This does mean that we look for our team members to be significantly better than industry peers. You have to have a solid understanding of data structures and be seriously interested in programming. You should also have a passion for problem solving and excellence.
                                </li><br />
                                <li>
                                    The nature of our work often requires us to work in areas where there are very few teams working world-wide. Consider the Windows Presentation Foundation or Silverlight. We started work, producing components for these platforms years before they became industry buzzwords. If you are truly looking to stay ahead of the curve there is no better place to work than Syncfusion.
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
    </div>
    </div>
        
{% endhighlight %}

{% highlight javascript %}

<script>
    angular.module('scrollerrApp', ['ejangular'])
     .controller('ScrollerCtrl', function ($scope) {
         $scope.height = "300px";
         $scope.width = "600px";
    });
</script>

{% endhighlight %}

Configuring Styles.

{% highlight html %}

<style type="text/css">
        .control {
            border: 1px solid #bbbcbb;
            width: 600px;
            margin: 0 auto;
            height: 300px;
        }

        .sampleContent {
            width: 700px;
            padding: 15px;
        }
        p,ul{
            text-align:justify;
        }
</style>

{% endhighlight %}

![](data-binding_images/one-way-binding.png)

## Two-Way Binding

Two-way binding in scroller in Angular JS is achieved by using (ng-model) attribute. Here, the scroll top and scroll left properties are bounded with the scroller. In the below sample, the value of the scroll left and scroll top properties are varied will reflect in textbox below and vice versa.

{% highlight html %}

    <div ng-controller="ScrollerCtrl">
    <div class="control">
                <div id="scrollcontent" ej-scroller e-height="height" e-width="width" e-scrolltop="top" e-scrollleft="left">
                <div>
                    <div class="sampleContent">
                        <h3 style="font-size: 20px;">Syncfusion</h3>
                        <div>
                            <p>
                                We are a world leader in software components. With close to a decade of experience, we have thousands of satisfied customers world-wide who have used our products to ship award winning software. We have won numerous industry awards which honors the top innovators and leaders in the software development industry.
                                Since we provide building blocks that power applications, our work requires a level of understanding that is not required when working on applications. We are always looking for candidates with the right technical aptitude and the will to be masters in this programming trade we all love.
                            </p>
                            <h4 style="font-size: 20px;">What we do</h4>
                            <ul>
                                <li>
                                    We work to produce software building blocks that other developers use. As software has become more and more complex to produce it is commonly the case that more and more companies rely on software building blocks to produce complex software.
                                </li>
                                <br />
                                <li>
                                    We work at a much lower level than typical application development. We write the plumbing that powers application development for thousands of developers worldwide. This does mean that we look for our team members to be significantly better than industry peers. You have to have a solid understanding of data structures and be seriously interested in programming. You should also have a passion for problem solving and excellence.
                                </li>
                                <br />
                                <li>
                                    The nature of our work often requires us to work in areas where there are very few teams working world-wide. Consider the Windows Presentation Foundation or Silverlight. We started work, producing components for these platforms years before they became industry buzzwords. If you are truly looking to stay ahead of the curve there is no better place to work than Syncfusion.
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
    </div>
            <p>Top Value:<input ng-model="top"/></p>
            <p>Left Value:<input ng-model="left" /></p>
    </div>
    

{% endhighlight %}

{% highlight javascript %}

<script>
    angular.module('scrollerrApp', ['ejangular'])
     .controller('ScrollerCtrl', function ($scope) {
         $scope.height = "300px";
         $scope.width = "600px";
         $scope.top = "20";
         $scope.left = "20";
    });
</script>
    
{% endhighlight %}

Configuring Styles.

{% highlight html %}

<style type="text/css">
        .control {
            border: 1px solid #bbbcbb;
            width: 600px;
            margin: 0 auto;
            height: 300px;
        }

        .sampleContent {
            width: 700px;
            padding: 15px;
        }
</style>
    
{% endhighlight %}

Run the above code to get the below output.

![](data-binding_images/two-way-binding.png)