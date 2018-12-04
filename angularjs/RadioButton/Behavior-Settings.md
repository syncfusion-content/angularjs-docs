---
layout: post
title: Behaviour settings RadioButton | AngularJS | Syncfusion
description: Behaviour settings
platform: AngularJS
control: RadioButton
documentation: ug
---

# Behavior Settings

In AngularJS, **ej-radioButton** control allows you to check an option to perform an action. This control allows you to select true or false or an intermediate option. These **ej-radioButton** control are supported with themes.
This section helps us to render the **ej-radioButton** component in AngularJS platform.

**HTML View Section**

{% highlight html %}

        <div class="frame">
                Hobbies <br /><br />
                <table>

                        <tr>
                    <td class="chkrad">
                            <input type="radio" ej-radiobutton id="radio1" name="hobbies" e-value="Music" e-checked="true"/>
                            <label for="radio1">Music</label>
                        
                        </td>
                        <td class="chkrad">
                            <input type="radio" ej-radiobutton id="radio3" name="hobbies" e-value="Sports" ng-model="all"/>
                            <label for="radio3">Sports</label>
                        </td>
                        <td class="chkrad">
                            <input type="radio" ej-radiobutton id="radio4" name="hobbies" e-value="BikeRiding"/>
                            <label for="radio4">Bike Riding</label>
                        </td>
                    </tr>
            </table><br />
            <br />
        </div>


{% endhighlight %} 

**Controller Section**

{% highlight JS %} 

    <script>
        angular.module('radiobuttonCtrl', ['ejangular'])
           .controller('radiobuttonCtrller',function ($scope) {
         
          $scope.PlayingGames="false";
          
           });     
    </script>


{% endhighlight %} 

## Checked	

This checked API of the **RadioButton** specifies whether **ej-radioButton** must be in checked state or not.By default,we can set the **ej-radioButton** in checked state for our application.

**HTML View Section**

{% highlight html %}

        
     <table>
           <tr>
               <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio1" name="hobbies" e-value="Music" e-checked/>
                    <label for="radio1">Music</label>
                
                </td>
                <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio3" name="hobbies" e-value="Sports" />
                    <label for="radio3">Sports</label>
                </td>
                <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio4" name="hobbies" e-value="BikeRiding"/>
                    <label for="radio4">Bike Riding</label>
                </td>
            </tr>
        </table>



{% endhighlight %} 

**Controller Section**

{% highlight JS %}

    <script>
           angular.module('radiobuttonCtrl', ['ejangular'])
           .controller('radiobuttonCtrller',function ($scope) {
      
           });     
    
            
    </script>

{% endhighlight %} 

The code will render the following output.

![](Behaviour_settings_images/radio1.png) 

## enabled

      In AngularJS, enabled API of **ej-radioButton** control specifies the RadioButton control state. The enabled API can be set with Boolean value whether as true or false to specifies current state of the component.

**HTML View Section**

{% highlight html %}

        <table>

                <tr>
               <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio1" e-value="Music" name="hobbies" e-checked="true" e-enabled="false"/>
                    <label for="radio1">Music</label>
                
                </td>
                <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio3" name="hobbies" e-value="Sports" />
                    <label for="radio3">Sports</label>
                </td>
                <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio4" name="hobbies" e-value="BikeRiding"/>
                    <label for="radio4">Bike Riding</label>
                </td>
            </tr>
        </table>


{% endhighlight %} 

**Controller Section**

{% highlight JS %}

   <script>
               angular.module('radiobuttonCtrl', ['ejangular'])
           .controller('radiobuttonCtrller',function ($scope) {
         
           });     
  
    </script>


{% endhighlight %} 

The above code will render the following output.

![](Behaviour_settings_images/radio1.png) 

## enableRTL

In AngularJS, enableRTL API of the **ej-radioButton** control is used to specify the right to left direction to that control.

**HTML View Section**

{% highlight html %}
  
  <table>

                <tr>
               <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio1" e-value="Music" name="hobbies" e-checked="true" e-enableRTL="true"/>
                    <label for="radio1">Music</label>
                
                </td>
                <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio3" name="hobbies" e-value="Sports" />
                    <label for="radio3">Sports</label>
                </td>
                <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio4" name="hobbies"  e-value="BikeRiding"/>
                    <label for="radio4">Bike Riding</label>
                </td>
            </tr>
        </table><



{% endhighlight %}

**Controller Section**

{% highlight JS%}

    <script>
           angular.module('radiobuttonCtrl', ['ejangular'])
           .controller('radiobuttonCtrller',function ($scope) {
          
           });     

    </script>

{% endhighlight %}

The above code will render the following output.

![](Behaviour_settings_images/radio1.png) 

## enablePersistence

In AngularJS, **e-enablePersistence** API specifies the persist property for **ej-radioButton** while initialization. The persist API save current model value to browser cookies for state maintains. While refreshing the ej-radioButton control page the model value apply from browser cookies.

**HTML View Section**

{% highlight html %}

   <table>
            <tr>
                <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radio1" e-value="Music" name="hobbies" e-enablepersistence="true" />
                    <label for="radio1">Music</label>
                </td>
                <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radiobutton3" e-value="Sports" name="hobbies" e-enablepersistence="true"/>
                    <label for="radiobutton3">Sports</label>
                </td>
                <td class="chkrad">
                    <input type="radio" ej-radiobutton id="radiobutton4" e-value="BikeRiding" name="hobbies" e-enablepersistence="true"/>
                    <label for="radiobutton4">Bike Riding</label>
                </td>
            </tr>
        </table>


{% endhighlight %}

**Controller Section**

{% highlight JS %}

    <script>
           angular.module('radiobuttonCtrl', ['ejangular'])
           .controller('radiobuttonCtrller', function ($scope) {
           });
 
    </script>


{% endhighlight %}

![](Behaviour_settings_images/radio3.png) 