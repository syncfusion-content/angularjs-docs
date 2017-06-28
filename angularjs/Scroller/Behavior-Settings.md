---
layout: post
title: Behavior-Settings
description: Behavior Settings 
platform: AngularJS
control: Scroller
documentation: ug
---

# Behavior Settings

## Auto Hide

The autohide property of the Scroller, makes the scroller visible only when the scroller control is being focused and will hide automatically when the focus is out of the control. The autohide property of the scroller enabled using the e-autohide property is shown below.

{% highlight html %}

    <div ng-controller="ScrollerCtrl">
    <div class="control">
            <div id="scrollcontent" ej-scroller e-height="height" e-width="width" e-autohide="hide">
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
    </div>
    
{% endhighlight %}

{% highlight javascript %}

<script>
    angular.module('scrollerrApp', ['ejangular'])
     .controller('ScrollerCtrl', function ($scope) {
         $scope.height = "300px";
         $scope.width = "600px";
         $scope.hide = true;
    });
</script>

{% endhighlight %}

Configuring Styles

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

![](Behavior-Settings_images/auto-hide.png) 

Here , Since the Scroller has not been focused, scroll bars are hidden.

## Scroll Left and Top

The scroll top and scroll left properties allows to move the scroll content and scroll bars to the specifies numeric value from top and left position respectively. The scroller moved from the top and left position to the given numeric value using e-scrollleft and e-scrolltop is shown below.

{% highlight html %}

    <div ng-controller="ScrollerCtrl">
    <div class="control">
            <div id="scrollcontent" ej-scroller e-scrollTop="top" e-scrollLeft="left" e-height="300px" e-width="600px">
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
    </div>
    
{% endhighlight %}

{% highlight javascript %}

<script>
    angular.module('scrollerrApp', ['ejangular'])
     .controller('ScrollerCtrl', function ($scope) {
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

Run the above code to get th below output.

![](Behavior-Settings_images/scroll-left.png) 

Here, the scrollers and the content are moved to the value being given in the code.

## Enable Persistence

The enable persistence property of the scroller saves the current position of the scroller to the browser cookies for state maintenance such that the scrolled values of the scroller retains. The enable persistence enabled using the e-enablePersistence property is shown below.

{% highlight html %}

    <body ng-controller="ScrollerCtrl">
    <div class="control">
            <div id="scrollcontent" ej-scroller e-height="height" e-width="width" e-enablePersistence="enable">
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
        
{% endhighlight %}

{% highlight javascript %}

<script>
    angular.module('scrollerrApp', ['ejangular'])
     .controller('ScrollerCtrl', function ($scope) {
         $scope.height = "300px";
         $scope.width = "600px";
         $scope.enable = true;
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

![](Behavior-Settings_images/enable-persistence.png) 

Here, the scroller has been scrolled and reloaded but the scroller retains in the same position whereas without enabling enablePersistence property, the scrollers will be moved to the initial position.

## Target Pane

The target pane property of the scroller allows us to target a particular area to which scroller have the appear. Usage of target pane to select a particular area for which the scroller has to appear, using e-tragetPane property is shown below.

{% highlight html %}

    <body ng-controller="ScrollerCtrl">
    <div class="control">
                <div ej-scroller e-targetPane="target" e-height="300px" e-width="700px">
                    <div class="sampleContent" id="sampleContent1">
                        <h3 style="font-size: 20px;">Syncfusion</h3>
                        <p>
                            We are a world leader in software components. With close to a decade of experience, we have thousands of satisfied customers world-wide who have used our products to ship award winning software. We have won numerous industry awards which honors the top innovators and leaders in the software development industry.
                            Since we provide building blocks that power applications, our work requires a level of understanding that is not required when working on applications. We are always looking for candidates with the right technical aptitude and the will to be masters in this programming trade we all love.
                        </p>
                    </div>
                    <div class="sampleContent" id="sampleContent2">
                        <div style='width: 700px;'>
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
    
{% endhighlight %}

{% highlight javascript %}

<script>
    angular.module('scrollerrApp', ['ejangular'])
     .controller('ScrollerCtrl', function ($scope) {
         $scope.target = "#sampleContent2";
     });
</script>
    
{% endhighlight %}

Configuring Styles.

{% highlight html %}

<style type="text/css" class="cssStyles">
        .control {
            border: 1px solid #bbbcbb;
            color: gray;
            width: 55%;
            height: 100%;
        }

        .sampleContent {
            overflow: hidden;
            float: left;
            text-align:justify;
        }

        #sampleContent1 {
            width: 25%;
        }

        #sampleContent2 {
            width: 75%;
        }


        @media (max-width: 700px) {
            .control {
                width: 85%;
            }
        }
</style>
    
{% endhighlight %}

Run the above code the get the below output.

![](Behavior-Settings_images/targetpane.png)

