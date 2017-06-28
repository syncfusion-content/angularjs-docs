---
layout: post
title: MaskEdit-Properties
description: maskedit properties
platform: angularjs
control: MaskEdit
documentation: ug
---

# MaskEdit Properties

## CustomCharacter

The **MaskEdit** allows you to use the custom character option. The specified character is allowed to enter in the Mask Edit Textbox by using the **customCharacter** property.

## HidePromptOnLeave

The **MaskEdit** provides the option to hide the prompt when you focus out from the control. The mask prompt is visible when you focus again to the control. The default value of **hidePromptOnLeave** is false.

## InputMode

The **MaskEdit** supports two type of inputs such as text and password that have been assigned by using the enum values **ej.InputMode.Text** and **ej.InputMode.Password**. The default value for **inputMode** is text in **MaskEdit**.

## MaskFormat

The **MaskEdit** provides the option to define the **maskFormat** to the value. The default value for **maskFormat** property is empty string.

The following steps explain the implementation of **MaskEdit Properties**.



In the **HTML** page, add a **&lt;input&gt;** element to render the **MaskEdit** widget. 


{% highlight html %}

<input id="maskedit" type="text" ej-maskedit e-inputmode="ej.InputMode.Text" e-maskformat='99-999-CCCC' e-name="mask" e-customcharacter="r" e-hidepromptonleave="true" /> 
	
{% endhighlight %}

The output for **MaskEdit** with its properties is as follows.

![](MaskEdit-Properties_images/MaskEdit-Properties_img1.png)

MaskEdit with MaskFormat
{:.caption}



![](MaskEdit-Properties_images/MaskEdit-Properties_img2.png)

MaskEdit with HidePromptOnLeave
{:.caption}



![](MaskEdit-Properties_images/MaskEdit-Properties_img3.png)

MaskEdit with prompt focus
{:.caption}



![](MaskEdit-Properties_images/MaskEdit-Properties_img4.png)

MaskEdit with InputMode text
{:.caption}

![](MaskEdit-Properties_images/MaskEdit-Properties_img5.png)

MaskEdit with CustomCharacter
{:.caption}

