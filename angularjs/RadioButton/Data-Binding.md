---
layout: post
title: Behaviour settings RadioButton | AngularJS | Syncfusion
description: Behaviour settings
platform: AngularJS
control: RadioButton
documentation: ug
---

# Data Binding

## Two-way Binding

When data in the model changes, the view reflects the change, and when data in the view changes, the model updated as well. This happens immediately and automatically, which makes sure that the model and the view is updated always.
 Once we change the state of the **ej-radiobutton** control changed then its value will have reflected in the paragraph html element in the webpage.

**HTML View Section**

{%highlight html%}

    <td class="chkrad">
         <input type="radiobutton" ej-radiobutton id="radio1" e-value="Music"/>
            <label for="radio1">Music</label>
                <p>The value of Music is: {{Music}} </p>
            </td>



{% endhighlight %}

**Controller Section**

{%highlight JS%}

    <script>
        angular.module('radiobuttonCtrl', ['ejangular'])
           .controller('radiobuttonCtrller', function ($scope) {
               $scope.Music = "false";
           });

    </script>

{%endhighlight%}

The code will render the following output.

![](Databinding_images/radio23.png) 

## Event Binding

In AngularJS, **ej-radiobutton** component can be used to bind events. The events that can be binded are beforeChange, change, create, destroy.
beforeChange event of the **ej-radiobutton** will be triggered before the RadioButton has been checked and unchecked.

**HTML View Section**

{%highlight html%}

    <div class="frame">
       Read the terms and conditions <input type="radio" id="ch1" ej-radiobutton e-beforeChange="change">
        <button id="butn" ej-button e-text="submit"></button>
    </div>


{%endhighlight%}

**Controller Section**

{%highlight JS%}

    <script>
           angular.module('radiobuttonCtrl', ['ejangular'])
              .controller('radiobuttonCtrller', function ($scope) {
                  $scope.change=function(e){
                      alert('You Have accepted the terms and conditions');
                  }
              });

            
    </script>

{%endhighlight%}

The above code will render the following output.

![](Databinding_images/radio5.png) 