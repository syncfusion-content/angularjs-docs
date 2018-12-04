---
layout: post
title: Behaviour settings CheckBox | AngularJS | Syncfusion
description: Behaviour settings
platform: AngularJS
control: CheckBox
documentation: ug
---

# Behavior Settings

In AngularJS, **CheckBox** control allows you to check an option to perform an action. This control allows you to select true or false or an intermediate option. These **ej-checkBox** are supported with themes.

This section helps us to render the **ej-checkBox** component in AngularJS platform.

**HTML View Section**

{% highlight html %}

    <div class="frame">
            Hobbies <br /><br />
            <table>
                <tr>
                <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="check1" e-value="Music" e-checked="true"/>
                        <label for="check1">Music</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox3" e-value="Sports" ng-model="all"/>
                        <label for="Checkbox3">Sports</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox4" e-value="BikeRiding"/>
                        <label for="Checkbox4">Bike Riding</label>
                    </td>
                </tr>
            </table><br /><br />
            Favorite Search Engines<br /><br />
            <table>
                <tr>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox1" e-value="playingGames" e-size="medium" e-checked="true"/>
                        <label for="Checkbox1">Playing Games</label>
                        <p> Value of playing Games: {{PlayingGames}}</p>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox5" e-value="HearingSongs" e-size="medium"/>
                        <label for="Checkbox5">Hearing Songs</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox6" e-value="WatchingTV" e-size="medium" />
                        <label for="Checkbox6">Watching Tv</label>
                    </td>
                </tr>
            </table><br /><br />
            Media Player<br /><br />
            <table>
                <tr>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox2" e-value="Video" e-size="medium" />
                        <label for="Checkbox2">Video</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox7" e-value="Audio" e-size="medium" />
                        <label for="Checkbox7">Audio</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox8" e-value="Picture" e-size="medium" />
                        <label for="Checkbox8">Picture</label>
                    </td>
                </tr>
                
            </table>
            <br />
        </div>

{% endhighlight %} 

**Controller Section**

{% highlight JS %} 

    <script>
            angular.module('CheckboxCtrl', ['ejangular'])
            .controller('CheckboxCtrller',function ($scope) {
            
            $scope.PlayingGames="false";
            
            });     
    </script>

{% endhighlight %} 

## Checked	

This **checked** API of the checkbox specifies whether **ej-checkBox** has to be in checked or not. By default, we can manually set the **ej-checkBox** in checked state for our application.

**HTML View Section**

{% highlight html %}

        
    <table>
            <tr>
                <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="check1" e-value="Music" e-checked="true"/>
                        <label for="check1">Music</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox3" e-value="Sports" ng-model="all"/>
                        <label for="Checkbox3">Sports</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox4" e-value="BikeRiding"/>
                        <label for="Checkbox4">Bike Riding</label>
                    </td>
                </tr>
            </table>


{% endhighlight %} 

**Controller Section**

{% highlight JS %}

    <script>
            angular.module('CheckboxCtrl', ['ejangular'])
            .controller('CheckboxCtrller',function ($scope) {
        
            });     
            
    </script>

{% endhighlight %} 

The code will render the following output.

![](Behaviour_settings_images/img1.png) 

## enabled

      In AngularJS, enabled API of **ej-checkBox** control specifies the checkbox control state. The enabled API can be set with Boolean value to specifies current state of the component.

**HTML View Section**

{% highlight html %}

    <table>
                <tr>
                <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="check1" e-value="Music" e-checked="true" e-enabled="true"/>
                        <label for="check1">Music</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox3" e-value="Sports" e-enabled="false"/>
                        <label for="Checkbox3">Sports</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox4" e-value="BikeRiding"/>
                        <label for="Checkbox4">Bike Riding</label>
                    </td>
                </tr>
            </table>

{% endhighlight %} 

**Controller Section**

{% highlight JS %}

    <script>
        angular.module('CheckboxCtrl', ['ejangular'])
           .controller('CheckboxCtrller',function ($scope) {
         
           });     
    </script>


{% endhighlight %} 

The above code will render the following output.

![](Behaviour_settings_images/img2.png) 

## enableTristate

In AngularJS, enableTriState API of **ej-checkbox** control defines the enable or disabled state of component.

**HTML View Section**

{% highlight html %}

     <table>
           <tr>
                <td class="chkrad">
                    <input type="checkbox" ej-checkbox id="check1" e-value="Music" e-enabletristate="true"/>
                    <label for="check1">Music</label>
                </td>
                <td class="chkrad">
                    <input type="checkbox" ej-checkbox id="Checkbox3" e-value="Sports" e-enabletristate="true" />
                    <label for="Checkbox3">Sports</label>
                </td>
                <td class="chkrad">
                    <input type="checkbox" ej-checkbox id="Checkbox4" e-value="BikeRiding" e-enabletristate="true"/>
                    <label for="Checkbox4">Bike Riding</label>
                </td>
            </tr>
        </table>


{% endhighlight %}

**Controller Section**

{% highlight JS%}

    <script>
            angular.module('CheckboxCtrl', ['ejangular'])
            .controller('CheckboxCtrller',function ($scope) {
            
            });     
    </script>

{% endhighlight %}

The above code will render the following output.

![](Behaviour_settings_images/img2.png) 

## enablePersistence

In AngularJS, **e-enablePersistence** API specifies the persistent property for **ej-checkBox** while initialization. The e-enablePersistance API save current model value to browser cookies for state maintains. While refreshing the **ej-checkbox** control page the model value apply from browser cookies.

**HTML View Section**

{% highlight html %}

    <table> 
    <tr>
        <td class="chkrad">
        <input type="checkbox" ej-checkbox id="check1" e-value="Music" e-enablepersistence="false" />
            <label for="check1">Music</label>
                </td>
                <td class="chkrad">
                <input type="checkbox" ej-checkbox id="Checkbox3" e-value="Sports" e-enablepersistence="false"/>
                    <label for="Checkbox3">Sports</label>
                    </td>
                    <td class="chkrad">
                        <input type="checkbox" ej-checkbox id="Checkbox4" e-value="BikeRiding" e-enablepersistence="false"/>
                        <label for="Checkbox4">Bike Riding</label>
                    </td>
                </tr>
            </table>

{% endhighlight %}

**Controller Section**

{% highlight JS %}

    <script>
            angular.module('CheckboxCtrl', ['ejangular'])
            .controller('CheckboxCtrller',function ($scope) {
            
            });     
    </script>


{% endhighlight %}

![](Behaviour_settings_images/img3.png) 