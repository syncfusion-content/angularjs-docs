---
layout: post
title: rtl support
description: rtl support
platform: Angular-1
control: Control Name undefined
documentation: ug
---

## RTL Support

This feature supports to change the left-to-right alignment of the Rotator to right-to-left (RTL). (i.e.) Sets the Rotator to do its actions from right to left. The property e-enableRTL sets the Rotator from right to left. The value set to this property is boolean type.

{% highlight html %}


<ul id="sliderContent" ej-rotator e-slidewidth="500px" e-slideheight="300px" e-enableRTL="true" >
                            <li><img class="image" src="../images/rotator/snow.jpg" title="Nature" /></li>
                            <li><img class="image" src="../images/rotator/bird.jpg" title="Beautiful Bird" /></li>
                            <li><img class="image" src="../images/rotator/sculpture.jpg" title="Amazing Sculptures" /></li>
                            <li><img class="image" src="../images/rotator/seaview.jpg" title="Sea-View" /></li>
                            <li><img class="image" src="../images/rotator/snowfall.jpg" title="Snow Fall" /></li>
                        </ul>



{% endhighlight %}





