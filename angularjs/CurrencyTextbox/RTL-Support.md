---
layout: post
title: RTL-Support
description: rtl support
platform: AngularJS
control: CurrencyTextBox  
documentation: ug
---

# RTL Support

The **Textbox** provides **RTL** (Right-To-Left) support. The alignment of CurrencyTextBox can be changed from **Left-To-Right** into **Right-To-Left**.

## Enable RTL

The following steps explain the implementation of **enableRTL** in CurrencyTextBox.

In the **HTML** page set the corresponding **&lt;input&gt;** elements for rendering CurrencyTextBox controls.


{% highlight html %}

<input id="currency" type="text" ej-currencytextbox e-value="33" e-enablertl="true" />
	
{% endhighlight %}

The output for CurrencyTextBox when **enableRTL** is **“true”** is as follows. 

![](RTL-Support_images/RTL-Support_img1.png) 

